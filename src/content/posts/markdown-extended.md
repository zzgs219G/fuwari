---
title: Markdown 扩展语法功能介绍
published: 2024-05-01
updated: 2024-11-29
description: '阅读关于博客中 Markdown 额外功能和扩展语法的更多信息'
image: ''
tags: [演示, 示例, Markdown, Fuwari]
category: 示例
draft: false 
---

## GitHub 项目仓库卡片
你可以添加动态的 GitHub 仓库链接卡片。在页面加载时，仓库信息会自动从 GitHub 的接口拉取。

::github{repo="Fabrizz/MMM-OnSpotify"}

使用以下代码来创建一个 GitHub 仓库卡片： `::github{repo="<所有者>/<仓库名>"}`

```markdown
<!-- ::github{repo="saicaca/fuwari"} -->
```

## 提示框 (Admonitions)

目前支持以下类型的提示框：`note` (笔记)、`tip` (提示)、`important` (重要)、`warning` (警告)、`caution` (注意)

:::note
**笔记**：突出显示用户即使在粗略浏览时也应该注意的信息。
:::

:::tip
**提示**：一些有助于用户更好完成目标的额外信息。
:::

:::important
**重要**：用户必须了解的关键信息。
:::

:::warning
**警告**：由于存在潜在风险，需要用户立即关注的关键内容。
:::

:::caution
**注意**：某项操作可能带来的负面后果。
:::

### 基础语法

```markdown
:::note
**笔记**：突出显示用户即使在粗略浏览时也应该注意的信息。
:::

:::tip
**提示**：一些有助于用户更好完成目标的额外信息。
:::
```

### 自定义提示框标题

你可以自定义提示框的标题名称。

:::note[我是自定义的标题]
这是一个带有自定义标题的提示框。
:::

```markdown
:::note[我是自定义的标题]
这是一个带有自定义标题的提示框。
:::
```

### 兼容 GitHub 语法

> [!TIP]
> 博客也完美支持 [GitHub 风格的提示框语法](https://github.com/orgs/community/discussions/16925)。

```markdown
> [!NOTE]
> 这是一段 GitHub 语法的提示内容。

> [!TIP]
> 这是一段 GitHub 语法的提示内容。
```

### 剧透遮挡文字 (Spoiler)

你可以在文字中加入被遮挡的“剧透”内容（鼠标移上去才能看清）。遮挡里面的文字也支持加粗等 **Markdown** 语法。

这段内容里面有 :spoiler[被隐藏的**秘密**]！

```markdown
这段内容里面有 :spoiler[被隐藏的**秘密**]！
```