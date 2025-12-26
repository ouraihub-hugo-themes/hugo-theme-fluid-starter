---
title: "程式碼區塊功能演示"
date: 2024-12-23T10:00:00+08:00
draft: false
categories: ["技術"]
tags: ["程式碼", "演示", "Hugo"]
description: "展示 Hugo Fluid 主題的程式碼區塊功能，包括語法高亮、語言標籤和一鍵複製。"
index_img: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop"
---

本文展示 Hugo Fluid 主題的程式碼區塊功能。

<!--more-->

## JavaScript 範例

```javascript
// 主題切換函數
function toggleTheme() {
  const html = document.documentElement;
  const current = html.getAttribute('data-user-color-scheme');
  const next = current === 'dark' ? 'light' : 'dark';
  html.setAttribute('data-user-color-scheme', next);
  localStorage.setItem('Fluid_Color_Scheme', next);
}

// 事件監聽
document.addEventListener('DOMContentLoaded', () => {
  console.log('頁面載入完成');
});
```

## TypeScript 範例

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

## Python 範例

```python
def fibonacci(n: int) -> list[int]:
    """生成費波那契數列"""
    if n <= 0:
        return []
    elif n == 1:
        return [0]
    
    fib = [0, 1]
    for i in range(2, n):
        fib.append(fib[i-1] + fib[i-2])
    return fib

# 使用範例
print(fibonacci(10))
```

## Go 範例

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

## Shell 命令

```bash
# 安裝 Hugo
brew install hugo

# 建立新網站
hugo new site my-blog

# 啟動開發伺服器
hugo server -D
```

點擊程式碼區塊右上角的複製按鈕，即可一鍵複製程式碼！
