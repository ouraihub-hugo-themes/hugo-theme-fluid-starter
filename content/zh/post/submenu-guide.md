---
title: "导航栏子菜单配置指南"
date: 2024-12-24
categories:
  - 教程
tags:
  - Hugo
  - 导航栏
  - 子菜单
  - 配置
description: "详细介绍如何在 Hugo Theme Fluid 中配置导航栏下拉子菜单"
index_img: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800&h=400&fit=crop"
---

Hugo Theme Fluid 支持导航栏下拉子菜单功能，让你可以更好地组织导航链接。本文将详细介绍如何配置和使用子菜单功能。

<!--more-->

## 功能特性

- 📂 支持多级下拉菜单
- 🖱️ 桌面端悬浮显示
- 📱 移动端点击展开
- 🎨 平滑动画效果
- ♿ 完整的无障碍支持

## 配置方法

### 基本配置

在 `config/_default/menus.toml` 中配置子菜单：

```toml
# 父菜单项（不需要 url，只需要 identifier）
[[main]]
name = "文档"
weight = 7
pre = "iconfont icon-books"
identifier = "docs"

# 子菜单项（使用 parent 指向父菜单的 identifier）
[[main]]
name = "配置指南"
url = "https://hexo.fluid-dev.com/docs/guide/"
weight = 1
parent = "docs"

[[main]]
name = "图标用法"
url = "https://hexo.fluid-dev.com/docs/icon/"
weight = 2
parent = "docs"
```

### 配置说明

| 参数 | 说明 | 示例 |
|------|------|------|
| `name` | 菜单显示名称 | `"文档"` |
| `url` | 链接地址（父菜单可省略） | `"/docs/"` |
| `weight` | 排序权重 | `7` |
| `pre` | 图标类名 | `"iconfont icon-books"` |
| `identifier` | 父菜单标识符 | `"docs"` |
| `parent` | 子菜单指向的父菜单标识符 | `"docs"` |
| `post` | 链接打开方式 | `"_blank"` |

### 完整示例

```toml
# Hugo Theme Fluid - Menu Configuration

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

# 带子菜单的菜单项
[[main]]
name = "分类"
weight = 3
pre = "iconfont icon-category-fill"
identifier = "categories"

[[main]]
name = "技术"
url = "/categories/技术/"
weight = 1
parent = "categories"

[[main]]
name = "生活"
url = "/categories/生活/"
weight = 2
parent = "categories"

[[main]]
name = "教程"
url = "/categories/教程/"
weight = 3
parent = "categories"

# 外部链接子菜单
[[main]]
name = "资源"
weight = 8
pre = "iconfont icon-link"
identifier = "resources"

[[main]]
name = "Hugo 官网"
url = "https://gohugo.io/"
weight = 1
parent = "resources"
post = "_blank"

[[main]]
name = "Fluid 文档"
url = "https://hexo.fluid-dev.com/docs/"
weight = 2
parent = "resources"
post = "_blank"
```

## 交互行为

### 桌面端（≥992px）

- **悬浮触发** - 鼠标悬浮在父菜单上时自动显示下拉菜单
- **点击跳转** - 点击子菜单项跳转到对应链接
- **自动隐藏** - 鼠标移开后下拉菜单自动隐藏

### 移动端（<992px）

- **点击展开** - 点击父菜单项展开/收起下拉菜单
- **箭头指示** - 下拉箭头旋转指示展开状态
- **点击跳转** - 点击子菜单项跳转到对应链接
- **自动收起** - 点击其他区域或切换菜单时自动收起

## 样式自定义

### CSS 变量

```css
/* 下拉菜单背景 */
.navbar .dropdown-menu {
  background-color: rgb(0 0 0 / 30%);
}

/* 下拉菜单项颜色 */
.navbar .dropdown-item {
  color: var(--navbar-text-color);
}

/* 悬浮效果 */
.navbar .dropdown-item:hover {
  color: var(--link-hover-color);
  background-color: rgb(0 0 0 / 10%);
}
```

### 移动端样式

```css
@media (width < 992px) {
  .navbar .dropdown-menu {
    background-color: rgb(0 0 0 / 20%);
  }

  .navbar .dropdown-arrow.open {
    transform: rotate(180deg);
  }
}
```

## 无障碍支持

子菜单组件包含完整的无障碍支持：

- `role="button"` - 标识可点击元素
- `aria-haspopup="true"` - 标识有弹出菜单
- `aria-expanded` - 动态更新展开状态
- `aria-labelledby` - 关联菜单标签

## 常见问题

### Q: 如何让父菜单也可点击跳转？

父菜单默认不可点击（`href="javascript:;"`），如果需要点击跳转，可以添加 `url` 参数，但这会影响移动端的展开体验。

### Q: 子菜单可以嵌套吗？

目前只支持一级子菜单，不支持多级嵌套。

### Q: 如何在新窗口打开链接？

使用 `post = "_blank"` 参数：

```toml
[[main]]
name = "外部链接"
url = "https://example.com"
parent = "resources"
post = "_blank"
```

### Q: 如何添加子菜单图标？

使用 `pre` 参数添加图标类名：

```toml
[[main]]
name = "配置指南"
url = "/docs/guide/"
parent = "docs"
pre = "iconfont icon-book"
```

## 最佳实践

1. **合理分组** - 将相关链接组织在同一个子菜单下
2. **控制数量** - 每个子菜单建议不超过 5-7 个项目
3. **清晰命名** - 使用简洁明了的菜单名称
4. **图标辅助** - 适当使用图标增强可识别性
5. **移动优先** - 测试移动端的展开/收起体验

## 总结

导航栏子菜单功能让你可以更好地组织网站导航，提供更清晰的信息架构。通过简单的配置，即可实现：

- 多级菜单结构
- 响应式交互
- 平滑动画效果
- 完整的无障碍支持

希望这篇教程能帮助你配置出理想的导航菜单！
