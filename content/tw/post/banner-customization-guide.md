---
title: "Banner 背景圖片配置完全指南"
date: 2024-12-24
draft: false
categories: ["教學"]
tags: ["主題配置", "Banner", "圖片優化"]
index_img: "https://images.unsplash.com/photo-1579546929518-9e396f3cc809?w=800&h=400&fit=crop"
banner_img: "/img/post.webp"
---

本文將詳細介紹如何為 Hugo Fluid 主題配置自訂 Banner 背景圖片，包括使用 AI 生成圖片、壓縮優化、以及配置到主題中的完整流程。

<!--more-->

## 概述

Hugo Fluid 主題的每個頁面都可以配置獨立的 Banner 背景圖片，包括：

- 首頁 (Home)
- 文章頁 (Post)
- 歸檔頁 (Archive)
- 分類頁 (Category)
- 標籤頁 (Tag)
- 關於頁 (About)
- 友鏈頁 (Links)
- 404 頁面

本主題推薦使用**扁平化插畫風格**的圖片，與 Material Design 設計語言相匹配。

### 效果預覽

以下是本主題使用的 Banner 圖片效果：

| 首頁 | 文章頁 |
|:----:|:------:|
| ![首頁 Banner](/img/home.webp) | ![文章頁 Banner](/img/post.webp) |

| 歸檔頁 | 分類頁 |
|:------:|:------:|
| ![歸檔頁 Banner](/img/archive.webp) | ![分類頁 Banner](/img/category.webp) |

| 標籤頁 | 關於頁 |
|:------:|:------:|
| ![標籤頁 Banner](/img/tag.webp) | ![關於頁 Banner](/img/about.webp) |

| 友鏈頁 | 404 頁面 |
|:------:|:--------:|
| ![友鏈頁 Banner](/img/links.webp) | ![404 頁面 Banner](/img/404.webp) |

## 第一步：獲取圖片

### 方式一：使用 AI 生成（推薦）

使用 AI 圖片生成工具可以快速獲得風格統一的插畫。

#### 推薦工具

| 工具 | 網址 | 特點 |
|------|------|------|
| **LM Arena** | [lmarena.ai](https://lmarena.ai/) | ⭐ **強烈推薦**，免費，多模型可選 |
| ChatGPT (DALL-E 3) | [chat.openai.com](https://chat.openai.com) | 簡單易用，需訂閱 |
| Midjourney | [midjourney.com](https://midjourney.com) | 品質最高，需付費 |

#### 使用 LM Arena 生成圖片（推薦）

本主題的 Banner 圖片就是使用 LM Arena 生成的，效果非常好。

**操作步驟**：

1. 開啟 [lmarena.ai](https://lmarena.ai/)
2. 點擊頂部的 **Image** 標籤切換到圖片生成模式
3. 在模型選擇下拉框中選擇 **gemini-3-pro-image-preview (nano-banana-pro)**
4. 將下方的提示詞複製貼上到輸入框
5. 點擊生成，等待幾秒即可得到圖片
6. 右鍵儲存圖片

> **提示**：Gemini 3 Pro 模型生成的扁平化插畫風格非常適合本主題，色彩豐富，層次分明。

## 第二步：壓縮圖片

圖片壓縮是**非常重要**的一步，直接影響網站載入速度。

### 使用 Squoosh（推薦）

[Squoosh](https://squoosh.app/) 是 Google 開發的免費線上圖片壓縮工具，操作簡單，效果出色。

#### 操作步驟

1. 開啟 [squoosh.app](https://squoosh.app/)

2. 將圖片拖入頁面，或點擊選擇檔案

3. 在右側面板進行設定：

   **格式選擇**：點擊 "Compress" 下拉選單，選擇 `WebP`

   **品質設定**：
   - Quality: `70`（推薦值，平衡品質和大小）
   - Effort: `6`（壓縮力度，越高檔案越小）

4. 查看右下角的檔案大小預覽

5. 點擊右下角的下載按鈕儲存

#### 推薦設定參數

| 設定項 | 推薦值 | 說明 |
|--------|--------|------|
| 格式 | WebP | 檔案最小，現代瀏覽器都支援 |
| Quality | 70 | 品質和大小的最佳平衡點 |
| Effort | 6 | 壓縮力度，6 是較好的選擇 |
| Resize 寬度 | 1920 | 保持 1920x1080 的比例 |

#### 目標檔案大小

| 檔案大小 | 評價 | 載入體驗 |
|----------|------|----------|
| < 100KB | ⭐⭐⭐ 極佳 | 秒開，幾乎無感知 |
| 100-200KB | ⭐⭐ 良好 | 很快，體驗流暢 |
| 200-300KB | ⭐ 可接受 | 稍有等待 |
| > 300KB | ❌ 太大 | 需要降低 Quality 重新壓縮 |

## 第三步：儲存圖片到專案

將壓縮後的圖片儲存到主題的 `static/img/` 目錄：

```
your-site/
└── static/
    └── img/
        ├── home.webp      # 首頁
        ├── post.webp      # 文章頁
        ├── archive.webp   # 歸檔頁
        ├── category.webp  # 分類頁
        ├── tag.webp       # 標籤頁
        ├── about.webp     # 關於頁
        ├── links.webp     # 友鏈頁
        └── 404.webp       # 404頁面
```

## 第四步：修改配置

編輯站點配置檔案 `config/_default/params.toml`，修改各頁面的 `banner_img` 配置：

```toml
#---------------------------
# 首頁
#---------------------------
[index]
banner_img = "/img/home.webp"
banner_img_height = 100
banner_mask_alpha = 0.3

#---------------------------
# 文章頁
#---------------------------
[post]
banner_img = "/img/post.webp"
banner_img_height = 70
banner_mask_alpha = 0.3
```

### 配置說明

| 參數 | 說明 | 推薦值 |
|------|------|--------|
| `banner_img` | 圖片路徑，相對於 static 目錄 | `/img/xxx.webp` |
| `banner_img_height` | Banner 高度，佔螢幕百分比 | 60-100 |
| `banner_mask_alpha` | 遮罩透明度，0-1 之間 | 0.3 |

## 第五步：驗證效果

啟動開發伺服器查看效果：

```bash
hugo server
```

訪問 `http://localhost:1313` 檢查各頁面的 Banner 是否正確顯示。

## 總結

配置自訂 Banner 的完整流程：

1. **生成圖片**：使用 AI 工具或免費圖片網站
2. **壓縮圖片**：使用 Squoosh，WebP 格式，Quality 70
3. **儲存圖片**：放到 `static/img/` 目錄
4. **修改配置**：更新 `params.toml` 中的 `banner_img`
5. **驗證效果**：啟動開發伺服器檢查

按照本教學操作，你可以獲得載入速度快、視覺效果好的自訂 Banner 背景。
