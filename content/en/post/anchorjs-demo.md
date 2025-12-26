---
title: "Anchor Link Feature Demo"
date: 2024-12-20T10:00:00+08:00
draft: false
description: "This article demonstrates the anchor link feature in Hugo Theme Fluid, making it easy to share specific sections of articles."
categories:
  - Tutorial
tags:
  - AnchorJS
  - Anchors
  - Feature Demo
index_img: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800&h=400&fit=crop"
banner_img: "/img/default.png"
---

This article demonstrates the anchor link feature in Hugo Theme Fluid. Anchor links make it easy to share specific sections of articles.

<!--more-->

## What are Anchor Links

Anchor Links are links that allow users to jump directly to a specific position on a page. When you hover over a heading, you'll see an anchor icon (default is `#` or `§`). Clicking it will:

1. Update the URL in the browser address bar
2. Allow you to copy the link to share with others
3. When others open the link, they'll automatically scroll to that position

## Features

### Support for Multiple Heading Levels

Anchor links support all heading levels from h1 to h6. The default configuration adds anchors to all headings.

#### Fourth Level Heading Example

This is a fourth level heading, which also has an anchor icon.

##### Fifth Level Heading Example

Fifth level headings are also supported.

###### Sixth Level Heading Example

Sixth level headings are supported as well.

### Flexible Position Configuration

The anchor icon can be configured to appear on the left or right side of the heading:

- **Left placement**: Anchor icon appears to the left of the heading text
- **Right placement**: Anchor icon appears to the right of the heading text

### Configurable Display Mode

There are two display modes for anchor icons:

- **hover**: Only show on mouse hover (default)
- **always**: Always visible

### Custom Icons

You can customize the anchor icon. Common options include:

- `§` (default)
- `#`
- `❡`
- `🔗`

## Configuration

Configure anchor links in `params.toml`:

```toml
[fun_features.anchorjs]
enable = true                    # Enable anchor links
element = "h1,h2,h3,h4,h5,h6"   # Elements to add anchors to
placement = "left"               # Position: left or right
visible = "hover"                # Display mode: hover or always
icon = ""                        # Custom icon, leave empty for default
```

## Use Cases

### Technical Documentation

Anchor links are very useful when writing technical documentation. Readers can directly share links to specific APIs or configuration items.

### Tutorial Articles

Tutorial articles usually have multiple steps. Anchor links allow readers to quickly jump to specific steps.

### FAQ Pages

Each question on an FAQ page can have its own anchor link, making it easy for users to share answers to specific questions.

## Integration with Other Features

### Works with TOC

Anchor links work perfectly with the Table of Contents (TOC). Clicking a heading in the TOC jumps to the corresponding position and updates the anchor in the URL.

### Works with Search

Search results can link directly to specific sections of articles, improving user experience.

## Summary

Anchor links are a simple but practical feature that can:

- Improve article shareability
- Enhance navigation experience for long articles
- Work together with TOC, search, and other features

Try hovering over any heading in this article to experience the anchor link feature!
