---
subject:
  - Physics
topic:
  - Quantum Mechanics
  - Atomic Physics
source: "self-authored; atomic physics notes"
comprehension: vague
aliases:
  - 好量子数
  - Good quantum number
  - 坏量子数
  - Bad quantum number
  - 守恒量子数
status: Draft
date: 2026-06-05
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Quantum_Numbers
  - Symmetry
  - Conservation_Law
---

# Good Quantum Number (好量子数)

好量子数（Good Quantum Number）是指：在给定系统的**当前总哈密顿量**下，某个量子数对应的物理量在时间演化中保持守恒，并且可以稳定地用来标记量子态。

换句话说，问一个量子数“好不好”，本质上不是问它名字重不重要，而是问：**当前系统真的会不会把这个标签保留下来？**

> [!tip] 核心图像：状态标签有没有被时间演化“洗掉”
> 如果一个量子态一开始带着标签 $a$，经过时间演化后仍然可以清楚地说“它还是那个 $a$ 态”，那么 $a$ 就是好量子数。若相互作用会把不同 $a$ 的态混合在一起，使这个标签不再稳定，那么 $a$ 就退化为坏量子数（Bad Quantum Number）。

---

## 数学本质：与哈密顿量对易

设 $\hat{A}$ 是某个力学量算符，它的本征值 $a$ 用来标记态：

$$
\hat{A}\ket{\psi}=a\ket{\psi}.
$$

在海森堡绘景中，若 $\hat{A}$ 本身不显含时间，则

$$
\frac{d\hat{A}}{dt}=\frac{1}{i\hbar}[\hat{A},\hat{H}].
$$

因此：

- 若 $[\hat{A},\hat{H}]=0$，则 $d\hat{A}/dt=0$，$\hat{A}$ 是守恒量；
- 若 $[\hat{A},\hat{H}]\neq 0$，则 $\hat{A}$ 通常会随时间变化，对应量子数不再稳定。

> [!info] 严格判据
> 一个量子数是否是好量子数，取决于它对应的算符是否与**当前完整哈密顿量**对易。只看自由粒子哈密顿量、只看中心力场，或只看某个近似项，都可能得出不同答案。

如果 $[\hat{A},\hat{H}]=0$，那么在合适条件下，能量本征态可以同时选成 $\hat{A}$ 的本征态。此时 $a$ 就能和能量一起成为能级的稳定标签。

---

## 物理图像：定海神针 vs 拖着残影

在原子物理中，最典型的例子来自角动量。

### 自旋-轨道耦合前

在理想中心力场中，轨道角动量 $\mathbf{L}$ 和自旋角动量 $\mathbf{S}$ 近似各自独立。此时常用量子数是

$$
(n,l,m_l,s,m_s).
$$

这里 $m_l$ 与 $m_s$ 可以分别标记轨道和自旋在 $z$ 轴上的投影。

### 加入自旋-轨道耦合后

当加入 [[Spin-Orbit-Coupling|自旋-轨道耦合]]

$$
\hat{H}_{SO}\propto \mathbf{L}\cdot\mathbf{S}
$$

之后，$\mathbf{L}$ 和 $\mathbf{S}$ 会绕总角动量

$$
\mathbf{J}=\mathbf{L}+\mathbf{S}
$$

进动。此时 $m_l$ 与 $m_s$ 不再稳定，不能继续作为精细结构能级的好标签；但 $j$ 和 $m_j$ 仍然可以稳定标记态。

> [!tip] 定海神针
> 在自旋-轨道耦合存在时，$\mathbf{L}$ 和 $\mathbf{S}$ 自己像在快速进动，单独的投影会“拖残影”；但合成后的 $\mathbf{J}$ 才是更稳定的轴。因此好量子数从 $(m_l,m_s)$ 转向 $(j,m_j)$。

---

## 好与坏是相对的：取决于当前哈密顿量

好量子数不是绝对身份，而是相对于当前相互作用的“有效标签”。原子物理中常见的演变是：

