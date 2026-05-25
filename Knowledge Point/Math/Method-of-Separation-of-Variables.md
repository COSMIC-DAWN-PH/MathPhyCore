---
subject:
  - Math
topic:
  - PDE
aliases:
  - 分离变量
  - Separation of Variables
  - 分离变量法
  - Fourier方法
status: In-Progress
date: 2026-05-25
tags:
  - Math
  - PDE
  - ODE
  - Sturm-Liouville
---

# Method of Separation of Variables (分离变量法)

## 核心思想

分离变量法是求解线性偏微分方程（PDE）**最经典、最直观**的方法。核心理念一句话：

> 把多变量 PDE **分解**成多个单变量 ODE，分别求解后再**叠加**回来。

具体步骤：

1. **假设分离形式**：$u(x,t) = X(x)\,T(t)$（以一维含时问题为例）
2. **代入 PDE**：将乘积形式代入原方程
3. **分离变量**：将与 $x$ 有关的部分和与 $t$ 有关的部分分到等号两边，令两者等于同一个**分离常数**（separation constant）$-\lambda$（或 $\lambda$）
4. **解 ODE**：得到空间部分的 ODE $X'' + \lambda X = 0$ 和时间部分的 ODE $T' + \alpha\lambda T = 0$
5. **施加边界条件**：空间 ODE + 边界条件构成 Sturm-Liouville 问题，确定本征值 $\lambda_n$ 和本征函数 $X_n(x)$
6. **叠加**：通解是各本征解的线性组合 $u(x,t) = \sum_n c_n X_n(x) T_n(t)$
7. **初始条件定系数**：利用本征函数的正交性，通过 Fourier 展开确定 $c_n$

> [!info] 为什么能分离？
> 分离变量法能工作，本质上依赖于方程和边界条件的**对称性**（坐标可分离性）。不是所有 PDE 都能分离——例如 $u_{xx} + (1+x)u_{yy} = 0$ 就不能。

> [!tip] 分离常数的物理意义
> 对于含时问题（热方程、波动方程）：
> - 若空间部分 $X'' + \lambda X = 0$ 且时间部分 $T' + \alpha\lambda T = 0$（热方程），则 $\lambda > 0$ 时 $T \propto e^{-\alpha\lambda t}$ → 衰减；
> - $\lambda$ 越大 → 空间振荡越快 → 衰减也越快（高频模先消失）。
> - 在量子力学中，分离常数直接就是**能量本征值**，对应的 $X_n(x)$ 就是本征态，$c_n$ 是概率幅。

---

## 一维热方程

### 问题设定

$$\frac{\partial u}{\partial t} = \alpha \frac{\partial^2 u}{\partial x^2},\quad 0 < x < L,\; t > 0$$

**边界条件（Dirichlet）**：$u(0,t) = u(L,t) = 0$
**初始条件**：$u(x,0) = f(x)$

### 分离变量

设 $u(x,t) = X(x)\,T(t)$，代入热方程：

$$X T' = \alpha X'' T \quad\Longrightarrow\quad \frac{T'}{\alpha T} = \frac{X''}{X} = -\lambda$$

得到两个 ODE：

$$\begin{cases}
X'' + \lambda X = 0 \\[4pt]
T' + \alpha\lambda T = 0
\end{cases}$$

### 求本征值和本征函数

空间方程 $X'' + \lambda X = 0$，边界条件 $X(0)=X(L)=0$。

> [!warning] 三种情况都要检查
> $\lambda$ 可以是负、零、正，必须逐一用边界条件筛选。

