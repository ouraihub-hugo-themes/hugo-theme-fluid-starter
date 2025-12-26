---
title: "配置指南"
description: "Hugo Fluid 主题详细配置指南"
date: 2024-12-26
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# 配置指南

本页面详细介绍 Hugo Fluid 主题的各项配置选项。

## 基础配置

### Hugo 配置 (hugo.toml)

```toml
baseURL = "https://example.com/"
title = "我的博客"
theme = "hugo-theme-fluid"

# 默认语言
defaultContentLanguage = "zh"
defaultContentLanguageInSubdir = false

# CJK 语言支持
hasCJKLanguage = true

# 输出格式
[outputs]
home = ["HTML", "RSS", "JSON"]
section = ["HTML", "RSS"]
taxonomy = ["HTML"]
term = ["HTML"]
```

### 主题参数 (params.toml)

#### 全局配置

```toml
# 网站图标
favicon = "/img/fluid.png"
apple_touch_icon = "/img/fluid.png"

# 站点描述
description = "一个优雅的 Material Design 风格博客"
author = "Your Name"

# 代码块配置
[code]
copy_btn = true
[code.language]
enable = true
default = "TEXT"
[code.highlight]
enable = true
line_number = true
```

#### 主题颜色

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

## 页面配置

### 首页配置

```toml
[index]
banner_img = "/img/home.webp"
banner_img_height = 100
banner_mask_alpha = 0.3
[index.slogan]
enable = true
# 标语文本在语言特定配置中设置
[index.post_meta]
date = true
category = true
tag = true
```

### 文章页配置

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

### 归档页配置

```toml
[archive]
banner_img = "/img/archive.webp"
banner_img_height = 60
banner_mask_alpha = 0.3
```

### 分类页配置

```toml
[category]
enable = true
banner_img = "/img/category.webp"
banner_img_height = 60
banner_mask_alpha = 0.3
order_by = "-length"  # length | name | -length | -name
collapse_depth = 0
```

### 标签页配置

```toml
[tag]
enable = true
banner_img = "/img/tag.webp"
banner_img_height = 80
banner_mask_alpha = 0.3
[tag.tagcloud]
min_font = 15
max_font = 30
unit = "px"
start_color = "#BBBBEE"
end_color = "#337ab7"
```

## 功能配置

### 搜索功能

```toml
[search]
enable = true
path = "/index.json"
field = "post"  # post | page | all
content = true
```

### 导航栏

```toml
[navbar]
blog_title = "Hugo Fluid"
[navbar.ground_glass]
enable = true
px = 3
alpha = 0.7
```

### 页脚

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

[footer.beian]
enable = true
icp_text = "京ICP证123456号"
police_text = "京公网安备12345678号"
police_code = "12345678"
```

### 图片懒加载

```toml
[lazyload]
enable = true
loading_img = "/img/loading.gif"
onlypost = false
offset_factor = 2
```

### 数学公式

```toml
[post.math]
enable = true
specific = true
engine = "mathjax"  # mathjax | katex
```

### 流程图

```toml
[post.mermaid]
enable = true
specific = true
[post.mermaid.options]
theme = "default"
```

## 菜单配置

### 主菜单 (menus.zh.toml)

Hugo Fluid 主题支持普通菜单项和下拉菜单。菜单配置文件位于 `config/_default/menus.zh.toml`（中文）、`menus.en.toml`（英文）、`menus.tw.toml`（繁体中文）。

#### 普通菜单项

```toml
[[main]]
name = "首页"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"

[[main]]
name = "归档"
url = "/archives/"
weight = 2
pre = "iconfont icon-archive-fill"
```

#### 下拉菜单配置

下拉菜单需要一个父菜单项和多个子菜单项。父菜单项使用 `hasChildren = true` 标识，子菜单项使用 `parent` 属性指向父菜单。

```toml
# 父菜单项 - 文档下拉菜单
[[main]]
name = "文档"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true  # 标识这是一个下拉菜单

# 子菜单项 1
[[main]]
name = "快速开始"
url = "/docs/"
weight = 71
parent = "文档"  # 指向父菜单的 name

# 子菜单项 2
[[main]]
name = "配置指南"
url = "/docs/config/"
weight = 72
parent = "文档"

# 子菜单项 3
[[main]]
name = "主题特性"
url = "/docs/features/"
weight = 73
parent = "文档"
```

#### 菜单参数说明

| 参数 | 说明 | 示例 |
|------|------|------|
| `name` | 菜单显示名称 | `"首页"` |
| `url` | 链接地址 | `"/"` 或 `"https://example.com"` |
| `weight` | 排序权重（数字越小越靠前） | `1`, `2`, `3` |
| `pre` | 图标类名 | `"iconfont icon-home-fill"` |
| `post` | 链接打开方式 | `"_blank"`（新标签页） |
| `hasChildren` | 是否为下拉菜单父项 | `true` |
| `parent` | 父菜单名称（仅子菜单项使用） | `"文档"` |

#### 外部链接配置

如果要链接到外部网站并在新标签页打开：

```toml
[[main]]
name = "GitHub"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 8
pre = "iconfont icon-github"
post = "_blank"  # 在新标签页打开
```

#### 下拉菜单外部链接

下拉菜单也可以包含外部链接：

```toml
# 父菜单项
[[main]]
name = "链接"
url = "#"
weight = 9
pre = "iconfont icon-link"
hasChildren = true

