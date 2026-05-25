---
subject:
  - Physics
topic:
  - Statistical Physics
aliases:
  - 伊辛模型
  - Ising模型
  - Ising Model
status: Evergreen
date: 2026-05-25
tags:
  - Physics
  - Statistical_Physics
  - Phase_Transition
  - Ising_Model
---

# Ising Model

> **Ising Model** 是统计物理学中研究相变（Phase Transition）和临界现象最经典的格点模型，它通过极其简单的局部自旋相互作用，展现了极为丰富的宏观集体行为与自发对称性破缺（Spontaneous Symmetry Breaking）。

---

## 物理直觉

要理解 Ising Model，首先要建立它的物理图像：**微观的局部“对齐”倾向与宏观温度导致的“无序”热涨落之间的相互竞争**。

### 1. 微观物理图像：自旋与交换作用
考虑一个 $D$ 维的正则格点，每个格点 $i$ 上都有一个经典的“自旋”变量 $s_i$。与真正的量子自旋不同，在经典 Ising 模型中，自旋只有两个可能的取值：
- $s_i = +1$ （自旋向上，$\uparrow$）
- $s_i = -1$ （自旋向下，$\downarrow$）

相邻两个格点 $i$ 和 $j$ 之间的相互作用由**交换耦合常数 (Exchange Interaction)** $J$ 描述：
- **铁磁性 (Ferromagnetic, $J > 0$)**：当相邻自旋方向一致时（同为 $+1$ 或 $-1$），系统能量降低。这驱使系统在低温下走向所有自旋同向对齐的**有序态**。
- **反铁磁性 (Antiferromagnetism, $J < 0$)**：当相邻自旋方向相反时，系统能量降低，驱使自旋呈交错排列。
- **外磁场 (External Magnetic Field)** $h$：倾向于将所有自旋拉向外磁场的方向。

> [!TIP] 物理直觉：能量与熵的博弈
> 系统的热力学状态由平衡态下的亥姆霍兹自由能 $F = U - TS$ 决定（其中 $U$ 是内能，$T$ 是温度，$S$ 是熵）。
> - **在极低温度下（$T \to 0$）**：自由能主要由内能 $U$ 决定。为了使内能最小，铁磁 Ising 模型中的自旋会倾向于全部朝同一方向排列（自发磁化），这是一种**高度有序的基态**。
> - **在极高温度下（$T \to \infty$）**：自由能主要由熵项 $-TS$ 决定。为了使熵最大，自旋会剧烈地发生热涨落，完全随机地指向各个方向，系统处于**完全无序的无磁性状态**。
> - **临界温度（$T_c$）**：在这两个极限之间，必定存在一个相变的临界温度 $T_c$。在 $T < T_c$ 时，微观的对齐作用克服了热涨落，系统产生宏观磁化；在 $T > T_c$ 时，热涨落彻底摧毁了宏观的有序排列。

### 2. 维度对相变的影响 (维度灾难与 Peierls 论证)
Ising 模型的相变行为与空间维度 $D$ 密切相关：
- **$D = 1$ (一维 Ising 模型)**：在任何有限温度 $T > 0$ 下，**都不存在**自发的磁性相变。这是因为在一维链中，打破一条键（产生一个畴壁 Domain Wall）只需要消耗有限的能量（$2J$），但这一畴壁可以在整条链的 $N$ 个位置任意放置，带来的熵增益正比于 $k_B \ln N$。在热力学极限下（$N \to \infty$），熵的贡献总是压倒能量的代价，因此任何热涨落都会把长程有序撕成碎片。
- **$D \ge 2$ (二维及以上 Ising 模型)**：在低温下**存在**铁磁相变。以二维格点为例，如果存在一个畴，其畴壁（Domain Wall）的长度正比于畴的周长。要摧毁长程有序，需要形成一条闭合的、无限长的畴壁，这需要消耗正比于边界长度的能量。Peierls 论证（Peierls Argument）严格证明了当温度足够低时，大尺度无序畴的概率呈指数衰减，从而使宏观自发磁化稳定存在。

---

## 核心定义与公式

### 1. 哈密顿量 (Hamiltonian)
Ising 模型的总能量由以下哈密顿量描述：
$$ H = -J \sum_{\langle i, j \rangle} s_i s_j - h \sum_i s_i $$

