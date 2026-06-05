---
subject:
  - Physics
topic:
  - Atomic Physics
  - Quantum Mechanics
source: "Griffiths QM, Ch.9; Foot Atomic Physics"
comprehension: vague
aliases:
  - 选择定则
  - selection rules
  - 电偶极跃迁
  - electric dipole transition
status: Draft
date: 2026-06-04
tags:
  - Quantum_Mechanics
  - Atomic_Physics
  - Spectroscopy
  - Transition
  - Selection_Rules
---

# Selection-Rules（选择定则）

> 不是任意两个原子态之间都能发生跃迁——跃迁矩阵元非零的条件就是**选择定则**。它决定了原子光谱中哪些谱线"存在"、哪些"消失"。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 原子与光的相互作用主要通过**电偶极矩** $\mathbf{d} = -e\mathbf{r}$ 进行。跃迁速率正比于矩阵元 $|\langle f | \hat{\mathbf{r}} | i \rangle|^2$。选择定则就是这个矩阵元非零的量子数条件——不满足条件的跃迁被"禁止"（严格说，只是非常弱，并非绝对为零）。

---

## 核心定义与公式

### 1. 跃迁矩阵元

从初态 $|i\rangle$ 到终态 $|f\rangle$ 的电偶极跃迁概率振幅为：

$$
\mathbf{d}_{fi} = \langle f | \hat{\mathbf{d}} | i \rangle = -e \langle f | \mathbf{r} | i \rangle
$$

跃迁速率（Fermi's Golden Rule）：

$$
\Gamma_{i \to f} = \frac{\omega_{fi}^3}{3\pi \epsilon_0 \hbar c^3} |\mathbf{d}_{fi}|^2
$$

### 2. 电偶极选择定则（E1 选择定则）

在单电子原子（氢、碱金属）中，$\mathbf{r}$ 的矩阵元非零要求：

$$
\boxed{\Delta l = \pm 1, \quad \Delta m_l = 0, \pm 1}
$$

物理含义：
- **$\Delta l = \pm 1$**：光子携带一个单位的角动量（$\hbar$），吸收光子使电子的轨道角动量改变 1
- **$\Delta m_l = 0, \pm 1$**：光子的角动量在 $z$ 方向的投影为 $0$ 或 $\pm 1$（对应 $\pi$ 偏振或 $\sigma^\pm$ 偏振）

### 3. 完整选择定则（L-S 耦合下）

对于多电子原子 ${}^{2S+1}L_J$：

| 量子数 | 选择定则 | 物理原因 |
|--------|---------|---------|
| $\Delta L$ | $\pm 1$ | 光子携带 $1\hbar$ 角动量 |
| $\Delta S$ | $0$ | 光子不与自旋直接耦合 |
| $\Delta J$ | $0, \pm 1$（$J=0 \to J=0$ 禁戒） | 角动量守恒 |
| $\Delta m_J$ | $0, \pm 1$ | $z$ 分量角动量守恒 |
| $\Delta l$ | $\pm 1$（对单电子跃迁） | 同上 |

### 4. 超精细选择定则

对于 $F = J + I$ 耦合（超精细量子数）：

$$
\Delta F = 0, \pm 1 \quad (F = 0 \to F = 0 \text{ 禁戒})
$$

$$
\Delta m_F = 0, \pm 1
$$

### 5. 偏振与选择定则的对应

| 偏振 | $\Delta m$ | 光子角动量投影 |
|------|-----------|-------------|
| $\pi$ 偏振（线偏振，$\mathbf{E} \| \hat{z}$） | $0$ | $0$ |
| $\sigma^+$ 偏振（右旋圆偏振） | $+1$ | $+\hbar$ |
| $\sigma^-$ 偏振（左旋圆偏振） | $-1$ | $-\hbar$ |

> [!tip] 偏振选择定则的直觉
> $\pi$ 偏振的电场沿 $z$ 方向振荡，不给原子角动量 $z$ 分量的任何"推力"→ $\Delta m = 0$。
> $\sigma^+$ 偏振携带 $+\hbar$ 的角动量→ 吸收时原子 $m$ 增加 1。

---

## 关键性质

- **"禁戒"跃迁并非绝对禁止**：高阶多极跃迁（M1, E2, ...）可以发生，但速率比 E1 低 $10^5 \sim 10^8$ 倍
- **$J=0 \to J=0$ 对所有光子都禁戒**：角动量守恒不允许
- **$\Delta S = 0$ 不是严格的**：自旋-轨道耦合混合不同 $S$ 的态，使部分"自旋禁戒"跃迁可以发生（intercombination lines）
- **选择定则决定能级寿命**：允许跃迁 $\Gamma \sim 10^8$ s$^{-1}$（寿命 $\sim 10$ ns），禁戒跃迁可到 ms 甚至 s 量级

> [!warning] 常见错误
> 选择定则是针对**特定阶跃迁**（E1, M1, E2, ...）的。电偶极选择定则是最常见的，但不是唯一的。比如 $\Delta l = 0$ 的跃迁在 E1 下禁戒，但在 M1（磁偶极）下允许。

---

## 与其他知识的联系

- [[Angular-Momentum-Coupling|角动量耦合]] — CG 系数决定跃迁矩阵元的结构
- [[Zeeman-Effect|塞曼效应]] — $\Delta m$ 选择定则 + 偏振 = Zeeman 跃迁的偏振规则
- [[Fine-Structure|精细结构]] — L-S 耦合下的完整选择定则需要精细结构量子数
- [[Hyperfine-Structure|超精细结构]] — 超精细跃迁的选择定则（$\Delta F$）
- [[Perturbation-Theory|微扰论]] — 跃迁矩阵元的计算基于含时微扰论
- [[Electron-Spin|电子自旋]] — $\Delta S = 0$ 选择定则的来源
- [[Lande-g-Factor|朗德 g 因子]] — Zeeman 跃迁的相对强度需要 $g_J$

---

## 典型应用场景

- **氢原子光谱**：Lyman 系、Balmer 系等都是 E1 允许跃迁
- **碱金属的 $D$ 线**：${}^2S_{1/2} \to {}^2P_{1/2,3/2}$ 是 E1 允许跃迁
- **中性原子量子计算**：选择定则决定哪些激光可以驱动哪些跃迁，是量子比特操控的基础
- **Rydberg 激发路径**：从基态到 Rydberg 态的跃迁需要满足选择定则

> [!info] 在量子计算中的角色
> Rb-87 的量子比特编码在 ${}^5S_{1/2}$ 的超精细态 $|F=1, m_F\rangle$ 和 $|F=2, m_F\rangle$ 之间。微波驱动这个跃迁需要满足 $\Delta F = \pm 1, \Delta m_F = 0, \pm 1$。Rydberg 激发通常走 $5S \to 5P \to nS/nD$ 的级联路径，每一步都受选择定则约束。

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\Delta l$ | 轨道角动量变化 | $\pm 1$（E1 选择定则） |
| $\Delta m_l$ | 磁量子数变化 | $0, \pm 1$ |
| $\Delta J$ | 总角动量变化 | $0, \pm 1$（$0 \to 0$ 禁戒） |
| $\Delta S$ | 自旋变化 | $0$（严格） |
| $\Gamma_{i \to f}$ | 跃迁速率 | $\frac{\omega^3}{3\pi\epsilon_0\hbar c^3}|\mathbf{d}_{fi}|^2$ |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — E1 选择定则、偏振对应、超精细选择定则
