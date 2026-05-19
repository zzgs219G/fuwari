---
title: 博客系统使用指南
published: 2024-04-01
description: "如何使用这个博客模板的简单指南。"
image: "./cover.jpeg"
tags: ["Fuwari", "博客", "自定义"]
category: 指南
draft: false
---

> 封面图片来源: [来源链接](https://image.civitai.com/xG1nkqKTMzGDvpLrqFT7WA/208fc754-890d-4adb-9753-2c963332675d/width=2048/01651-1456859105-(colour_1.5),girl,_Blue,yellow,green,cyan,purple,red,pink,_best,8k,UHD,masterpiece,male%20focus,%201boy,gloves,%20ponytail,%20long%20hair,.jpeg)

本博客模板基于 [Astro](https://astro.build/) 框架构建。如果本指南里没有提到某些功能，你或许可以在 [Astro 官方文档](https://docs.astro.build/) 中找到答案。

## 文章开头的 Front-matter 配置

当你写每一篇文章时，文章最开头都会有一段由 `---` 包裹起来的配置代码，这叫 Front-matter。它告诉了博客这篇内容的各种属性信息：

```yaml
---
title: 我的第一篇博客文章
published: 2023-09-09
description: 这是我新建立的博客的第一篇文章。
image: ./cover.jpg
tags: [标签1, 标签2]
category: 前端
draft: false
---
```

| 属性配置名 | 说明 |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`       | 文章的标题。 |
| `published`   | 文章的发布日期。格式推荐：YYYY-MM-DD。 |
| `description` | 文章的一句话简短描述，它会显示在博客首页的列表中。 |
| `image`       | 文章封面图的路径。<br/>1. 以 `http://` 或 `https://` 开头：使用网络图片链接<br/>2. 以 `/` 开头：代表存放在项目 `public` 文件夹下的图片<br/>3. 直接写文件名（无前缀）：代表和这篇 markdown 文章在同一个文件夹下的相对路径图片。 |
| `tags`        | 这篇文章的标签，可以写多个。 |
| `category`    | 这篇文章的分类，通常只填一个大的分类。 |
| `draft`       | 如果是 `true`，这篇文章就是一篇草稿，别人在你的博客前台是看不到的。 |

## 把写好的文章放在哪里？

你所有的 markdown 文章文件都应该放在 `src/content/posts/` 这个目录里面。
你可以直接在里面放 `.md` 文件，也可以在里面建子文件夹来管理你的文章和图片素材：

```text
src/content/posts/
├── 我的第一篇文章.md
└── 我的第二篇长文章/
    ├── cover.png (文章配套的图片)
    └── index.md (文章正文)
```
