---
subject:
  - Physics
topic:
  - Atomic Physics
  - Electrodynamics
source: "Sihao 自撰推导 (2026-06-03)"
comprehension: getting there
aliases:
  - 磁矩在梯度磁场中的受力
  - 梯度磁场力
  - 磁偶极子受力
  - Force on magnetic dipole
status: WIP
date: 2026-06-03
tags:
  - Physics
  - Atomic_Physics
  - Electrodynamics
  - Magnetic_Moment
  - Magnetic_Field_Gradient
  - Stern_Gerlach
  - Magnetic_Trapping
---

# Force on Magnetic Dipole in Gradient Field

在**均匀磁场**中，[[Magnetic-Moment|磁矩]]只受[[Torque|力矩]] $\vec{\tau}=\vec{\mu}\times\vec{B}$，发生**转动**而无净平动力。但如果我们想把中性原子"推"或"拉"走——比如著名的**斯特恩-盖拉赫实验**中将原子束在空间上分离，或在冷原子物理中利用磁场**囚禁**中性原子——就必须依靠**磁场的空间不均匀性**，即磁场梯度。

> [!tip] 核心直觉
> 均匀磁场只能让磁矩"转头"；**梯度磁场**才能让磁矩"搬家"。就像一个指南针在均匀地磁场中只会偏转，但如果地磁场在某方向存在强度差异，指南针两端就会受到不等的拉力，从而产生净平动力。

---

## 从势能到受力

### 磁势能

磁矩 $\vec{\mu}$ 在外磁场 $\vec{B}$ 中的势能为：

$$
U = -\vec{\mu} \cdot \vec{B}
$$

展开为直角坐标分量：

$$
U = -(\mu_x B_x + \mu_y B_y + \mu_z B_z)
$$

### 力是势能的负梯度

在保守力场中，力等于势能的负梯度：

$$
\vec{F} = -\nabla U
$$

我们关心 $z$ 方向的力 $F_z$，对 $z$ 求偏导。由于原子的**固有磁矩 $\vec{\mu}$ 不随空间位置改变**（它是粒子内禀性质），可以把 $\mu_x,\mu_y,\mu_z$ 当作常数提出来：

$$
F_z = -\frac{\partial U}{\partial z} = \mu_x \frac{\partial B_x}{\partial z} + \mu_y \frac{\partial B_y}{\partial z} + \mu_z \frac{\partial B_z}{\partial z}
$$

> [!info] 关键假设
> 这里假设 $\vec{\mu}$ 是"刚性"磁矩——大小方向不随外场变化。对于原子的**内禀磁矩**（如电子自旋磁矩），这个近似在大多数实验条件下成立。但对于经典感应磁矩（如抗磁性），$\vec{\mu}$ 本身也是 $\vec{B}$ 的函数，情况会更复杂。

---

## 麦克斯韦方程组的约束

最理想的情况是：如果磁场只有 $z$ 分量且只在 $z$ 方向变化，那前两项直接为零。但**磁场高斯定理**告诉我们：

$$
\nabla \cdot \vec{B} = 0
$$

展开为：

$$
\frac{\partial B_x}{\partial x} + \frac{\partial B_y}{\partial y} + \frac{\partial B_z}{\partial z} = 0
$$

> [!warning] 物理约束
> 这意味着**你不可能制造出一个纯粹只有单一方向梯度的磁场**。只要 $\frac{\partial B_z}{\partial z} \neq 0$，磁场就必然在其他方向产生分量和变化——就像水流不可能只往一个方向挤压而不在侧面鼓出来一样。

---

## 两种消除前两项的机制

### 机制一：几何近似（磁极设计）

通过精心设计磁极形状（如斯特恩-盖拉赫实验中的劈裂磁极），可以在原子飞行的**中心轴线附近**让横向磁场梯度 $\frac{\partial B_x}{\partial z}$ 和 $\frac{\partial B_y}{\partial z}$ 尽可能趋近于零。于是前两项可忽略，得到：

$$
F_z \approx \mu_z \frac{\partial B_z}{\partial z}
$$

### 机制二：[[Larmor-Precession|拉莫尔进动]]平均（更强的物理理由）

在存在强背景主磁场 $B_z$ 的实验中（如斯特恩-盖拉赫实验），磁矩 $\vec{\mu}$ 会绕着 $B_z$ 方向做**极速的拉莫尔进动**。

因为进动速度极快（拉莫尔频率 $\omega_L = \gamma B$ 通常在 MHz 量级以上），在原子移动一小段距离的时间内，$\mu_x$ 和 $\mu_y$ 已经在正负之间震荡了无数次，其**时间平均值严格为零**：

$$
\langle \mu_x \rangle = 0, \quad \langle \mu_y \rangle = 0
$$

因此，即使 $\frac{\partial B_x}{\partial z}$ 和 $\frac{\partial B_y}{\partial z}$ 在空间中不为零，乘以零均值的振荡分量后，前两项的贡献在时间平均意义上也被消除。

