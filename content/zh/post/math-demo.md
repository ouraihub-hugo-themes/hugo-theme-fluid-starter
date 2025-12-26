---
title: "数学公式使用指南"
date: 2024-01-15T10:00:00+08:00
draft: false
description: "详细介绍 Hugo Fluid 主题的数学公式功能，包括 MathJax 和 KaTeX 配置、LaTeX 语法说明和丰富的公式示例。"
categories:
  - 教程
tags:
  - 数学公式
  - LaTeX
  - MathJax
  - KaTeX
  - 功能演示
index_img: "https://images.unsplash.com/photo-1635070041078-e363dbe005cb?w=800&h=400&fit=crop"
math: true
---

本文详细介绍 Hugo Fluid 主题的数学公式功能，包括配置方法、语法说明和丰富的示例。

<!--more-->

## 快速开始

### 1. 启用数学公式

在 `params.toml` 中启用数学公式支持：

```toml
[post.math]
enable = true
specific = false  # 设为 true 则需要在文章中单独启用
engine = "mathjax"  # 可选 mathjax 或 katex
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

## 基础语法

### 行内公式

使用单个美元符号 `$...$` 包裹行内公式：

| 写法 | 效果 |
|------|------|
| `$E = mc^2$` | $E = mc^2$ |
| `$a^2 + b^2 = c^2$` | $a^2 + b^2 = c^2$ |
| `$\sqrt{x^2 + y^2}$` | $\sqrt{x^2 + y^2}$ |
| `$\frac{a}{b}$` | $\frac{a}{b}$ |

### 块级公式

使用双美元符号 `$$...$$` 包裹块级公式：

```latex
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$
```

效果：

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

---

## 常用数学符号

### 希腊字母

| 写法 | 效果 | 写法 | 效果 |
|------|------|------|------|
| `$\alpha$` | $\alpha$ | `$\beta$` | $\beta$ |
| `$\gamma$` | $\gamma$ | `$\delta$` | $\delta$ |
| `$\epsilon$` | $\epsilon$ | `$\theta$` | $\theta$ |
| `$\lambda$` | $\lambda$ | `$\mu$` | $\mu$ |
| `$\pi$` | $\pi$ | `$\sigma$` | $\sigma$ |
| `$\phi$` | $\phi$ | `$\omega$` | $\omega$ |
| `$\Gamma$` | $\Gamma$ | `$\Delta$` | $\Delta$ |
| `$\Theta$` | $\Theta$ | `$\Omega$` | $\Omega$ |

### 运算符

| 写法 | 效果 | 说明 |
|------|------|------|
| `$\times$` | $\times$ | 乘号 |
| `$\div$` | $\div$ | 除号 |
| `$\pm$` | $\pm$ | 正负号 |
| `$\mp$` | $\mp$ | 负正号 |
| `$\cdot$` | $\cdot$ | 点乘 |
| `$\leq$` | $\leq$ | 小于等于 |
| `$\geq$` | $\geq$ | 大于等于 |
| `$\neq$` | $\neq$ | 不等于 |
| `$\approx$` | $\approx$ | 约等于 |
| `$\equiv$` | $\equiv$ | 恒等于 |
| `$\in$` | $\in$ | 属于 |
| `$\notin$` | $\notin$ | 不属于 |
| `$\subset$` | $\subset$ | 子集 |
| `$\cup$` | $\cup$ | 并集 |
| `$\cap$` | $\cap$ | 交集 |

### 箭头

| 写法 | 效果 | 写法 | 效果 |
|------|------|------|------|
| `$\rightarrow$` | $\rightarrow$ | `$\leftarrow$` | $\leftarrow$ |
| `$\Rightarrow$` | $\Rightarrow$ | `$\Leftarrow$` | $\Leftarrow$ |
| `$\leftrightarrow$` | $\leftrightarrow$ | `$\Leftrightarrow$` | $\Leftrightarrow$ |

---

## 上下标与分数

### 上标和下标

```latex
$x^2$, $x_i$, $x_i^2$, $x_{i,j}^{n+1}$
```

效果：$x^2$, $x_i$, $x_i^2$, $x_{i,j}^{n+1}$

### 分数

```latex
$\frac{1}{2}$, $\frac{x+1}{x-1}$, $\dfrac{a}{b}$
```

效果：$\frac{1}{2}$, $\frac{x+1}{x-1}$, $\dfrac{a}{b}$

### 根号

```latex
$\sqrt{2}$, $\sqrt[3]{8}$, $\sqrt{x^2 + y^2}$
```

效果：$\sqrt{2}$, $\sqrt[3]{8}$, $\sqrt{x^2 + y^2}$

---

## 求和、积分与极限

### 求和

$$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$$

```latex
$$\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$$
```

### 连乘

$$
\prod_{i=1}^{n} i = n!
$$

```latex
$$\prod_{i=1}^{n} i = n!$$
```

### 积分

$$
\int_0^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
$$

```latex
$$\int_0^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}$$
```

### 多重积分

$$
\iint_D f(x,y) \, dx \, dy
$$

$$
\iiint_V f(x,y,z) \, dx \, dy \, dz
$$

### 极限

$$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$$

```latex
$$\lim_{x \to 0} \frac{\sin x}{x} = 1$$
```

$$
\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e
$$

---

## 矩阵与行列式

### 普通矩阵

$$
\begin{matrix}
a & b \\
c & d
\end{matrix}
$$

### 带括号的矩阵

$$
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$$

```latex
$$
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$$
```

### 带方括号的矩阵

$$
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
$$

### 行列式

$$
\begin{vmatrix}
a & b \\
c & d
\end{vmatrix}
= ad - bc
$$

### 矩阵运算

$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
=
\begin{pmatrix}
ax + by \\
cx + dy
\end{pmatrix}
$$

---

## 多行公式

### 对齐公式

使用 `aligned` 环境：

$$
\begin{aligned}
f(x) &= (x+1)^2 \\
     &= x^2 + 2x + 1
\end{aligned}
$$

```latex
$$
\begin{aligned}
f(x) &= (x+1)^2 \\
     &= x^2 + 2x + 1
