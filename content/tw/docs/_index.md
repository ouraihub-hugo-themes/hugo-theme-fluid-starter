---
title: "文檔"
description: "Hugo Fluid 主題使用文檔"
date: 2024-12-26
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# Hugo Fluid 主題文檔

歡迎使用 Hugo Fluid 主題！這是一個基於 Material Design 的現代化 Hugo 部落格主題。

## 快速開始

### 安裝主題

#### 方法一：Git Submodule（推薦）

```bash
# 在您的 Hugo 網站根目錄執行
git submodule add https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist.git themes/hugo-theme-fluid
```

#### 方法二：直接下載

1. 下載主題檔案
2. 解壓到 `themes/hugo-theme-fluid` 目錄

### 配置主題

在您的 `hugo.toml` 中設定主題：

```toml
theme = "hugo-theme-fluid"
```

### 基本配置

創建基本的配置檔案：

```toml
# hugo.toml
baseURL = "https://example.com/"
title = "我的部落格"
theme = "hugo-theme-fluid"

# 語言設定
defaultContentLanguage = "tw"
hasCJKLanguage = true

# 輸出格式
[outputs]
home = ["HTML", "RSS", "JSON"]
section = ["HTML", "RSS"]
taxonomy = ["HTML"]
term = ["HTML"]

# 主題參數
[params]
description = "一個優雅的 Material Design Hugo 主題"
author = "您的姓名"

# 深色模式
[params.dark_mode]
enable = true
default = "auto"

# 搜尋功能
[params.search]
enable = true
```

### 創建內容

#### 創建文章

```bash
hugo new post/my-first-post.md
```

#### 文章前置資料範例

```yaml
---
title: "我的第一篇文章"
date: 2024-12-26T10:00:00+08:00
draft: false
description: "這是我的第一篇文章"
banner_img: "/img/post.webp"
banner_img_height: 70
banner_mask_alpha: 0.3
categories: ["技術"]
tags: ["Hugo", "部落格"]
---

這裡是文章內容...
```

### 啟動開發伺服器

```bash
hugo server -D
```

然後在瀏覽器中開啟 `http://localhost:1313`

## 主要功能

### 🎨 Material Design
- 現代化的 Material Design 介面
- 響應式設計
- 流暢的動畫效果

### 🌙 深色模式
- 自動檢測系統主題
- 手動切換淺色/深色模式
- 持久化使用者偏好

### 🔍 搜尋功能
- 快速本地搜尋
- 多語言支援
- 即時搜尋結果

### 📱 響應式設計
- 完美適配手機、平板、桌面
- 觸控友好的操作介面

### 💬 評論系統
支援多種評論系統：
- Giscus（推薦）
- Utterances
- Disqus
- Gitalk
- Waline

## 目錄結構

```
your-site/
├── content/           # 內容檔案
│   ├── post/         # 文章
│   ├── about/        # 關於頁面
│   └── links/        # 友情連結
├── static/           # 靜態檔案
│   └── img/          # 圖片
├── themes/
│   └── hugo-theme-fluid/  # 主題檔案
├── hugo.toml         # Hugo 配置
└── params.toml       # 主題參數
```

## 下一步

- 📖 查看 [配置指南](/docs/config/) 了解詳細配置選項
- 🚀 探索 [主題特性](/docs/features/) 了解所有功能
- 🎨 自訂您的主題外觀和功能

## 需要幫助？

如果您在使用過程中遇到問題：

1. 查看 [配置指南](/docs/config/) 和 [主題特性](/docs/features/)
2. 搜索 [GitHub Issues](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/issues)
3. 在 [Discussions](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/discussions) 中提問

## 貢獻

歡迎為 Hugo Fluid 主題做出貢獻！

- 🐛 [回報 Bug](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/issues/new?template=bug_report.md)
- 💡 [功能建議](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/issues/new?template=feature_request.md)
- 🔧 [提交 Pull Request](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/pulls)

感謝您選擇 Hugo Fluid 主題！