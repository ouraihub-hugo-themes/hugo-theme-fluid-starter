---
title: "Dropdown Menu Configuration Guide"
description: "Detailed guide on how to configure dropdown menus in Hugo Fluid theme"
date: 2024-12-26
banner_img: "/img/default.png"
banner_img_height: 60
banner_mask_alpha: 0.3
---

# Dropdown Menu Configuration Guide

This guide provides detailed instructions on how to configure dropdown menus in the Hugo Fluid theme, including both regular menu items and multi-level dropdown menus.

## Menu Configuration File Locations

Hugo Fluid theme menu configuration files are located in the `config/_default/` directory:

```
config/_default/
├── menus.zh.toml    # Simplified Chinese menu
├── menus.en.toml    # English menu
└── menus.tw.toml    # Traditional Chinese menu
```

## Basic Menu Configuration

### Regular Menu Items

Regular menu items are the most basic menu type that directly link to pages:

```toml
[[main]]
name = "Home"
url = "/"
weight = 1
pre = "iconfont icon-home-fill"
```

### Menu Parameter Description

| Parameter | Required | Description | Example |
|-----------|----------|-------------|---------|
| `name` | ✅ | Menu display name | `"Home"` |
| `url` | ✅ | Link address | `"/"` or `"https://example.com"` |
| `weight` | ✅ | Sort weight (smaller numbers appear first) | `1`, `2`, `3` |
| `pre` | ❌ | Icon class name | `"iconfont icon-home-fill"` |
| `post` | ❌ | Link opening method | `"_blank"` (new tab) |
| `hasChildren` | ❌ | Whether it's a dropdown menu parent | `true` |
| `parent` | ❌ | Parent menu name (for child items only) | `"Docs"` |

## Dropdown Menu Configuration

### Basic Dropdown Menu

A dropdown menu consists of one parent menu item and multiple child menu items:

```toml
# Parent menu item - Docs dropdown menu
[[main]]
name = "Docs"
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true  # Identifies this as a dropdown menu

# Child menu item 1
[[main]]
name = "Quick Start"
url = "/docs/"
weight = 71
parent = "Docs"  # Points to parent menu's name

# Child menu item 2
[[main]]
name = "Configuration Guide"
url = "/docs/config/"
weight = 72
parent = "Docs"

# Child menu item 3
[[main]]
name = "Theme Features"
url = "/docs/features/"
weight = 73
parent = "Docs"
```

### Configuration Key Points

1. **Parent Menu Item**:
   - Must set `hasChildren = true`
   - Can have its own URL (navigates when parent menu is clicked)
   - Can also set `url = "#"` (serves only as dropdown container)

2. **Child Menu Items**:
   - Must set `parent` attribute with the value of parent menu's `name`
   - Weight should use parent menu weight × 10 + sequence number

### Weight Sorting Rules

To maintain clear menu order, use the following weight rules:

- **Main menu item weights**: 1-10 (interval of 1)
- **Child menu item weights**: parent menu weight × 10 + sequence number

Example:
```toml
# Parent menu weight is 7
[[main]]
name = "Docs"
weight = 7
hasChildren = true

# Child menu weights are 71, 72, 73
[[main]]
name = "Quick Start"
weight = 71
parent = "Docs"

[[main]]
name = "Configuration Guide"
weight = 72
parent = "Docs"

[[main]]
name = "Theme Features"
weight = 73
parent = "Docs"
```

## External Link Dropdown Menu

Dropdown menus can also contain external links:

```toml
# Parent menu item
[[main]]
name = "Related Links"
url = "#"  # No navigation, serves only as dropdown container
weight = 8
pre = "iconfont icon-link"
hasChildren = true

# External link child item
[[main]]
name = "Hugo Official"
url = "https://gohugo.io/"
weight = 81
parent = "Related Links"
post = "_blank"  # Open in new tab

# Internal link child item
[[main]]
name = "GitHub Repository"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 82
parent = "Related Links"
post = "_blank"
```

## Icon Configuration

