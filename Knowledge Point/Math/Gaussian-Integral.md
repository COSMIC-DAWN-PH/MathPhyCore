---
subject:
  - Math
topic:
  - Calculus
aliases:
  - 高斯积分
  - Gaussian Integral
  - 概率积分
  - Gauss积分
source: "self-authored (数学物理方法课程整理)"
comprehension: understood
status: WIP
date: 2026-05-25
tags:
  - Math
  - Calculus
  - Integration
  - Gaussian
---

# Gaussian Integral (高斯积分)

## 物理直觉

高斯积分是数学物理中最常出现的积分之一，核心形式是

$$\int_{-\infty}^{\infty} e^{-a x^2}\,dx$$

它描述的是"钟形曲线下的面积"。为什么它无处不在？因为**凡是出现 $e^{-x^2}$ 的地方，几乎必然涉及归一化、概率、或热力学权重**：

- **量子力学**：谐振子基态波函数 $\psi_0(x) \propto e^{-m\omega x^2/2\hbar}$ 的归一化；
- **统计物理**：配分函数 $Z = \int e^{-\beta H} d\Gamma$ 中动能项是 $\int e^{-\beta p^2/2m} dp$；
- **概率论**：正态分布 $N(\mu,\sigma^2)$ 的归一化常数；
- **路径积分**：自由粒子传播子本质上是一个高斯积分。

> [!info] 历史注记
> 这个积分最早由 de Moivre (1733) 在研究二项分布的极限时遇到，后来由 Laplace 和 Gauss 系统化。Poisson 在 1809 年前后也独立推导过，因此有时也叫 Poisson 积分或 Euler-Poisson 积分。

---

## 一维基本形式

### 核心公式

$$\boxed{\int_{-\infty}^{\infty} e^{-a x^2}\,dx = \sqrt{\frac{\pi}{a}},\qquad \operatorname{Re}(a) > 0}$$

> [!tip] 记忆技巧
> 注意到 $\sqrt{\pi}$ 出现的根本原因：在极坐标系中半径 $r$ 从 $0$ 到 $\infty$，角度 $\theta$ 从 $0$ 到 $2\pi$，因此 $\pi$ 来自角度积分的一半（平方根）。

### 经典推导——极坐标变换

考虑 $I = \int_{-\infty}^{\infty} e^{-a x^2} dx$，构造其平方：

$$I^2 = \left(\int_{-\infty}^{\infty} e^{-a x^2}dx\right)\left(\int_{-\infty}^{\infty} e^{-a y^2}dy\right) = \int_{-\infty}^{\infty}\int_{-\infty}^{\infty} e^{-a(x^2+y^2)}\,dx\,dy$$

转为极坐标 $(x,y) \to (r,\theta)$，其中 $dx\,dy = r\,dr\,d\theta$：

$$I^2 = \int_{0}^{2\pi}\int_{0}^{\infty} e^{-a r^2} r\,dr\,d\theta$$

令 $u = r^2$，$du = 2r\,dr$：

$$I^2 = \int_{0}^{2\pi} d\theta \cdot \int_{0}^{\infty} e^{-a u} \frac{du}{2} = 2\pi \cdot \frac{1}{2a} = \frac{\pi}{a}$$

因此 $I = \sqrt{\pi/a}$（取正根，因为被积函数 $>0$）。

> [!warning] 常见错误
> 不要忘记 Jacobian $r$！直接写成 $\iint e^{-a(x^2+y^2)} dxdy \to \iint e^{-a r^2} dr d\theta$ 是错的，正确是 $\iint e^{-a r^2} r\,dr\,d\theta$。

---

## 推广形式

### 带线性项的配方技巧

$$\boxed{\int_{-\infty}^{\infty} e^{-a x^2 + b x}\,dx = \sqrt{\frac{\pi}{a}}\;\exp\left(\frac{b^2}{4a}\right),\qquad \operatorname{Re}(a) > 0}$$

**推导**：配方法（complete the square）：

$$-a x^2 + b x = -a\left(x^2 - \frac{b}{a}x\right) = -a\left(x - \frac{b}{2a}\right)^2 + \frac{b^2}{4a}$$

然后平移积分变量 $x \to x + \frac{b}{2a}$，积分限不变：