其中：
- $\langle i, j \rangle$ 表示只对**最近邻 (Nearest Neighbors)** 格点对进行求和。
- $J$ 是交换作用常数。
- $h$ 是外磁场强度（已吸收磁矩因子）。
- $s_i \in \{+1, -1\}$。

### 2. 配分函数与热力学物理量
根据正则系综，系统的**配分函数 (Partition Function)** $Z$ 为：
$$ Z = \sum_{\{s\}} e^{-\beta H} = \sum_{s_1 = \pm 1} \sum_{s_2 = \pm 1} \dots \sum_{s_N = \pm 1} \exp\left( \beta J \sum_{\langle i, j \rangle} s_i s_j + \beta h \sum_i s_i \right) $$

这里 $\beta = \frac{1}{k_B T}$。一旦求得 $Z$，所有的热力学量均可通过配分函数推导：
- **每个自旋的自由能 (Free Energy per Spin)**：
  $$ f = -\frac{1}{\beta N} \ln Z $$
- **平均磁化强度 (Magnetization per Spin)** $m$：
  $$ m = \langle s_i \rangle = -\frac{\partial f}{\partial h} = \frac{1}{\beta N} \frac{\partial \ln Z}{\partial h} $$
- **磁化率 (Magnetic Susceptibility)** $\chi$：
  $$ \chi = \frac{\partial m}{\partial h} = \beta N \left( \langle s^2 \rangle - \langle s \rangle^2 \right) $$

---

## 1D Ising 模型的严格求解：转移矩阵法 (Transfer Matrix Method)

为了解析求解一维含有 $N$ 个自旋的 Ising 模型，我们采用**转移矩阵法**。这是一种极为优美的方法，将格点求和问题转化为线性代数的特征值问题，非常契合表象理论与算符形式的物理思维。

为了消除边界效应，我们引入**周期性边界条件 (Periodic Boundary Condition)**：$s_{N+1} = s_1$。此时一维哈密顿量可写为：
$$ H = -J \sum_{i=1}^N s_i s_{i+1} - \frac{h}{2} \sum_{i=1}^N (s_i + s_{i+1}) $$

配分函数 $Z$ 可以分解为格点对的乘积：
$$ Z = \sum_{s_1, \dots, s_N = \pm 1} \prod_{i=1}^N \exp\left( \beta J s_i s_{i+1} + \frac{\beta h}{2} (s_i + s_{i+1}) \right) $$

### 1. 引入转移矩阵
我们定义一个 $2 \times 2$ 的**转移矩阵 (Transfer Matrix)** $P$，其矩阵元对应两个相邻自旋状态 $s_i$ 和 $s_{i+1}$ 之间的玻尔兹曼因子：
$$ P_{s_i, s_{i+1}} = \exp\left( \beta J s_i s_{i+1} + \frac{\beta h}{2} (s_i + s_{i+1}) \right) $$

由于 $s_i, s_{i+1} \in \{+1, -1\}$，转移矩阵在基底 $\{|+\rangle, |-\rangle\}$ 下的显式矩阵表示为：
$$ P = \begin{pmatrix} P_{++} & P_{+-} \\ P_{-+} & P_{--} \end{pmatrix} = \begin{pmatrix} e^{\beta J + \beta h} & e^{-\beta J} \\ e^{-\beta J} & e^{\beta J - \beta h} \end{pmatrix} $$

利用矩阵乘法的定义，配分函数 $Z$ 可以写为转移矩阵之积的迹（Trace）：
$$ Z = \sum_{s_1, \dots, s_N} P_{s_1, s_2} P_{s_2, s_3} \dots P_{s_N, s_1} = \text{Tr}(P^N) $$

### 2. 矩阵对角化与特征值
因为 $P$ 是一个实对称矩阵，可以通过相似变换进行对角化。设其特征值为 $\lambda_1$ 和 $\lambda_2$（且 $\lambda_1 > \lambda_2$）：
$$ Z = \text{Tr}(P^N) = \lambda_1^N + \lambda_2^N $$

求解特征方程 $\det(P - \lambda I) = 0$：
$$ \begin{vmatrix} e^{\beta J + \beta h} - \lambda & e^{-\beta J} \\ e^{-\beta J} & e^{\beta J - \beta h} - \lambda \end{vmatrix} = 0 $$
$$ \lambda^2 - \lambda \left( e^{\beta J + \beta h} + e^{\beta J - \beta h} \right) + \left( e^{2\beta J} - e^{-2\beta J} \right) = 0 $$
$$ \lambda^2 - 2 \lambda e^{\beta J} \cosh(\beta h) + 2 \sinh(2\beta J) = 0 $$

