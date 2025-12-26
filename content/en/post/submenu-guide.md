---
title: "Navigation Bar Submenu Configuration Guide"
date: 2024-12-24
categories:
  - Tutorial
tags:
  - Hugo
  - Navigation
  - Submenu
  - Configuration
description: "A detailed guide on how to configure navigation bar dropdown submenus in Hugo Theme Fluid"
index_img: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800&h=400&fit=crop"
---

Hugo Theme Fluid supports navigation bar dropdown submenu functionality, allowing you to better organize navigation links. This article provides a detailed guide on how to configure and use the submenu feature.

<!--more-->

## Features

- 📂 Support for multi-level dropdown menus
- 🖱️ Hover display on desktop
- 📱 Click to expand on mobile
- 🎨 Smooth animation effects
- ♿ Full accessibility support

## Configuration Method

### Basic Configuration

Configure submenus in `config/_default/menus.toml`:

```toml
# Parent menu item (no url needed, only identifier)
[[main]]
name = "Docs"
weight = 7
pre = "iconfont icon-books"
identifier = "docs"

# Child menu items (use parent to point to parent's identifier)
[[main]]
name = "Configuration Guide"
url = "https://hexo.fluid-dev.com/docs/guide/"
weight = 1
parent = "docs"

[[main]]
name = "Icon Usage"
url = "https://hexo.fluid-dev.com/docs/icon/"
weight = 2
parent = "docs"
```

### Configuration Description

| Parameter | Description | Example |
|-----------|-------------|---------|
| `name` | Menu display name | `"Docs"` |
| `url` | Link URL (can be omitted for parent) | `"/docs/"` |
| `weight` | Sort weight | `7` |
| `pre` | Icon class name | `"iconfont icon-books"` |
| `identifier` | Parent menu identifier | `"docs"` |
| `parent` | Child menu's parent identifier | `"docs"` |
| `post` | Link open method | `"_blank"` |

### Complete Example

```toml
# Hugo Theme Fluid - Menu Configuration

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

# Menu item with submenu
[[main]]
name = "Categories"
weight = 3
pre = "iconfont icon-category-fill"
identifier = "categories"

[[main]]
name = "Tech"
url = "/categories/tech/"
weight = 1
parent = "categories"

[[main]]
name = "Life"
url = "/categories/life/"
weight = 2
parent = "categories"

[[main]]
name = "Tutorial"
url = "/categories/tutorial/"
weight = 3
parent = "categories"

# External link submenu
[[main]]
name = "Resources"
weight = 8
pre = "iconfont icon-link"
identifier = "resources"

[[main]]
name = "Hugo Official"
url = "https://gohugo.io/"
weight = 1
parent = "resources"
post = "_blank"

[[main]]
name = "Fluid Docs"
url = "https://hexo.fluid-dev.com/docs/"
weight = 2
parent = "resources"
post = "_blank"
```

## Interaction Behavior

### Desktop (≥992px)

- **Hover trigger** - Dropdown menu automatically shows when hovering over parent menu
- **Click to navigate** - Click submenu item to navigate to corresponding link
- **Auto hide** - Dropdown menu automatically hides when mouse leaves

### Mobile (<992px)

- **Click to expand** - Click parent menu item to expand/collapse dropdown menu
- **Arrow indicator** - Dropdown arrow rotates to indicate expanded state
- **Click to navigate** - Click submenu item to navigate to corresponding link
- **Auto collapse** - Automatically collapses when clicking other areas or switching menus

## Style Customization

### CSS Variables

```css
/* Dropdown menu background */
.navbar .dropdown-menu {
  background-color: rgb(0 0 0 / 30%);
}

/* Dropdown menu item color */
.navbar .dropdown-item {
  color: var(--navbar-text-color);
}

/* Hover effect */
.navbar .dropdown-item:hover {
  color: var(--link-hover-color);
  background-color: rgb(0 0 0 / 10%);
}
```

## Accessibility Support

The submenu component includes full accessibility support:

- `role="button"` - Identifies clickable elements
- `aria-haspopup="true"` - Indicates popup menu exists
- `aria-expanded` - Dynamically updates expanded state
- `aria-labelledby` - Associates menu label

## FAQ

### Q: How to make parent menu also clickable for navigation?

Parent menus are not clickable by default (`href="javascript:;"`). If you need click navigation, you can add the `url` parameter, but this will affect the expand experience on mobile.

### Q: Can submenus be nested?

Currently only one level of submenu is supported, multi-level nesting is not supported.

### Q: How to open links in a new window?

Use the `post = "_blank"` parameter:

```toml
[[main]]
name = "External Link"
url = "https://example.com"
parent = "resources"
post = "_blank"
```

## Best Practices

1. **Group logically** - Organize related links under the same submenu
2. **Control quantity** - Each submenu should have no more than 5-7 items
3. **Clear naming** - Use concise and clear menu names
4. **Icon assistance** - Use icons appropriately to enhance recognition
5. **Mobile first** - Test expand/collapse experience on mobile

## Summary

The navigation bar submenu feature allows you to better organize website navigation and provide clearer information architecture. With simple configuration, you can achieve:

- Multi-level menu structure
- Responsive interaction
- Smooth animation effects
- Full accessibility support

Hope this tutorial helps you configure your ideal navigation menu!