$$\int_{-\infty}^{\infty} e^{-a\left(x - \frac{b}{2a}\right)^2 + \frac{b^2}{4a}}\,dx = e^{b^2/4a} \cdot \sqrt{\frac{\pi}{a}}$$

### 高斯矩（Gaussian Moments）

利用生成函数 $I(b) = \int_{-\infty}^{\infty} e^{-a x^2 + b x}\,dx$ 对 $b$ 求导可获得各阶矩：

$$\int_{-\infty}^{\infty} x^{2n} e^{-a x^2}\,dx = \left.\frac{\partial^{2n}}{\partial b^{2n}} I(b)\right|_{b=0}$$

常见结果（用 Gamma 函数表达）：

$$\boxed{\int_{-\infty}^{\infty} x^{2n} e^{-a x^2}\,dx = \frac{\Gamma\left(n + \frac{1}{2}\right)}{a^{n + 1/2}} = \frac{(2n-1)!!}{2^n a^n}\sqrt{\frac{\pi}{a}}}$$

奇数次幂积分为零（被积函数是奇函数）：

$$\int_{-\infty}^{\infty} x^{2n+1} e^{-a x^2}\,dx = 0$$

> [!tip] 双阶乘记忆
> $(2n-1)!! = 1 \cdot 3 \cdot 5 \cdots (2n-1)$。例如 $n=1$ 时 $(1)!! = 1$，得到 $\langle x^2 \rangle = 1/(2a)$——这就是正态分布 $\sigma^2$ 的由来。

### 误差函数 (Error Function)

半无限区间的高斯积分无法用初等函数表达，由此定义误差函数：

$$\operatorname{erf}(z) = \frac{2}{\sqrt{\pi}} \int_0^z e^{-t^2}\,dt$$

从而：

$$\int_0^{\infty} e^{-a x^2}\,dx = \frac{1}{2}\sqrt{\frac{\pi}{a}},\qquad \int_{-\infty}^{z} e^{-a x^2}\,dx = \frac{1}{2}\sqrt{\frac{\pi}{a}}\Big[1 + \operatorname{erf}(\sqrt{a}\,z)\Big]$$

---

## 高维推广

多变量高斯积分是多元统计和场论的基石：

$$\boxed{\int_{\mathbb{R}^n} \exp\left(-\frac{1}{2}\mathbf{x}^T A \mathbf{x} + \mathbf{b}^T \mathbf{x}\right) d^n\mathbf{x} = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}\;\exp\left(\frac{1}{2}\mathbf{b}^T A^{-1} \mathbf{b}\right)}$$

**条件**：$A$ 是 $n \times n$ 正定实对称矩阵。推导思路：对 $A$ 做正交对角化 $A = O^T \Lambda O$，换元后分解为 $n$ 个独立的一维高斯积分相乘。

> [!info] 场论中的应用
> 路径积分中，自由场的作用量 $S = \frac{1}{2}\int \phi(-\partial^2+m^2)\phi\,d^4x$ 本身就是无穷维高斯积分。配分函数 $Z[J] \propto \exp\left(\frac{1}{2}J G J\right)$ 就是上述公式的无穷维推广，其中 $G$ 是 Green 函数（算子 $-\partial^2+m^2$ 的逆核）。

---

## 物理应用概述

| 领域 | 应用 | 形式 |
|------|------|------|
| 量子力学 | 谐振子基态归一化 | $\int \lvert\psi_0\rvert^2 dx \propto \int e^{-m\omega x^2/\hbar} dx$ |
| 统计物理 | Maxwell 速度分布 | $\int e^{-mv^2/2k_BT} d^3v$ |
| 统计物理 | 配分函数动能部分 | $\int e^{-\beta p^2/2m} d^3p$ |
| 概率论 | 正态分布归一化 | $\int e^{-(x-\mu)^2/2\sigma^2} dx = \sigma\sqrt{2\pi}$ |
| 量子场论 | 自由场传播子 | $\int \mathcal{D}\phi\, e^{iS[\phi]}$ 的 Gauss 近似 |
| 固体物理 | 紧束缚模型 | $e^{-k^2 a^2}$ 能动量关系中的积分 |

---

## Python 图示

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

x = np.linspace(-4, 4, 400)

