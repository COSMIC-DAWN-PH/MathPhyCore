---
subject:
  - Physics
topic:
  - Quantum Mechanics
  - Atomic Physics
source: "Griffiths QM, Ch.4; 实验事实"
comprehension: vague
aliases:
  - 电子自旋
  - 自旋角动量
  - Pauli matrices
  - 泡利矩阵
  - electron spin
status: Draft
date: 2026-06-04
tags:
  - Quantum_Mechanics
  - Atomic_Physics
  - Spin
  - Pauli_Matrices
  - Fermion
---

# Electron-Spin（电子自旋）

> 电子的内禀角动量，量子数 $s = 1/2$，没有经典对应——纯粹是量子力学的产物。泡利矩阵是它在自旋 $1/2$ 子空间中的矩阵表示。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 电子自旋就像一个"自带的陀螺"：不管电子在做什么运动，它永远有一个大小为 $\frac{\sqrt{3}}{2}\hbar$ 的内禀角动量。这个角动量只有两个 $z$ 分量——"向上" $+\frac{1}{2}\hbar$ 和"向下" $-\frac{1}{2}\hbar$。自旋不是电子真的在"自转"，而是电子与生俱来的量子自由度。

自旋的存在从 Stern-Gerlach 实验中被直接观测到：银原子束被劈成两条，无法用轨道角动量解释。

---

## 核心定义与公式

### 1. 自旋角动量

自旋是电子的**内禀角动量**，用量子数 $s$ 描述：

$$
s = \frac{1}{2} \quad \text{（固定值，电子的内禀属性）}
$$

自旋算符 $\hat{\mathbf{S}}$ 满足角动量的对易关系：

$$
[\hat{S}_i, \hat{S}_j] = i\hbar \epsilon_{ijk} \hat{S}_k
$$

自旋角动量的大小：

$$
|\hat{\mathbf{S}}| = \hbar\sqrt{s(s+1)} = \frac{\sqrt{3}}{2}\hbar
$$

### 2. 自旋投影（$z$ 分量）

$$
\hat{S}_z |s, m_s\rangle = m_s \hbar |s, m_s\rangle
$$

$$
m_s = -s, -s+1, \ldots, s = -\frac{1}{2}, +\frac{1}{2}
$$

**两种本征态**：
- $|\!\uparrow\rangle = |s=\frac{1}{2}, m_s=+\frac{1}{2}\rangle$：自旋向上
- $|\!\downarrow\rangle = |s=\frac{1}{2}, m_s=-\frac{1}{2}\rangle$：自旋向下

### 3. 泡利矩阵（Pauli Matrices）

自旋 $1/2$ 粒子的自旋算符用 $2 \times 2$ 矩阵表示：

$$
\hat{S}_i = \frac{\hbar}{2} \sigma_i \quad (i = x, y, z)
$$

泡利矩阵为：

$$
\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad
\sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

> [!tip] 泡利矩阵的记忆方法
> - $\sigma_z$：对角线上是 $+1, -1$（对应两个自旋本征态的投影值）
> - $\sigma_x$：非对角线上是 $1$（对应自旋翻转——$|\uparrow\rangle \leftrightarrow |\downarrow\rangle$）
> - $\sigma_y$：非对角线上是 $\pm i$（复相位版的翻转）

**关键代数性质**：

$$
\sigma_i \sigma_j = \delta_{ij} I + i\epsilon_{ijk} \sigma_k
$$

$$
\{\sigma_i, \sigma_j\} = 2\delta_{ij} I \quad \text{（反对易关系）}
$$

$$
\sigma_i^2 = I
$$

### 4. 自旋态的一般形式

任意自旋态可以写成：

$$
|\psi\rangle = \alpha |\!\uparrow\rangle + \beta |\!\downarrow\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}
$$

其中 $\lvert\alpha\rvert^2 + \lvert\beta\rvert^2 = 1$。

### 5. 自旋磁矩

自旋角动量对应的磁矩为：