| $\lambda$ | 通解 | $X(0)=0$ | $X(L)=0$ | 结论 |
|-----------|------|----------|----------|------|
| $\lambda < 0$（设 $\lambda = -k^2$） | $X = Ae^{kx} + Be^{-kx}$ | $A+B=0$ → $X \propto \sinh(kx)$ | $\sinh(kL)=0$ → $k=0$ → 矛盾 | 无非零解 |
| $\lambda = 0$ | $X = Ax + B$ | $B=0$ | $AL=0$ → $A=0$ | 无非零解 |
| $\lambda > 0$（设 $\lambda = k^2$） | $X = A\cos(kx) + B\sin(kx)$ | $A=0$ | $B\sin(kL)=0$ | $\color{#e74c3c}{\sin(kL)=0}$ |

只有 $\lambda > 0$ 有非零解，条件 $\sin(kL)=0$ 给出：

$$k_n = \frac{n\pi}{L},\quad n = 1, 2, 3, \dots$$

因此**本征值**和**本征函数**为：

$$\boxed{\lambda_n = \left(\frac{n\pi}{L}\right)^2},\qquad \boxed{X_n(x) = \sin\left(\frac{n\pi x}{L}\right)}$$

对应的时间部分：$T_n(t) = e^{-\alpha (n\pi/L)^2 t}$

### 通解

$$u(x,t) = \sum_{n=1}^{\infty} b_n \sin\!\left(\frac{n\pi x}{L}\right) e^{-\alpha (n\pi/L)^2 t}$$

系数 $b_n$ 由初始条件 $u(x,0)=f(x)$ 和 Fourier 正弦级数确定：

$$\boxed{b_n = \frac{2}{L}\int_0^L f(x)\,\sin\!\left(\frac{n\pi x}{L}\right) dx}$$

> [!tip] 物理图像
> 初始温度分布 $f(x)$ 被分解为不同频率的正弦模。高频模（大 $n$）按 $e^{-\alpha n^2 \pi^2 t / L^2}$ 指数衰减，**极快消失**。这正是热扩散"抹平尖刺"的数学解释。

---

## 一维波动方程

$$\frac{\partial^2 u}{\partial t^2} = c^2 \frac{\partial^2 u}{\partial x^2},\quad 0 < x < L$$

**边界条件（Dirichlet）**：$u(0,t) = u(L,t) = 0$
**初始条件**：$u(x,0) = f(x)$，$u_t(x,0) = g(x)$

### 分离变量

设 $u = X(x)T(t)$：

$$\frac{T''}{c^2 T} = \frac{X''}{X} = -\lambda$$

空间方程同热方程：$X'' + \lambda X = 0$，边界条件 $X(0)=X(L)=0$ → 相同本征函数 $X_n(x) = \sin(n\pi x/L)$，$\lambda_n = (n\pi/L)^2$。

时间方程变为：$T'' + c^2 \lambda_n T = 0$ → 简谐振子方程：

$$T_n(t) = A_n \cos\!\left(\frac{n\pi c t}{L}\right) + B_n \sin\!\left(\frac{n\pi c t}{L}\right)$$

### 通解（d'Alembert 分解前）

$$u(x,t) = \sum_{n=1}^{\infty} \left[A_n\cos\!\left(\frac{n\pi c t}{L}\right) + B_n\sin\!\left(\frac{n\pi c t}{L}\right)\right] \sin\!\left(\frac{n\pi x}{L}\right)$$

系数由初始条件定：

$$\boxed{A_n = \frac{2}{L}\int_0^L f(x)\sin\!\left(\frac{n\pi x}{L}\right)dx},\qquad \boxed{B_n = \frac{2}{n\pi c}\int_0^L g(x)\sin\!\left(\frac{n\pi x}{L}\right)dx}$$

> [!tip] 与热方程的区别
> 波动方程的时间部分是**振荡**（$\cos, \sin$），热方程的时间部分是**指数衰减**（$e^{-\alpha\lambda_n t}$）。根本原因：热方程是 $T'$ 一阶耗散，波动方程是 $T''$ 二阶保守。

---

## 二维问题

### 二维方法核心差异

从一维到二维，分离变量法的思路不变，但关键差异在于**分离常数的引入方式**：

一维：$u(x,t) = X(x)T(t)$ → 一个分离常数 $\lambda$（方程两边各自等于同一个常数）

二维：$u(x,y,t) = X(x)Y(y)T(t)$ 或稳态时 $u(x,y) = X(x)Y(y)$ → 需要**两个**分离常数 $\lambda$ 和 $\mu$，且它们通过方程联系起来

**技巧**：将含两个变量的项移到一边后，得到的等式两边必须同时等于同一个常数（因为两边分别是不同变量的函数）。这个常数就是分离常数。每一步分离引入一个新的分离常数。

**数学表达**：

对于稳态方程 $\nabla^2 u = 0$（Laplace），假设 $u(x,y) = X(x)Y(y)$：

$$X''Y + XY'' = 0 \;\Longrightarrow\; \frac{X''}{X} = -\frac{Y''}{Y} = \lambda$$

→ 这一步引入了第一个分离常数 $\lambda$，得到 $X'' - \lambda X = 0$ 和 $Y'' + \lambda Y = 0$。两个 ODE 的符号相反（一个带 $-\lambda$，一个带 $+\lambda$）——这是 Laplace 方程的特征。

各 ODE 再通过各自的边界条件确定允许的 $\lambda$ 值。


### 矩形区域 Laplace 方程

$$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0,\quad 0 < x < a,\; 0 < y < b$$

设 $u(x,y) = X(x)Y(y)$：

$$\frac{X''}{X} = -\frac{Y''}{Y} = \lambda$$

> [!warning] 注意符号选择
> 这里把 $\lambda$ 放在 $X$ 一侧。如果交换 $\lambda \to -\lambda$，解的形式不变但表达式不同。物理上要根据哪个方向有齐次边界条件来决定 $\lambda$ 的符号。

若 $X(0)=X(a)=0$（$x$ 方向 Dirichlet 齐次），则取 $\lambda < 0$，设 $\lambda = -k^2$：

- $X'' + k^2 X = 0$ → $X_n(x) = \sin(n\pi x/a)$，$k_n = n\pi/a$
- $Y'' - k^2 Y = 0$ → $Y_n(y) = C_n \sinh(k_n y) + D_n \sinh(k_n(b-y))$

### 圆域 Laplace 方程（极坐标）

极坐标下的 Laplace 算子：

$$\frac{\partial^2 u}{\partial r^2} + \frac{1}{r}\frac{\partial u}{\partial r} + \frac{1}{r^2}\frac{\partial^2 u}{\partial \theta^2} = 0$$

设 $u(r,\theta) = R(r)\Theta(\theta)$：

$$\frac{r^2 R'' + r R'}{R} = -\frac{\Theta''}{\Theta} = \lambda$$

- **角度方程**：$\Theta'' + \lambda \Theta = 0$，周期条件 $\Theta(\theta+2\pi)=\Theta(\theta)$ → $\lambda_n = n^2$（$n=0,1,2,\dots$），$\Theta_n(\theta) = A_n\cos(n\theta) + B_n\sin(n\theta)$
- **径向方程**：$r^2 R'' + r R' - n^2 R = 0$ —— 这是 **Euler 方程**！解为 $R_n(r) = C_n r^n + D_n r^{-n}$（或圆内时 $D_n=0$ 去掉原点奇点）

---

## 一般框架：Sturm-Liouville 理论

分离变量法之所以系统有效，是因为它背后有 **Sturm-Liouville 理论**支撑。

空间部分 $X'' + \lambda X = 0$ 是 Sturm-Liouville 方程

$$\frac{d}{dx}\left(p(x)\frac{dX}{dx}\right) + q(x)X + \lambda w(x)X = 0$$

在 $p=1, q=0, w=1$ 时的特例。一般而言：

| 坐标系 | 径向方程 | 本征函数 | 正交权重 |
|--------|----------|----------|----------|
| 直角坐标 $(x)$ | $X'' + \lambda X = 0$ | $\sin, \cos$ | $w=1$ |
| 极坐标 $(r)$ | $r^2 R'' + rR' + (\lambda r^2 - n^2)R = 0$ | Bessel $J_n$ | $w = r$ |
| 球坐标 $(r)$ | 球 Bessel 方程 | 球 Bessel $j_\ell$ | $w = r^2$ |
| 球坐标 $(\theta)$ | Legendre 方程 | $P_\ell(\cos\theta)$ | $w = \sin\theta$ |

> [!info] 核心结论
> Sturm-Liouville 问题保证了：本征函数族 $\{X_n\}$ 是**正交完备**的，所以任何满足边界条件的函数 $f(x)$ 都可以展开为 $\sum c_n X_n(x)$。这就是初始条件定系数这步能操作用的数学基础。

---

## Python 图示：热方程本征模叠加

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

L = 1.0
alpha = 1.0
x = np.linspace(0, L, 300)

# 初始波形: 三角脉冲（Fourier 级数展开）
def u_exact(x, t, n_terms=50):
    result = np.zeros_like(x)
    for n in range(1, n_terms + 1):
        bn = 8 / (np.pi**2 * n**2) * np.sin(n * np.pi / 2)
        result += bn * np.sin(n * np.pi * x / L) * np.exp(-alpha * (n * np.pi / L)**2 * t)
    return result

# 前三个本征模
fig, axes = plt.subplots(1, 2, figsize=(13, 5))

# 左图：前三个本征模
modes = [1, 2, 3]
colors_modes = ['#e74c3c', '#2ecc71', '#3498db']
for n, c in zip(modes, colors_modes):
    Xn = np.sin(n * np.pi * x / L)
    axes[0].plot(x, Xn, color=c, linewidth=2,
                 label=rf'$n={n}$: $\sin({n}\pi x/L)$')
axes[0].set_xlabel('$x$', fontsize=12)
axes[0].set_ylabel('$X_n(x)$', fontsize=12)
axes[0].set_title(r'前三个本征模 (空间部分)', fontsize=13)
axes[0].legend(fontsize=10)
axes[0].grid(alpha=0.3)
axes[0].axhline(y=0, color='gray', linewidth=0.5)

# 右图：不同时刻的温度分布
times = [0.0, 0.002, 0.01, 0.05]
colors_t = ['#2c3e50', '#e74c3c', '#f39c12', '#3498db']
for t_val, c in zip(times, colors_t):
    u = u_exact(x, t_val, n_terms=80)
    axes[1].plot(x, u, color=c, linewidth=2,
                 label=rf'$t={t_val}$')
axes[1].set_xlabel('$x$', fontsize=12)
axes[1].set_ylabel('$u(x,t)$', fontsize=12)
axes[1].set_title(r'热方程 $\partial_t u = \partial_x^2 u$ (Dirichlet 边界)', fontsize=13)
axes[1].legend(fontsize=10)
axes[1].grid(alpha=0.3)
axes[1].set_ylim(-0.05, 0.55)

plt.tight_layout()
plt.show()
```

---

## 📐 核心公式摘要

| 方程类型 | PDE | 空间 ODE | 时间 ODE | 本征函数 |
|----------|-----|----------|----------|----------|
| 热方程 | $u_t = \alpha u_{xx}$ | $X'' + \lambda X = 0$ | $T' + \alpha\lambda T = 0$ | $\sin,\cos$ |
| 波动方程 | $u_{tt} = c^2 u_{xx}$ | $X'' + \lambda X = 0$ | $T'' + c^2\lambda T = 0$ | $\sin,\cos$ |
| Laplace (直角) | $u_{xx} + u_{yy} = 0$ | $X'' + \lambda X = 0$ | $Y'' - \lambda Y = 0$ | $\sin,\cos;\ \sinh,\cosh$ |
| Laplace (极坐标) | $u_{rr} + \frac{1}{r}u_r + \frac{1}{r^2}u_{\theta\theta} = 0$ | 径向: Euler/Bessel | 角度: $\Theta'' + n^2\Theta = 0$ | $\sin,\cos;\ r^n,\ J_n$ |

**本征值**（Dirichlet 边界）：$\lambda_n = (n\pi/L)^2$，$n = 1, 2, 3, \dots$

**Fourier 系数**（热方程 Dirichlet）：$\displaystyle b_n = \frac{2}{L}\int_0^L f(x)\sin\!\left(\frac{n\pi x}{L}\right)dx$

---

## 相关概念

- [[Quantum-Numbers|量子数]] — 量子数就是 Schrödinger 方程分离变量后的空间本征值指标
- [[Bose-Einstein-Distribution|Bose-Einstein Distribution (玻色-爱因斯坦分布)]] — 模式展开和态密度的计算依赖分离变量法
- [[Gaussian-Integral|Gaussian Integral (高斯积分)]] — 分离出的谐振子本征函数的归一化积分

---

## 📝 更新记录

- 2026-05-25: 从 Draft 大幅扩展到 In-Progress：补充核心思想（7 步法）、一维热方程完整推导（含 $\lambda$ 三种情况筛选表）、一维波动方程、二维 Laplace 方程（矩形 + 极坐标）、Sturm-Liouville 一般框架、Python 图示（本征模 + 热扩散时间演化）、核心公式摘要、双向链接
