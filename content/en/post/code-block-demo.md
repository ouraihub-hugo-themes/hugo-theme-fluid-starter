---
title: "Code Block Demo"
date: 2024-12-23T10:00:00+08:00
draft: false
categories: ["Technology"]
tags: ["Code", "Demo", "Hugo"]
description: "Showcasing Hugo Fluid theme's code block features including syntax highlighting, language labels, and one-click copy."
index_img: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop"
---

This article demonstrates Hugo Fluid theme's code block features.

<!--more-->

## JavaScript Example

```javascript
// Theme toggle function
function toggleTheme() {
  const html = document.documentElement;
  const current = html.getAttribute('data-user-color-scheme');
  const next = current === 'dark' ? 'light' : 'dark';
  html.setAttribute('data-user-color-scheme', next);
  localStorage.setItem('Fluid_Color_Scheme', next);
}

// Event listener
document.addEventListener('DOMContentLoaded', () => {
  console.log('Page loaded');
});
```

## TypeScript Example

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

## Python Example

```python
def fibonacci(n: int) -> list[int]:
    """Generate Fibonacci sequence"""
    if n <= 0:
        return []
    elif n == 1:
        return [0]
    
    fib = [0, 1]
    for i in range(2, n):
        fib.append(fib[i-1] + fib[i-2])
    return fib

# Usage example
print(fibonacci(10))
```

## Go Example

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

## HTML Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example Page</title>
</head>
<body>
  <h1>Welcome to Hugo Fluid</h1>
  <p>This is an example page.</p>
</body>
</html>
```

## CSS Example

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

## Shell Commands

```bash
# Install Hugo
brew install hugo

# Create new site
hugo new site my-blog

# Start dev server
hugo server -D
```

## JSON Configuration

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

## YAML Configuration

```yaml
title: Hugo Fluid Theme
baseURL: https://example.com/
languageCode: en

params:
  navbar:
    brand: Fluid
  banner:
    enable: true
```

## Plain Code Block

```
This is a code block without language specification
It will show the default TEXT label
```

Click the copy button in the top right corner of code blocks to copy code with one click!
