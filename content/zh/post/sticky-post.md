---
title: "置顶文章示例"
date: 2023-01-01T08:00:00+08:00
draft: false
description: "这是一篇置顶文章，用于测试置顶功能。"
categories:
  - 示例
tags:
  - 置顶
  - 测试
sticky: 1
index_img: "https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=800&h=400&fit=crop"
---

这是一篇置顶文章示例。

## 置顶功能说明

在文章的 front matter 中添加 `sticky` 字段即可实现置顶：

```yaml
---
title: "置顶文章"
sticky: 1
---
```

- `sticky` 值越大，排序越靠前
- `sticky: 1` 表示置顶
- `sticky: 2` 会排在 `sticky: 1` 前面

## 效果

置顶文章会：
1. 显示在文章列表最前面
2. 标题前显示置顶图标

享受你的博客之旅！
