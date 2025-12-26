---
title: "Hugo Fluid Theme Guide"
date: 2024-01-15
categories: ["Tutorial"]
tags: ["Hugo", "Fluid", "Theme"]
description: "A detailed guide on how to use the Hugo Fluid theme."
index_img: "https://images.unsplash.com/photo-1499750310107-5fef28a66643?w=800&h=400&fit=crop"
---

## Introduction

Hugo Fluid is a Material Design style Hugo blog theme ported from hexo-theme-fluid.

<!--more-->

## Installation

### Method 1: Git Submodule

```bash
git submodule add https://github.com/fluid-dev/hugo-theme-fluid.git themes/hugo-theme-fluid
```

### Method 2: Hugo Modules

```bash
hugo mod init github.com/your-username/your-blog
```

Then add to `hugo.toml`:

```toml
[module]
[[module.imports]]
path = "github.com/fluid-dev/hugo-theme-fluid"
```

## Configuration

Configure theme parameters in `config/_default/params.toml`:

```toml
# Dark mode
[dark_mode]
enable = true
default = "auto"

# Navbar
[navbar]
blog_title = "My Blog"
```

## Features

### Dark Mode

The theme supports three modes:
- `auto`: Follow system settings
- `light`: Always light
- `dark`: Always dark

### Code Highlighting

Supports syntax highlighting for multiple programming languages:

```javascript
function hello() {
  console.log("Hello, Fluid!");
}
```

```python
def hello():
    print("Hello, Fluid!")
```

### Math Formulas

Supports LaTeX math formulas (enable in front-matter):

$
E = mc^2
$

## Summary

Hugo Fluid theme provides rich features and elegant design, perfect for technical blogs.
