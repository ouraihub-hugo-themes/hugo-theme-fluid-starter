---
title: "Math Formula Guide"
date: 2024-01-15T10:00:00+08:00
draft: false
description: "A detailed guide to Hugo Fluid theme's math formula features, including MathJax and KaTeX configuration, LaTeX syntax, and rich formula examples."
categories:
  - Tutorial
tags:
  - Math
  - LaTeX
  - MathJax
  - KaTeX
index_img: "https://images.unsplash.com/photo-1635070041078-e363dbe005cb?w=800&h=400&fit=crop"
math: true
---

This article details Hugo Fluid theme's math formula features, including configuration, syntax, and examples.

<!--more-->

## Quick Start

### 1. Enable Math Formulas

Enable math formula support in `params.toml`:

```toml
[post.math]
enable = true
specific = false  # Set to true to enable per-article
engine = "mathjax"  # Options: mathjax or katex
```

### 2. Use in Articles

If `specific = true`, add to article Front-matter:

```yaml
---
title: "My Article"
math: true
---
```

---

## Basic Syntax

### Inline Formulas

Use single dollar signs `$...$` for inline formulas:

| Syntax | Result |
|--------|--------|
| `$E = mc^2$` | $E = mc^2$ |
| `$a^2 + b^2 = c^2$` | $a^2 + b^2 = c^2$ |
| `$\sqrt{x^2 + y^2}$` | $\sqrt{x^2 + y^2}$ |

### Block Formulas

Use double dollar signs for block formulas:

$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$

---

## Common Math Symbols

### Greek Letters

| Syntax | Result | Syntax | Result |
|--------|--------|--------|--------|
| `$\alpha$` | $\alpha$ | `$\beta$` | $\beta$ |
| `$\gamma$` | $\gamma$ | `$\delta$` | $\delta$ |
| `$\pi$` | $\pi$ | `$\sigma$` | $\sigma$ |

### Operators

| Syntax | Result | Description |
|--------|--------|-------------|
| `$\times$` | $\times$ | Multiplication |
| `$\div$` | $\div$ | Division |
| `$\pm$` | $\pm$ | Plus-minus |
| `$\leq$` | $\leq$ | Less than or equal |
| `$\geq$` | $\geq$ | Greater than or equal |
| `$\neq$` | $\neq$ | Not equal |

---

## Summation, Integration & Limits

### Summation

$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$

### Integration

$
\int_0^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
$

### Limits

$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$

---

## Matrices

### Matrix with Parentheses

$
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$

### Matrix with Brackets

$
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{bmatrix}
$

---

## Classic Formula Examples

### Euler's Formula

$
e^{i\pi} + 1 = 0
$

### Taylor Expansion

$
e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}
$

### Maxwell's Equations

$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0
\end{aligned}
$

---

## Engine Comparison

### MathJax

**Pros:**
- Most comprehensive, supports almost all LaTeX commands
- High rendering quality
- Right-click menu support

**Cons:**
- Slower loading
- Larger file size

### KaTeX

**Pros:**
- Extremely fast rendering
- Small file size

**Cons:**
- Fewer supported LaTeX commands
- Some complex formulas may not render

---

## References

- [LaTeX Math Symbols](https://www.caam.rice.edu/~heinken/latex/symbols.pdf)
- [MathJax Documentation](https://docs.mathjax.org/)
- [KaTeX Supported Functions](https://katex.org/docs/supported.html)
