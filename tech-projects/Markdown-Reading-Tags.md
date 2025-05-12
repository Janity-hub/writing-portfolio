---
title: "Track Reading Progress in Markdown with Anchor Links"
date: 2025-05-11
categories: ["Tech Projects"]
---

*Works with Obsidian, Typora, VSCode, Hugo, or any Markdown-compatible platform.*

## Why Do You Need Paragraph-Level Markers?

When you're managing large notes, reading long documents, or reviewing content for publication, you may face these issues:

- The document is too long — **you forget where you stopped reading**
- You find a paragraph worth sharing, but **can't find it again later**
- Obsidian only jumps to headings by default — **not to precise paragraphs**

Unlike Word (which supports comments but is heavy and Git-unfriendly), Markdown offers a cleaner approach with:

- Marked reading positions (across multiple files)
- Highlighted quotes for future publishing
- Searchable tags, anchor jumps, and linkable blocks

## Step 1: Insert a Navigation Block at the Top

```markdown
# Random Notes 10

## 🔖 Quick Navigation

- 🟡 [Last Reading Position](#reading-position)
- 📌 [Quote for Publishing 1](#publish-quote-1)
- 📌 [Quote for Publishing 2](#publish-quote-2)
```

## Step 2: Insert Anchors in the Body

```markdown

## 🟡 <a name="reading-position"></a>🔖 Reading Position Marker

This is where I left off reading.
```

```markdown
## 📌 <a name="publish-quote-1"></a>Quote for Publishing (1)

> "Timely response reflects emotional responsibility."
```

```markdown
## 📌 <a name="publish-quote-2"></a>Quote for Publishing (2)

> "Tact isn’t delay; it’s the wisdom of pacing information."
```

> **Note:** The `name="..."` attribute is a standard HTML anchor. It works in most Markdown renderers and allows precise jumps.  
> Emojis are optional but help visually distinguish sections.

## Step 3: Reference Paragraphs from Other Notes

```markdown
# Publish-Worthy Highlights

## Random Notes 10
- 📌 [[Random Notes 10#publish-quote-1]]
- 📌 [[Random Notes 10#publish-quote-2]]

## Random Notes 11
- 📌 [[Random Notes 11#publish-quote-3]]
```

> Obsidian’s `[[filename#anchor]]` syntax allows smooth jump to section titles or HTML anchors you insert.
This lightweight method helps you stay organized while navigating and reusing long Markdown notes with ease.

---

# 使用锚链接跟踪 Markdown 阅读进度

> 适用于 Obsidian / Typora / VSCode / Hugo 等支持 Markdown 的任意平台

## 为什么需要段落级标记？

当你在整理大量笔记、反复阅读长篇文档、或者批量筛选内容用于发布时，常常会遇到这些问题：

- 文档太长，**不知道上次读到哪里**
- 想保存某段话用于发微博、写博客，但**日后很难再翻出来**
- Obsidian 默认只能跳转标题，**不能跳转到具体段落**

虽然 Word 可以“添加批注”或“Ctrl+F”，但笨重又不兼容 Git。本文教你用纯 Markdown 实现：

- 标记阅读进度（支持多文件）
- 标记可发布的金句/段落（跨文件汇总）
- 全局搜索、跳转定位、链接互通

## 步骤 1：在文章顶部加入导航区块

```markdown
# 杂谈10

## 🔖 快速跳转导航

- 🟡 [上次阅读位置](#reading-position)
- 📌 [适合发布的段落1](#publish-quote-1)
- 📌 [适合发布的段落2](#publish-quote-2)
```

## 步骤 2：在正文中插入跳转锚点

```markdown
## 🟡 <a name="reading-position"></a>🔖 阅读进度标记

我上次读到这里。
```

```markdown
## 📌 <a name="publish-quote-1"></a>适合发布的内容（1）

> “及时时效的背后，其实是某种情感秩序的维护。”
```

```markdown
## 📌 <a name="publish-quote-2"></a>适合发布的内容（2）

> “得体不是延迟，而是控制信息密度的智慧节奏。”
```

- `name="..."` 是 HTML 标准锚点，兼容所有 Markdown 解析器
- 表情符号可选，纯文本也可以（如 `<!-- READ-HERE -->`）

## 步骤 3：在其他笔记中引用这些段落（交叉引用）

```markdown
# 我的发布合集

## 杂谈10
- 📌 [[杂谈10#publish-quote-1]]
- 📌 [[杂谈10#publish-quote-2]]

## 杂谈11
- 📌 [[杂谈11#publish-quote-3]]
```

> Obsidian 的 `[[文件名#锚点名]]` 支持跳转到标题段，搭配你手动插入的 `<a name>` 使用非常灵活。
