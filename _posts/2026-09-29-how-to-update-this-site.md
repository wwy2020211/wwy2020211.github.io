---
layout: post
title: 如何更新这个网站
description: 加新闻、加论文、写博客，各只需要改一个文件。
tags: [meta]
lang: zh-CN
---

这篇文章既是示例，也是使用说明。确认网站能正常运行之后，可以把它删掉。

## 加一条新闻

打开 `_data/news.yml`，在**最上面**加两行：

```yaml
- date: "2026.10"
  text: 我们的论文被 **CVPR 2027** 接收！
```

## 加一篇论文

打开 `_data/publications.yml`，照着已有格式加一个条目。想让它显示在首页，就加上 `selected: true`。

## 写一篇博客

在 `_posts/` 里新建文件，文件名必须是 `年-月-日-英文标题.md` 的格式，例如 `2026-10-01-my-first-post.md`，开头写上：

```yaml
---
layout: post
title: 我的第一篇博客
description: 一句话简介，会显示在博客列表里
tags: [research]
---
```

下面正文就用普通 Markdown 写。改完之后 push 到 GitHub，一两分钟后网站自动更新。