| 物理环境 | 当前主导相互作用 | 好量子数 | 退化的坏量子数 | 直观原因 |
|---|---|---|---|---|
| 理想中心力场 | 中心势 $V(r)$ | $n,l,m_l,s,m_s$ | 无 | 轨道和自旋近似各自独立 |
| 精细结构 | 自旋-轨道耦合 | $n,l,s,j,m_j$ | $m_l,m_s$ | $\mathbf{L}$ 与 $\mathbf{S}$ 被耦合成 $\mathbf{J}$ |
| 弱磁场 Zeeman 极限 | 自旋-轨道耦合强于外磁场 | $n,l,s,j,m_j$ | 通常不用 $m_l,m_s$ 单独标记 | $\mathbf{J}$ 仍是主要耦合轴 |
| 强磁场 Paschen-Back 极限 | 外磁场强于自旋-轨道耦合 | $n,l,s,m_l,m_s$ | $j$ | 外磁场把 $\mathbf{L}$ 与 $\mathbf{S}$ 拉回各自绕 $z$ 轴进动 |

> [!warning] 不要把“量子数存在”误认为“好量子数”
> 一个量子数可以在数学上定义，但不一定适合标记当前能级。例如强磁场中仍然可以写出 $\mathbf{J}=\mathbf{L}+\mathbf{S}$，但若 $j$ 不再与当前哈密顿量对易，它就不是好量子数。

---

## 详细对易子推导：为什么量子数会变好或变坏

下面把“好量子数会随物理环境改变”落实为具体的对易子计算。核心原则只有一句：**先写当前总哈密顿量，再检查候选算符是否与它对易。**

> [!question] 待学习问题
> 为什么在中心力场、精细结构、弱 Zeeman 场这三种环境中，$m_l,m_s$ 会从好量子数变成坏量子数，而 $j,m_j$ 又会变成新的好量子数？这个问题已同步到 [[Study-Roadmap|学习路径]] 的“学习疑问”区，保持未勾选状态。

### 情况一：理想中心力场

最基础的氢原子模型只保留中心势。哈密顿量为

$$
\hat{H}_0=\frac{\hat{p}^2}{2\mu}+V(r)
=-\frac{\hbar^2}{2\mu}\nabla^2+V(r),
$$

其中 $V(r)$ 只依赖半径 $r$，没有任何显式自旋算符。

#### 自旋量子数为什么是好的？

自旋算符 $\hat{S}^2,\hat{S}_z$ 作用在自旋空间；$\hat{H}_0$ 中的 $\hat{p}^2$ 与 $V(r)$ 作用在空间坐标部分。两个空间独立，因此

$$
[\hat{S}^2,\hat{H}_0]=0,\qquad [\hat{S}_z,\hat{H}_0]=0.
$$

所以 $s,m_s$ 是好量子数。

#### 轨道量子数为什么是好的？

在球坐标中，

$$
\nabla^2=
\frac{1}{r^2}\frac{\partial}{\partial r}
\left(r^2\frac{\partial}{\partial r}\right)
-\frac{\hat{L}^2}{\hbar^2 r^2}.
$$

因此

$$
\hat{H}_0=
-\frac{\hbar^2}{2\mu r^2}\frac{\partial}{\partial r}
\left(r^2\frac{\partial}{\partial r}\right)
+\frac{\hat{L}^2}{2\mu r^2}+V(r).
$$

这里径向项只依赖 $r$，$\hat{L}^2$ 只作用在角变量上，所以

$$
[\hat{L}^2,\hat{H}_0]=0.
$$

同时 $\hat{L}_z=-i\hbar\,\partial/\partial\phi$，而中心力场哈密顿量不显含 $\phi$，并且 $[\hat{L}_z,\hat{L}^2]=0$，于是

$$
[\hat{L}_z,\hat{H}_0]=0.
$$

所以 $l,m_l$ 也是好量子数。

> [!tip] 情况一结论
> 在理想中心力场中，$l,m_l,s,m_s$ 全部是好量子数。原因是系统既有球对称性，又没有把自旋和轨道混合起来的相互作用。

### 情况二：加入自旋-轨道耦合

精细结构中最关键的一项是 [[Spin-Orbit-Coupling|自旋-轨道耦合]]：

$$
\hat{H}=\hat{H}_0+\hat{H}_{SO}
=\hat{H}_0+\xi(r)\,\mathbf{L}\cdot\mathbf{S},
$$

其中

$$
\mathbf{L}\cdot\mathbf{S}
=\hat{L}_x\hat{S}_x+\hat{L}_y\hat{S}_y+\hat{L}_z\hat{S}_z.
$$

#### 为什么 $m_l$ 变坏？

因为 $[\hat{L}_z,\hat{H}_0]=0$，只需检查耦合项：

