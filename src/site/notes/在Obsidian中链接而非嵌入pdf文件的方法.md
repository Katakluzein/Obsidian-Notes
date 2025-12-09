---
{"dg-publish":true,"permalink":"/在Obsidian中链接而非嵌入pdf文件的方法/","tags":["obsidian"]}
---

在 Obsidian 里，“链接本地 PDF 文件（而不是嵌入）”可以通过多种方式实现，下面是常用方法 + 注意点 + 扩展插件推荐：

---

## 一、原生方法 — Markdown 外部文件链接 / 内部文件链接

### 1. 对于 vault 内部的 PDF（即 PDF 存放在你的 Obsidian 笔记库里）

这种情况下，你可以像链接普通文件那样用 Wiki 链接或 Markdown 链接：

- **Wiki 链接**（Obsidian 内部链接）
    
    ```md
    [[my-document.pdf]]
    ```
    
    或者如果你想显示不同的文字：
    
    ```md
    [[my-document.pdf|这是 PDF 文件]]
    ```
    
    这样做不会把 PDF 嵌入，而是作为一个可点击链接，点击后会在 Obsidian 的 PDF 预览器或外部应用中打开。
    
- **Markdown 链接**
    
    ```md
    [点击这里查看 PDF](my-document.pdf)
    ```
    
    若文件名或路径中有空格等特殊字符，可能要用 URL 编码或用尖括号 `<...>` 包裹路径。
    

---

### 2. 链接 vault 之外、本地磁盘或网络驱动器上的 PDF

如果 PDF 不在你的 Obsidian 笔记库中，而是存在其他磁盘路径（比如 D:\docs\paper.pdf 或网络驱动器上），可以用 **文件 URI** 的方式来链接：

```md
[某篇论文](<file:///D:/资料/论文/my-paper.pdf>)
```

其中：

- `file:///` 是标准文件协议前缀
    
- 斜杠方向、路径格式要按你系统（Windows、macOS、Linux）规则写
    
- 如果路径中有空格或特殊字符，建议用 `<…>` 包裹整个 URI，或者对空格做 `%20` 编码。  
    比如：
    
    ```md
    [论文标题](<file:///C:/Users/YourName/Documents/Some%20Paper.pdf>)
    ```
    
==最好用的方法：==
有用户反馈可以通过 **Ctrl + 拖拽**（Windows／Linux）或 **Command + 拖拽**（macOS）将文件从文件系统拖进 Obsidian 笔记中，这样会自动生成上述的 file:/// 链接，而不是将文件复制到 vault 中。([Reddit](https://www.reddit.com/r/ObsidianMD/comments/m6ynmt/how_to_create_a_link_to_a_locally_saved_pdf_not/?utm_source=chatgpt.com "How to create a link to a locally saved PDF, not embed PDF? - Reddit"))

---

## 二、示例对比

|场景|Markdown 语法|效果 / 备注|
|---|---|---|
|Vault 内部 PDF 链接|`[[paper.pdf]]` 或 `[论文](paper.pdf)`|点击即可打开，不会嵌入|
|Vault 内部 PDF，显示别名|`[[paper.pdf|这篇论文]]`|
|Vault 外部 PDF 链接|`[title](<file:///路径/文件.pdf>)`|在预览模式下可点击打开外部文件|
|拖拽 + Ctrl（Windows）|Ctrl + 拖拽文件到笔记|自动生成 file:/// 链接，不复制文件到 vault 中 ([Reddit](https://www.reddit.com/r/ObsidianMD/comments/m6ynmt/how_to_create_a_link_to_a_locally_saved_pdf_not/?utm_source=chatgpt.com "How to create a link to a locally saved PDF, not embed PDF? - Reddit"))|

---

## 三、注意事项 / 限制

- 在编辑模式里，即使写了外部文件链接（file:///…），有时候 Obsidian 可能在编辑视图中不显示为“可点链接”（但在预览模式中可以点击）。([Obsidian Forum](https://forum.obsidian.md/t/link-to-external-files/8107?utm_source=chatgpt.com "Link to external files - Help - Obsidian Forum"))
    
- 如果你移动了那个 PDF 的路径（比如重命名目录、改磁盘位置等），链接会失效，因为文件 URI 是“绝对路径”。
    
- PDF 指定到某一页的链接在外部文件（file:///）情境中通常不可用，或者依赖于操作系统与 PDF 阅读器是否支持。很多用户反馈 `#page=...` 等方式不稳定或不生效。([Obsidian Forum](https://forum.obsidian.md/t/need-help-with-opening-a-specific-page-of-a-local-pdf-file-in-obsidian/24245?utm_source=chatgpt.com "Need help with opening a specific page of a local pdf file in Obsidian"))
    
- 若你导出笔记为 PDF 或在某些情境下，外部链接可能无法在导出的版本中保持可点击性。
    

---

## 四、插件 / 扩展工具推荐

如果这些原生方法不能满足你对链接外部文件或管理外部资源的需求，这里有一些插件 / 扩展可以帮助：

- **External File Embed and Link 插件**  
    这个插件可以让你以相对路径链接 vault 外的文件（包括 PDF、图片、音视频等）。([Obsidian Stats](https://www.obsidianstats.com/plugins/external-file-embed-and-link?utm_source=chatgpt.com "External File Embed and Link - Obsidian Stats"))
    
- **obsidian-file-link**（GitHub 项目）  
    这个插件可以快速通过命令面板选文件来生成链接，甚至切换嵌入 / 链接模式。([github.com](https://github.com/marcjulianschwarz/obsidian-file-link?utm_source=chatgpt.com "marcjulianschwarz/obsidian-file-link: A plugin for the note ... - GitHub"))
    

---

如果你愿意的话，我可以给你一个更详细的操作步骤（针对 Windows / macOS 系统）以及推荐适合你目前环境的最佳插件。要吗？