---
title: "Sticky Post Example"
date: 2023-01-01T08:00:00+08:00
draft: false
description: "This is a sticky post example to test the sticky feature."
categories:
  - Example
tags:
  - Sticky
  - Test
sticky: 1
index_img: "https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=800&h=400&fit=crop"
---

This is a sticky post example.

## Sticky Feature Description

Add the `sticky` field in the article's front matter to enable sticky:

```yaml
---
title: "Sticky Post"
sticky: 1
---
```

- Higher `sticky` values appear first
- `sticky: 1` means sticky
- `sticky: 2` will appear before `sticky: 1`

## Effect

Sticky posts will:
1. Appear at the top of the post list
2. Display a sticky icon before the title

Enjoy your blogging journey!
