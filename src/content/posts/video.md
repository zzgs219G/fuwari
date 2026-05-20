---
title: 在文章中嵌入视频
published: 2023-08-01
description: 这篇文章演示了如何在博客文章中包含嵌入式视频。
tags: [示例, 视频]
category: 示例
draft: false
---

如果你想在博客里放视频，做法非常简单。你只需要去视频网站（比如哔哩哔哩 Bilibili 或 YouTube）复制它的“嵌入代码”，然后直接粘贴到你的 markdown 文件里就行了。

```yaml
---
title: 在文章中嵌入视频
published: 2023-10-19
// ... 这里是文章的头部配置
---

<iframe width="100%" height="468" src="//player.bilibili.com/player.html..." allowfullscreen></iframe>
```

## Bilibili (B站) 视频示例

<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1fK4y1s7Qf&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

## YouTube 视频示例

<iframe width="100%" height="468" src="https://www.youtube.com/embed/5gIf0_xpFPI?si=N1WTorLKL0uwLsU_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
