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

## 1. 终极偷懒技巧：让 AI 帮我写格式完美的文章（进阶版）

被抓到偷懒啦！为了让你做世界上最舒服的“甩手掌柜”，我把博客支持的**所有高级扩展功能**全部编织进了这个“终极版 AI 调教指令”里。

你只需要点击下面代码块右上角的**复制**按钮，发给任何 AI 助手，它就能帮你生成带有华丽特效（提示框、终端代码高亮、剧透文字等）的完美文章。

````text
请你扮演一名专业的前端博客作者，帮我写一篇技术/经验分享文章。
文章必须严格遵循 Astro Fuwari 博客的高级 Markdown 扩展格式要求。请仔细阅读并遵守以下格式指南：

### 1. 必需的 Frontmatter 配置
请在生成的文章最开头，必须使用 `---` 包裹以下 YAML 格式的信息，并根据文章内容自动填充：
---
title: "文章的标题"
published: YYYY-MM-DD (填入今天的真实日期，格式必须是 年-月-日)
description: "一句话简介，准确概括文章内容，用于首页展示"
image: "" (封面图路径，暂时留空)
tags: [标签1, 标签2] (提取2-3个相关标签)
category: 文章的大分类 (只能选一个最合适的主分类)
draft: false
---

### 2. 基础排版与图片规则
- 语言风格：通俗易懂、生动幽默，像朋友在聊天一样。重点词汇请使用加粗 `**文字**`。
- 图片插入：默认所有图片都在当前文章所在同级目录下。必须使用此格式：`![图片说明](./图片文件名.png)`。

### 3. Astro Fuwari 高级扩展语法（请根据内容适时选用，增强文章排版表现力）：

【功能 A：提示框 Admonitions】
当需要强调重要信息时，请务必使用以下三种语法之一：
1. 默认类型支持：:::note, :::tip, :::important, :::warning, :::caution
   写法：
   :::tip
   这里是提示内容...
   :::
2. 自定义标题类型：
   :::note[我是自定义的标题]
   这是一个带有自定义标题的提示框。
   :::
3. GitHub 风格提示框（兼容支持）：
   > [!NOTE]
   > 这里是提示内容...

【功能 B：剧透遮挡文字 Spoiler】
当有一些惊喜、答案或剧透信息时，使用 spoiler 语法将其隐藏（悬停可见）：
写法： 这是一段包含 :spoiler[被隐藏秘密] 的文字。

【功能 C：高级代码块高亮 Expressive Code】
如果有代码示例，必须使用代码块，并可根据需要添加特定的增强属性：
1. 带终端/Mac窗口样式的代码块（添加 frame 和 title）：
   ```bash frame="terminal" title="运行以下命令"
   pnpm install
   ```
2. 高亮/增加/删除特定代码行：
   ```js {1} ins={2} del={3}
   console.log('这行会被普通高亮');
   console.log('这行会显示绿色新增背景');
   console.log('这行会显示红色删除背景');
   ```

【功能 D：GitHub 仓库卡片】
如果提到开源项目，请插入动态仓库卡片（不要直接贴链接）：
写法： ::github{repo="仓库所有者/仓库名"}

---
如果你已经理解了上述所有排版规则，请根据我给出的主题，生成包含完整 Frontmatter 以及穿插使用上述高级语法的最终 Markdown 文章代码。

我的主题是：【在这里填入你想写的内容，比如：教大家如何使用 ZeroTermux 运行 Python 脚本】
````

你只要把最后大括号里的【主题】换掉发给 AI，生成的 `.md` 文件直接粘贴，零修改直接发布，华丽到没朋友！

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

**YouTube 视频示例：**
<iframe width="100%" height="468" src="https://www.youtube.com/embed/5gIf0_xpFPI?si=N1WTorLKL0uwLsU_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

**怎么写：**
```html
<iframe width="100%" height="468" src="https://www.youtube.com/embed/5gIf0_xpFPI?si=N1WTorLKL0uwLsU_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
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