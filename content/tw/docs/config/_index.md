---
title: "配置指南"
description: "Hugo Fluid 主題詳細配置指南"
date: 2024-12-26
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# 配置指南

本頁面提供 Hugo Fluid 主題的詳細配置說明。

## 基礎配置

### Hugo 配置 (hugo.toml)

```toml
baseURL = "https://example.com/"
title = "我的部落格"
theme = "hugo-theme-fluid"

# 預設語言
defaultContentLanguage = "tw"
defaultContentLanguageInSubdir = false

# CJK 語言支援
hasCJKLanguage = true

# 輸出格式
[outputs]
home = ["HTML", "RSS", "JSON"]
section = ["HTML", "RSS"]
taxonomy = ["HTML"]
term = ["HTML"]
```

### 主題參數 (params.toml)

#### 全域配置

```toml
# 網站圖示
favicon = "/img/fluid.png"
apple_touch_icon = "/img/fluid.png"

# 網站描述
description = "一個優雅的 Material Design Hugo 主題"
author = "您的姓名"

# 程式碼區塊配置
[code]
copy_btn = true
[code.language]
enable = true
default = "TEXT"
[code.highlight]
enable = true
line_number = true
```

#### 主題色彩

```toml
[color]
body_bg_color = "#eee"
body_bg_color_dark = "#181c27"
navbar_bg_color = "#2f4154"
navbar_bg_color_dark = "#1f3144"
text_color = "#3c4858"
text_color_dark = "#c4c6c9"
link_color = "#0366d6"
link_color_dark = "#1589e9"
```

#### 深色模式

```toml
[dark_mode]
enable = true
default = "auto"  # auto | light | dark
```

## 頁面配置

### 首頁配置

```toml
[index]
banner_img = "/img/home.webp"
banner_img_height = 100
banner_mask_alpha = 0.3
[index.slogan]
enable = true
# 標語文字在語言特定配置中設定
[index.post_meta]
date = true
category = true
tag = true
```

### 文章頁面配置

```toml
[post]
banner_img = "/img/post.webp"
banner_img_height = 70
banner_mask_alpha = 0.3

[post.toc]
enable = true
placement = "right"  # left | right
headingSelector = "h1,h2,h3,h4,h5,h6"
collapseDepth = 0

[post.copyright]
enable = true
license = "BY"  # BY | BY-SA | BY-ND | BY-NC | BY-NC-SA | BY-NC-ND | ZERO

[post.comments]
enable = false
type = "giscus"  # utterances | disqus | gitalk | valine | waline | giscus
```

## 功能配置

### 搜尋功能

```toml
[search]
enable = true
path = "/index.json"
field = "post"  # post | page | all
content = true
```

### 導航列

```toml
[navbar]
blog_title = "Hugo Fluid"
[navbar.ground_glass]
enable = true
px = 3
alpha = 0.7
```

### 頁尾

```toml
[footer]
content = '''
<a href="https://gohugo.io" target="_blank" rel="nofollow noopener"><span>Hugo</span></a>
<i class="iconfont icon-love"></i>
<a href="https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist" target="_blank" rel="nofollow noopener"><span>Fluid</span></a>
'''

[footer.statistics]
enable = true
source = "busuanzi"  # busuanzi | leancloud | umami
```

## 選單配置

### 主選單 (menus.tw.toml)

Hugo Fluid 主題支援普通選單項目和下拉選單。選單配置檔案位於 `config/_default/menus.tw.toml`（繁體中文）、`menus.zh.toml`（簡體中文）、`menus.en.toml`（英文）。

#### 普通選單項目

```toml
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
```

#### 下拉選單配置

下拉選單需要一個父選單項目和多個子選單項目。父選單項目使用 `hasChildren = true` 標識，子選單項目使用 `parent` 屬性指向父選單。

```toml
# 父選單項目 - 文檔下拉選單
[[main]]
name = "文檔"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true  # 標識這是一個下拉選單

# 子選單項目 1
[[main]]
name = "快速開始"
url = "/docs/"
weight = 71
parent = "文檔"  # 指向父選單的 name

# 子選單項目 2
[[main]]
name = "配置指南"
url = "/docs/config/"
weight = 72
parent = "文檔"

# 子選單項目 3
[[main]]
name = "主題特性"
url = "/docs/features/"
weight = 73
parent = "文檔"
```

#### 選單參數說明

| 參數 | 說明 | 範例 |
|------|------|------|
| `name` | 選單顯示名稱 | `"首頁"` |
| `url` | 連結地址 | `"/"` 或 `"https://example.com"` |
| `weight` | 排序權重（數字越小越靠前） | `1`, `2`, `3` |
| `pre` | 圖示類別名稱 | `"iconfont icon-home-fill"` |
| `post` | 連結開啟方式 | `"_blank"`（新分頁） |
| `hasChildren` | 是否為下拉選單父項 | `true` |
| `parent` | 父選單名稱（僅子選單項目使用） | `"文檔"` |

#### 外部連結配置

如果要連結到外部網站並在新分頁開啟：

```toml
[[main]]
name = "GitHub"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 8
pre = "iconfont icon-github"
post = "_blank"  # 在新分頁開啟
```

