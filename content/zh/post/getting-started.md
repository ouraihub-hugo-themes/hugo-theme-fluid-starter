---
title: "Hugo Fluid 主题使用指南"
date: 2024-01-15
categories: ["教程"]
tags: ["Hugo", "Fluid", "主题"]
description: "这是一篇关于如何使用 Hugo Fluid 主题的详细指南。"
index_img: "https://images.unsplash.com/photo-1499750310107-5fef28a66643?w=800&h=400&fit=crop"
---

## 简介

Hugo Fluid 是一个基于 hexo-theme-fluid 改写的 Material Design 风格 Hugo 博客主题。

<!--more-->

## 安装

### 方式一：Git Submodule

```bash
git submodule add https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist.git themes/hugo-theme-fluid
```

### 方式二：Hugo Modules

```bash
hugo mod init github.com/your-username/your-blog
```

然后在 `hugo.toml` 中添加：

```toml
[module]
[[module.imports]]
path = "github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
```

## 配置

在 `config/_default/params.toml` 中配置主题参数：

```toml
# 暗色模式
[dark_mode]
enable = true
default = "auto"

# 导航栏
[navbar]
blog_title = "My Blog"
```

## 特性

### 深色模式

主题支持三种模式：
- `auto`: 跟随系统设置
- `light`: 始终浅色
- `dark`: 始终深色

### 代码高亮

支持多种编程语言的语法高亮：

```javascript
function hello() {
  console.log("Hello, Fluid!");
}
```

```python
def hello():
    print("Hello, Fluid!")
```

### 数学公式

支持 LaTeX 数学公式（需要在 front-matter 中启用）：

$$
E = mc^2
$$

## 总结

Hugo Fluid 主题提供了丰富的功能和优雅的设计，非常适合技术博客使用。