> [!tip] 两种机制的互补
> 几何近似是从**空间设计**角度消除横向梯度；进动平均是从**时间平均**角度消除横向磁矩分量。实际实验中两者往往同时起作用，使得最终有效的力非常干净地简化为 $F_z \approx \mu_z \frac{\partial B_z}{\partial z}$。

---

## 最终公式与物理意义

$$
\boxed{F_z \approx \mu_z \frac{\partial B_z}{\partial z}}
$$

这个公式的物理意义极其清晰：

- **$\mu_z$**：磁矩在 $z$ 方向的投影，可正可负（取决于量子数 $m_l$ 或自旋取向）
- **$\frac{\partial B_z}{\partial z}$**：磁场在 $z$ 方向的梯度，反映场的不均匀程度
- **正负号**：$\mu_z > 0$ 的原子沿梯度方向运动（被推向强场区），$\mu_z < 0$ 的原子逆梯度方向运动（被推向弱场区）

> [!warning] 符号注意
> 当 $\mu_z > 0$ 且 $\frac{\partial B_z}{\partial z} > 0$ 时，$F_z > 0$，原子被推向 $z$ 正方向（强场区）。但对于自旋向下的电子，$\mu_z < 0$，力的方向相反。正是这种"一正一反"的分裂，使得斯特恩-盖拉赫实验中银原子束分成两条。

---

## 应用

### 斯特恩-盖拉赫实验（Stern-Gerlach Experiment）

1922 年，Stern 和 Gerlach 让银原子束通过一个非均匀磁场，观察到原子束分成**离散的两条**而非连续分布。这直接证明了角动量投影的量子化。

银原子的外层电子处于 $s$ 态（$l=0$），轨道磁矩为零。原子束的分裂来自**电子自旋磁矩**在梯度磁场中的受力差异，其 $z$ 分量只能取两个离散值，对应 $m_s = \pm\frac{1}{2}$。

### 磁光阱与中性原子囚禁

在冷原子物理中，磁场梯度被用于构造**磁阱**（magnetic trap）。通过四极磁场（anti-Helmholtz 线圈产生的线性梯度场），使得处于弱场搜寻态（weak-field seeking state，$\mu_z > 0$）的原子被推向磁场零点附近，从而实现对中性原子的囚禁。

> [!info] Majorana 丢失问题
> 在四极磁阱的磁场零点处，磁场方向突变。快速运动的原子可能无法跟随场方向的翻转，导致自旋反转并从阱中逃逸——这称为 **Majorana 丢失**。解决方案是采用 Ioffe-Pritchard 阱等"无零点"位形。

---

## 与均匀磁场中力矩的对比

| | 均匀磁场 | 非均匀磁场（梯度场） |
|---|---|---|
| **效应** | 力矩（转动） | 力（平动） |
| **公式** | $\vec{\tau}=\vec{\mu}\times\vec{B}$ | $F_z\approx\mu_z\frac{\partial B_z}{\partial z}$ |
| **能量变化** | 改变磁矩方向 | 改变原子空间位置 |
| **典型实验** | [[Larmor-Precession\|拉莫尔进动]]、塞曼分裂 | 斯特恩-盖拉赫实验、磁阱囚禁 |

---

## 相关概念

- [[Magnetic-Moment|磁矩]] — 力的来源，$F_z \propto \mu_z$
- [[Magnetic-Quantum-Number|磁量子数]] — 决定 $\mu_z$ 的量子化取值
- [[Torque|力矩]] — 均匀磁场中磁矩受到的转动效应
- [[Larmor-Precession|拉莫尔进动]] — 进动平均消除横向力项的物理机制
- [[Spontaneous-Symmetry-Breaking|自发对称性破缺]] — 对称性破缺与磁序相关

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $U$ | 磁矩在磁场中的势能 | $U=-\vec{\mu}\cdot\vec{B}$ |
| $\vec{F}$ | 磁矩在非均匀磁场中的力 | $\vec{F}=-\nabla U$ |
| $F_z$ | $z$ 方向力（完整） | $F_z=\mu_x\frac{\partial B_x}{\partial z}+\mu_y\frac{\partial B_y}{\partial z}+\mu_z\frac{\partial B_z}{\partial z}$ |
| $F_z$（近似） | 进动平均/几何近似后 | $F_z\approx\mu_z\frac{\partial B_z}{\partial z}$ |
| $\nabla\cdot\vec{B}=0$ | 磁场高斯定理 | $\frac{\partial B_x}{\partial x}+\frac{\partial B_y}{\partial y}+\frac{\partial B_z}{\partial z}=0$ |

---

## 📝 更新记录

- 2026-06-03: 从用户推导整理创建，涵盖势能→受力推导、麦克斯韦约束、几何近似与进动平均两种消除机制、斯特恩-盖拉赫实验和磁阱应用。
