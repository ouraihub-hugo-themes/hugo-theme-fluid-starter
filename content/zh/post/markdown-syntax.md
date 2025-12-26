---
title: "Markdown 语法示例"
date: 2024-01-10
categories: ["示例"]
tags: ["Markdown", "语法"]
description: "展示 Markdown 的各种语法和样式效果。"
index_img: "https://images.unsplash.com/photo-1542831371-29b0f74f9713?w=800&h=400&fit=crop"
---

这篇文章展示了 Markdown 的基本语法和 Hugo Fluid 主题的渲染效果。

<!--more-->

## 标题

# H1 标题
## H2 标题
### H3 标题
#### H4 标题
##### H5 标题
###### H6 标题

## 段落和强调

这是一个普通段落。

这是 **粗体** 文本，这是 *斜体* 文本，这是 ~~删除线~~ 文本。

这是 `行内代码` 示例。

## 列表

### 无序列表

- 项目 1
- 项目 2
  - 子项目 2.1
  - 子项目 2.2
- 项目 3

### 有序列表

1. 第一项
2. 第二项
3. 第三项

## 引用

> 这是一段引用文本。
> 
> 引用可以包含多个段落。

## 代码块

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Hugo Fluid!")
}
```

## 表格

| 名称 | 类型 | 描述 |
|------|------|------|
| Hugo | SSG | 静态站点生成器 |
| Fluid | Theme | Material Design 主题 |
| Go | Language | 编程语言 |

## 链接和图片

这是一个 [链接示例](https://gohugo.io)。

## 分隔线

---

## 任务列表

- [x] 已完成任务
- [ ] 未完成任务
- [ ] 另一个未完成任务

## 脚注

这是一个带脚注的文本[^1]。

[^1]: 这是脚注内容。
