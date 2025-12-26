---
title: "頁尾配置指南"
date: 2024-12-24
description: "詳細介紹 Hugo Fluid 主題的頁尾配置，包括自訂內容、PV/UV 統計和備案資訊設定。"
categories: ["教學"]
tags: ["頁尾", "配置", "統計", "備案"]
index_img: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800&h=400&fit=crop"
---

本文介紹如何配置 Hugo Fluid 主題的頁尾元件，包括自訂內容、PV/UV 統計和備案資訊。

<!--more-->

## 頁尾效果預覽

捲動到本頁面底部即可看到頁尾效果，包括：

1. **自訂內容**：顯示 "Hugo ❤ Fluid" 連結
2. **PV/UV 統計**：顯示訪問量和訪客數
3. **備案資訊**：顯示 ICP 備案號和公安備案號

## 配置檔案位置

頁尾配置位於 `config/_default/params.toml` 檔案中的 `[footer]` 部分。

## 基礎配置

```toml
[footer]
# 頁尾第一行文字的 HTML
content = '''
<a href="https://gohugo.io" target="_blank" rel="nofollow noopener"><span>Hugo</span></a>
<i class="iconfont icon-love"></i>
<a href="https://github.com/fluid-dev/hexo-theme-fluid" target="_blank" rel="nofollow noopener"><span>Fluid</span></a>
'''
```

你可以自訂 `content` 的內容，支援 HTML 格式：

```toml
content = '''
Copyright © 2024 My Blog
<br>
Powered by <a href="https://gohugo.io">Hugo</a> & <a href="https://github.com/fluid-dev/hexo-theme-fluid">Fluid</a>
'''
```

## PV/UV 統計配置

頁尾可以顯示網站的訪問量（PV）和訪客數（UV）統計。

```toml
[footer.statistics]
# 是否啟用統計
enable = true

# 統計資料來源: busuanzi | leancloud | umami
source = "busuanzi"

# PV 顯示格式，{} 為數字佔位符
pv_format = "總訪問量 {} 次"

# UV 顯示格式，{} 為數字佔位符
uv_format = "總訪客數 {} 人"
```

### 統計源說明

| 統計源 | 說明 | 配置要求 |
|--------|------|----------|
| `busuanzi` | 不蒜子統計，免費易用 | 無需額外配置 |
| `leancloud` | LeanCloud 統計 | 需要配置 LeanCloud 參數 |
| `umami` | Umami 統計 | 需要配置 Umami 參數 |

### 格式化文字範例

```toml
# 中文格式
pv_format = "總訪問量 {} 次"
uv_format = "總訪客數 {} 人"

# 英文格式
pv_format = "Total Views: {}"
uv_format = "Total Visitors: {}"

# 簡潔格式
pv_format = "PV: {}"
uv_format = "UV: {}"
```

## 備案資訊配置

如果你的網站部署在中國大陸伺服器，需要顯示 ICP 備案資訊。

```toml
[footer.beian]
# 是否啟用備案資訊
enable = true

# ICP 備案號
icp_text = "京ICP證123456號"

# 公安備案號（可選）
police_text = "京公網安備12345678號"

# 公安備案編號，用於 URL 跳轉查詢
police_code = "12345678"

# 公安備案圖示路徑
police_icon = "/img/police_beian.png"
```

### 配置說明

| 參數 | 說明 | 必填 |
|------|------|------|
| `enable` | 是否啟用備案資訊 | 是 |
| `icp_text` | ICP 備案號 | 是 |
| `police_text` | 公安備案號 | 否 |
| `police_code` | 公安備案編號 | 否 |
| `police_icon` | 公安備案圖示 | 否 |

## 完整配置範例

```toml
[footer]
content = '''
<a href="https://gohugo.io" target="_blank"><span>Hugo</span></a>
<i class="iconfont icon-love"></i>
<a href="https://github.com/fluid-dev/hexo-theme-fluid" target="_blank"><span>Fluid</span></a>
'''

[footer.statistics]
enable = true
source = "busuanzi"
pv_format = "總訪問量 {} 次"
uv_format = "總訪客數 {} 人"

[footer.beian]
enable = true
icp_text = "京ICP證123456號"
police_text = "京公網安備12345678號"
police_code = "12345678"
police_icon = "/img/police_beian.png"
```

## 常見問題

### 不蒜子統計資料顯示很大的數字？

這是正常現象。在本地開發環境中，不蒜子會顯示測試資料。部署到生產環境後會顯示真實資料。

### 統計資料不顯示？

檢查以下幾點：
1. 確保 `footer.statistics.enable = true`
2. 確保網路可以訪問統計服務
3. 檢查瀏覽器控制台是否有錯誤

### 如何關閉頁尾功能？

- 關閉統計：設定 `footer.statistics.enable = false`
- 關閉備案：設定 `footer.beian.enable = false`

## 相關檔案

- 頁尾模板：`layouts/partials/footer/footer.html`
- 統計元件：`layouts/partials/footer/statistics.html`
- 備案元件：`layouts/partials/footer/beian.html`
