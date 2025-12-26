---
title: "代码块功能演示"
date: 2024-12-23T10:00:00+08:00
draft: false
categories: ["技术"]
tags: ["代码", "演示", "Hugo"]
description: "展示 Hugo Fluid 主题的代码块功能，包括语法高亮、语言标签和一键复制。"
index_img: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop"
---

本文展示 Hugo Fluid 主题的代码块功能。

<!--more-->

## JavaScript 示例

```javascript
// 主题切换函数
function toggleTheme() {
  const html = document.documentElement;
  const current = html.getAttribute('data-user-color-scheme');
  const next = current === 'dark' ? 'light' : 'dark';
  html.setAttribute('data-user-color-scheme', next);
  localStorage.setItem('Fluid_Color_Scheme', next);
}

// 事件监听
document.addEventListener('DOMContentLoaded', () => {
  console.log('页面加载完成');
});
```

## TypeScript 示例

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

async function fetchUser(id: number): Promise<User> {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
}
```

## Python 示例

```python
def fibonacci(n: int) -> list[int]:
    """生成斐波那契数列"""
    if n <= 0:
        return []
    elif n == 1:
        return [0]
    
    fib = [0, 1]
    for i in range(2, n):
        fib.append(fib[i-1] + fib[i-2])
    return fib

# 使用示例
print(fibonacci(10))
```

## Go 示例

```go
package main

import "fmt"

func main() {
    messages := make(chan string)

    go func() {
        messages <- "Hello, Hugo!"
    }()

    msg := <-messages
    fmt.Println(msg)
}
```

## HTML 示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>示例页面</title>
</head>
<body>
  <h1>欢迎使用 Hugo Fluid</h1>
  <p>这是一个示例页面。</p>
</body>
</html>
```

## CSS 示例

```css
.code-wrapper {
  position: relative;
  margin: 1rem 0;
  border-radius: 0.5rem;
  overflow: hidden;
}

.copy-btn:hover {
  opacity: 1;
  transform: scale(1.1);
}
```

## Shell 命令

```bash
# 安装 Hugo
brew install hugo

# 创建新站点
hugo new site my-blog

# 启动开发服务器
hugo server -D
```

## JSON 配置

```json
{
  "name": "hugo-theme-fluid",
  "version": "1.0.0",
  "scripts": {
    "dev": "hugo server",
    "build": "hugo --minify"
  }
}
```

## YAML 配置

```yaml
title: Hugo Fluid 主题
baseURL: https://example.com/
languageCode: zh-CN

params:
  navbar:
    brand: Fluid
  banner:
    enable: true
```

## 无语言标记的代码块

```
这是一段没有指定语言的代码块
会显示默认的 TEXT 标签
```

点击代码块右上角的复制按钮，即可一键复制代码！
