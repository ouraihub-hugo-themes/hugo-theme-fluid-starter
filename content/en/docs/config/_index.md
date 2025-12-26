---
title: "Configuration Guide"
description: "Detailed configuration guide for Hugo Fluid theme"
date: 2024-12-26
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# Configuration Guide

This page provides detailed information about configuring the Hugo Fluid theme.

## Basic Configuration

### Hugo Configuration (hugo.toml)

```toml
baseURL = "https://example.com/"
title = "My Blog"
theme = "hugo-theme-fluid"

# Default language
defaultContentLanguage = "en"
defaultContentLanguageInSubdir = false

# CJK language support
hasCJKLanguage = true

# Output formats
[outputs]
home = ["HTML", "RSS", "JSON"]
section = ["HTML", "RSS"]
taxonomy = ["HTML"]
term = ["HTML"]
```

### Theme Parameters (params.toml)

#### Global Configuration

```toml
# Site icons
favicon = "/img/fluid.png"
apple_touch_icon = "/img/fluid.png"

# Site description
description = "An elegant Material-Design theme for Hugo"
author = "Your Name"

# Code block configuration
[code]
copy_btn = true
[code.language]
enable = true
default = "TEXT"
[code.highlight]
enable = true
line_number = true
```

#### Theme Colors

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

#### Dark Mode

```toml
[dark_mode]
enable = true
default = "auto"  # auto | light | dark
```

## Page Configuration

### Homepage Configuration

```toml
[index]
banner_img = "/img/home.webp"
banner_img_height = 100
banner_mask_alpha = 0.3
[index.slogan]
enable = true
# Slogan text is set in language-specific configuration
[index.post_meta]
date = true
category = true
tag = true
```

### Post Page Configuration

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

## Feature Configuration

### Search Function

```toml
[search]
enable = true
path = "/index.json"
field = "post"  # post | page | all
content = true
```

### Navigation Bar

```toml
[navbar]
blog_title = "Hugo Fluid"
[navbar.ground_glass]
enable = true
px = 3
alpha = 0.7
```

### Footer

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

## Menu Configuration

### Main Menu (menus.en.toml)

Hugo Fluid theme supports both regular menu items and dropdown menus. Menu configuration files are located at `config/_default/menus.en.toml` (English), `menus.zh.toml` (Chinese), and `menus.tw.toml` (Traditional Chinese).

#### Regular Menu Items

```toml
[[main]]
name = "Home"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"

[[main]]
name = "Archives"
url = "/archives/"
weight = 2
pre = "iconfont icon-archive-fill"
```

#### Dropdown Menu Configuration

Dropdown menus require a parent menu item and multiple child menu items. The parent item uses `hasChildren = true`, and child items use the `parent` property to reference the parent menu.

```toml
# Parent menu item - Documentation dropdown
[[main]]
name = "Docs"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true  # Marks this as a dropdown menu

# Child menu item 1
[[main]]
name = "Quick Start"
url = "/docs/"
weight = 71
parent = "Docs"  # References parent menu name

# Child menu item 2
[[main]]
name = "Configuration"
url = "/docs/config/"
weight = 72
parent = "Docs"

# Child menu item 3
[[main]]
name = "Features"
url = "/docs/features/"
weight = 73
parent = "Docs"
```

#### Menu Parameters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `name` | Display name | `"Home"` |
| `url` | Link URL | `"/"` or `"https://example.com"` |
| `weight` | Sort order (lower numbers first) | `1`, `2`, `3` |
| `pre` | Icon class name | `"iconfont icon-home-fill"` |
| `post` | Link target | `"_blank"` (new tab) |
| `hasChildren` | Whether this is a dropdown parent | `true` |
| `parent` | Parent menu name (child items only) | `"Docs"` |

#### External Links

To link to external websites and open in new tab:

```toml
[[main]]
name = "GitHub"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 8
pre = "iconfont icon-github"
post = "_blank"  # Open in new tab
```

#### Dropdown with External Links

Dropdown menus can also contain external links:

```toml
# Parent menu item
[[main]]
name = "Links"
url = "#"
weight = 9
pre = "iconfont icon-link"
hasChildren = true

# External link child item
[[main]]
name = "Hugo Docs"
url = "https://gohugo.io/documentation/"
weight = 91
parent = "Links"
post = "_blank"

# Internal link child item
[[main]]
name = "Friend Links"
url = "/links/"
weight = 92
parent = "Links"
```

#### Weight Sorting Rules

- Main menu items: 1-10 (recommended interval: 1)
- Child menu items: Parent weight × 10 + sequence number
  - Example: Parent weight 7, child weights 71, 72, 73

#### Icon Configuration

The theme uses iconfont icon library. Common icon classes:

```toml
# Common icons
pre = "iconfont icon-home-fill"      # Home
pre = "iconfont icon-archive-fill"   # Archives
pre = "iconfont icon-category-fill"  # Categories
pre = "iconfont icon-tags-fill"      # Tags
pre = "iconfont icon-link-fill"      # Links
pre = "iconfont icon-user-fill"      # About
pre = "iconfont icon-books"          # Documentation
pre = "iconfont icon-github"         # GitHub
pre = "iconfont icon-search"         # Search
```

#### Complete Example

Here's a complete configuration example with both regular and dropdown menus:

```toml
# Regular menu items
[[main]]
name = "Home"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"

[[main]]
name = "Archives"
url = "/archives/"
weight = 2
pre = "iconfont icon-archive-fill"

[[main]]
name = "Categories"
url = "/categories/"
weight = 3
pre = "iconfont icon-category-fill"

[[main]]
name = "Tags"
url = "/tags/"
weight = 4
pre = "iconfont icon-tags-fill"

[[main]]
name = "Links"
url = "/links/"
weight = 5
pre = "iconfont icon-link-fill"

[[main]]
name = "About"
url = "/about/"
weight = 6
pre = "iconfont icon-user-fill"

# Documentation dropdown menu
[[main]]
name = "Docs"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "Quick Start"
url = "/docs/"
weight = 71
parent = "Docs"

[[main]]
name = "Configuration"
url = "/docs/config/"
weight = 72
parent = "Docs"

[[main]]
name = "Features"
url = "/docs/features/"
weight = 73
parent = "Docs"

# External links dropdown menu
[[main]]
name = "Related"
url = "#"
weight = 8
pre = "iconfont icon-link"
hasChildren = true

[[main]]
name = "Hugo Official"
url = "https://gohugo.io/"
weight = 81
parent = "Related"
post = "_blank"

[[main]]
name = "GitHub Repo"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 82
parent = "Related"
post = "_blank"
```

#### Multi-language Menus

Different language menu configuration files:

- `menus.en.toml` - English menu
- `menus.zh.toml` - Simplified Chinese menu
- `menus.tw.toml` - Traditional Chinese menu

Each language file has the same structure, only translate the `name` field:

```toml
# menus.zh.toml
[[main]]
name = "文档"           # Chinese name
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "快速开始"        # Chinese name
url = "/docs/"
weight = 71
parent = "文档"         # Corresponding Chinese parent name
```

## Multi-language Configuration

### Language Settings (languages.toml)

```toml
[en]
languageCode = "en"
languageName = "English"
weight = 1
title = "Hugo Fluid Blog"
contentDir = "content/en"

[zh]
languageCode = "zh-CN"
languageName = "简体中文"
weight = 2
title = "Hugo Fluid 博客"
contentDir = "content/zh"
```

For more configuration options, please refer to the [Features](/docs/features/) page.