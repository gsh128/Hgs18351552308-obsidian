# obsidian-git 插件 ENOENT 错误修复记录

**日期：** 2026-04-29

## 问题现象

Obsidian 启动后 obsidian-git 插件报错：

```
ENOENT: no such file or directory, open 'E:\HgsFiles\Hgs-obsidian-github\obsidian\plugins\obsidian-git\obsidian_askpass.sh'
```

## 原因分析

1. obsidian-git 插件（v2.38.2）在 `main.js` 中硬编码了插件目录名为 `plugins/obsidian-git/`，用于向该目录写入 `obsidian_askpass.sh` 凭据辅助脚本。

2. Obsidian 实际安装插件时使用的目录名是 `obsidian-git-2.38.2`（带版本号后缀），与插件代码期望的 `obsidian-git` 不一致。

3. 插件尝试向不存在的 `plugins/obsidian-git/` 目录写入文件，导致 ENOENT 错误。

4. 此外在某些情况下，路径中 `.obsidian` 的点号会被去掉，变成 `obsidian`，进一步加剧路径匹配问题。

## 修复步骤

### 1. 复制插件目录到代码期望的路径

```bash
cp -r ".obsidian/plugins/obsidian-git-2.38.2" ".obsidian/plugins/obsidian-git"
```

### 2. 创建无点号路径的备用

```bash
mkdir -p "obsidian/plugins/obsidian-git"
cp ".obsidian/plugins/obsidian-git/obsidian_askpass.sh" "obsidian/plugins/obsidian-git/"
```

## 修复后目录结构

```
.obsidian/plugins/
├── obsidian-git/           # 插件代码期望的路径（修复后新建）
│   ├── main.js
│   ├── manifest.json
│   ├── styles.css
│   ├── data.json
│   └── obsidian_askpass.sh
└── obsidian-git-2.38.2/    # 原始安装目录
    └── ...

obsidian/plugins/obsidian-git/
└── obsidian_askpass.sh      # 无点号备用路径
```

## 注意事项

- 以后 obsidian-git 插件更新时，Obsidian 可能重新创建带版本号的新目录，届时可能需要再次手动复制
- 这是 obsidian-git 插件本身的路径处理问题，不是 Obsidian 配置问题
- `obsidian_askpass.sh` 用于 git 操作的凭据认证，缺失时会导致自动备份、commit、push/pull 等功能异常
