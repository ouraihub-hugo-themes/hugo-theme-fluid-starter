---
title: "Complete Guide to Banner Background Image Configuration"
date: 2024-12-24
draft: false
categories: ["Tutorial"]
tags: ["Theme Configuration", "Banner", "Image Optimization"]
index_img: "https://images.unsplash.com/photo-1579546929518-9e396f3cc809?w=800&h=400&fit=crop"
banner_img: "/img/post.webp"
---

This article provides a detailed guide on how to configure custom Banner background images for the Hugo Fluid theme, including using AI to generate images, compression optimization, and the complete process of configuring them in the theme.

<!--more-->

## Overview

Each page in the Hugo Fluid theme can have its own Banner background image, including:

- Home Page
- Post Page
- Archive Page
- Category Page
- Tag Page
- About Page
- Links Page
- 404 Page

This theme recommends using **flat illustration style** images that match the Material Design language.

### Preview

Here are the Banner image effects used in this theme:

| Home | Post |
|:----:|:----:|
| ![Home Banner](/img/home.webp) | ![Post Banner](/img/post.webp) |

| Archive | Category |
|:------:|:------:|
| ![Archive Banner](/img/archive.webp) | ![Category Banner](/img/category.webp) |

| Tag | About |
|:------:|:------:|
| ![Tag Banner](/img/tag.webp) | ![About Banner](/img/about.webp) |

| Links | 404 Page |
|:------:|:--------:|
| ![Links Banner](/img/links.webp) | ![404 Banner](/img/404.webp) |

## Step 1: Get Images

### Option 1: Use AI Generation (Recommended)

Using AI image generation tools can quickly produce illustrations with a consistent style.

#### Recommended Tools

| Tool | URL | Features |
|------|-----|----------|
| **LM Arena** | [lmarena.ai](https://lmarena.ai/) | ⭐ **Highly Recommended**, Free, Multiple models |
| ChatGPT (DALL-E 3) | [chat.openai.com](https://chat.openai.com) | Easy to use, Subscription required |
| Midjourney | [midjourney.com](https://midjourney.com) | Highest quality, Paid |

#### Using LM Arena to Generate Images (Recommended)

The Banner images for this theme were generated using LM Arena with excellent results.

**Steps**:

1. Open [lmarena.ai](https://lmarena.ai/)
2. Click the **Image** tab at the top to switch to image generation mode
3. Select **gemini-3-pro-image-preview (nano-banana-pro)** from the model dropdown
4. Copy and paste the prompt below into the input box
5. Click generate and wait a few seconds for the image
6. Right-click to save the image

> **Tip**: The Gemini 3 Pro model generates flat illustration styles that are perfect for this theme, with rich colors and clear layers.

#### Generation Prompts

Here are prompts designed for each page, just copy them into the AI tool:

##### 1. Home Page

```text
Create a flat design landscape illustration, 1920x1080 pixels, 16:9 aspect ratio. Purple and pink gradient sky at dusk with Saturn planet floating in the upper right. Multiple layers of mountain silhouettes transitioning from dark purple in foreground to light pink in background. Small birds flying in the sky. Pine trees silhouette at the bottom. Minimalist vector style, soft dreamy atmosphere, no text, suitable for website banner background with text overlay in the center.
```

##### 2. Post Page

```text
Create a flat design night landscape illustration, 1920x1080 pixels, 16:9 aspect ratio. Deep blue to purple gradient night sky with scattered stars and a crescent moon. Multiple layers of mountain silhouettes in dark blue and navy tones. Calm lake with subtle reflection in the foreground. Minimalist vector style, peaceful and focused reading atmosphere, no text, suitable for website banner background with text overlay in the center.
```

## Step 2: Compress Images

Image compression is a **very important** step that directly affects website loading speed.

### Using Squoosh (Recommended)

[Squoosh](https://squoosh.app/) is a free online image compression tool developed by Google, simple to use with excellent results.

#### Steps

1. Open [squoosh.app](https://squoosh.app/)

2. Drag the image into the page, or click to select a file

3. Configure settings in the right panel:

   **Format Selection**: Click the "Compress" dropdown, select `WebP`

   **Quality Settings**:
   - Quality: `70` (recommended, balances quality and size)
   - Effort: `6` (compression level, higher = smaller file)

4. Check the file size preview in the bottom right

5. Click the download button to save

#### Recommended Settings

| Setting | Recommended Value | Description |
|---------|------------------|-------------|
| Format | WebP | Smallest file size, supported by modern browsers |
| Quality | 70 | Best balance of quality and size |
| Effort | 6 | Good compression level |
| Resize Width | 1920 | Maintain 1920x1080 ratio |

#### Target File Size

| File Size | Rating | Loading Experience |
|-----------|--------|-------------------|
| < 100KB | ⭐⭐⭐ Excellent | Instant, almost imperceptible |
| 100-200KB | ⭐⭐ Good | Very fast, smooth experience |
| 200-300KB | ⭐ Acceptable | Slight wait |
| > 300KB | ❌ Too Large | Need to reduce Quality and recompress |

## Step 3: Save Images to Project

Save the compressed images to the theme's `static/img/` directory:

```
your-site/
└── static/
    └── img/
        ├── home.webp      # Home page
        ├── post.webp      # Post page
        ├── archive.webp   # Archive page
        ├── category.webp  # Category page
        ├── tag.webp       # Tag page
        ├── about.webp     # About page
        ├── links.webp     # Links page
        └── 404.webp       # 404 page
```

## Step 4: Modify Configuration

Edit the site configuration file `config/_default/params.toml` to modify the `banner_img` settings for each page:

```toml
#---------------------------
# Home Page
#---------------------------
[index]
banner_img = "/img/home.webp"
banner_img_height = 100
banner_mask_alpha = 0.3

#---------------------------
# Post Page
#---------------------------
[post]
banner_img = "/img/post.webp"
banner_img_height = 70
banner_mask_alpha = 0.3
```

### Configuration Description

| Parameter | Description | Recommended Value |
|-----------|-------------|-------------------|
| `banner_img` | Image path, relative to static directory | `/img/xxx.webp` |
| `banner_img_height` | Banner height, percentage of screen | 60-100 |
| `banner_mask_alpha` | Mask transparency, between 0-1 | 0.3 |

## Step 5: Verify Results

Start the development server to check the results:

```bash
hugo server
```

Visit `http://localhost:1313` to check if the Banner is displayed correctly on each page.

## Summary

Complete process for configuring custom Banners:

1. **Generate Images**: Use AI tools or free image websites
2. **Compress Images**: Use Squoosh, WebP format, Quality 70
3. **Save Images**: Place in `static/img/` directory
4. **Modify Configuration**: Update `banner_img` in `params.toml`
5. **Verify Results**: Start development server to check

Following this tutorial, you can get fast-loading, visually appealing custom Banner backgrounds.
