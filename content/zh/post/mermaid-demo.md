---
title: "Mermaid 流程图使用指南"
date: 2024-01-16T10:00:00+08:00
draft: false
description: "详细介绍 Hugo Fluid 主题的 Mermaid 流程图功能，包括配置方法、语法说明和丰富的图表示例。"
categories:
  - 教程
tags:
  - Mermaid
  - 流程图
  - 图表
  - 功能演示
index_img: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&h=400&fit=crop"
mermaid: true
---

本文详细介绍 Hugo Fluid 主题的 Mermaid 流程图功能，包括配置方法、语法说明和丰富的示例。

<!--more-->

## 快速开始

### 1. 启用 Mermaid

在 `params.toml` 中启用 Mermaid 支持：

```toml
[post.mermaid]
enable = true
specific = true  # 设为 true 则需要在文章中单独启用
[post.mermaid.options]
theme = "default"  # 可选: default, dark, forest, neutral
```

### 2. 在文章中使用

如果 `specific = true`，需要在文章的 Front-matter 中添加：

```yaml
---
title: "我的文章"
mermaid: true
---
```

然后在文章中使用 Markdown 代码块，语言标记为 `mermaid`。

---

## 流程图 (Flowchart)

### 基础流程图

**写法：**

````markdown
```mermaid
graph TD
    A[开始] --> B{判断条件}
    B -->|是| C[执行操作A]
    B -->|否| D[执行操作B]
    C --> E[结束]
    D --> E
```
````

**效果：**

```mermaid
graph TD
    A[开始] --> B{判断条件}
    B -->|是| C[执行操作A]
    B -->|否| D[执行操作B]
    C --> E[结束]
    D --> E
```

### 从左到右的流程图

**写法：**

````markdown
```mermaid
graph LR
    A[输入] --> B[处理]
    B --> C[输出]
```
````

**效果：**

```mermaid
graph LR
    A[输入] --> B[处理]
    B --> C[输出]
```

### 节点形状

**写法：**

````markdown
```mermaid
graph TD
    A[矩形] --> B(圆角矩形)
    B --> C{菱形}
    C --> D((圆形))
    D --> E>旗帜形]
    E --> F[[子程序]]
    F --> G[(数据库)]
```
````

**效果：**

```mermaid
graph TD
    A[矩形] --> B(圆角矩形)
    B --> C{菱形}
    C --> D((圆形))
    D --> E>旗帜形]
    E --> F[[子程序]]
    F --> G[(数据库)]
```

---

## 时序图 (Sequence Diagram)

### 基础时序图

**写法：**

````markdown
```mermaid
sequenceDiagram
    participant 用户
    participant 浏览器
    participant 服务器
    
    用户->>浏览器: 输入网址
    浏览器->>服务器: HTTP 请求
    服务器-->>浏览器: HTTP 响应
    浏览器-->>用户: 显示页面
```
````

**效果：**

```mermaid
sequenceDiagram
    participant 用户
    participant 浏览器
    participant 服务器
    
    用户->>浏览器: 输入网址
    浏览器->>服务器: HTTP 请求
    服务器-->>浏览器: HTTP 响应
    浏览器-->>用户: 显示页面
```

### 带循环和条件的时序图

**写法：**

````markdown
```mermaid
sequenceDiagram
    participant C as 客户端
    participant S as 服务器
    participant D as 数据库
    
    C->>S: 登录请求
    S->>D: 查询用户
    
    alt 用户存在
        D-->>S: 返回用户信息
        S->>S: 验证密码
        alt 密码正确
            S-->>C: 登录成功
        else 密码错误
            S-->>C: 密码错误
        end
    else 用户不存在
        D-->>S: 用户不存在
        S-->>C: 用户不存在
    end
```
````

**效果：**

```mermaid
sequenceDiagram
    participant C as 客户端
    participant S as 服务器
    participant D as 数据库
    
    C->>S: 登录请求
    S->>D: 查询用户
    
    alt 用户存在
        D-->>S: 返回用户信息
        S->>S: 验证密码
        alt 密码正确
            S-->>C: 登录成功
        else 密码错误
            S-->>C: 密码错误
        end
    else 用户不存在
        D-->>S: 用户不存在
        S-->>C: 用户不存在
    end
```

---

## 类图 (Class Diagram)

**写法：**

````markdown
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
        +fetch()
    }
    
    class Cat {
        +String color
        +meow()
        +scratch()
    }
    
    Animal <|-- Dog
    Animal <|-- Cat
```
````

**效果：**

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
        +fetch()
    }
    
    class Cat {
        +String color
        +meow()
        +scratch()
    }
    
    Animal <|-- Dog
    Animal <|-- Cat
```

---

## 状态图 (State Diagram)

**写法：**

````markdown
```mermaid
stateDiagram-v2
    [*] --> 待机
    待机 --> 运行: 启动
    运行 --> 暂停: 暂停
    暂停 --> 运行: 继续
    运行 --> 停止: 停止
    暂停 --> 停止: 停止
    停止 --> [*]
```
````

**效果：**

```mermaid
stateDiagram-v2
    [*] --> 待机
    待机 --> 运行: 启动
    运行 --> 暂停: 暂停
    暂停 --> 运行: 继续
    运行 --> 停止: 停止
    暂停 --> 停止: 停止
    停止 --> [*]
```

---

## 甘特图 (Gantt Chart)

**写法：**

