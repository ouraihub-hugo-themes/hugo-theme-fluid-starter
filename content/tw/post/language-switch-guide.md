---
title: "多語言配置與語言切換指南"
date: 2024-12-25
categories:
  - 教學
tags:
  - Hugo
  - 多語言
  - 配置
  - i18n
description: "詳細介紹如何在 Hugo Theme Fluid 中配置多語言支援和使用語言切換功能"
index_img: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=800&h=400&fit=crop"
---

Hugo Theme Fluid 提供了完整的多語言支援，讓你可以輕鬆建立多語言部落格。本文將詳細介紹如何配置和使用語言切換功能。

<!--more-->

## 功能特性

- 🌐 支援多種語言（簡體中文、繁體中文、英文、日文等）
- 🔄 導覽列語言切換下拉選單
- 📄 自動偵測翻譯頁面
- 🏠 無翻譯時跳轉到目標語言首頁
- 🎨 美觀的下拉選單樣式

## 配置步驟

### 1. 配置 hugo.toml

在 `config/_default/hugo.toml` 中配置多語言：

```toml
# 預設語言
defaultContentLanguage = "zh-CN"
defaultContentLanguageInSubdir = false

# 多語言配置
[languages]
[languages.zh-CN]
languageCode = "zh-CN"
languageName = "简体中文"
weight = 1
title = "我的部落格"

[languages.en]
languageCode = "en"
languageName = "English"
weight = 2
title = "My Blog"

[languages.zh-TW]
languageCode = "zh-TW"
languageName = "繁體中文"
weight = 3
title = "我的部落格"

[languages.ja]
languageCode = "ja"
languageName = "日本語"
weight = 4
title = "私のブログ"
```

**配置說明：**

| 參數 | 說明 |
|------|------|
| `defaultContentLanguage` | 預設語言代碼 |
| `defaultContentLanguageInSubdir` | 預設語言是否使用子目錄（如 `/zh-CN/`） |
| `languageCode` | 語言代碼，用於 HTML lang 屬性 |
| `languageName` | 語言顯示名稱 |
| `weight` | 排序權重，數字越小越靠前 |
| `title` | 該語言下的站點標題 |

### 2. 配置語言專屬選單（可選）

如果需要為不同語言配置不同的選單，可以在 `menus.toml` 中使用語言後綴：

```toml
# 簡體中文選單
[[menus.zh-CN.main]]
name = "首頁"
url = "/"
weight = 1

[[menus.zh-CN.main]]
name = "歸檔"
url = "/archives/"
weight = 2

# 英文選單
[[menus.en.main]]
name = "Home"
url = "/"
weight = 1

[[menus.en.main]]
name = "Archives"
url = "/archives/"
weight = 2
```

### 3. 建立多語言內容

Hugo 支援兩種多語言內容組織方式：

#### 方式一：檔名後綴（推薦）

```
content/
├── post/
│   ├── hello-world.md        # 預設語言（簡體中文）
│   ├── hello-world.en.md     # 英文版本
│   └── hello-world.zh-TW.md  # 繁體中文版本
```

#### 方式二：語言目錄

```
content/
├── zh-CN/
│   └── post/
│       └── hello-world.md
├── en/
│   └── post/
│       └── hello-world.md
└── zh-TW/
    └── post/
        └── hello-world.md
```

### 4. 翻譯介面文字

主題的介面文字翻譯檔案位於 `i18n/` 目錄：

```
i18n/
├── zh-CN.toml    # 簡體中文
├── en.toml       # 英文
├── zh-TW.toml    # 繁體中文
├── ja.toml       # 日文
├── de.toml       # 德文
├── es.toml       # 西班牙文
├── ru.toml       # 俄文
└── eo.toml       # 世界語
```

## 語言切換元件

### 顯示位置

語言切換按鈕位於導覽列右側，在搜尋按鈕和主題切換按鈕之間。

### 互動方式

1. **懸浮/點擊** - 顯示語言下拉選單
2. **選擇語言** - 點擊目標語言切換

### 切換邏輯

- **有翻譯版本** - 跳轉到當前頁面的翻譯版本
- **無翻譯版本** - 跳轉到目標語言的首頁

## 支援的語言標識

| 語言代碼 | 顯示標識 | 語言名稱 |
|----------|----------|----------|
| `zh-CN` | 简 | 簡體中文 |
| `zh-TW` | 繁 | 繁體中文 |
| `zh-HK` | 港 | 香港繁體 |
| `en` | EN | English |
| `ja` | 日 | 日本語 |
| `de` | DE | Deutsch |
| `es` | ES | Español |
| `ru` | RU | Русский |
| `eo` | EO | Esperanto |

## 常見問題

### Q: 如何禁用語言切換？

只配置一種語言即可，語言切換元件會自動隱藏。

### Q: 如何新增新語言？

1. 在 `hugo.toml` 中新增語言配置
2. 建立對應的 `i18n/xx.toml` 翻譯檔案
3. 建立該語言的內容檔案

### Q: 翻譯頁面如何關聯？

Hugo 會自動透過檔名關聯翻譯頁面：
- `hello-world.md` 和 `hello-world.en.md` 會自動關聯
- 使用 `.Translations` 變數可以獲取所有翻譯版本

### Q: 如何設定預設語言不使用子目錄？

```toml
defaultContentLanguage = "zh-CN"
defaultContentLanguageInSubdir = false
```

這樣預設語言的 URL 是 `/post/hello/`，而不是 `/zh-CN/post/hello/`。

## 最佳實踐

1. **選擇合適的預設語言** - 根據主要受眾選擇
2. **保持翻譯同步** - 定期更新各語言版本
3. **使用檔名後綴** - 更容易管理和維護
4. **完善 i18n 翻譯** - 確保介面文字都有翻譯
5. **測試語言切換** - 確保各語言間切換正常

## 總結

Hugo Theme Fluid 的多語言支援讓你可以輕鬆建立面向全球讀者的部落格。透過簡單的配置，即可實現：

- 多語言內容管理
- 自動語言切換
- 介面文字本地化
- 美觀的語言選擇器

希望這篇教學能幫助你順利配置多語言部落格！
