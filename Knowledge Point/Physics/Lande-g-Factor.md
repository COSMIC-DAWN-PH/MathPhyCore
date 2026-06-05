---
subject:
  - Physics
topic:
  - Quantum Mechanics
  - Atomic Physics
source: "Griffiths QM, Ch.7; Bransden & Joachain"
comprehension: vague
aliases:
  - 朗德 g 因子
  - Landé g-factor
  - g 因子
status: Draft
date: 2026-06-04
tags:
  - Quantum_Mechanics
  - Atomic_Physics
  - Zeeman_Effect
  - Magnetic_Moment
  - Spectroscopy
---

# Lande-g-Factor（朗德 g 因子）

> 原子态在磁场中的能级分裂大小取决于**朗德 g 因子**——它综合了轨道角动量 $L$、自旋 $S$ 和总角动量 $J$ 的贡献，是计算塞曼效应分裂的必备工具。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 轨道运动和自旋都产生磁矩，但它们的磁矩强度不同（轨道的 $g_L=1$，自旋的 $g_S \approx 2$）。朗德 g 因子告诉我们在给定的原子态中，"有效的磁矩强度"是多大。$g_J$ 越大，能级在磁场中分裂得越开。

---

## 核心定义与公式

### 1. 原子磁矩的一般形式

在 L-S 耦合下，原子态 ${}^{2S+1}L_J$ 的有效磁矩为：

$$
\boldsymbol{\mu}_J = -g_J \mu_B \frac{\mathbf{J}}{\hbar}
$$

其中 $g_J$ 是朗德 g 因子。

### 2. 朗德 g 因子公式

对于 $L$-$S$ 耦合的原子态 ${}^{2S+1}L_J$：

$$
\boxed{g_J = 1 + \frac{J(J+1) + S(S+1) - L(L+1)}{2J(J+1)}}
$$

> [!warning] 公式不适用于纯轨道或纯自旋的情况
> 当 $L = 0$ 时，$g_J = g_S \approx 2$（纯自旋贡献）。
> 当 $S = 0$ 时，$g_J = 1$（纯轨道贡献）。
> 公式本身自动包含了这两个极限。

### 3. 推导思路

总磁矩：

$$
\boldsymbol{\mu} = \boldsymbol{\mu}_L + \boldsymbol{\mu}_S = -\frac{\mu_B}{\hbar}(\mathbf{L} + 2\mathbf{S})
$$

由于 $\mathbf{L}$ 和 $\mathbf{S}$ 绕 $\mathbf{J}$ 进动（$\mathbf{J}$ 是运动常数），只有 $\boldsymbol{\mu}$ 在 $\mathbf{J}$ 方向上的投影有物理意义：

$$
\mu_J = \boldsymbol{\mu} \cdot \frac{\mathbf{J}}{|\mathbf{J}|}
$$

利用 $\mathbf{L} = \mathbf{J} - \mathbf{S}$ 和 $\mathbf{S} \cdot \mathbf{J} = \frac{1}{2}(J^2 + S^2 - L^2)$：

$$
\mu_J = -\frac{\mu_B}{\hbar}\left[1 + \frac{J(J+1) + S(S+1) - L(L+1)}{2J(J+1)}\right]J
$$

> [!info] 为什么 $g$ 因子介于 1 和 2 之间？
> 纯轨道运动 $g_L=1$（对应经典电流环），纯自旋 $g_S=2$（Dirac 方程预言）。朗德 g 因子本质上是两者的加权平均，权重由 $L$ 和 $S$ 在 $\mathbf{J}$ 中的"投影份额"决定。

> [!question] 待深入：朗德 g 因子推导的量子力学细节
> 推导思路中直接使用了"投影定理"$\boldsymbol{\mu} \cdot \hat{\mathbf{J}} = \frac{\langle \boldsymbol{\mu} \cdot \hat{\mathbf{J}} \rangle}{J(J+1)\hbar^2} \hat{\mathbf{J}}$，但这一步的严格量子力学论证需要从 $[\hat{J}_i, \hat{J}_j] = i\hbar\epsilon_{ijk}\hat{J}_k$ 出发，利用 Wigner-Eckart 定理来证明。关键问题：
>
> 1. 为什么 $\langle J, m_J | \boldsymbol{\mu} | J, m_J' \rangle$ 只有 $m_J = m_J'$ 分量非零？
> 2. 投影定理中分母 $J(J+1)\hbar^2$ 的来源是什么？
> 3. $\mathbf{S} \cdot \mathbf{J} = \frac{1}{2}(J^2 + S^2 - L^2)$ 这步代数操作的物理意义是什么？
>
> 参见 [[Study-Roadmap|学习路径]] 中的学习疑问。

### 4. 特殊情况

| 态 | $L$ | $S$ | $J$ | $g_J$ |
|----|-----|-----|-----|-------|
| ${}^1S_0$ | 0 | 0 | 0 | — (无磁矩) |
| ${}^2S_{1/2}$ | 0 | 1/2 | 1/2 | 2 |
| ${}^2P_{1/2}$ | 1 | 1/2 | 1/2 | 2/3 |
| ${}^2P_{3/2}$ | 1 | 1/2 | 3/2 | 4/3 |
| ${}^3P_1$ | 1 | 1 | 1 | 3/2 |
| ${}^1P_1$ | 1 | 0 | 1 | 1 |

---

## 关键性质

- $g_J$ 完全由 $L, S, J$ 决定（已知耦合方案下）
- $S=0$ 的单重态：$g_J = 1$（无自旋贡献，纯轨道磁矩）
- $L=0$ 的 $S$ 态：$g_J = 2$（纯自旋贡献）
- 塞曼分裂的间距直接正比于 $g_J$

> [!warning] 反常塞曼效应的关键
> $g_J = 1$ 时（正常塞曼效应），能级分裂为三个等间距的子能级（$m_J = 0, \pm 1$）。$g_J \neq 1$ 时（反常塞曼效应），分裂间距不等——这就是"反常"的含义，也是 $g$ 因子最重要的应用。

---

## 与其他知识的联系

- [[Zeeman-Effect|塞曼效应]] — 朗德 g 因子直接决定分裂间距
- [[Electron-Spin|电子自旋]] — $g_S \approx 2$ 是朗德公式的自旋来源
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — $g$ 因子综合了 $L$ 和 $S$ 的贡献
- [[Fine-Structure|精细结构]] — 精细结构能级标记 ${}^{2S+1}L_J$ 直接用于计算 $g_J$
- [[Magnetic-Moment|磁矩]] — $\mu_J = -g_J \mu_B J / \hbar$
- [[Angular-Momentum-Coupling|角动量耦合]] — L-S 耦合下 $g_J$ 公式成立

---

## 典型应用场景

- **计算塞曼分裂间距**：$\Delta E = g_J \mu_B B \cdot m_J$
- **光谱学**：判断跃迁的偏振特性需要知道初末态的 $g_J$
- **中性原子量子计算**：选择定则 $\Delta m_J = 0, \pm 1$ 依赖于 Zeeman 子能级的标记

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $g_J$ | 朗德 g 因子 | $1 + \frac{J(J+1) + S(S+1) - L(L+1)}{2J(J+1)}$ |
| $\mu_J$ | 原子有效磁矩 | $-g_J \mu_B \mathbf{J}/\hbar$ |
| $\Delta E$ | 塞曼分裂间距 | $g_J \mu_B B$（相邻 $m_J$ 之间） |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 朗德 g 因子公式、推导思路、特殊情况表
