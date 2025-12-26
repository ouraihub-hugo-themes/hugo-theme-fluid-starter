---
title: "Custom Page Configuration and Usage Guide"
date: 2024-12-24
categories:
  - Tutorial
tags:
  - Hugo
  - Custom Pages
  - Configuration
  - Templates
description: "A detailed guide on how to create and configure custom pages in Hugo Theme Fluid, including documentation pages, community pages, and more"
index_img: "https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800&h=400&fit=crop"
---

Hugo Theme Fluid supports creating various custom pages, such as documentation pages, community pages, terms of service pages, and more. This article provides a detailed guide on how to configure and use the custom page feature.

<!--more-->

## What are Custom Pages?

Custom pages are special pages independent of blog posts, typically used for:

- 📄 Documentation pages
- 👥 Community/Team introduction pages
- 📋 Terms of Service pages
- 🔒 Privacy Policy pages
- 📞 Contact Us pages
- 🎯 Project showcase pages

## Quick Creation

### Method 1: Using Hugo Command

```bash
hugo new page/my-page.md
```

This creates a new page in the `content/page/` directory using the theme's `archetypes/page.md` template.

### Method 2: Manual Creation

Create Markdown files in the `content/` directory:

```
content/
├── docs.md           # Documentation page
├── community.md      # Community page
├── terms.md          # Terms of Service
└── privacy.md        # Privacy Policy
```

## Page Configuration

### Basic Front Matter

```yaml
---
title: "Page Title"
subtitle: "Page Subtitle (optional)"
date: 2024-12-24
layout: "page"
---
```

### Complete Configuration Example

```yaml
---
title: "Documentation Center"
subtitle: "Hugo Theme Fluid Usage Documentation"
date: 2024-12-24
layout: "page"

# Banner Configuration
banner_img: "/img/docs-banner.jpg"
banner_img_height: 60
banner_mask_alpha: 0.3

# Feature Toggles
comments: true      # Enable comments
math: true          # Enable math formulas
mermaid: true       # Enable Mermaid diagrams
image_zoom: true    # Enable image zoom (enabled by default)
---
```

## Configuration Parameters

### Banner Configuration

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `banner_img` | string | Theme default | Banner background image |
| `banner_img_height` | number | 70 | Banner height percentage |
| `banner_mask_alpha` | number | 0.3 | Mask transparency (0-1) |

### Feature Toggles

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `comments` | boolean | false | Enable comments |
| `math` | boolean | false | Enable math formulas |
| `mermaid` | boolean | false | Enable Mermaid diagrams |
| `image_zoom` | boolean | true | Enable image zoom |

## Practical Examples

### Example 1: Documentation Page

```yaml
---
title: "User Documentation"
subtitle: "Quick Start Guide"
layout: "page"
banner_img: "https://images.unsplash.com/photo-1456513080510-7bf3a84b82f8?w=1200"
---

## Installation

1. Clone the theme repository
2. Configure hugo.toml
3. Run hugo server

## Configuration

Detailed configuration instructions...
```

### Example 2: Page with Math Formulas

```yaml
---
title: "Math Notes"
layout: "page"
math: true
---

## Euler's Formula

The famous Euler's formula:

$e^{i\pi} + 1 = 0$

This formula connects five of the most important mathematical constants.
```

## Adding to Navigation Menu

Add menu items in `config/_default/menus.toml`:

```toml
[[main]]
name = "Docs"
url = "/docs/"
weight = 50

[[main]]
name = "Community"
url = "/community/"
weight = 60
```

## Differences from Post Pages

| Feature | Custom Page | Post Page |
|---------|-------------|-----------|
| Layout | `page` | `post` |
| TOC | No | Yes |
| Categories/Tags | No | Yes |
| Prev/Next Navigation | No | Yes |
| Comments | Optional | Enabled by default |
| List Display | Not shown | Shown on homepage |

## Best Practices

### 1. Organize Directory Structure Properly

```
content/
├── post/           # Blog posts
├── page/           # Custom pages (recommended)
│   ├── docs.md
│   └── terms.md
├── about/          # About page
└── links/          # Links page
```

### 2. Use Meaningful URLs

```yaml
---
title: "Terms of Service"
url: "/terms-of-service/"
---
```

### 3. Configure Appropriate Banners

- Choose images related to page content
- Adjust mask transparency to ensure title readability
- Consider using lower Banner heights

## Summary

Hugo Theme Fluid's custom page feature allows you to easily create various standalone pages:

- ✅ Simple Front Matter configuration
- ✅ Support for math formulas and flowcharts
- ✅ Optional comment functionality
- ✅ Flexible Banner configuration
- ✅ Image zoom and anchor links

Hope this tutorial helps you make full use of the custom page feature!
