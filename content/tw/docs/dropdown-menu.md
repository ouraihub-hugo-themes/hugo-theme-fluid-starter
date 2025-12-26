---
title: "下拉選單配置指南"
description: "詳細說明如何在 Hugo Fluid 主題中配置下拉選單"
date: 2024-12-26
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# 下拉選單配置指南

本指南詳細說明如何在 Hugo Fluid 主題中配置下拉選單，包括普通選單項和多級下拉選單的設置方法。

## 選單配置檔案位置

Hugo Fluid 主題的選單配置檔案位於 `config/_default/` 目錄下：

```
config/_default/
├── menus.zh.toml    # 簡體中文選單
├── menus.en.toml    # 英文選單
└── menus.tw.toml    # 繁體中文選單
```

## 基礎選單配置

### 普通選單項

普通選單項是最基本的選單類型，直接連結到頁面：

```toml
[[main]]
name = "首頁"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"
```

### 選單參數說明

| 參數 | 必需 | 說明 | 示例 |
|------|------|------|------|
| `name` | ✅ | 選單顯示名稱 | `"首頁"` |
| `url` | ✅ | 連結地址 | `"/"` 或 `"https://example.com"` |
| `weight` | ✅ | 排序權重（數字越小越靠前） | `1`, `2`, `3` |
| `pre` | ❌ | 圖示類名 | `"iconfont icon-home-fill"` |
| `post` | ❌ | 連結開啟方式 | `"_blank"`（新標籤頁） |
| `hasChildren` | ❌ | 是否為下拉選單父項 | `true` |
| `parent` | ❌ | 父選單名稱（僅子選單項使用） | `"文檔"` |

## 下拉選單配置

### 基本下拉選單

下拉選單由一個父選單項和多個子選單項組成：

```toml
# 父選單項 - 文檔下拉選單
[[main]]
name = "文檔"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true  # 標識這是一個下拉選單

# 子選單項 1
[[main]]
name = "快速開始"
url = "/docs/"
weight = 71
parent = "文檔"  # 指向父選單的 name

# 子選單項 2
[[main]]
name = "配置指南"
url = "/docs/config/"
weight = 72
parent = "文檔"

# 子選單項 3
[[main]]
name = "主題特性"
url = "/docs/features/"
weight = 73
parent = "文檔"
```

### 配置要點

1. **父選單項**：
   - 必須設置 `hasChildren = true`
   - 可以有自己的 URL（點擊父選單時跳轉）
   - 也可以設置 `url = "#"`（僅作為下拉容器）

2. **子選單項**：
   - 必須設置 `parent` 屬性，值為父選單的 `name`
   - 權重建議使用父選單權重 × 10 + 序號的方式

### 權重排序規則

為了保持選單順序的清晰性，建議使用以下權重規則：

- **主選單項權重**：1-10（間隔為 1）
- **子選單項權重**：父選單權重 × 10 + 序號

示例：
```toml
# 父選單權重為 7
[[main]]
name = "文檔"
weight = 7
hasChildren = true

# 子選單權重為 71, 72, 73
[[main]]
name = "快速開始"
weight = 71
parent = "文檔"

[[main]]
name = "配置指南"
weight = 72
parent = "文檔"

[[main]]
name = "主題特性"
weight = 73
parent = "文檔"
```

## 外部連結下拉選單

下拉選單也可以包含外部連結：

```toml
# 父選單項
[[main]]
name = "相關連結"
url = "#"  # 不跳轉，僅作為下拉容器
weight = 8
pre = "iconfont icon-link"
hasChildren = true

# 外部連結子項
[[main]]
name = "Hugo 官網"
url = "https://gohugo.io/"
weight = 81
parent = "相關連結"
post = "_blank"  # 在新標籤頁開啟

# 內部連結子項
[[main]]
name = "GitHub 倉庫"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 82
parent = "相關連結"
post = "_blank"
```

## 圖示配置

Hugo Fluid 主題使用 iconfont 圖示庫，以下是常用圖示：

```toml
# 常用圖示類名
pre = "iconfont icon-home-fill"      # 首頁
pre = "iconfont icon-archive-fill"   # 歸檔
pre = "iconfont icon-category-fill"  # 分類
pre = "iconfont icon-tags-fill"      # 標籤
pre = "iconfont icon-link-fill"      # 友鏈
pre = "iconfont icon-user-fill"      # 關於
pre = "iconfont icon-books"          # 文檔
pre = "iconfont icon-github"         # GitHub
pre = "iconfont icon-search"         # 搜尋
pre = "iconfont icon-link"           # 連結
```

