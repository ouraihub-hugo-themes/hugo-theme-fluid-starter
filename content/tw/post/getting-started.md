---
title: "Hugo Fluid 主題使用指南"
date: 2024-01-15
categories: ["教程"]
tags: ["Hugo", "Fluid", "主題"]
description: "這是一篇關於如何使用 Hugo Fluid 主題的詳細指南。"
index_img: "https://images.unsplash.com/photo-1499750310107-5fef28a66643?w=800&h=400&fit=crop"
---

## 簡介

Hugo Fluid 是一個基於 hexo-theme-fluid 改寫的 Material Design 風格 Hugo 部落格主題。

<!--more-->

## 安裝

### 方式一：Git Submodule

```bash
git submodule add https://github.com/fluid-dev/hugo-theme-fluid.git themes/hugo-theme-fluid
```

### 方式二：Hugo Modules

```bash
hugo mod init github.com/your-username/your-blog
```

然後在 `hugo.toml` 中添加：

```toml
[module]
[[module.imports]]
path = "github.com/fluid-dev/hugo-theme-fluid"
```

## 配置

在 `config/_default/params.toml` 中配置主題參數：

```toml
# 暗色模式
[dark_mode]
enable = true
default = "auto"

# 導航欄
[navbar]
blog_title = "My Blog"
```

## 特性

### 深色模式

主題支援三種模式：
- `auto`: 跟隨系統設定
- `light`: 始終淺色
- `dark`: 始終深色

### 程式碼高亮

支援多種程式語言的語法高亮：

```javascript
function hello() {
  console.log("Hello, Fluid!");
}
```

```python
def hello():
    print("Hello, Fluid!")
```

### 數學公式

支援 LaTeX 數學公式（需要在 front-matter 中啟用）：

$
E = mc^2
$

## 總結

Hugo Fluid 主題提供了豐富的功能和優雅的設計，非常適合技術部落格使用。
