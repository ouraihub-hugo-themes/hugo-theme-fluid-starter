---
title: "页脚配置指南"
date: 2024-12-24
description: "详细介绍 Hugo Fluid 主题的页脚配置，包括自定义内容、PV/UV 统计和备案信息设置。"
categories: ["教程"]
tags: ["页脚", "配置", "统计", "备案"]
index_img: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800&h=400&fit=crop"
---

本文介绍如何配置 Hugo Fluid 主题的页脚组件，包括自定义内容、PV/UV 统计和备案信息。

<!--more-->

## 页脚效果预览

滚动到本页面底部即可看到页脚效果，包括：

1. **自定义内容**：显示 "Hugo ❤ Fluid" 链接
2. **PV/UV 统计**：显示访问量和访客数
3. **备案信息**：显示 ICP 备案号和公安备案号

## 配置文件位置

页脚配置位于 `config/_default/params.toml` 文件中的 `[footer]` 部分。

## 基础配置

```toml
[footer]
# 页脚第一行文字的 HTML
content = '''
<a href="https://gohugo.io" target="_blank" rel="nofollow noopener"><span>Hugo</span></a>
<i class="iconfont icon-love"></i>
<a href="https://github.com/fluid-dev/hexo-theme-fluid" target="_blank" rel="nofollow noopener"><span>Fluid</span></a>
'''
```

你可以自定义 `content` 的内容，支持 HTML 格式：

```toml
content = '''
Copyright © 2024 My Blog
<br>
Powered by <a href="https://gohugo.io">Hugo</a> & <a href="https://github.com/fluid-dev/hexo-theme-fluid">Fluid</a>
'''
```

## PV/UV 统计配置

页脚可以显示网站的访问量（PV）和访客数（UV）统计。

```toml
[footer.statistics]
# 是否启用统计
enable = true

# 统计数据来源: busuanzi | leancloud | umami
source = "busuanzi"

# PV 显示格式，{} 为数字占位符
pv_format = "总访问量 {} 次"

# UV 显示格式，{} 为数字占位符
uv_format = "总访客数 {} 人"
```

### 统计源说明

| 统计源 | 说明 | 配置要求 |
|--------|------|----------|
| `busuanzi` | 不蒜子统计，免费易用 | 无需额外配置 |
| `leancloud` | LeanCloud 统计 | 需要配置 LeanCloud 参数 |
| `umami` | Umami 统计 | 需要配置 Umami 参数 |

### 格式化文本示例

```toml
# 中文格式
pv_format = "总访问量 {} 次"
uv_format = "总访客数 {} 人"

# 英文格式
pv_format = "Total Views: {}"
uv_format = "Total Visitors: {}"

# 简洁格式
pv_format = "PV: {}"
uv_format = "UV: {}"
```

## 备案信息配置

如果你的网站部署在中国大陆服务器，需要显示 ICP 备案信息。

```toml
[footer.beian]
# 是否启用备案信息
enable = true

# ICP 备案号
icp_text = "京ICP证123456号"

# 公安备案号（可选）
police_text = "京公网安备12345678号"

# 公安备案编号，用于 URL 跳转查询
police_code = "12345678"

# 公安备案图标路径
police_icon = "/img/police_beian.png"
```

### 配置说明

| 参数 | 说明 | 必填 |
|------|------|------|
| `enable` | 是否启用备案信息 | 是 |
| `icp_text` | ICP 备案号 | 是 |
| `police_text` | 公安备案号 | 否 |
| `police_code` | 公安备案编号 | 否 |
| `police_icon` | 公安备案图标 | 否 |

### 仅显示 ICP 备案

```toml
[footer.beian]
enable = true
icp_text = "京ICP证123456号"
police_text = ""
```

## 完整配置示例

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
pv_format = "总访问量 {} 次"
uv_format = "总访客数 {} 人"

[footer.beian]
enable = true
icp_text = "京ICP证123456号"
police_text = "京公网安备12345678号"
police_code = "12345678"
police_icon = "/img/police_beian.png"
```

## 常见问题

### 不蒜子统计数据显示很大的数字？

这是正常现象。在本地开发环境中，不蒜子会显示测试数据。部署到生产环境后会显示真实数据。

### 统计数据不显示？

检查以下几点：
1. 确保 `footer.statistics.enable = true`
2. 确保网络可以访问统计服务
3. 检查浏览器控制台是否有错误

### 如何关闭页脚功能？

- 关闭统计：设置 `footer.statistics.enable = false`
- 关闭备案：设置 `footer.beian.enable = false`

## 相关文件

- 页脚模板：`layouts/partials/footer/footer.html`
- 统计组件：`layouts/partials/footer/statistics.html`
- 备案组件：`layouts/partials/footer/beian.html`
