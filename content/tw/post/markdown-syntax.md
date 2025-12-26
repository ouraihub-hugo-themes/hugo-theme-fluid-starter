---
title: "Markdown 語法範例"
date: 2024-01-10
categories: ["範例"]
tags: ["Markdown", "語法"]
description: "展示 Markdown 的各種語法和樣式效果。"
index_img: "https://images.unsplash.com/photo-1542831371-29b0f74f9713?w=800&h=400&fit=crop"
---

這篇文章展示了 Markdown 的基本語法和 Hugo Fluid 主題的渲染效果。

<!--more-->

## 標題

# H1 標題
## H2 標題
### H3 標題
#### H4 標題
##### H5 標題
###### H6 標題

## 段落和強調

這是一個普通段落。

這是 **粗體** 文字，這是 *斜體* 文字，這是 ~~刪除線~~ 文字。

這是 `行內程式碼` 範例。

## 列表

### 無序列表

- 項目 1
- 項目 2
  - 子項目 2.1
  - 子項目 2.2
- 項目 3

### 有序列表

1. 第一項
2. 第二項
3. 第三項

## 引用

> 這是一段引用文字。
> 
> 引用可以包含多個段落。

## 程式碼區塊

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Hugo Fluid!")
}
```

## 表格

| 名稱 | 類型 | 描述 |
|------|------|------|
| Hugo | SSG | 靜態網站生成器 |
| Fluid | Theme | Material Design 主題 |
| Go | Language | 程式語言 |

## 連結和圖片

這是一個 [連結範例](https://gohugo.io)。

## 分隔線

---

## 任務列表

- [x] 已完成任務
- [ ] 未完成任務
- [ ] 另一個未完成任務

## 腳註

這是一個帶腳註的文字[^1]。

[^1]: 這是腳註內容。