解得特征值为：
$$ \lambda_{1, 2} = e^{\beta J} \cosh(\beta h) \pm \sqrt{e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J}} $$

### 3. 热力学极限下的解析结果
在热力学极限下（$N \to \infty$），由于 $\lambda_1 > \lambda_2 \ge 0$，第二特征值项在 $N$ 次方后可以忽略：
$$ \lim_{N \to \infty} \left( \frac{\lambda_2}{\lambda_1} \right)^N = 0 \implies Z \approx \lambda_1^N $$

因此，每个自旋的自由能为：
$$ f = -k_B T \ln \lambda_1 = -k_B T \ln \left[ e^{\beta J} \cosh(\beta h) + \sqrt{e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J}} \right] $$

对此式关于外场 $h$ 求导，我们得到一维 Ising 模型的磁化强度 $m(T, h)$：
$$ m = -\frac{\partial f}{\partial h} = \frac{\sinh(\beta h)}{\sqrt{\sinh^2(\beta h) + e^{-4\beta J}}} $$

> [!WARNING] 一维无自发相变定理的数学确证
> 如果我们在**零外场**（$h = 0$）极限下观察磁化强度：
> $$ m(T, h=0) = \lim_{h \to 0} \frac{\sinh(\beta h)}{\sqrt{\sinh^2(\beta h) + e^{-4\beta J}}} $$
> 
> - 对于任何**有限温度** $T > 0$（即 $\beta < \infty$），分母中的 $e^{-4\beta J} > 0$。因此随着 $h \to 0$，分子 $\sinh(\beta h) \to 0$，磁化强度 $m = 0$。**系统完全没有自发磁化**！
> - 只有在**绝对零度** $T = 0$（即 $\beta \to \infty$）时，分母中的 $e^{-4\beta J} \to 0$。此时极限与求和顺序不可交换，在 $h \to 0^+$ 时 $m = 1$，系统才展现出完美的自旋对齐（基态简并）。这说明一维 Ising 模型在任何非零温度下均没有相变。

---

## 2D Ising 模型与 Onsager 严格解

二维 Ising 模型的求解是现代统计物理的丰碑之一，由 Lars Onsager 于 1944 年解析给出。

### 1.  Onsager 临界温度 $T_c$
在零外磁场（$h = 0$）下，二维正方格点铁磁 Ising 模型的配分函数在以下临界温度 $T_c$ 处发生非解析的相变：
$$ \sinh\left(\frac{2J}{k_B T_c}\right) = 1 \implies \frac{k_B T_c}{J} = \frac{2}{\ln(1+\sqrt{2})} \approx 2.26918 $$

### 2. 自发磁化强度 (Spontaneous Magnetization)
当温度降至 $T_c$ 以下时，即使外磁场 $h = 0$，系统也会表现出宏观的磁性。Onsager 导出的零磁场自发磁化强度为（由 Yang 1952 年严格证明）：
$$ m(T) = \begin{cases} \left[ 1 - \sinh^{-4}\left( \frac{2J}{k_B T} \right) \right]^{1/8}, & T < T_c \\ 0, & T \ge T_c \end{cases} $$

当温度逼近临界点时，自发磁化强度的行为表现为幂律衰减：
$$ m(T) \propto (T_c - T)^\beta $$
其中 $\beta = 1/8 = 0.125$ 是二维 Ising 模型的**临界指数 (Critical Exponent)**。这证实了该相变属于**连续相变（二级相变）**。

---

## 📐 核心公式摘要

| 物理符号 | 物理含义 | 公式/表达式 |
| :--- | :--- | :--- |
| $H$ | Ising 模型哈密顿量 | $H = -J \sum_{\langle i, j \rangle} s_i s_j - h \sum_i s_i$ |
| $P$ | 一维 Ising 模型转移矩阵 | $P = \begin{pmatrix} e^{\beta J + \beta h} & e^{-\beta J} \\ e^{-\beta J} & e^{\beta J - \beta h} \end{pmatrix}$ |
| $Z_{1D}$ | 一维 Ising 周期性边界配分函数 | $Z = \text{Tr}(P^N) = \lambda_1^N + \lambda_2^N$ |
| $m_{1D}$ | 一维有限外磁场磁化强度 | $m = \frac{\sinh(\beta h)}{\sqrt{\sinh^2(\beta h) + e^{-4\beta J}}}$ |
| $T_c^{(2D)}$ | 二维正方格点临界相变温度 | $k_B T_c / J = \frac{2}{\ln(1+\sqrt{2})} \approx 2.269$ |
| $m_{2D}$ | 二维零外场自发磁化强度 | $m = \left[ 1 - \sinh^{-4}\left( \frac{2J}{k_B T} \right) \right]^{1/8} \quad (T < T_c)$ |