fig, axes = plt.subplots(1, 2, figsize=(12, 5))

# 左图：不同 a 值的高斯函数
alphas = [0.25, 0.5, 1.0, 2.0]
colors = ['#2ecc71', '#3498db', '#9b59b6', '#e74c3c']
for a, c in zip(alphas, colors):
    y = np.exp(-a * x**2)
    sigma = 1/np.sqrt(2*a)
    axes[0].plot(x, y, color=c, linewidth=2,
                 label=r'$a=' + str(a) + r',\;\sigma=' + f'{sigma:.2f}' + r'$')
axes[0].set_xlabel('$x$', fontsize=12)
axes[0].set_ylabel(r'$e^{-ax^2}$', fontsize=12)
axes[0].set_title(r'Gaussian 函数: $f(x)=e^{-ax^2}$', fontsize=13)
axes[0].legend(fontsize=10, framealpha=0.8)
axes[0].grid(alpha=0.3)
axes[0].set_ylim(0, 1.05)

# 右图：面积归一化验证
a_fix = 1.0
x_dense = np.linspace(-5, 5, 500)
y_dense = np.exp(-a_fix * x_dense**2)
integral_approx = np.trapezoid(y_dense, x_dense)
theoretical = np.sqrt(np.pi / a_fix)

axes[1].fill_between(x_dense, y_dense, alpha=0.4, color='#3498db')
axes[1].plot(x_dense, y_dense, color='#2980b9', linewidth=2)
axes[1].set_xlabel('$x$', fontsize=12)
axes[1].set_ylabel(r'$e^{-x^2}$', fontsize=12)
axes[1].set_title(
    r'面积: $\int_{-\infty}^{\infty}e^{-x^2}dx' +
    rf'\approx {integral_approx:.4f}$' + '\n' +
    rf'($\sqrt{{\pi}}={theoretical:.4f}$)',
    fontsize=13
)
axes[1].grid(alpha=0.3)

plt.tight_layout()
plt.show()
```

---

## 📐 核心公式摘要

| 公式 | 表达式 |
|------|--------|
| 一维基本 | $\displaystyle \int_{-\infty}^{\infty} e^{-a x^2} dx = \sqrt{\frac{\pi}{a}}$ |
| 带线性项 | $\displaystyle \int_{-\infty}^{\infty} e^{-ax^2+bx} dx = \sqrt{\frac{\pi}{a}}\;e^{b^2/4a}$ |
| 偶数阶矩 | $\displaystyle \int_{-\infty}^{\infty} x^{2n} e^{-a x^2} dx = \frac{(2n-1)!!}{2^n a^n}\sqrt{\frac{\pi}{a}}$ |
| 半无限 | $\displaystyle \int_{0}^{\infty} e^{-a x^2} dx = \frac{1}{2}\sqrt{\frac{\pi}{a}}$ |
| $n$ 维多变量 | $\displaystyle \int_{\mathbb{R}^n} e^{-\frac{1}{2}\mathbf{x}^T A \mathbf{x}} d^n\mathbf{x} = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}$ |
| 正态分布归一化 | $\displaystyle \int_{-\infty}^{\infty} e^{-(x-\mu)^2/2\sigma^2} dx = \sigma\sqrt{2\pi}$ |

---

## 相关概念

- [[Ising-Model|Ising Model (伊辛模型)]] — 平均场理论和配分函数中频繁用到高斯积分
- [[Bose-Einstein-Distribution|Bose-Einstein Distribution (玻色-爱因斯坦分布)]] — 动量空间的积分本质上就是高斯积分
- [[Method-of-Separation-of-Variables|Separation of Variables (分离变量法)]] — 分离出的空间部分常得到 Hermite 多项式，其权重函数 $e^{-x^2/2}$ 的归一化依赖高斯积分
- [[Unitary-Matrix|Unitary Matrix (酉矩阵)]] — 多变量高斯积分中对协方差矩阵做酉对角化

---

## 📝 更新记录

- 2026-05-25: 从 Draft 大幅扩展到 In-Progress：补充物理直觉、一维基本推导、推广形式（线性项、矩公式、误差函数）、高维多变量高斯积分、物理应用表、Python 图示、核心公式摘要、双向链接