$$
\begin{aligned}
[\hat{L}_z,\mathbf{L}\cdot\mathbf{S}]
&=[\hat{L}_z,\hat{L}_x]\hat{S}_x
+[\hat{L}_z,\hat{L}_y]\hat{S}_y
+[\hat{L}_z,\hat{L}_z]\hat{S}_z \\
&=(i\hbar\hat{L}_y)\hat{S}_x
+(-i\hbar\hat{L}_x)\hat{S}_y+0 \\
&=i\hbar(\hat{L}_y\hat{S}_x-\hat{L}_x\hat{S}_y)\neq 0.
\end{aligned}
$$

所以 $\hat{L}_z$ 不再与总哈密顿量对易，$m_l$ 退化为坏量子数。

同理，

$$
[\hat{S}_z,\mathbf{L}\cdot\mathbf{S}]
=-i\hbar(\hat{L}_y\hat{S}_x-\hat{L}_x\hat{S}_y)\neq 0,
$$

因此 $m_s$ 也变坏。

#### 为什么 $j,m_j$ 变好？

引入总角动量

$$
\mathbf{J}=\mathbf{L}+\mathbf{S}.
$$

由平方展开，

$$
\mathbf{L}\cdot\mathbf{S}
=\frac{1}{2}\left(\hat{J}^2-\hat{L}^2-\hat{S}^2\right).
$$

这说明自旋-轨道耦合项天然按 $\hat{J}^2,\hat{L}^2,\hat{S}^2$ 来分类。因此 $\hat{J}^2$ 与 $\hat{H}_{SO}$ 对易，$j$ 成为新的好量子数。

再看总投影 $\hat{J}_z=\hat{L}_z+\hat{S}_z$：

$$
\begin{aligned}
[\hat{J}_z,\mathbf{L}\cdot\mathbf{S}]
&=[\hat{L}_z+\hat{S}_z,\mathbf{L}\cdot\mathbf{S}]\\
&=i\hbar(\hat{L}_y\hat{S}_x-\hat{L}_x\hat{S}_y)
-i\hbar(\hat{L}_y\hat{S}_x-\hat{L}_x\hat{S}_y)\\
&=0.
\end{aligned}
$$

> [!tip] 正负抵消的物理意义
> 轨道投影 $m_l$ 和自旋投影 $m_s$ 各自会被耦合项改变，但一个减少时另一个可以补偿。真正守恒的是总投影 $m_j=m_l+m_s$。

因此在精细结构中，$l,s,j,m_j$ 是好量子数，而 $m_l,m_s$ 不再是好量子数。

### 情况三：弱外磁场 Zeeman 极限

在精细结构基础上加一个沿 $z$ 方向的弱磁场 $\mathbf{B}=B\hat{z}$：

$$
\hat{H}=\hat{H}_0+\xi(r)\mathbf{L}\cdot\mathbf{S}
+\frac{\mu_B B}{\hbar}(\hat{L}_z+2\hat{S}_z).
$$

最后一项是 Zeeman 相互作用。这里“弱场”是指 Zeeman 能量远小于精细结构间隔，因此 $\hat{H}_Z$ 作为微扰处理。

#### 为什么 $m_j$ 仍然严格是好量子数？

计算

$$
[\hat{J}_z,\hat{H}_Z]\propto
[\hat{L}_z+\hat{S}_z,\hat{L}_z+2\hat{S}_z].
$$

展开得

$$
[\hat{L}_z,\hat{L}_z]
+2[\hat{L}_z,\hat{S}_z]
+[\hat{S}_z,\hat{L}_z]
+2[\hat{S}_z,\hat{S}_z]=0.
$$

所以

$$
[\hat{J}_z,\hat{H}]=0.
$$

这对应一个非常清楚的物理图像：外磁场选定了 $z$ 轴，但仍保留绕 $z$ 轴旋转的轴对称性，因此总角动量在 $z$ 方向的投影 $m_j$ 严格守恒。

#### 为什么说 $j$ 只是近似好量子数？

对 $\hat{J}^2$ 来说，磁场项并不完全友好：

$$
[\hat{J}^2,\hat{H}_Z]\propto
[\hat{J}^2,\hat{L}_z+2\hat{S}_z]
=[\hat{J}^2,\hat{J}_z+\hat{S}_z].
$$

由于 $[\hat{J}^2,\hat{J}_z]=0$，剩下

$$
[\hat{J}^2,\hat{S}_z]\neq 0.
$$

这说明严格地说，外磁场会混合不同 $j$ 的态。