# 外部链接子项
[[main]]
name = "官方文档"
url = "https://gohugo.io/documentation/"
weight = 91
parent = "链接"
post = "_blank"

# 内部链接子项
[[main]]
name = "友情链接"
url = "/links/"
weight = 92
parent = "链接"
```

#### 权重排序规则

- 主菜单项权重：1-10（推荐间隔为 1）
- 子菜单项权重：父菜单权重 × 10 + 序号
  - 例如：父菜单权重为 7，子菜单权重为 71、72、73

#### 图标配置

主题使用 iconfont 图标库，常用图标类名：

```toml
# 常用图标
pre = "iconfont icon-home-fill"      # 首页
pre = "iconfont icon-archive-fill"   # 归档
pre = "iconfont icon-category-fill"  # 分类
pre = "iconfont icon-tags-fill"      # 标签
pre = "iconfont icon-link-fill"      # 友链
pre = "iconfont icon-user-fill"      # 关于
pre = "iconfont icon-books"          # 文档
pre = "iconfont icon-github"         # GitHub
pre = "iconfont icon-search"         # 搜索
```

#### 完整示例

以下是一个包含普通菜单和下拉菜单的完整配置示例：

```toml
# 普通菜单项
[[main]]
name = "首页"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"

[[main]]
name = "归档"
url = "/archives/"
weight = 2
pre = "iconfont icon-archive-fill"

[[main]]
name = "分类"
url = "/categories/"
weight = 3
pre = "iconfont icon-category-fill"

[[main]]
name = "标签"
url = "/tags/"
weight = 4
pre = "iconfont icon-tags-fill"

[[main]]
name = "友链"
url = "/links/"
weight = 5
pre = "iconfont icon-link-fill"

[[main]]
name = "关于"
url = "/about/"
weight = 6
pre = "iconfont icon-user-fill"

# 文档下拉菜单
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

[[main]]
name = "配置指南"
url = "/docs/config/"
weight = 72
parent = "文档"

[[main]]
name = "主题特性"
url = "/docs/features/"
weight = 73
parent = "文档"

# 外部链接下拉菜单
[[main]]
name = "相关链接"
url = "#"
weight = 8
pre = "iconfont icon-link"
hasChildren = true

[[main]]
name = "Hugo 官网"
url = "https://gohugo.io/"
weight = 81
parent = "相关链接"
post = "_blank"

[[main]]
name = "GitHub 仓库"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 82
parent = "相关链接"
post = "_blank"
```

#### 多语言菜单

不同语言的菜单配置文件：

- `menus.zh.toml` - 简体中文菜单
- `menus.en.toml` - 英文菜单  
- `menus.tw.toml` - 繁体中文菜单

每个语言文件的结构相同，只需要翻译 `name` 字段：

```toml
# menus.en.toml
[[main]]
name = "Docs"           # 英文名称
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "Quick Start"    # 英文名称
url = "/docs/"
weight = 71
parent = "Docs"         # 对应英文父菜单名
```

# 下拉菜单示例
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

## 多语言配置

### 语言设置 (languages.toml)

```toml
[zh]
languageCode = "zh-CN"
languageName = "简体中文"
weight = 1
title = "Hugo Fluid 博客"
contentDir = "content/zh"

[en]
languageCode = "en"
languageName = "English"
weight = 2
title = "Hugo Fluid Blog"
contentDir = "content/en"
```

### 语言特定参数

创建 `params.zh.toml`：

```toml
[index.slogan]
text = "一个优雅的 Material Design 风格 Hugo 主题"
```

创建 `params.en.toml`：

```toml
[index.slogan]
text = "An elegant Material-Design theme for Hugo"
```

## 评论系统配置

### Giscus

```toml
[post.comments]
enable = true
type = "giscus"

[giscus]
repo = "your-username/your-repo"
repo-id = "your-repo-id"
category = "Announcements"
category-id = "your-category-id"
mapping = "pathname"
theme-light = "light"
theme-dark = "dark"
lang = "zh-CN"
```

### Utterances

```toml
[post.comments]
enable = true
type = "utterances"

[utterances]
repo = "your-username/your-repo"
issue_term = "pathname"
label = "utterances"
theme = "github-light"
theme_dark = "github-dark"
```

## 高级配置

### 自定义 CSS

```toml
custom_css = [
  "/css/custom.css"
]
```

### 自定义 JavaScript

```toml
custom_js = [
  "/js/custom.js"
]
```

### Open Graph

```toml
[open_graph]
enable = true
twitter_card = "summary_large_image"
```

### 网站统计

```toml
[footer.statistics]
enable = true
source = "busuanzi"
# 自定义格式
pv_format = "总访问量 {} 次"
uv_format = "总访客数 {} 人"
```

## 常见问题

### 如何自定义 Banner 图片？

在页面的 Front Matter 中设置：

```yaml
---
title: "我的文章"
banner_img: "/img/my-banner.jpg"
banner_img_height: 70
banner_mask_alpha: 0.3
---
```

### 如何禁用某个页面的功能？

在页面的 Front Matter 中设置：

```yaml
---
title: "我的文章"
toc: false          # 禁用目录
comments: false     # 禁用评论
copyright: false    # 禁用版权声明
---
```

### 如何添加自定义页面？

1. 创建页面文件：
```bash
hugo new page/my-page.md
```

2. 在菜单中添加链接：
```toml
[[main]]
name = "我的页面"
url = "/page/my-page/"
weight = 10
```

更多配置选项请参考 [主题特性](/docs/features/) 页面。