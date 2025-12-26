---
title: "Documentation"
description: "Hugo Fluid theme documentation and guides"
date: 2024-12-26
layout: "docs"
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# Hugo Fluid Theme Documentation

Welcome to Hugo Fluid theme! Here you'll find comprehensive documentation and guides for using the theme.

## Quick Start

### Installation

#### Method 1: Git Submodule

```bash
git submodule add https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist.git themes/hugo-theme-fluid
```

#### Method 2: Hugo Modules

```bash
hugo mod init github.com/your-username/your-blog
```

Then add to `hugo.toml`:

```toml
[module]
[[module.imports]]
path = "github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
```

### Basic Configuration

Create the following configuration files in `config/_default/` directory:

- `hugo.toml` - Hugo basic configuration
- `params.toml` - Theme parameters
- `menus.toml` - Menu configuration
- `languages.toml` - Multi-language configuration

## Key Features

### 🎨 Theme Features

- **Material Design**: Elegant Material Design language
- **Responsive Design**: Perfect adaptation for desktop, tablet, mobile devices
- **Dark Mode**: Support automatic/manual dark/light theme switching
- **Multi-language**: Built-in Chinese, English, Traditional Chinese and more
- **Fast Search**: Full-text search powered by Pagefind

### 📝 Content Features

- **Content Management**: Support categories, tags, archives and more
- **Code Highlighting**: Syntax highlighting for multiple programming languages
- **Math Formulas**: LaTeX math formula rendering support
- **Diagrams**: Mermaid flowcharts and diagrams support
- **Image Optimization**: Image lazy loading and zoom functionality

### 🔧 Technical Features

- **Modern Tech Stack**: TypeScript + Tailwind CSS + Hugo
- **High Performance**: Optimized build process and resource loading
- **SEO Friendly**: Complete SEO optimization and Open Graph support
- **Comment Systems**: Support for multiple comment system integrations

## Configuration Guide

For detailed configuration instructions, please refer to individual feature pages:

- [Basic Configuration](./basic-config/)
- [Theme Configuration](./theme-config/)
- [Menu Configuration](./menu-config/)
- [Multi-language Configuration](./i18n-config/)
- [Comment Systems](./comments/)
- [Search Functionality](./search/)

## FAQ

### How to customize colors?

You can customize theme colors in the `[color]` section of `params.toml`:

```toml
[color]
body_bg_color = "#eee"
navbar_bg_color = "#2f4154"
text_color = "#3c4858"
# ... more color configurations
```

### How to add custom pages?

Create new pages using Hugo command:

```bash
hugo new page/my-page.md
```

### How to enable comments?

Configure comment system in `params.toml`:

```toml
[post.comments]
enable = true
type = "giscus"  # or other supported comment systems
```

## Getting Help

- **GitHub Issues**: [Submit issues and suggestions](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/issues)
- **Discussions**: [Join community discussions](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/discussions)
- **Documentation**: [View complete documentation](https://hexo.fluid-dev.com/docs/)

## Contributing

Contributions to Hugo Fluid theme are welcome! Please check the [Contributing Guide](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/blob/master/CONTRIBUTING.md).