#### 下拉選單外部連結

下拉選單也可以包含外部連結：

```toml
# 父選單項目
[[main]]
name = "連結"
url = "#"
weight = 9
pre = "iconfont icon-link"
hasChildren = true

# 外部連結子項
[[main]]
name = "官方文檔"
url = "https://gohugo.io/documentation/"
weight = 91
parent = "連結"
post = "_blank"

# 內部連結子項
[[main]]
name = "友情連結"
url = "/links/"
weight = 92
parent = "連結"
```

#### 權重排序規則

- 主選單項目權重：1-10（建議間隔為 1）
- 子選單項目權重：父選單權重 × 10 + 序號
  - 例如：父選單權重為 7，子選單權重為 71、72、73

#### 圖示配置

主題使用 iconfont 圖示庫，常用圖示類別名稱：

```toml
# 常用圖示
pre = "iconfont icon-home-fill"      # 首頁
pre = "iconfont icon-archive-fill"   # 歸檔
pre = "iconfont icon-category-fill"  # 分類
pre = "iconfont icon-tags-fill"      # 標籤
pre = "iconfont icon-link-fill"      # 友鏈
pre = "iconfont icon-user-fill"      # 關於
pre = "iconfont icon-books"          # 文檔
pre = "iconfont icon-github"         # GitHub
pre = "iconfont icon-search"         # 搜尋
```

#### 完整範例

以下是一個包含普通選單和下拉選單的完整配置範例：

```toml
# 普通選單項目
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

#### 多語言選單

不同語言的選單配置檔案：

- `menus.tw.toml` - 繁體中文選單
- `menus.zh.toml` - 簡體中文選單
- `menus.en.toml` - 英文選單

每個語言檔案的結構相同，只需要翻譯 `name` 欄位：

```toml
# menus.en.toml
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

## 多語言配置

### 語言設定 (languages.toml)

```toml
[tw]
languageCode = "zh-TW"
languageName = "繁體中文"
weight = 1
title = "Hugo Fluid 部落格"
contentDir = "content/tw"

[zh]
languageCode = "zh-CN"
languageName = "简体中文"
weight = 2
title = "Hugo Fluid 博客"
contentDir = "content/zh"

[en]
languageCode = "en"
languageName = "English"
weight = 3
title = "Hugo Fluid Blog"
contentDir = "content/en"
```

## 評論系統配置

### Giscus 配置

```toml
[post.comments.giscus]
repo = "owner/repo"
repo_id = "your-repo-id"
category = "Announcements"
category_id = "your-category-id"
theme_light = "light"
theme_dark = "dark"
mapping = "pathname"
reactions_enabled = true
emit_metadata = false
input_position = "bottom"
lang = "zh-TW"
```

### Utterances 配置

```toml
[post.comments.utterances]
repo = "owner/repo"
issue_term = "pathname"
theme = "github-light"
theme_dark = "github-dark"
```

## 統計分析配置

### Google Analytics

```toml
[analytics.google]
measurement_id = "G-XXXXXXXXXX"
```

### 百度統計

```toml
[analytics.baidu]
analytics_id = "your-baidu-id"
```

### 不蒜子統計

```toml
[footer.statistics.busuanzi]
site_pv = true
site_uv = true
page_pv = true
```

## 數學公式配置

### MathJax

```toml
[math]
enable = true
engine = "mathjax"
[math.mathjax]
src = "https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"
config = '''
{
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']],
    displayMath: [['$$', '$$'], ['\\[', '\\]']]
  }
}
'''
```

### KaTeX

```toml
[math]
enable = true
engine = "katex"
[math.katex]
src = "https://cdn.jsdelivr.net/npm/katex@0.16.0/dist/katex.min.js"
css = "https://cdn.jsdelivr.net/npm/katex@0.16.0/dist/katex.min.css"
```

## 程式碼高亮配置

### 高亮主題

```toml
[code.highlight]
theme = "github"  # github | monokai | dracula | nord | etc.
theme_dark = "github-dark"
```

### 支援的語言

主題支援所有 Hugo 內建的語言高亮，包括但不限於：
- JavaScript/TypeScript
- Python
- Go
- Java
- C/C++
- HTML/CSS
- Markdown
- YAML/TOML
- Shell/Bash

## 自訂樣式

### CSS 變數

您可以透過覆寫 CSS 變數來自訂主題外觀：

```css
:root {
  --body-bg-color: #f8f9fa;
  --text-color: #212529;
  --link-color: #007bff;
  --navbar-bg-color: #343a40;
}

[data-user-color-scheme="dark"] {
  --body-bg-color: #121212;
  --text-color: #e0e0e0;
  --link-color: #64b5f6;
  --navbar-bg-color: #1e1e1e;
}
```

### 自訂字型

```toml
[font]
font_family = "'Noto Sans TC', 'PingFang TC', 'Microsoft JhengHei', sans-serif"
font_size = "16px"
code_font_family = "'JetBrains Mono', 'Fira Code', 'Consolas', monospace"
```

更多配置選項請參考 [主題特性](/docs/features/) 頁面。