---

## 🎨 二维自发磁化与一维磁化对比图

在零磁场下，一维和二维 Ising 模型的行为截然不同：一维自发磁化恒为 0，而二维在 $T < T_c$ 下存在自发磁化。通过以下 Python 代码，我们可以直观绘制出这种非平庸的物理行为。

```python
import matplotlib.pyplot as plt
import numpy as np

# 1. 2D Ising Spontaneous Magnetization (Onsager's Exact Solution)
# Tc in units of J/kB
tc_2d = 2.0 / np.log(1.0 + np.sqrt(2.0))

def m_2d_onsager(t):
    # Only defined for T < Tc
    if t >= tc_2d:
        return 0.0
    val = 1.0 - np.sinh(2.0 / t)**(-4)
    if val < 0:
        return 0.0
    return val**(0.125)

# 2. 1D Ising Magnetization under small external field h
def m_1d(t, h):
    # m = sinh(beta*h) / sqrt(sinh^2(beta*h) + exp(-4*beta*J))
    beta = 1.0 / t
    sinh_bh = np.sinh(beta * h)
    return sinh_bh / np.sqrt(sinh_bh**2 + np.exp(-4.0 * beta))

# Generate temperature range
t_vals = np.linspace(0.1, 4.0, 500)

# Calculate magnetization curves
m_2d_vals = [m_2d_onsager(t) for t in t_vals]
m_1d_h01 = [m_1d(t, 0.05) for t in t_vals]
m_1d_h02 = [m_1d(t, 0.1) for t in t_vals]
m_1d_h05 = [m_1d(t, 0.2) for t in t_vals]

# Plotting with professional academic style
plt.figure(figsize=(8, 5))

# Plot 2D Spontaneous Magnetization (h=0)
plt.plot(t_vals, m_2d_vals, color='#1f77b4', linewidth=3, 
         label=r'2D Spontaneous Magnetization ($h=0$, Exact)')

# Plot 1D Magnetization under various fields
plt.plot(t_vals, m_1d_h01, color='#ff7f0e', linewidth=1.8, linestyle='--',
         label=r'1D Magnetization ($h/J = 0.05$)')
plt.plot(t_vals, m_1d_h02, color='#2ca02c', linewidth=1.8, linestyle='-.',
         label=r'1D Magnetization ($h/J = 0.1$)')
plt.plot(t_vals, m_1d_h05, color='#d62728', linewidth=1.8, linestyle=':',
         label=r'1D Magnetization ($h/J = 0.2$)')

# Add phase transition threshold indicator
plt.axvline(x=tc_2d, color='#7f7f7f', linestyle=':', alpha=0.8, linewidth=1.5)
plt.text(tc_2d + 0.05, 0.6, r'$k_BT_c/J \approx 2.269$', fontsize=11, color='#4f4f4f')

# Format details
plt.xlabel(r'Temperature $k_B T / J$', fontsize=12)
plt.ylabel(r'Magnetization $m$', fontsize=12)
plt.title('Ising Model Magnetization: 1D vs 2D Phase Transition', fontsize=13, fontweight='bold')
plt.xlim(0.1, 4.0)
plt.ylim(-0.05, 1.05)
plt.grid(alpha=0.3, ls=':')
plt.legend(frameon=False, loc='upper right', fontsize=10)
plt.tight_layout()
plt.show()
```

---

## 相关概念

- [[Spontaneous-Symmetry-Breaking|Spontaneous Symmetry Breaking (自发对称性破缺)]]
- [[Bose-Einstein-Distribution|Bose-Einstein Distribution (玻色-爱因斯坦分布)]]
- [[Gaussian-Integral|Gaussian Integral (高斯积分)]]
- [[Method-of-Separation-of-Variables|Separation of Variables (分离变量法)]]

---

## 📝 更新记录

- 2026-05-25: 创建初稿，详尽补充 1D 转移矩阵法与 2D Onsager 自发磁化解，并配备专业英文学术图表。
