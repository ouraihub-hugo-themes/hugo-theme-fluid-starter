---
title: "置頂文章範例"
date: 2023-01-01T08:00:00+08:00
draft: false
description: "這是一篇置頂文章，用於測試置頂功能。"
categories:
  - 範例
tags:
  - 置頂
  - 測試
sticky: 1
index_img: "https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=800&h=400&fit=crop"
---

這是一篇置頂文章範例。

## 置頂功能說明

在文章的 front matter 中新增 `sticky` 欄位即可實現置頂：

```yaml
---
title: "置頂文章"
sticky: 1
---
```

- `sticky` 值越大，排序越靠前
- `sticky: 1` 表示置頂
- `sticky: 2` 會排在 `sticky: 1` 前面

## 效果

置頂文章會：
1. 顯示在文章列表最前面
2. 標題前顯示置頂圖示

享受你的部落格之旅！