$$
\boldsymbol{\mu}_s = -g_s \frac{e}{2m_e} \mathbf{S} = -g_s \mu_B \frac{\mathbf{S}}{\hbar}
$$

其中 $g_s \approx 2.0023$ 是电子自旋 $g$ 因子（电子的精确值与 Dirac 理论的 $g_s=2$ 略有偏差，偏差来自 QED 辐射修正）。

> [!warning] 经典预期：自旋 $g$ 因子应为 1
> 对于经典自转球体，$g = 1$。但 Dirac 方程预言 $g_s = 2$，实测值 $2.0023$ 进一步证实自旋没有经典对应——它不是真正的"自转"。

---

## 关键性质

- **$s = 1/2$ 是电子的固有属性**：不可改变，所有电子都是如此
- **自旋 $1/2$ 粒子是费米子**：服从费米-狄拉克统计，多电子波函数反对称
- **泡利不相容原理**：同一原子态最多容纳两个电子（自旋相反）
- **自旋是量子力学的"纯粹产物"**：没有经典对应，Dirac 方程自然导出
- **电子总角动量**：$\mathbf{J} = \mathbf{L} + \mathbf{S}$，自旋与轨道角动量耦合

> [!warning] 常见错误
> 自旋不是"电子绕自身轴旋转"——电子被认为是点粒子（无内部结构）。自旋是纯粹的量子力学自由度，就像电荷和质量一样是内禀属性。

---

## 与其他知识的联系

- [[Stern-Gerlach-Experiment|施特恩-格拉赫实验]] — 自旋存在的最早实验证据
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 自旋磁矩在轨道运动等效磁场中的相互作用
- [[Fine-Structure|精细结构]] — 自旋-轨道耦合导致的能级分裂
- [[Angular-Momentum-Coupling|角动量耦合]] — 自旋与轨道角动量的量子力学合成
- [[Hyperfine-Structure|超精细结构]] — 电子自旋角动量与核自旋的耦合
- [[Zeeman-Effect|塞曼效应]] — 自旋磁矩在外磁场中的能量分裂
- [[Magnetic-Moment|磁矩]] — 自旋磁矩的物理来源
- [[Lande-g-Factor|朗德 g 因子]] — 原子态的有效 $g$ 因子，综合 $L$ 和 $S$ 的贡献

---

## 典型应用场景

- **量子比特的基本载体**：自旋向上/向下天然对应 $|0\rangle$ 和 $|1\rangle$
- **原子能级结构**：自旋-轨道耦合产生精细结构
- **超精细量子比特**：中性原子量子计算中，量子比特编码在超精细基态上（$F = J + I$，其中 $J$ 包含自旋 $S$）
- **EPR/ESR（电子顺磁共振）**：自旋在磁场中的 Rabi 振荡是量子操控的基础

> [!info] Pauli 矩阵在量子计算中的地位
> 泡利矩阵 $\sigma_x, \sigma_y, \sigma_z$（加上单位矩阵 $I$）构成单量子比特门的基底。$X$ 门 = $\sigma_x$，$Y$ 门 = $\sigma_y$，$Z$ 门 = $\sigma_z$。理解自旋 $1/2$ 的数学框架是量子计算的入门必修。

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $s$ | 自旋量子数 | $s = 1/2$（电子固定） |
| $\lVert \hat{\mathbf{S}} \rVert$ | 自旋角动量大小 | $\frac{\sqrt{3}}{2}\hbar$ |
| $m_s$ | 自旋投影量子数 | $\pm 1/2$ |
| $\sigma_x, \sigma_y, \sigma_z$ | 泡利矩阵 | 见上方矩阵定义 |
| $g_s$ | 电子自旋 $g$ 因子 | $\approx 2.0023$ |
| $\boldsymbol{\mu}_s$ | 自旋磁矩 | $-g_s \mu_B \mathbf{S}/\hbar$ |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 自旋定义、泡利矩阵、自旋磁矩、与 Stern-Gerlach 的关系
