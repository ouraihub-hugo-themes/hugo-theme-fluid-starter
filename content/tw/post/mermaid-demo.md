---
title: "Mermaid 流程圖使用指南"
date: 2024-01-16T10:00:00+08:00
draft: false
description: "詳細介紹 Hugo Fluid 主題的 Mermaid 流程圖功能，包括配置方法、語法說明和豐富的圖表範例。"
categories:
  - 教程
tags:
  - Mermaid
  - 流程圖
  - 圖表
index_img: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&h=400&fit=crop"
mermaid: true
---

本文詳細介紹 Hugo Fluid 主題的 Mermaid 流程圖功能。

<!--more-->

## 快速開始

### 1. 啟用 Mermaid

在 `params.toml` 中啟用 Mermaid 支援：

```toml
[post.mermaid]
enable = true
specific = true
[post.mermaid.options]
theme = "default"
```

### 2. 在文章中使用

如果 `specific = true`，需要在文章的 Front-matter 中添加：

```yaml
---
title: "我的文章"
mermaid: true
---
```

---

## 流程圖 (Flowchart)

### 基礎流程圖

```mermaid
graph TD
    A[開始] --> B{判斷條件}
    B -->|是| C[執行操作A]
    B -->|否| D[執行操作B]
    C --> E[結束]
    D --> E
```

### 從左到右的流程圖

```mermaid
graph LR
    A[輸入] --> B[處理]
    B --> C[輸出]
```

---

## 時序圖 (Sequence Diagram)

```mermaid
sequenceDiagram
    participant 使用者
    participant 瀏覽器
    participant 伺服器
    
    使用者->>瀏覽器: 輸入網址
    瀏覽器->>伺服器: HTTP 請求
    伺服器-->>瀏覽器: HTTP 回應
    瀏覽器-->>使用者: 顯示頁面
```

---

## 類別圖 (Class Diagram)

```mermaid
classDiagram
    class Animal {
        +String name
        +int age
        +makeSound()
    }
    
    class Dog {
        +String breed
        +bark()
    }
    
    class Cat {
        +String color
        +meow()
    }
    
    Animal <|-- Dog
    Animal <|-- Cat
```

---

## 狀態圖 (State Diagram)

```mermaid
stateDiagram-v2
    [*] --> 待機
    待機 --> 運行: 啟動
    運行 --> 暫停: 暫停
    暫停 --> 運行: 繼續
    運行 --> 停止: 停止
    停止 --> [*]
```

---

## 甘特圖 (Gantt Chart)

```mermaid
gantt
    title 專案開發計畫
    dateFormat  YYYY-MM-DD
    
    section 設計階段
    需求分析     :a1, 2024-01-01, 7d
    UI設計       :a2, after a1, 5d
    
    section 開發階段
    前端開發     :b1, after a2, 14d
    後端開發     :b2, after a2, 14d
    
    section 測試階段
    單元測試     :c1, after b1, 5d
    整合測試     :c2, after c1, 5d
```

---

## 圓餅圖 (Pie Chart)

```mermaid
pie title 程式語言使用佔比
    "JavaScript" : 35
    "Python" : 25
    "Java" : 20
    "Go" : 10
    "其他" : 10
```

---

## Git 圖 (Git Graph)

```mermaid
gitGraph
    commit id: "初始提交"
    commit id: "添加功能A"
    branch develop
    checkout develop
    commit id: "開發功能B"
    commit id: "修復Bug"
    checkout main
    merge develop id: "合併develop"
    commit id: "發布v1.0"
```

---

## 參考資源

- [Mermaid 官方文檔](https://mermaid.js.org/)
- [Mermaid 線上編輯器](https://mermaid.live/)
