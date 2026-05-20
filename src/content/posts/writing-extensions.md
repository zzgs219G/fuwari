---
title: "文章撰写与高级扩展教程集合"
published: 2026-05-20
description: "包含了让 AI 帮你写文章的专属指令，以及博客支持的各种高级 Markdown 扩展功能（GitHub卡片、视频、提示框等）演示。"
tags: [教程, 扩展, AI]
category: 教程
draft: false
---

这篇文章是为了让你在写博客时更加得心应手而准备的“高级装备库”。

---

## 1. 终极偷懒技巧：让 AI 帮我写格式完美的文章

如果你懒得自己排版，想让 AI（比如 ChatGPT、Kimi 等）直接帮你生成符合咱们博客格式的 `.md` 文件，**请直接复制下面这段指令发给 AI**：

> 请你帮我写一篇博客文章，文章需要严格遵循 Astro Fuwari 博客的 Markdown 格式要求。
>
> **1. 【开头必须包含 Frontmatter 配置】：**
> 请在文章最开头，使用 `---` 包裹以下格式的信息，注意保持换行格式，并根据文章内容自动生成或填充：
>
> \`\`\`yaml
> ---
> title: "文章的标题"
> published: YYYY-MM-DD (填入今天的日期)
> description: "一句话简介，描述这篇文章讲了什么"
> image: "" (封面图路径，暂时留空)
> tags: [标签1, 标签2] (提取2-3个相关标签)
> category: 文章的大分类 (选一个最合适的分类)
> draft: false
> ---
> \`\`\`
>
> **2. 【正文排版要求】：**
> - 使用标准 Markdown 语法。
> - 语言风格：通俗易懂、口语化一点，像朋友在聊天（或者根据你的喜好修改）。
> - 遇到重点内容，请使用加粗 `**文字**`。
>
> **3. 【关于图片（重要）】：**
> 如果文章中需要插入图片，请统一假设图片存放在该文章的同级目录下。插入图片的格式一律使用：`![图片说明](./图片文件名.jpg)`。
>
> **4. 【高级扩展功能要求（可选）】：**
> - 如果需要展示 GitHub 项目仓库，请使用 `::github{repo="作者名/仓库名"}`。
> - 如果需要强调提示信息，请使用 GitHub 风格提示框，如 `> [!NOTE]` 或 `> [!WARNING]`。
> - 如果需要插入哔哩哔哩或 YouTube 视频，请直接使用对应网站提供的 iframe 嵌入代码。
>
> **现在，请根据以下主题帮我写这篇文章：**
> [在这里填入你想让AI写的主题，比如：今天我学会了怎么做红烧肉，帮我写一篇食谱分享。]

---

## 2. 博客支持的高级扩展功能大全

除了基础的文本和图片，我们在编写博客时还可以使用以下炫酷的内置功能。当 AI 生成文章时，你也可以要求它使用这些功能。

### 2.1 GitHub 项目仓库卡片
你可以添加动态的 GitHub 仓库链接卡片。在页面加载时，仓库信息会自动从 GitHub 获取并展示得很漂亮。

**示例：**
::github{repo="hanxinhao000/ZeroTermux"}

**怎么写：**
```markdown
::github{repo="hanxinhao000/ZeroTermux"}
```

---

### 2.2 在文章中嵌入视频
如果你想在博客里放视频，做法非常简单。你只需要去视频网站（比如哔哩哔哩 Bilibili 或 YouTube）复制它的“嵌入代码”，然后直接粘贴到你的 markdown 文件里就行了。

**B站视频示例：**
<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1fK4y1s7Qf&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

**怎么写：**
```html
<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1fK4y1s7Qf&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
```

---

### 2.3 提示框 (Admonitions)
你可以用彩色的提示框来吸引读者的注意力。目前支持：`note` (笔记)、`tip` (提示)、`important` (重要)、`warning` (警告)、`caution` (注意)。

**示例：**
:::tip
**提示**：一些有助于用户更好完成目标的额外信息。
:::
:::warning
**警告**：由于存在潜在风险，需要用户立即关注的关键内容。
:::

**怎么写：**
```markdown
:::tip
**提示**：一些有助于用户更好完成目标的额外信息。
:::

:::warning
**警告**：由于存在潜在风险，需要用户立即关注的关键内容。
:::
```

**你也可以直接使用 GitHub 风格的提示框：**
> [!NOTE]
> 这是一段 GitHub 语法的提示内容。

```markdown
> [!NOTE]
> 这是一段 GitHub 语法的提示内容。
```

---

### 2.4 剧透遮挡文字 (Spoiler)
你可以隐藏文字，鼠标移上去才能看清。

**示例：**
这段内容里面有 :spoiler[被隐藏的**秘密**]！

**怎么写：**
```markdown
这段内容里面有 :spoiler[被隐藏的**秘密**]！
```

---

### 2.5 漂亮的代码高亮 (Expressive Code)
如果你要在文章里分享代码，博客自带了强大的高亮功能。

#### 基础语法高亮
```js
// 普通的语法高亮
console.log('Hello world!')
```

#### 带有特定的边框风格（终端）
```bash frame="terminal" title="安装命令"
pnpm install
```

**怎么写：**
如果你想要终端框并带标题，只需要在三个反引号后面加上语言、`frame="terminal"` 和 `title="你的标题"`：
````markdown
```bash frame="terminal" title="安装命令"
pnpm install
```
````

#### 高亮特定的代码行
```js {1} ins={2} del={3}
// 这个代码块使用了一些标记
console.log('这行是新增的绿色代码')
console.log('这行是删除的红色代码')
```

**怎么写：**
在大括号 `{}` 里写上想高亮的行号，`ins={}` 表示新增，`del={}` 表示删除。
````markdown
```js {1} ins={2} del={3}
// 这个代码块使用了一些标记
console.log('这行是新增的绿色代码')
console.log('这行是删除的红色代码')
```
````