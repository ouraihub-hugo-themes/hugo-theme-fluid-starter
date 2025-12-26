---
title: "文档"
description: "Hugo Fluid 主题使用文档"
date: 2024-12-26
layout: "docs"
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# Hugo Fluid 主题文档

欢迎使用 Hugo Fluid 主题！这里是主题的使用文档和指南。

## 快速开始

### 安装主题

#### 方法一：Git Submodule

```bash
git submodule add https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist.git themes/hugo-theme-fluid
```

#### 方法二：Hugo Modules

```bash
hugo mod init github.com/your-username/your-blog
```

然后在 `hugo.toml` 中添加：

```toml
[module]
[[module.imports]]
path = "github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
```

### 基础配置

在 `config/_default/` 目录下创建以下配置文件：

- `hugo.toml` - Hugo 基础配置
- `params.toml` - 主题参数配置
- `menus.toml` - 菜单配置
- `languages.toml` - 多语言配置

## 主要功能

### 🎨 主题特性

- **Material Design 风格**：优雅的 Material Design 设计语言
- **响应式设计**：完美适配桌面、平板、手机等所有设备
- **深色模式**：支持自动/手动切换深色/浅色主题
- **多语言支持**：内置中文、英文、繁体中文等多种语言
- **快速搜索**：基于 Pagefind 的全文搜索功能

### 📝 内容功能

- **文章管理**：支持分类、标签、归档等内容组织方式
- **代码高亮**：支持多种编程语言的语法高亮
- **数学公式**：支持 LaTeX 数学公式渲染
- **流程图**：支持 Mermaid 流程图和图表
- **图片优化**：图片懒加载和放大查看功能

### 🔧 技术特性

- **现代化技术栈**：TypeScript + Tailwind CSS + Hugo
- **高性能**：优化的构建流程和资源加载
- **SEO 友好**：完整的 SEO 优化和 Open Graph 支持
- **评论系统**：支持多种评论系统集成

## 配置指南

详细的配置说明请参考各个功能页面：

- [基础配置](./basic-config/)
- [主题配置](./theme-config/)
- [菜单配置](./menu-config/)
- [多语言配置](./i18n-config/)
- [评论系统](./comments/)
- [搜索功能](./search/)

## 常见问题

### 如何自定义颜色？

在 `params.toml` 中的 `[color]` 部分可以自定义主题颜色：

```toml
[color]
body_bg_color = "#eee"
navbar_bg_color = "#2f4154"
text_color = "#3c4858"
# ... 更多颜色配置
```

### 如何添加自定义页面？

使用 Hugo 命令创建新页面：

```bash
hugo new page/my-page.md
```

### 如何启用评论功能？

在 `params.toml` 中配置评论系统：

```toml
[post.comments]
enable = true
type = "giscus"  # 或其他支持的评论系统
```

## 获取帮助

- **GitHub Issues**: [提交问题和建议](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/issues)
- **讨论区**: [参与社区讨论](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/discussions)
- **文档**: [查看完整文档](https://hexo.fluid-dev.com/docs/)

## 贡献

欢迎为 Hugo Fluid 主题贡献代码和文档！请查看 [贡献指南](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist/blob/master/CONTRIBUTING.md)。