## 多語言選單配置

不同語言的選單配置檔案結構相同，只需要翻譯 `name` 欄位：

### 中文選單 (menus.zh.toml)

```toml
[[main]]
name = "文档"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "快速开始"
url = "/docs/"
weight = 71
parent = "文档"
```

### 英文選單 (menus.en.toml)

```toml
[[main]]
name = "Docs"           # 英文名稱
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "Quick Start"    # 英文名稱
url = "/docs/"
weight = 71
parent = "Docs"         # 對應英文父選單名
```

### 繁體中文選單 (menus.tw.toml)

```toml
[[main]]
name = "文檔"           # 繁體中文名稱
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "快速開始"       # 繁體中文名稱
url = "/docs/"
weight = 71
parent = "文檔"         # 對應繁體中文父選單名
```

## 完整配置示例

以下是一個包含普通選單和下拉選單的完整配置示例：

```toml
# 普通選單項
[[main]]
name = "首頁"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"

[[main]]
name = "歸檔"
url = "/archives/"
weight = 2
pre = "iconfont icon-archive-fill"

[[main]]
name = "分類"
url = "/categories/"
weight = 3
pre = "iconfont icon-category-fill"

[[main]]
name = "標籤"
url = "/tags/"
weight = 4
pre = "iconfont icon-tags-fill"

[[main]]
name = "友鏈"
url = "/links/"
weight = 5
pre = "iconfont icon-link-fill"

[[main]]
name = "關於"
url = "/about/"
weight = 6
pre = "iconfont icon-user-fill"

# 文檔下拉選單
[[main]]
name = "文檔"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "快速開始"
url = "/docs/"
weight = 71
parent = "文檔"

[[main]]
name = "配置指南"
url = "/docs/config/"
weight = 72
parent = "文檔"

[[main]]
name = "主題特性"
url = "/docs/features/"
weight = 73
parent = "文檔"

[[main]]
name = "下拉選單配置"
url = "/docs/dropdown-menu/"
weight = 74
parent = "文檔"

# 外部連結下拉選單
[[main]]
name = "相關連結"
url = "#"
weight = 8
pre = "iconfont icon-link"
hasChildren = true

[[main]]
name = "Hugo 官網"
url = "https://gohugo.io/"
weight = 81
parent = "相關連結"
post = "_blank"

[[main]]
name = "GitHub 倉庫"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 82
parent = "相關連結"
post = "_blank"
```

## 常見問題

### Q: 下拉選單不顯示怎麼辦？

A: 檢查以下幾點：
1. 父選單項是否設置了 `hasChildren = true`
2. 子選單項是否正確設置了 `parent` 屬性
3. `parent` 的值是否與父選單的 `name` 完全一致（區分大小寫）

### Q: 選單順序不對怎麼辦？

A: 檢查 `weight` 權重設置：
- 數字越小越靠前
- 確保權重沒有重複
- 子選單權重應該在父選單權重範圍內

### Q: 如何添加分隔線？

A: Hugo Fluid 主題暫不支援選單分隔線，可以透過權重間隔來視覺上分組。

### Q: 可以有多級下拉選單嗎？

A: 目前主題支援二級下拉選單（父選單 + 子選單），不支援更深層級的嵌套。

### Q: 如何隱藏某個選單項？

A: 直接刪除或註釋掉對應的選單配置即可：

```toml
# [[main]]
# name = "隱藏的選單"
# url = "/hidden/"
# weight = 10
```

## 測試選單配置

配置完成後，可以透過以下方式測試：

1. **啟動開發伺服器**：
   ```bash
   pnpm dev
   ```

2. **訪問網站**：
   開啟 `http://localhost:1313` 查看選單效果

3. **檢查多語言**：
   切換不同語言查看選單是否正確顯示

4. **測試響應式**：
   在不同裝置尺寸下測試選單的響應式效果

## 總結

下拉選單配置的關鍵點：

1. **父選單項**：設置 `hasChildren = true`
2. **子選單項**：設置正確的 `parent` 屬性
3. **權重排序**：使用合理的權重規則
4. **多語言支援**：為每種語言建立對應的選單檔案
5. **圖示配置**：使用 iconfont 圖示類名

透過合理配置下拉選單，可以讓網站導航更加清晰和使用者友好。