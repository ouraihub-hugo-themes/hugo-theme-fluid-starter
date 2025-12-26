---
title: "打字機效果配置指南"
date: 2024-01-20
categories: ["教學"]
tags: ["Hugo", "Fluid", "打字機效果"]
description: "本文介紹如何在 Hugo Fluid 主題中配置和使用打字機效果。"
index_img: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=800&h=400&fit=crop"
banner_img: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=1920&h=1080&fit=crop"
---

本文介紹如何在 Hugo Fluid 主題中配置和使用打字機效果。

<!--more-->

## 什麼是打字機效果

打字機效果是一種動態文字展示效果，文字會像打字機一樣逐字顯示，配合閃爍的游標，讓頁面更具動態感。在 Fluid 主題中，打字機效果主要用於首頁的副標題（slogan）展示。

## 基礎配置

在 `config/_default/params.toml` 中配置打字機效果：

```toml
[fun_features.typing]
enable = true        # 是否啟用打字機效果
typeSpeed = 70       # 打字速度，數字越大越慢
cursorChar = "_"     # 游標字元
loop = false         # 是否循環播放
scope = []           # 生效範圍，空陣列表示所有頁面
```

## 配置項詳解

### enable

控制是否啟用打字機效果。設定為 `false` 可以完全禁用此功能。

```toml
[fun_features.typing]
enable = true
```

### typeSpeed

控制打字速度，單位是毫秒。數值越大，打字越慢。

```toml
[fun_features.typing]
typeSpeed = 70    # 預設值，適中的速度
# typeSpeed = 50  # 更快
# typeSpeed = 100 # 更慢
```

### cursorChar

設定游標字元，預設是底線 `_`。你可以改成其他字元：

```toml
[fun_features.typing]
cursorChar = "_"   # 底線（預設）
# cursorChar = "|" # 豎線
# cursorChar = "▌" # 方塊
```

### loop

控制打字動畫是否循環播放。如果設定為 `true`，文字打完後會刪除並重新開始打字。

```toml
[fun_features.typing]
loop = false  # 只播放一次（預設）
# loop = true # 循環播放
```

### scope

限制打字機效果的生效範圍。可選值包括：

- `home` - 首頁
- `post` - 文章頁
- `tag` - 標籤頁
- `category` - 分類頁
- `about` - 關於頁
- `links` - 友鏈頁
- `page` - 普通頁面
- `404` - 404 頁面

```toml
[fun_features.typing]
scope = []              # 空陣列表示所有頁面都啟用
# scope = ["home"]      # 只在首頁啟用
# scope = ["home", "post"]  # 在首頁和文章頁啟用
```

## 首頁副標題配置

打字機效果主要用於首頁的副標題。在 `params.toml` 中配置：

### 單條文字

```toml
[index.slogan]
enable = true
text = "An elegant Material-Design theme for Hugo"
```

### 多條文字隨機顯示

如果你想每次重新整理頁面顯示不同的文字，可以配置為陣列：

```toml
[index.slogan]
enable = true
text = [
  "An elegant Material-Design theme for Hugo",
  "簡潔、優雅、高效",
  "專注於內容創作"
]
```

每次頁面載入時，會隨機選擇一條文字進行打字展示。

## 在文章頁禁用打字效果

如果你想在某篇文章中禁用打字機效果，可以在文章的 Front Matter 中設定：

```yaml
---
title: "我的文章"
subtitle: false  # 禁用副標題和打字效果
---
```

## 完整配置範例

```toml
# 打字機效果配置
[fun_features.typing]
enable = true
typeSpeed = 70
cursorChar = "_"
loop = false
scope = ["home", "about"]  # 只在首頁和關於頁啟用

# 首頁副標題配置
[index.slogan]
enable = true
text = [
  "An elegant Material-Design theme for Hugo",
  "簡潔、優雅、高效",
  "專注於內容創作"
]
```

## 注意事項

1. 打字機效果依賴 [typed.js](https://github.com/mattboldt/typed.js/) 函式庫，會從 CDN 載入
2. 如果網路較慢，可能會有短暫延遲才開始打字動畫
3. 打字速度設定過快可能導致動畫效果不明顯
4. 循環播放模式下，文字會不斷重複打字和刪除

## 效果預覽

重新整理本頁面，觀察頂部 Banner 區域的副標題，你會看到文字逐字顯示的打字機效果。
