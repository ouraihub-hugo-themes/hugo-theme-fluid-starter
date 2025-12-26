---
title: "Footer Configuration Guide"
date: 2024-12-24
description: "A detailed guide on configuring the footer in Hugo Fluid theme, including custom content, PV/UV statistics, and ICP filing information."
categories: ["Tutorial"]
tags: ["Footer", "Configuration", "Statistics", "Filing"]
index_img: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800&h=400&fit=crop"
---

This article explains how to configure the footer component in Hugo Fluid theme, including custom content, PV/UV statistics, and filing information.

<!--more-->

## Footer Preview

Scroll to the bottom of this page to see the footer effect, including:

1. **Custom Content**: Displays "Hugo ❤ Fluid" links
2. **PV/UV Statistics**: Shows page views and visitor counts
3. **Filing Information**: Displays ICP filing number and public security filing number

## Configuration File Location

Footer configuration is located in the `[footer]` section of the `config/_default/params.toml` file.

## Basic Configuration

```toml
[footer]
# HTML for the first line of footer text
content = '''
<a href="https://gohugo.io" target="_blank" rel="nofollow noopener"><span>Hugo</span></a>
<i class="iconfont icon-love"></i>
<a href="https://github.com/fluid-dev/hexo-theme-fluid" target="_blank" rel="nofollow noopener"><span>Fluid</span></a>
'''
```

You can customize the `content`, which supports HTML format:

```toml
content = '''
Copyright © 2024 My Blog
<br>
Powered by <a href="https://gohugo.io">Hugo</a> & <a href="https://github.com/fluid-dev/hexo-theme-fluid">Fluid</a>
'''
```

## PV/UV Statistics Configuration

The footer can display website page views (PV) and visitor count (UV) statistics.

```toml
[footer.statistics]
# Enable statistics
enable = true

# Statistics source: busuanzi | leancloud | umami
source = "busuanzi"

# PV display format, {} is the number placeholder
pv_format = "Total Views: {}"

# UV display format, {} is the number placeholder
uv_format = "Total Visitors: {}"
```

### Statistics Source Description

| Source | Description | Configuration Required |
|--------|-------------|----------------------|
| `busuanzi` | Busuanzi statistics, free and easy to use | No additional configuration |
| `leancloud` | LeanCloud statistics | Requires LeanCloud parameters |
| `umami` | Umami statistics | Requires Umami parameters |

### Format Text Examples

```toml
# English format
pv_format = "Total Views: {}"
uv_format = "Total Visitors: {}"

# Simple format
pv_format = "PV: {}"
uv_format = "UV: {}"
```

## Filing Information Configuration

If your website is deployed on servers in mainland China, you need to display ICP filing information.

```toml
[footer.beian]
# Enable filing information
enable = true

# ICP filing number
icp_text = "ICP License No. 123456"

# Public security filing number (optional)
police_text = "Public Security Filing No. 12345678"

# Public security filing code for URL redirect
police_code = "12345678"

# Public security filing icon path
police_icon = "/img/police_beian.png"
```

### Configuration Description

| Parameter | Description | Required |
|-----------|-------------|----------|
| `enable` | Enable filing information | Yes |
| `icp_text` | ICP filing number | Yes |
| `police_text` | Public security filing number | No |
| `police_code` | Public security filing code | No |
| `police_icon` | Public security filing icon | No |

## Complete Configuration Example

```toml
[footer]
content = '''
<a href="https://gohugo.io" target="_blank"><span>Hugo</span></a>
<i class="iconfont icon-love"></i>
<a href="https://github.com/fluid-dev/hexo-theme-fluid" target="_blank"><span>Fluid</span></a>
'''

[footer.statistics]
enable = true
source = "busuanzi"
pv_format = "Total Views: {}"
uv_format = "Total Visitors: {}"

[footer.beian]
enable = true
icp_text = "ICP License No. 123456"
police_text = "Public Security Filing No. 12345678"
police_code = "12345678"
police_icon = "/img/police_beian.png"
```

## FAQ

### Busuanzi statistics showing very large numbers?

This is normal. In the local development environment, Busuanzi displays test data. Real data will be shown after deployment to production.

### Statistics not showing?

Check the following:
1. Ensure `footer.statistics.enable = true`
2. Ensure network can access the statistics service
3. Check browser console for errors

### How to disable footer features?

- Disable statistics: Set `footer.statistics.enable = false`
- Disable filing: Set `footer.beian.enable = false`

## Related Files

- Footer template: `layouts/partials/footer/footer.html`
- Statistics component: `layouts/partials/footer/statistics.html`
- Filing component: `layouts/partials/footer/beian.html`