Hugo Fluid theme uses the iconfont icon library. Here are commonly used icons:

```toml
# Common icon class names
pre = "iconfont icon-home-fill"      # Home
pre = "iconfont icon-archive-fill"   # Archive
pre = "iconfont icon-category-fill"  # Category
pre = "iconfont icon-tags-fill"      # Tags
pre = "iconfont icon-link-fill"      # Links
pre = "iconfont icon-user-fill"      # About
pre = "iconfont icon-books"          # Docs
pre = "iconfont icon-github"         # GitHub
pre = "iconfont icon-search"         # Search
pre = "iconfont icon-link"           # Link
```

## Multi-language Menu Configuration

Different language menu configuration files have the same structure, only need to translate the `name` field:

### Chinese Menu (menus.zh.toml)

```toml
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

### English Menu (menus.en.toml)

```toml
[[main]]
name = "Docs"           # English name
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "Quick Start"    # English name
url = "/docs/"
weight = 71
parent = "Docs"         # Corresponding English parent menu name
```

### Traditional Chinese Menu (menus.tw.toml)

```toml
[[main]]
name = "文檔"           # Traditional Chinese name
url = "/docs/"
weight = 7
pre = "iconfont icon-books"
hasChildren = true

[[main]]
name = "快速開始"       # Traditional Chinese name
url = "/docs/"
weight = 71
parent = "文檔"         # Corresponding Traditional Chinese parent menu name
```

## Complete Configuration Example

Here's a complete configuration example including both regular menus and dropdown menus:

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

# Docs dropdown menu
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
name = "Configuration Guide"
url = "/docs/config/"
weight = 72
parent = "Docs"

[[main]]
name = "Theme Features"
url = "/docs/features/"
weight = 73
parent = "Docs"

[[main]]
name = "Dropdown Menu Config"
url = "/docs/dropdown-menu/"
weight = 74
parent = "Docs"

# External links dropdown menu
[[main]]
name = "Related Links"
url = "#"
weight = 8
pre = "iconfont icon-link"
hasChildren = true

[[main]]
name = "Hugo Official"
url = "https://gohugo.io/"
weight = 81
parent = "Related Links"
post = "_blank"

[[main]]
name = "GitHub Repository"
url = "https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-dist"
weight = 82
parent = "Related Links"
post = "_blank"
```

## Common Issues

### Q: Dropdown menu not showing?

A: Check the following:
1. Is `hasChildren = true` set for the parent menu item?
2. Is the `parent` attribute correctly set for child menu items?
3. Does the `parent` value exactly match the parent menu's `name` (case-sensitive)?

### Q: Menu order is wrong?

A: Check `weight` settings:
- Smaller numbers appear first
- Ensure no duplicate weights
- Child menu weights should be within parent menu weight range

### Q: How to add separators?

A: Hugo Fluid theme doesn't currently support menu separators. Use weight intervals for visual grouping.

### Q: Can I have multi-level dropdown menus?

A: Currently the theme supports two-level dropdown menus (parent + child), not deeper nesting.

### Q: How to hide a menu item?

A: Simply delete or comment out the corresponding menu configuration:

```toml
# [[main]]
# name = "Hidden Menu"
# url = "/hidden/"
# weight = 10
```

## Testing Menu Configuration

After configuration, test using the following methods:

1. **Start development server**:
   ```bash
   pnpm dev
   ```

2. **Visit website**:
   Open `http://localhost:1313` to view menu effects

3. **Check multi-language**:
   Switch different languages to verify menu displays correctly

4. **Test responsive**:
   Test menu responsiveness on different device sizes

## Summary

Key points for dropdown menu configuration:

1. **Parent menu item**: Set `hasChildren = true`
2. **Child menu items**: Set correct `parent` attribute
3. **Weight sorting**: Use reasonable weight rules
4. **Multi-language support**: Create corresponding menu files for each language
5. **Icon configuration**: Use iconfont icon class names

Through proper dropdown menu configuration, you can make website navigation clearer and more user-friendly.