---
subject:
  - Physics
topic:
  - Atomic Physics
  - AMO Physics
source: "Saffman, Walker, Mølmer, Rev. Mod. Phys. 82, 2313 (2010)"
comprehension: vague
aliases:
  - Rydberg 原子
  - 里德堡原子
  - Rydberg atom
  - 里德堡态
  - Rydberg state
status: Draft
date: 2026-06-04
tags:
  - Atomic_Physics
  - AMO
  - Rydberg
  - Quantum_Computing
  - Neutral_Atom
---

# Rydberg-Atom（Rydberg 原子）

> 主量子数 $n \sim 50$–$100$ 的高激发态原子：电子轨道巨大（$\langle r \rangle \propto n^2$），偶极矩巨大（$\propto n^2$），相互作用巨大（$\propto n^{11}$）——是中性原子量子计算的核心资源。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 普通原子的电子紧贴原子核（$n \sim 1$–$5$）；Rydberg 原子的电子被"拉"到离核很远的地方，轨道半径可达微米量级——几乎和细菌一样大！这个巨大的电子云使 Rydberg 原子具有极端的电偶极矩和极强的长程相互作用，是量子门操作的关键。

---

## 核心定义与公式

### 1. Rydberg 态的定义

Rydberg 态：主量子数 $n \gg 1$ 的高激发态，通常 $n \sim 30$–$100$。

**量子数亏损（quantum defect）**：

$$
E_n = -\frac{R_\infty}{(n - \delta_l)^2}
$$

其中 $\delta_l$ 是量子数亏损（碱金属），$l$ 越大 $\delta_l$ 越小。

### 2. 标度律（Scaling Laws）

Rydberg 态的所有物理量随 $n$ 的标度关系是理解 Rydberg 物理的核心：

| 物理量 | 标度 | 数值示例（$n=50$, Rb） |
|--------|------|----------------------|
| 轨道半径 $\langle r \rangle$ | $n^2$ | $\sim 1.3$ $\mu$m |
| 能级间距 $\Delta E$ | $n^{-3}$ | $\sim 4$ GHz |
| 极化率 $\alpha$ | $n^7$ | $\sim 10^5$ a.u. |
| 偶极矩 $\langle d \rangle$ | $n^2$ | $\sim 3000$ D |
| 辐射寿命 $\tau$ | $n^3$ | $\sim 100$ $\mu$s（$n=50$）|
| 相互作用强度 | $n^{11}$（vdW）| — |

> [!tip] 为什么标度律这么重要？
> $n^{11}$ 的相互作用标度意味着从 $n=50$ 到 $n=60$，相互作用强度增加约 $(60/50)^{11} \approx 8$ 倍。这就是为什么 Rydberg 阻塞效应如此强大。

### 3. 冻结内核近似（Frozen Core）

在 Rydberg 原子中，外层电子远在离子实之外，内层电子（离子实）可以近似为一个**冻结**的、带有效核电荷 $Z_{\text{eff}} = 1$ 的球对称电荷分布。

**结果**：Rydberg 原子的低角动量态（$s, p, d$）行为类似**氢原子**，但有量子数亏损修正。

### 4. 常用 Rydberg 态（Rb-87）

| 跃迁 | $n$ | 类型 | 偶极矩阵元 |
|------|-----|------|-----------|
| $5S \to 5P \to nS$ | $50$–$100$ | 阻塞 | $\sim 100$–$500$ a.u. |
| $5S \to 5P \to nD$ | $50$–$100$ | 阻塞 | $\sim 100$–$500$ a.u. |

典型的级联激发路径：

$$
|5S_{1/2}, F=2\rangle \xrightarrow{D_2} |5P_{3/2}, F'=3\rangle \xrightarrow{\text{Rydberg laser}} |nS_{1/2}\rangle \text{ or } |nD_{5/2}\rangle
$$

### 5. Rydberg 原子的特殊性质

**巨大的尺寸**：$\langle r \rangle \approx n^2 a_0$，$n=50$ 时 $\sim 0.13$ $\mu$m

**巨大的电偶极矩**：$\langle d \rangle \approx 3na_0 e$，$n=50$ 时 $\sim 1000$ Debye

**巨大的极化率**：$\alpha \propto n^7$，对电场极其敏感

**长寿命**：$\tau \propto n^3$，可达 $\sim 100$ $\mu$s

**冻结内核**：内层电子屏蔽完整，外层电子像氢原子一样运动

> [!warning] Rydberg 原子极其脆弱
> 虽然寿命长（$\sim 100$ $\mu$s），但巨大的偶极矩使 Rydberg 原子对**微弱的电场噪声**极其敏感。实验中需要极低的电场噪声环境才能保持相干性。

---

## 与其他知识的联系

- [[Rydberg-Blockade|Rydberg 阻塞]] — Rydberg 原子间强相互作用导致阻塞效应
- [[Hydrogen-Atom-Model|氢原子模型]] — Rydberg 态类似氢原子（冻结内核近似）
- [[Fine-Structure|精细结构]] — Rydberg 态的精细结构标度 $\sim n^{-3}$
- [[Alkali-Metal-Doublet|碱金属双线]] — 量子数亏损在 Rydberg 态中更显著
- [[Optical-Tweezers|光镊]] — Rydberg 原子是光镊阵列量子计算的核心资源
- [[AC-Stark-Effect|AC Stark 效应]] — 光镊囚禁势基于 AC Stark shift
- [[Van-der-Waals-Interaction|van der Waals 相互作用]] — Rydberg 原子间的主要相互作用形式
- [[Selection-Rules|选择定则]] — Rydberg 激发路径受选择定则约束

---

## 典型应用场景

- **中性原子量子计算**：Rydberg 阻塞是两比特门的基础
- **量子模拟**：利用 Rydberg 相互作用模拟多体物理
- **精密测量**：Rydberg 原子对电场的极端敏感性用于微波电场传感
- **里德堡缀饰态（Rydberg dressing）**：弱耦合 Rydberg 态，实现可调长程相互作用

> [!info] 为什么选 Rydberg 态实现两比特门？
> 普通基态原子之间的偶极-偶极相互作用极弱（$\sim 10^{-40}$ J·m$^2$）。但 Rydberg 态的偶极矩巨大，相互作用强度可达 $\sim 10^{-23}$ J·m$^3$，使得阻塞半径达几微米——与光镊间距匹配。这是中性原子量子计算能工作的根本原因。

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $E_n$ | Rydberg 能级 | $-R_\infty/(n-\delta_l)^2$ |
| $\langle r \rangle$ | 轨道半径 | $\approx n^2 a_0$ |
| $\tau$ | 辐射寿命 | $\propto n^3$ |
| $C_6$ | vdW 系数 | $\propto n^{11}$ |
| $R_b$ | 阻塞半径 | $(C_6/\hbar\Omega)^{1/6}$ |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 标度律、冻结内核近似、Rb-87 Rydberg 态、在量子计算中的角色
