---
title: "Typing Effect Configuration Guide"
date: 2024-01-20
categories: ["Tutorial"]
tags: ["Hugo", "Fluid", "Typing Effect"]
description: "This article explains how to configure and use the typing effect in Hugo Fluid theme."
index_img: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=800&h=400&fit=crop"
banner_img: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=1920&h=1080&fit=crop"
---

This article explains how to configure and use the typing effect in Hugo Fluid theme.

<!--more-->

## What is the Typing Effect

The typing effect is a dynamic text display effect where text appears character by character like a typewriter, with a blinking cursor, making the page more dynamic. In the Fluid theme, the typing effect is mainly used for the homepage subtitle (slogan) display.

## Basic Configuration

Configure the typing effect in `config/_default/params.toml`:

```toml
[fun_features.typing]
enable = true        # Enable typing effect
typeSpeed = 70       # Typing speed, higher = slower
cursorChar = "_"     # Cursor character
loop = false         # Loop playback
scope = []           # Scope, empty array means all pages
```

## Configuration Details

### enable

Controls whether to enable the typing effect. Set to `false` to completely disable this feature.

```toml
[fun_features.typing]
enable = true
```

### typeSpeed

Controls typing speed in milliseconds. Higher values mean slower typing.

```toml
[fun_features.typing]
typeSpeed = 70    # Default, moderate speed
# typeSpeed = 50  # Faster
# typeSpeed = 100 # Slower
```

### cursorChar

Sets the cursor character, default is underscore `_`. You can change it to other characters:

```toml
[fun_features.typing]
cursorChar = "_"   # Underscore (default)
# cursorChar = "|" # Vertical bar
# cursorChar = "▌" # Block
```

### loop

Controls whether the typing animation loops. If set to `true`, the text will be deleted and retyped after completion.

```toml
[fun_features.typing]
loop = false  # Play once (default)
# loop = true # Loop playback
```

### scope

Limits the scope of the typing effect. Options include:

- `home` - Homepage
- `post` - Post page
- `tag` - Tag page
- `category` - Category page
- `about` - About page
- `links` - Links page
- `page` - Regular pages
- `404` - 404 page

```toml
[fun_features.typing]
scope = []              # Empty array means all pages
# scope = ["home"]      # Only on homepage
# scope = ["home", "post"]  # On homepage and post pages
```

## Homepage Subtitle Configuration

The typing effect is mainly used for the homepage subtitle. Configure in `params.toml`:

### Single Text

```toml
[index.slogan]
enable = true
text = "An elegant Material-Design theme for Hugo"
```

### Multiple Texts with Random Display

If you want different text to display on each page refresh, configure as an array:

```toml
[index.slogan]
enable = true
text = [
  "An elegant Material-Design theme for Hugo",
  "Simple, elegant, efficient",
  "Focus on content creation"
]
```

Each time the page loads, one text will be randomly selected for the typing display.

## Disable Typing Effect in Articles

If you want to disable the typing effect in a specific article, set in the article's Front Matter:

```yaml
---
title: "My Article"
subtitle: false  # Disable subtitle and typing effect
---
```

## Complete Configuration Example

```toml
# Typing effect configuration
[fun_features.typing]
enable = true
typeSpeed = 70
cursorChar = "_"
loop = false
scope = ["home", "about"]  # Only on homepage and about page

# Homepage subtitle configuration
[index.slogan]
enable = true
text = [
  "An elegant Material-Design theme for Hugo",
  "Simple, elegant, efficient",
  "Focus on content creation"
]
```

## Notes

1. The typing effect depends on the [typed.js](https://github.com/mattboldt/typed.js/) library, loaded from CDN
2. If the network is slow, there may be a brief delay before the typing animation starts
3. Setting typing speed too fast may make the animation effect less noticeable
4. In loop mode, text will continuously type and delete

## Preview

Refresh this page and observe the subtitle in the top Banner area to see the typing effect with text appearing character by character.