> [!warning] “弱场中 $j$ 是好量子数”是近似说法
> 在一级微扰的弱场极限中，不同 $j$ 多重态之间已有较大的精细结构能量间隔，$\hat{H}_Z$ 引起的跨 $j$ 混合很小，所以 $j$ 可以作为近似好量子数使用。严格守恒的是 $m_j$；近似保留的是 $j$。

因此弱 Zeeman 效应中常用 $(n,l,s,j,m_j)$ 标记能级，并得到

$$
\Delta E=g_j\mu_B m_j B.
$$

---

## 与 Zeeman Effect 的联系

[[Zeeman-Effect|塞曼效应]] 是“好量子数会随物理环境改变”的典型例子。

在弱磁场极限中，自旋-轨道耦合仍然主导，能级先按 [[Fine-Structure|精细结构]] 分成固定的 $j$ 多重态；外磁场只是在每个 $j$ 多重态内部按 $m_j$ 进一步劈裂。因此可用

$$
\Delta E=g_j\mu_B m_j B
$$

来描述能量修正，其中 $g_j$ 是 [[Lande-g-Factor|Landé g 因子]]。

但在强磁场 Paschen-Back 极限中，外磁场主导，$j$ 不再是稳定标签，系统改用 $m_l,m_s$ 标记：

$$
\Delta E=\mu_B B(m_l+2m_s).
$$

这说明：**同一个原子态，在弱场和强场中应该选择不同的好量子数。**

---

## 判断流程

遇到一个新问题时，可以按下面顺序判断：

1. 写出当前总哈密顿量 $\hat{H}$，包括你关心的相互作用项；
2. 列出候选算符，例如 $\hat{L}^2,\hat{L}_z,\hat{S}^2,\hat{S}_z,\hat{J}^2,\hat{J}_z$；
3. 检查哪些算符与 $\hat{H}$ 对易；
4. 用这些对易算符的本征值来标记量子态；
5. 若两个相互作用强度可比，简单标签可能失效，需要直接对角化哈密顿量。

> [!question] 学习时最该问的问题
> “在这个具体物理环境下，现在的总哈密顿量能和谁对易？谁才是当前表象中最稳定的态标签？”

---

## 与其他知识的联系

- [[Quantum-Numbers|量子数]]：好量子数是量子数在具体动力学系统中的可用性判据。
- [[Zeeman-Effect|塞曼效应]]：弱场用 $j,m_j$，强场用 $m_l,m_s$，是好量子数切换的核心例子。
- [[Spin-Orbit-Coupling|自旋-轨道耦合]]：让 $m_l,m_s$ 退化、让 $j,m_j$ 成为更自然标签的相互作用。
- [[Fine-Structure|精细结构]]：精细结构能级通常用 $n,l,j$ 标记。
- [[Lande-g-Factor|Landé g 因子]]：弱场 Zeeman 能量修正中使用好量子数 $j,m_j$ 的结果。
- [[Angular-Momentum-Coupling|角动量耦合]]：不同耦合方案对应不同的好量子数选择。

---

## 📐 核心公式摘要

**核心公式：**

- 好量子数判据：$[\hat{A},\hat{H}]=0$
- 海森堡运动方程：$\displaystyle \frac{d\hat{A}}{dt}=\frac{1}{i\hbar}[\hat{A},\hat{H}]$
- 总角动量：$\mathbf{J}=\mathbf{L}+\mathbf{S}$
- 自旋-轨道耦合等价形式：$\displaystyle \mathbf{L}\cdot\mathbf{S}=\frac{1}{2}(\hat{J}^2-\hat{L}^2-\hat{S}^2)$
- 弱场中严格守恒：$[\hat{J}_z,\hat{H}]=0$
- 弱场中近似守恒：$[\hat{J}^2,\hat{H}_Z]\neq 0$，但跨 $j$ 混合可在一级近似中忽略
- 弱场 Zeeman 修正：$\Delta E=g_j\mu_B m_j B$
- 强场 Paschen-Back 修正：$\Delta E=\mu_B B(m_l+2m_s)$

---

## 📝 更新记录

- 2026-06-05: 补充中心力场、精细结构、弱 Zeeman 场三种环境下好/坏量子数切换的详细对易子推导，并将“为什么量子数会变好或变坏”同步为 roadmap 待解决学习问题。
- 2026-06-05: 初始创建——整理好量子数的对易判据、角动量物理图像、Zeeman/Paschen-Back 中好量子数切换，并与塞曼效应、精细结构、自旋-轨道耦合建立双链。
