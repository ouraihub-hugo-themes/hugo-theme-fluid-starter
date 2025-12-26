---
title: "數學公式使用指南"
date: 2024-01-15T10:00:00+08:00
draft: false
description: "詳細介紹 Hugo Fluid 主題的數學公式功能，包括 MathJax 和 KaTeX 配置、LaTeX 語法說明和豐富的公式範例。"
categories:
  - 教程
tags:
  - 數學公式
  - LaTeX
  - MathJax
  - KaTeX
index_img: "https://images.unsplash.com/photo-1635070041078-e363dbe005cb?w=800&h=400&fit=crop"
math: true
---

本文詳細介紹 Hugo Fluid 主題的數學公式功能。

<!--more-->

## 快速開始

### 1. 啟用數學公式

在 `params.toml` 中啟用數學公式支援：

```toml
[post.math]
enable = true
specific = false
engine = "mathjax"
```

### 2. 在文章中使用

如果 `specific = true`，需要在文章的 Front-matter 中添加：

```yaml
---
title: "我的文章"
math: true
---
```

---

## 基礎語法

### 行內公式

使用單個美元符號包裹行內公式：

| 寫法 | 效果 |
|------|------|
| `$E = mc^2$` | $E = mc^2$ |
| `$a^2 + b^2 = c^2$` | $a^2 + b^2 = c^2$ |
| `$\sqrt{x^2 + y^2}$` | $\sqrt{x^2 + y^2}$ |

### 區塊公式

$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$

---

## 常用數學符號

### 希臘字母

| 寫法 | 效果 | 寫法 | 效果 |
|------|------|------|------|
| `$\alpha$` | $\alpha$ | `$\beta$` | $\beta$ |
| `$\gamma$` | $\gamma$ | `$\delta$` | $\delta$ |
| `$\pi$` | $\pi$ | `$\sigma$` | $\sigma$ |

### 運算符

| 寫法 | 效果 | 說明 |
|------|------|------|
| `$\times$` | $\times$ | 乘號 |
| `$\div$` | $\div$ | 除號 |
| `$\pm$` | $\pm$ | 正負號 |
| `$\leq$` | $\leq$ | 小於等於 |
| `$\geq$` | $\geq$ | 大於等於 |
| `$\neq$` | $\neq$ | 不等於 |

---

## 求和、積分與極限

### 求和

$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$

### 積分

$
\int_0^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
$

### 極限

$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$

---

## 矩陣

### 帶括號的矩陣

$
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$

### 帶方括號的矩陣

$
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{bmatrix}
$

---

## 經典公式範例

### 歐拉公式

$
e^{i\pi} + 1 = 0
$

### 泰勒展開

$
e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}
$

### 麥克斯韋方程組

$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0
\end{aligned}
$

---

## 參考資源

- [LaTeX 數學符號表](https://www.caam.rice.edu/~heinken/latex/symbols.pdf)
- [MathJax 官方文檔](https://docs.mathjax.org/)
- [KaTeX 支援的函數列表](https://katex.org/docs/supported.html)
