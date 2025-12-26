---
title: "Image Lazy Loading Demo"
date: 2024-12-20
categories: ["Demo"]
tags: ["Lazy Loading", "Performance Optimization"]
description: "Demonstrating the image lazy loading feature. Scroll the page to see images load on demand."
index_img: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=800&h=400&fit=crop"
---

This article demonstrates the image lazy loading feature. Scroll down the page to observe how images load on demand.

<!--more-->

## What is Lazy Loading?

Lazy Loading is a performance optimization technique that delays loading images on a page until the user scrolls near the image's location. This can:

- 🚀 **Speed up initial page load** - Only load images in the visible area
- 💾 **Save bandwidth** - Users may not scroll to all images
- ⚡ **Improve user experience** - Page responds faster

## Lazy Loading Demo

Below are a series of images. Please scroll down to see the lazy loading effect. Open the Network panel in your browser's developer tools to observe that images only start loading when you scroll near them.

---

### Image 1 - Mountain Landscape

![Mountain Landscape](https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?w=1200&h=800&fit=crop)

*Magnificent view of the Alps*

---

### Image 2 - Ocean Sunset

![Ocean Sunset](https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=1200&h=800&fit=crop)

*Beautiful sunset at a tropical beach*

---

### Image 3 - City Night View

![City Night View](https://images.unsplash.com/photo-1519501025264-65ba15a82390?w=1200&h=800&fit=crop)

*Dazzling night view of a bustling city*

---

### Image 4 - Forest Path

![Forest Path](https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=1200&h=800&fit=crop)

*Winding path through a peaceful forest*

---

### Image 5 - Snow Mountain Lake

![Snow Mountain Lake](https://images.unsplash.com/photo-1439066615861-d1af74d74000?w=1200&h=800&fit=crop)

*Crystal clear lake reflecting snow-capped mountains*

---

### Image 6 - Desert Starry Sky

![Desert Starry Sky](https://images.unsplash.com/photo-1507400492013-162706c8c05e?w=1200&h=800&fit=crop)

*Brilliant Milky Way over the desert*

---

### Image 7 - Waterfall

![Waterfall](https://images.unsplash.com/photo-1432405972618-c60b0225b8f9?w=1200&h=800&fit=crop)

*Majestic waterfall*

---

### Image 8 - Flower Field

![Flower Field](https://images.unsplash.com/photo-1490750967868-88aa4486c946?w=1200&h=800&fit=crop)

*Colorful flower field*

---

### Image 9 - Aurora

![Aurora](https://images.unsplash.com/photo-1531366936337-7c912a4589a7?w=1200&h=800&fit=crop)

*Mysterious aurora in the Arctic Circle*

---

### Image 10 - Ancient Architecture

![Ancient Architecture](https://images.unsplash.com/photo-1548013146-72479768bada?w=1200&h=800&fit=crop)

*Historic ancient architecture*

---

## Technical Implementation

Hugo Fluid theme uses the **Intersection Observer API** to implement image lazy loading:

```typescript
// Create Intersection Observer
const observer = new IntersectionObserver(
  (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        const img = entry.target as HTMLImageElement;
        // Load actual image
        img.src = img.dataset.src;
        img.removeAttribute('data-src');
        observer.unobserve(img);
      }
    });
  },
  {
    rootMargin: '200px 0px', // Start loading 200px ahead
  }
);
```

## Configuration Options

You can configure lazy loading behavior in `params.toml`:

```toml
[lazyload]
  enable = true
  loading_img = "/img/loading.gif"
  onlypost = false
  offset_factor = 2
```

| Parameter | Description | Default |
|-----------|-------------|---------|
| `enable` | Enable lazy loading | `true` |
| `loading_img` | Placeholder image during loading | `/img/loading.gif` |
| `onlypost` | Enable only on post pages | `false` |
| `offset_factor` | Preload distance multiplier | `2` |

---

## Summary

Image lazy loading is a standard feature for modern websites that significantly improves page loading performance and user experience. Hugo Fluid theme has this feature built-in and ready to use!