````markdown
```mermaid
gantt
    title 项目开发计划
    dateFormat  YYYY-MM-DD
    
    section 设计阶段
    需求分析     :a1, 2024-01-01, 7d
    UI设计       :a2, after a1, 5d
    
    section 开发阶段
    前端开发     :b1, after a2, 14d
    后端开发     :b2, after a2, 14d
    
    section 测试阶段
    单元测试     :c1, after b1, 5d
    集成测试     :c2, after c1, 5d
    
    section 部署
    上线部署     :d1, after c2, 2d
```
````

**效果：**

```mermaid
gantt
    title 项目开发计划
    dateFormat  YYYY-MM-DD
    
    section 设计阶段
    需求分析     :a1, 2024-01-01, 7d
    UI设计       :a2, after a1, 5d
    
    section 开发阶段
    前端开发     :b1, after a2, 14d
    后端开发     :b2, after a2, 14d
    
    section 测试阶段
    单元测试     :c1, after b1, 5d
    集成测试     :c2, after c1, 5d
    
    section 部署
    上线部署     :d1, after c2, 2d
```

---

## 饼图 (Pie Chart)

**写法：**

````markdown
```mermaid
pie title 编程语言使用占比
    "JavaScript" : 35
    "Python" : 25
    "Java" : 20
    "Go" : 10
    "其他" : 10
```
````

**效果：**

```mermaid
pie title 编程语言使用占比
    "JavaScript" : 35
    "Python" : 25
    "Java" : 20
    "Go" : 10
    "其他" : 10
```

---

## 实体关系图 (ER Diagram)

**写法：**

````markdown
```mermaid
erDiagram
    USER ||--o{ ORDER : places
    USER {
        int id PK
        string name
        string email
    }
    ORDER ||--|{ ORDER_ITEM : contains
    ORDER {
        int id PK
        date created_at
        int user_id FK
    }
    PRODUCT ||--o{ ORDER_ITEM : "ordered in"
    PRODUCT {
        int id PK
        string name
        float price
    }
```
````

**效果：**

```mermaid
erDiagram
    USER ||--o{ ORDER : places
    USER {
        int id PK
        string name
        string email
    }
    ORDER ||--|{ ORDER_ITEM : contains
    ORDER {
        int id PK
        date created_at
        int user_id FK
    }
    PRODUCT ||--o{ ORDER_ITEM : "ordered in"
    PRODUCT {
        int id PK
        string name
        float price
    }
```

---

## Git 图 (Git Graph)

**写法：**

````markdown
```mermaid
gitGraph
    commit id: "初始提交"
    commit id: "添加功能A"
    branch develop
    checkout develop
    commit id: "开发功能B"
    commit id: "修复Bug"
    checkout main
    merge develop id: "合并develop"
    commit id: "发布v1.0"
```
````

**效果：**

```mermaid
gitGraph
    commit id: "初始提交"
    commit id: "添加功能A"
    branch develop
    checkout develop
    commit id: "开发功能B"
    commit id: "修复Bug"
    checkout main
    merge develop id: "合并develop"
    commit id: "发布v1.0"
```

---

## 用户旅程图 (User Journey)

**写法：**

````markdown
```mermaid
journey
    title 用户购物旅程
    section 浏览商品
      访问首页: 5: 用户
      搜索商品: 4: 用户
      查看详情: 4: 用户
    section 下单购买
      加入购物车: 5: 用户
      填写地址: 3: 用户
      支付订单: 4: 用户
    section 收货评价
      等待发货: 3: 用户
      确认收货: 5: 用户
      评价商品: 4: 用户
```
````

**效果：**

```mermaid
journey
    title 用户购物旅程
    section 浏览商品
      访问首页: 5: 用户
      搜索商品: 4: 用户
      查看详情: 4: 用户
    section 下单购买
      加入购物车: 5: 用户
      填写地址: 3: 用户
      支付订单: 4: 用户
    section 收货评价
      等待发货: 3: 用户
      确认收货: 5: 用户
      评价商品: 4: 用户
```

---

## 主题配置

Mermaid 支持多种主题，可以在配置中设置：

```toml
[post.mermaid.options]
theme = "default"  # 可选值: default, dark, forest, neutral
```

### 主题效果

- **default**: 默认主题，适合浅色背景
- **dark**: 深色主题，适合深色背景
- **forest**: 绿色主题，清新自然
- **neutral**: 中性主题，简洁大方

> 注意：Hugo Fluid 主题会根据当前的深色/浅色模式自动切换 Mermaid 主题。

---

## 常见问题

### 1. 图表不显示

- 检查是否在 `params.toml` 中启用了 `post.mermaid.enable = true`
- 如果 `specific = true`，检查文章 Front-matter 是否有 `mermaid: true`
- 检查代码块语言是否正确标记为 `mermaid`

### 2. 图表显示错误

- 检查 Mermaid 语法是否正确
- 注意缩进和空格
- 参考 [Mermaid 官方文档](https://mermaid.js.org/) 获取正确语法

### 3. 深色模式下图表不清晰

主题会自动根据当前模式切换 Mermaid 主题，如果仍有问题，可以尝试手动设置主题。

---

## 参考资源

- [Mermaid 官方文档](https://mermaid.js.org/)
- [Mermaid 在线编辑器](https://mermaid.live/)
- [Mermaid GitHub](https://github.com/mermaid-js/mermaid)
