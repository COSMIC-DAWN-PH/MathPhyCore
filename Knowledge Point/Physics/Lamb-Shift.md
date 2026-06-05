---
subject:
  - Physics
topic:
  - Quantum Electrodynamics
  - Atomic Physics
source: "Griffiths QM; 课纲 §4-9"
comprehension: vague
aliases:
  - 兰姆移位
  - Lamb shift
  - QED 修正
status: Draft
date: 2026-06-04
tags:
  - Quantum_Electrodynamics
  - Atomic_Physics
  - Precision_Physics
  - Hydrogen
---

# Lamb-Shift（兰姆移位）

> Dirac 方程预言氢原子的 $2S_{1/2}$ 和 $2P_{1/2}$ 严格简并，但 1947 年 Lamb 实验测到它们之间有约 **1057 MHz** 的微小分裂——这是量子电动力学（QED）的直接实验证据。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> Dirac 方程只考虑了电子与核库仑场的相互作用。但量子真空不是"空的"——虚光子的发射和吸收让电子的有效质量和库仑势发生了微小修正。$S$ 态电子在核附近出现的概率高，受这种真空涨落影响大，$P$ 态电子则不然，于是 $2S_{1/2}$ 的能量被略微抬高，打破了 $S$-$P$ 简并。

---

## 核心定义与公式

### 1. 精细结构中的简并

Dirac 方程给出的氢原子能级：

$$
E_{n,j} = m_e c^2 \left[1 + \left(\frac{\alpha}{n - (j+\frac{1}{2}) + \sqrt{(j+\frac{1}{2})^2 - \alpha^2}}\right)^2\right]^{-1/2}
$$

其中 $\alpha \approx 1/137$ 是精细结构常数。关键特征：能量只依赖于 $n$ 和 $j$，与 $l$ 无关。

因此 Dirac 理论预测：$2S_{1/2}$（$n=2, j=1/2, l=0$）和 $2P_{1/2}$（$n=2, j=1/2, l=1$）**严格简并**。

### 2. 实验观测到的分裂

1947 年 Willis Lamb 和 Robert Retherford 用微波谱学精确测量氢原子 $2S_{1/2}$ 和 $2P_{1/2}$ 能级之间的跃迁频率：

$$
\Delta E_{\text{Lamb}} = E(2S_{1/2}) - E(2P_{1/2}) \approx 1057.8 \text{ MHz}
$$

$2S_{1/2}$ 略高于 $2P_{1/2}$。

> [!info] 历史注记
> Lamb 移位的发现（1947）是推动 QED 发展的直接实验动因。Bethe、Tomonaga、Schwinger、Feynman 等人随后发展出完整的 QED 理论来解释这个微小却深刻的分裂。

### 3. QED 修正的物理来源

Lamb 移位主要来自三个 QED 效应：

**① 电子自能（self-energy）**
电子不断发射和吸收虚光子，这等效于改变了电子的有效质量。$S$ 态电子在核附近出现概率高，修正效果最显著。

**② 真空极化（vacuum polarization）**
核的强电场在真空中激发出虚电子-正电子对，等效于对库仑势的微小修正。这个效应略微**降低** $S$ 态能量（与自能效应方向相反）。

**③ 原子核的有限大小效应（nuclear size effect）**
氢原子核（质子）不是点电荷，其有限体积修正了核附近的库仑势。

### 4. 氢原子 $n=2$ 能级的完整图景

$$
\begin{aligned}
&2P_{3/2} && (\text{精细结构最高}) \\
&\uparrow \sim 10\,969 \text{ MHz} \quad (\text{精细结构分裂}) \\
&2S_{1/2} && (\text{Lamb 移位抬高}) \\
&\uparrow \sim 1058 \text{ MHz} \quad (\text{Lamb shift}) \\
&2P_{1/2} && (\text{精细结构最低})
\end{aligned}
$$

> [!warning] 能级大小关系容易记混
> $2S_{1/2}$ 在 Dirac 理论中与 $2P_{1/2}$ 简并，但 Lamb 移位使 $2S_{1/2}$ **高于** $2P_{1/2}$。而精细结构分裂（$2P_{3/2} - 2P_{1/2}$）约 10969 MHz，远大于 Lamb 移位（1058 MHz）。

---

## 关键性质

- Lamb 移位随 $n$ 增大而快速减小（$\sim 1/n^3$），高 $n$ 态不显著
- Lamb 移位的理论值与实验值符合到极高精度（QED 最精确的预言之一）
- 对于 $P$ 态（$l \geq 1$），电子在核附近概率低，QED 修正很小
- 超精细结构（$\sim 1420$ MHz for $n=1$）与 Lamb 移位是**不同的物理**：前者来自核自旋，后者来自 QED

> [!info] 精度竞赛
> QED 对氢原子能级的理论预言与实验测量符合到 $10^{-15}$ 量级，使氢原子成为检验基本物理最精确的系统之一。

---

## 与其他知识的联系

- [[Fine-Structure|精细结构]] — Lamb 移位是对 Dirac 精细结构的 QED 修正
- [[Hydrogen-Atom-Model|氢原子模型]] — 氢原子是 Lamb 移位最重要的系统
- [[Hyperfine-Structure|超精细结构]] — 与 Lamb 移位是不同物理起源的修正（核自旋 vs QED）
- [[Electron-Spin|电子自旋]] — Dirac 方程包含自旋，但不含 QED 修正

---

## 典型应用场景

- **检验 QED 理论**：Lamb 移位是 QED 最重要的实验验证之一
- **精密计量**：氢原子跃迁频率是定义基本物理常数的基础
- **反物质研究**：反氢原子的 Lamb 移位测量检验 CPT 对称性
- **确定质子电荷半径**：质子大小问题（proton radius puzzle）

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\Delta E_{\text{Lamb}}$ | Lamb 移位（$n=2$） | $E(2S_{1/2}) - E(2P_{1/2}) \approx 1058$ MHz |
| 标度律 | Lamb 移位随 $n$ 变化 | $\sim 1/n^3$ |
| 物理起源 | 主要修正 | 电子自能 + 真空极化 + 核有限大小 |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — Dirac 简并与 Lamb 移位、QED 修正来源、$n=2$ 能级图景
