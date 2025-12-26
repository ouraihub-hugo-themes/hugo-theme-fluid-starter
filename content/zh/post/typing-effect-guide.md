---
title: "打字机效果配置指南"
date: 2024-01-20
categories: ["教程"]
tags: ["Hugo", "Fluid", "打字机效果"]
description: "本文介绍如何在 Hugo Fluid 主题中配置和使用打字机效果。"
index_img: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=800&h=400&fit=crop"
banner_img: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=1920&h=1080&fit=crop"
---

本文介绍如何在 Hugo Fluid 主题中配置和使用打字机效果。

<!--more-->

## 什么是打字机效果

打字机效果是一种动态文字展示效果，文字会像打字机一样逐字显示，配合闪烁的光标，让页面更具动态感。在 Fluid 主题中，打字机效果主要用于首页的副标题（slogan）展示。

## 基础配置

在 `config/_default/params.toml` 中配置打字机效果：

```toml
[fun_features.typing]
enable = true        # 是否启用打字机效果
typeSpeed = 70       # 打字速度，数字越大越慢
cursorChar = "_"     # 光标字符
loop = false         # 是否循环播放
scope = []           # 生效范围，空数组表示所有页面
```

## 配置项详解

### enable

控制是否启用打字机效果。设置为 `false` 可以完全禁用此功能。

```toml
[fun_features.typing]
enable = true
```

### typeSpeed

控制打字速度，单位是毫秒。数值越大，打字越慢。

```toml
[fun_features.typing]
typeSpeed = 70    # 默认值，适中的速度
# typeSpeed = 50  # 更快
# typeSpeed = 100 # 更慢
```

### cursorChar

设置光标字符，默认是下划线 `_`。你可以改成其他字符：

```toml
[fun_features.typing]
cursorChar = "_"   # 下划线（默认）
# cursorChar = "|" # 竖线
# cursorChar = "▌" # 方块
```

### loop

控制打字动画是否循环播放。如果设置为 `true`，文字打完后会删除并重新开始打字。

```toml
[fun_features.typing]
loop = false  # 只播放一次（默认）
# loop = true # 循环播放
```

### scope

限制打字机效果的生效范围。可选值包括：

- `home` - 首页
- `post` - 文章页
- `tag` - 标签页
- `category` - 分类页
- `about` - 关于页
- `links` - 友链页
- `page` - 普通页面
- `404` - 404 页面

```toml
[fun_features.typing]
scope = []              # 空数组表示所有页面都启用
# scope = ["home"]      # 只在首页启用
# scope = ["home", "post"]  # 在首页和文章页启用
```

## 首页副标题配置

打字机效果主要用于首页的副标题。在 `params.toml` 中配置：

### 单条文字

```toml
[index.slogan]
enable = true
text = "An elegant Material-Design theme for Hugo"
```

### 多条文字随机显示

如果你想每次刷新页面显示不同的文字，可以配置为数组：

```toml
[index.slogan]
enable = true
text = [
  "An elegant Material-Design theme for Hugo",
  "简洁、优雅、高效",
  "专注于内容创作"
]
```

每次页面加载时，会随机选择一条文字进行打字展示。

## 在文章页禁用打字效果

如果你想在某篇文章中禁用打字机效果，可以在文章的 Front Matter 中设置：

```yaml
---
title: "我的文章"
subtitle: false  # 禁用副标题和打字效果
---
```

## 完整配置示例

```toml
# 打字机效果配置
[fun_features.typing]
enable = true
typeSpeed = 70
cursorChar = "_"
loop = false
scope = ["home", "about"]  # 只在首页和关于页启用

# 首页副标题配置
[index.slogan]
enable = true
text = [
  "An elegant Material-Design theme for Hugo",
  "简洁、优雅、高效",
  "专注于内容创作"
]
```

## 注意事项

1. 打字机效果依赖 [typed.js](https://github.com/mattboldt/typed.js/) 库，会从 CDN 加载
2. 如果网络较慢，可能会有短暂延迟才开始打字动画
3. 打字速度设置过快可能导致动画效果不明显
4. 循环播放模式下，文字会不断重复打字和删除

## 效果预览

刷新本页面，观察顶部 Banner 区域的副标题，你会看到文字逐字显示的打字机效果。
