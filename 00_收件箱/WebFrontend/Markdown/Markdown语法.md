# Markdown基本语法

## 🔗 外链接

> [!NOTE] TIP
> TIP 要创建链接，请将链接文本括在括号中

### 1. 行内式链接
最常用、最直接的方式。格式：
```markdown
[显示文本](https://example.com)
```
- `显示文本` 是读者看得见的可点击文字。
- `https://example.com` 是真实的链接地址。

**示例：**
```markdown
欢迎访问 [GitHub](https://github.com)。
```
效果：欢迎访问 [GitHub](https://github.com)。

### 2. 带标题的行内式链接
可以在链接后添加一个可选的标题，鼠标悬停时会显示。格式：
```markdown
[显示文本](https://example.com "悬浮提示文字")
```
**示例：**
```markdown
请参考 [Markdown 指南](https://www.markdownguide.org "最好的 Markdown 教程")。
```
效果：请参考 [Markdown 指南](https://www.markdownguide.org "最好的 Markdown 教程")。

### 3. 参考式链接
当文中多次用到同一链接，或者想让纯文本版更干净时，可以用参考式。它把链接地址统一放在其他地方定义。

**用法：**
```markdown
[显示文本][标签]
```
然后在文档任意位置（通常放在文末）定义标签：
```markdown
[标签]: https://example.com "可选标题"
```

**示例：**
```markdown
我经常使用 [这个搜索引擎][1] 来查资料。
有时候也用 [另一个][2]。

[1]: https://www.google.com "谷歌"
[2]: https://www.bing.com
```
标签可以是数字、字母或单词，不区分大小写。如果显示文本和标签名相同，还可以简写成 `[标签][]` 或 `[标签]`。

### 4. 自动链接
直接用尖括号包裹 URL 或邮箱，就会变成可点击的链接。
```markdown
<https://www.example.com>
```
会自动渲染为可点击的链接：https://www.example.com

邮箱同理：`<someone@example.com>` 会变成可点击的邮件地址。

---

### 📝 核心规则与注意事项
- **链接文本中可嵌套其他行内元素**，比如加粗、代码等，但不支持嵌套另一个链接。
- **链接地址** 如果包含空格，需要将其用 `<>` 包裹，例如 `[示例](<https://example.com/my page>)`。
- **参考式定义的地址** 也可以用尖括号包裹，标题可用双引号、单引号或括号。
- **相对路径** 同样适用，例如 `[文档](./docs/intro.md)`，这算内部链接，但本质与外链接语法一致。

以上就是在 Markdown 中创建外链接的完整语法。根据场景选择最合适的一种即可。