\end{aligned}
$$
```

### 分段函数

$$
f(x) = \begin{cases}
x^2 & \text{if } x \geq 0 \\
-x^2 & \text{if } x < 0
\end{cases}
$$

```latex
$$
f(x) = \begin{cases}
x^2 & \text{if } x \geq 0 \\
-x^2 & \text{if } x < 0
\end{cases}
$$
```

---

## 经典公式示例

### 欧拉公式

$$
e^{i\pi} + 1 = 0
$$

### 欧拉恒等式

$$
e^{ix} = \cos x + i \sin x
$$

### 泰勒展开

$$
e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots
$$

### 傅里叶变换

$$
\hat{f}(\xi) = \int_{-\infty}^{\infty} f(x) e^{-2\pi i x \xi} dx
$$

### 麦克斯韦方程组

$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\
\nabla \times \mathbf{B} &= \mu_0 \mathbf{J} + \mu_0 \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t}
\end{aligned}
$$

### 薛定谔方程

$$
i\hbar\frac{\partial}{\partial t}\Psi(\mathbf{r},t) = \left[-\frac{\hbar^2}{2m}\nabla^2 + V(\mathbf{r},t)\right]\Psi(\mathbf{r},t)
$$

### 黎曼 Zeta 函数

$$
\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_{p \text{ prime}} \frac{1}{1-p^{-s}}
$$

### 巴塞尔问题

$$
\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}
$$

---

## 引擎对比

### MathJax

**优点：**
- 功能最全面，支持几乎所有 LaTeX 命令
- 渲染质量高
- 支持右键菜单（复制公式、查看源码等）

**缺点：**
- 加载较慢
- 文件体积较大

### KaTeX

**优点：**
- 渲染速度极快
- 文件体积小
- 服务端渲染支持好

**缺点：**
- 支持的 LaTeX 命令较少
- 某些复杂公式可能无法渲染

### 选择建议

- 如果文章包含复杂公式（如物理、高等数学），推荐使用 **MathJax**
- 如果追求页面加载速度，且公式较简单，推荐使用 **KaTeX**

---

## 常见问题

### 1. 公式不显示

- 检查是否在 `params.toml` 中启用了 `post.math.enable = true`
- 如果 `specific = true`，检查文章 Front-matter 是否有 `math: true`

### 2. 行内公式换行问题

行内公式中避免使用 `\\` 换行，如需换行请使用块级公式。

### 3. 特殊字符转义

在 Markdown 中，某些字符需要转义：
- `_` 下划线：使用 `\_` 或放在 `$...$` 中
- `*` 星号：使用 `\*` 或放在 `$...$` 中

### 4. 公式编号

MathJax 支持自动编号，在 `$$...$$` 中使用 `\tag{1}` 手动编号：

$$
E = mc^2 \tag{1}
$$

---

## 参考资源

- [LaTeX 数学符号表](https://www.caam.rice.edu/~heinken/latex/symbols.pdf)
- [MathJax 官方文档](https://docs.mathjax.org/)
- [KaTeX 支持的函数列表](https://katex.org/docs/supported.html)
- [在线 LaTeX 公式编辑器](https://www.latexlive.com/)
