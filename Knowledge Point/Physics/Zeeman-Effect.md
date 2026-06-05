---
subject:
  - Physics
topic:
  - Atomic Physics
  - Quantum Mechanics
  - Spectroscopy
source: "Griffiths QM, Ch.6; Foot Atomic Physics, Ch.5"
comprehension: vague
aliases:
  - 塞曼效应
  - Zeeman effect
  - 塞曼分裂
  - Zeeman splitting
  - Anomalous Zeeman effect
  - 反常塞曼效应
  - Paschen-Back effect
status: Draft
date: 2026-06-03
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Zeeman_Effect
  - Angular_Momentum
  - Spectroscopy
  - Magnetic_Field
---

# Zeeman Effect (塞曼效应)

塞曼效应（Zeeman Effect）是指原子光谱线在外加磁场中发生**分裂**的现象。它是角动量量子化、[[Magnetic-Moment|磁矩]]与外磁场相互作用的直接体现，也是历史上最早证实空间量子化（[[Magnetic-Quantum-Number|磁量子数]]）存在的实验之一。

> [!info] 先搞懂“简并”
> “简并”就是：**两个或更多不同的量子态，拥有同一个能量**。
> 换句话说，能量不能把这些态区分开来。等到加入外磁场、晶体场或其他微扰时，这些原本同能量的态就可能被“拆开”成不同能级。
> 更系统的定义见 [[Degeneracy|简并]]。

> [!tip] 核心图像
> 把原子中的电子想象成一个有角动量的小陀螺。这个陀螺有磁矩（因为电荷在运动），放进外磁场后，陀螺的轴（角动量方向）会[[Larmor-Precession|绕磁场进动]]。不同"倾斜角度"的进动状态对应不同能量——磁场把这些原本简并的能级劈开了。能级劈开的具体模式取决于外磁场强度与[[Spin-Orbit-Coupling|自旋-轨道耦合]]强度的相对大小。

---

## 物理直觉：为什么磁场能劈开能级？

### 对称性破缺的视角

在没有外磁场时，原子在空间中是**各向同性**的——没有"特殊方向"。这意味着角动量在任意方向上的投影（[[Magnetic-Quantum-Number|磁量子数]] $m$）不影响能量，同一 $l$ 下的 $2l+1$ 个 $m$ 态完全简并。

加入沿 $z$ 方向的外磁场 $\mathbf{B} = B\hat{z}$ 后，空间旋转对称性被打破——$z$ 方向变得特殊。不同 $m$ 的态与磁场的相互作用能量不同，简并被解除。

### 磁矩-磁场相互作用

原子中的电子有总磁矩 $\boldsymbol{\mu}$（来自轨道运动和自旋），它在磁场中的势能为：

$$
U = -\boldsymbol{\mu} \cdot \mathbf{B}
$$

$\boldsymbol{\mu}$ 与 $\mathbf{B}$ 同向时能量最低（最稳定），反向时能量最高。由于角动量的投影是量子化的（$m$ 只能取离散值），能量劈开也是离散的。

### 原子能量的完整拆解：内部磁场 vs 外部磁场

这是理解塞曼效应的关键一步。原子中同时存在**两种磁场**，电子的自旋磁矩同时与两者发生相互作用：

**① 无外磁场时的总能量——内部有效磁场的作用**

电子的轨道运动在电子自身位置产生一个**内部有效磁场** $B_{\text{内}}$。这个内磁场的物理根源就是 [[Spin-Orbit-Coupling|自旋-轨道耦合]]——从电子的参考系看，带正电的原子核绕它运动，产生一个等效磁场。电子的自旋磁矩与这个内磁场相互作用，产生精细结构劈裂：

$$
E = E_{n,l} + \Delta E_{l,s} = E_{n,l} - g_S\, m_s\, \mu_B\, B_{\text{内}}
$$

- $E_{n,l}$ 是不考虑自旋时的库仑能级（主量子数 $n$ + 角量子数 $l$ 决定）
- $\Delta E_{l,s} = -g_S\, m_s\, \mu_B\, B_{\text{内}}$ 是自旋磁矩与内磁场的相互作用能
- 这个内磁场的数量级在 $10^{-1} \sim 10^{2}$ T——比大多数实验室能产生的外磁场**强得多**！

> [!tip] 内磁场的量级直觉
> 氢原子 $n=2$ 的内磁场约 $\sim 12.5$ T，重原子的内磁场可达 $10^{2}$ T 量级。这意味着实验室中的"弱磁场"（几特斯拉）相比内磁场确实很小，这也是为什么弱场极限如此常见。

**② 有外磁场时的总能量——增加原子磁矩与外磁场的相互作用**

加入外磁场 $B_{\text{外}}$ 后，原子的总磁矩 $\boldsymbol{\mu}_J$（由总角动量 $\mathbf{J} = \mathbf{L} + \mathbf{S}$ 产生的有效磁矩）与外磁场发生新的相互作用：

$$
E = E_{n,l} + \Delta E_{l,s} = E_{n,l} - g_S\, m_s\, \mu_B\, B_{\text{内}} - g_J\, m_J\, \mu_B\, B_{\text{外}}
$$

最后一项 $-g_J\, m_J\, \mu_B\, B_{\text{外}}$ 就是 Zeeman 相互作用——它在原有精细结构能级的基础上，额外按照 $m_j$ 进行劈开。

**③ 弱磁场条件：为什么 $B_{\text{外}} \ll B_{\text{内}}$ 意味着自旋-轨道耦合不受影响？**

当 $B_{\text{外}} \ll B_{\text{内}}$ 时，外磁场对电子自旋-轨道耦合的干扰可以忽略。此时：

- $\mathbf{L}$ 和 $\mathbf{S}$ 仍然被内部有效磁场**强耦合**在一起，形成总角动量 $\mathbf{J} = \mathbf{L} + \mathbf{S}$
- $\mathbf{J}$ 的大小（量子数 $j$）是一个**好量子数**
- $\mathbf{L}$ 和 $\mathbf{S}$ 各自**快速地绕 $\mathbf{J}$ 进动**（由内部强磁场驱动），而 $\mathbf{J}$ 本身则**缓慢地绕外磁场 $\mathbf{B}_{\text{外}}$ 进动**（由较弱的外磁场驱动）

> [!tip] 双重进动的图像
> 想象一个陀螺：$\mathbf{L}$ 和 $\mathbf{S}$ 像陀螺的两个分量在内部力矩作用下高速绕 $\mathbf{J}$ 旋转（自旋-轨道耦合驱动），而 $\mathbf{J}$ 整体又像一个大陀螺缓慢绕外磁场方向旋转（Zeeman 效应驱动）。两层进动的速度差由 $B_{\text{内}}$ 和 $B_{\text{外}}$ 的比值决定——弱场下内层远快于外层。

这正是下文"弱磁场极限"的物理图像：外场只是微扰，原有精细结构保持完整，能级按 $m_j$ 小心翼翼地劈开。

> [!info] 历史背景
> 1896 年，荷兰物理学家 Pieter Zeeman 观察到钠光谱线在磁场中变宽。Hendrik Lorentz 用经典电子论解释了这种"正常"三分裂现象。但很快人们发现，许多谱线的分裂模式比三分裂复杂得多——这些被称为"反常"塞曼效应（anomalous Zeeman effect）。"反常"之谜直到 1925 年 Goudsmit 和 Uhlenbeck 提出电子自旋后才得到解释。今天我们知道，所谓的"反常"其实才是普遍情况，"正常"三分裂只是一个特殊情况（当轨道角动量 $l = 0$ 或总角动量 $g$ 因子恰好为 1 时出现）。

---

## 核心定义与公式

### Zeeman Hamiltonian

总角动量为 $\mathbf{J} = \mathbf{L} + \mathbf{S}$ 的原子在外磁场 $\mathbf{B} = B\hat{z}$ 中的 Zeeman 哈密顿量为：

$$
\hat{H}_Z = -\boldsymbol{\mu} \cdot \mathbf{B} = \frac{\mu_B B}{\hbar}(g_L \hat{L}_z + g_S \hat{S}_z)
$$

其中：
- $\mu_B = \frac{e\hbar}{2m_e} \approx 9.274 \times 10^{-24}$ J/T 是玻尔磁子（Bohr magneton）
- $g_L = 1$ 是轨道 $g$ 因子
- $g_S \approx 2.0023 \approx 2$ 是电子自旋 $g$ 因子（Dirac 理论预测 $g_S = 2$，QED 修正给出小的偏差）

> [!warning] $g_S \neq 1$
> 轨道 $g$ 因子 $g_L = 1$，但自旋 $g$ 因子 $g_S \approx 2$。这个因子 2 的差异是**反常塞曼效应的根本原因**——如果 $g_L = g_S$，所有塞曼分裂都会是简单的"正常"三分裂。$g_S \neq 1$ 意味着自旋磁矩和轨道磁矩"效率不同"，导致分裂模式不对称。

### Landé $g$ 因子

在弱磁场极限下（自旋-轨道耦合远大于 Zeeman 相互作用），[[Good-Quantum-Number|好量子数]]是指在当前哈密顿量下仍然能稳定用来标记一个量子态的量子数；这里好量子数是 $(n, l, j, m_j)$。此时 Zeeman 能量修正可以用一个等效的 $g$ 因子表达：

$$
\Delta E = g_j\,\mu_B\,m_j\,B
$$

其中 **Landé $g$ 因子** $g_j$ 为：

$$
\boxed{g_j = 1 + \frac{j(j+1) - l(l+1) + s(s+1)}{2j(j+1)}}
$$

> [!tip] $g_j$ 的物理意义
> $g_j$ 衡量的是总角动量 $\mathbf{J}$ 的"磁效率"——即单位角动量投影 $m_j$ 产生的能量偏移（以 $\mu_B B$ 为单位）。
>
> 如果只有轨道角动量（$s = 0, j = l$），$g_j = 1$，就是"正常"塞曼效应。
> 如果只有自旋角动量（$l = 0, j = s$），$g_j = 2$。
> 一般情况下 $1 < g_j < 2$（对 $s = 1/2$），$g_j$ 的具体值取决于 $j$ 和 $l$ 的混合比例。

> [!info] $g_j$ 的推导思路
> 在耦合基 $\ket{j, m_j}$ 中，总角动量 $\mathbf{J}$ 绕外场 $\mathbf{B}$ [[Larmor-Precession|进动]]。根据投影定理（projection theorem），$\mathbf{L}$ 和 $\mathbf{S}$ 在 $\mathbf{J}$ 方向上的投影分别与 $\mathbf{J}$ 成正比。通过计算 $\langle\mathbf{L}\cdot\mathbf{J}\rangle$ 和 $\langle\mathbf{S}\cdot\mathbf{J}\rangle$（利用角动量恒等式 $\mathbf{L}\cdot\mathbf{J} = \frac{1}{2}(J^2 + L^2 - S^2)$ 等），可以得到 $g_j$ 的精确表达式。详见 [[Hyperfine-Structure|超精细结构]] 中 $g_F$ 因子的完整推导。

---

## 弱磁场极限：Zeeman 分裂

当外磁场足够弱，使得 Zeeman 相互作用远小于自旋-轨道耦合能（$\mu_B B \ll \Delta E_{SO}$）时，好量子数是 $(j, m_j)$。每个精细结构能级按 $m_j$ 劈开为 $2j+1$ 个子能级：

$$
\Delta E = g_j\,\mu_B\,m_j\,B, \qquad m_j = -j, -j+1, \ldots, j
$$

### 具体例子：$l = 1, s = 1/2$

**$j = 1/2$**（$p_{1/2}$ 态）：

$$
g_j = 1 + \frac{\frac{1}{2}\cdot\frac{3}{2} - 1\cdot 2 + \frac{1}{2}\cdot\frac{3}{2}}{2\cdot\frac{1}{2}\cdot\frac{3}{2}} = 1 + \frac{\frac{3}{4} - 2 + \frac{3}{4}}{\frac{3}{2}} = 1 - \frac{1}{3} = \frac{2}{3}
$$

$m_j = \pm 1/2$，两个能级：

- $m_j = +1/2$：$\Delta E = +\frac{1}{3}\mu_B B$
- $m_j = -1/2$：$\Delta E = -\frac{1}{3}\mu_B B$

**$j = 3/2$**（$p_{3/2}$ 态）：

$$
g_j = 1 + \frac{\frac{3}{2}\cdot\frac{5}{2} - 1\cdot 2 + \frac{1}{2}\cdot\frac{3}{2}}{2\cdot\frac{3}{2}\cdot\frac{5}{2}} = 1 + \frac{\frac{15}{4} - 2 + \frac{3}{4}}{\frac{15}{2}} = 1 + \frac{1}{3} = \frac{4}{3}
$$

$m_j = \pm 3/2, \pm 1/2$，四个能级：

- $m_j = +3/2$：$\Delta E = +2\mu_B B$
- $m_j = +1/2$：$\Delta E = +\frac{2}{3}\mu_B B$
- $m_j = -1/2$：$\Delta E = -\frac{2}{3}\mu_B B$
- $m_j = -3/2$：$\Delta E = -2\mu_B B$

> [!warning] 注意间距不均匀！
> 与"正常"塞曼效应的等间距三分裂不同，这里的劈裂**不均匀**——这正是"反常"塞曼效应的特征。例如 $j = 3/2$ 的四个子能级，相邻间隔为 $\frac{4}{3}\mu_B B$ 和 $\frac{4}{3}\mu_B B$（等间距，但整体不均匀地分布在零的两侧）。$j = 1/2$ 的两个子能级间距为 $\frac{2}{3}\mu_B B$，与 $j = 3/2$ 的间距不成简单比例。

### 选择定则与光谱线

#### 选择定则的物理根源：角动量守恒

电偶极跃迁的本质是电子通过**发射或吸收一个光子**在能级间发生跳跃。物理学中有一条至高无上的铁律——**角动量守恒**。

光子是自旋为 1 的玻色子（$s_{\text{photon}} = 1$），每个诞生或湮灭的光子都严格携带 $1\hbar$ 的角动量。光子在 $z$ 轴（磁场方向）上的投影只能取 $m = +1$（左旋圆偏振）、$m = -1$（右旋圆偏振），或者在特殊叠加态下投影为 $0$。

因此，原子在跃迁前后总角动量投影的改变 $\Delta m_j = m_{j,\text{初}} - m_{j,\text{末}}$，必须严格等于光子所能提供的投影角动量变化：

$$
\boxed{\Delta m_j = 0, \ \pm 1}
$$

> [!warning] 禁戒跃迁
> 如果两个能级的 $m_j$ 差值为 $\pm 2, \pm 3, \ldots$（例如从 $m_j = +3/2$ 跳到 $m_j = -1/2$，$\Delta m_j = +2$），由于单个光子无法带走这么多投影角动量，这类跃迁在电偶极近似下是**严格禁止的**（称为"禁戒跃迁"）。

#### 偏振的几何图像：从不同方向看跃迁

不同的 $\Delta m_j$ 对应不同的偏振态，而偏振态决定了从哪个方向能观测到哪条谱线。

**$\Delta m_j = 0$：$\pi$ 偏振（线偏振光）**

电子在 $z$ 轴方向的投影没有变化，这意味着原子的电偶极矩**沿着磁场方向（$z$ 轴）上下振荡**。根据经典电动力学，加速电荷产生的电磁波垂直于振荡方向传播。当你**沿着 $z$ 轴（磁场方向）**观察时，你正对着振荡轴线——而偶极子在自己的振荡轴方向上辐射的电磁波强度**严格为零**。因此，$\pi$ 线在**沿磁场方向看不到**，只有在**垂直于磁场方向**观察时才能看到（此时表现为沿 $\hat{z}$ 方向的线偏振光）。

**$\Delta m_j = \pm 1$：$\sigma^{\pm}$ 偏振（圆偏振光）**

电子在 $z$ 轴的投影发生了变化，这意味着原子的电偶极矩在 $xy$ 平面上做**顺时针或逆时针的圆周运动**。当你沿着磁场方向（$z$ 轴）观察时，正好能完整地看到这个圆周旋转，因此表现为**左旋（$\sigma^+$）或右旋（$\sigma^-$）圆偏振光**。

> [!tip] 偏振与观测方向的对照
> - **沿磁场方向（纵向）观测**：只能看到 $\sigma^+$ 和 $\sigma^-$（圆偏振），$\pi$ 线消失
> - **垂直于磁场方向（横向）观测**：三条线都能看到——$\pi$ 线是沿 $\hat{z}$ 的线偏振光，$\sigma^{\pm}$ 线是沿 $\hat{x}$（或 $\hat{y}$）的线偏振光
>
> 这个几何关系正是当年 Zeeman 效应实验的关键判据：纵向观测只看到两条 $\sigma$ 线，横向观测看到三条线（$\pi + 2\sigma$）。

#### 选择定则的完整分类

| 跃迁类型 | $\Delta m_j$ | 偏振态 | 电偶极矩运动 | 沿磁场方向可观测 |
|:--------:|:------------:|:------:|:----------:|:--------------:|
| $\pi$ | $0$ | 线偏振 | 沿 $z$ 轴振荡 | ❌ |
| $\sigma^+$ | $+1$ | 左旋圆偏振 | $xy$ 平面逆时针旋转 | ✅ |
| $\sigma^-$ | $-1$ | 右旋圆偏振 | $xy$ 平面顺时针旋转 | ✅ |

#### 实战数数：$2P_{3/2} \to 2S_{1/2}$ 的 6 条谱线

弱磁场下，$2P_{3/2}$（$j = 3/2$，$g_j = 4/3$）劈成 4 个子能级，$2S_{1/2}$（$j = 1/2$，$g_j = 2/3$）劈成 2 个子能级。两个能级的朗德因子不同，导致分裂间距不对称——这是"反常"的关键。

**所有子能级一览：**

上能级 $2P_{3/2}$（$g_j = 4/3$）：

- $m_j = +3/2$：$\Delta E = +2\mu_B B$
- $m_j = +1/2$：$\Delta E = +\frac{2}{3}\mu_B B$
- $m_j = -1/2$：$\Delta E = -\frac{2}{3}\mu_B B$
- $m_j = -3/2$：$\Delta E = -2\mu_B B$

下能级 $2S_{1/2}$（$g_j = 2/3$）：

- $m_j = +1/2$：$\Delta E = +\frac{1}{3}\mu_B B$
- $m_j = -1/2$：$\Delta E = -\frac{1}{3}\mu_B B$

按照选择定则 $\Delta m_j = m_{j,\text{上}} - m_{j,\text{下}}$ 逐条连线：

> [!example] 第一组：$\Delta m_j = 0$（$\pi$ 偏振，共 2 条）
> 1. $m_j = +\frac{1}{2} \to +\frac{1}{2}$，$\Delta E = \frac{2}{3} - \frac{1}{3} = +\frac{1}{3}\,\mu_B B$
> 2. $m_j = -\frac{1}{2} \to -\frac{1}{2}$，$\Delta E = -\frac{2}{3} - (-\frac{1}{3}) = -\frac{1}{3}\,\mu_B B$

> [!example] 第二组：$\Delta m_j = +1$（$\sigma^+$ 偏振，共 2 条）
> 3. $m_j = +\frac{3}{2} \to +\frac{1}{2}$，$\Delta E = 2 - \frac{1}{3} = +\frac{5}{3}\,\mu_B B$
> 4. $m_j = +\frac{1}{2} \to -\frac{1}{2}$，$\Delta E = \frac{2}{3} - (-\frac{1}{3}) = +1\,\mu_B B$

> [!example] 第三组：$\Delta m_j = -1$（$\sigma^-$ 偏振，共 2 条）
> 5. $m_j = -\frac{1}{2} \to +\frac{1}{2}$，$\Delta E = -\frac{2}{3} - \frac{1}{3} = -1\,\mu_B B$
> 6. $m_j = -\frac{3}{2} \to -\frac{1}{2}$，$\Delta E = -2 - (-\frac{1}{3}) = -\frac{5}{3}\,\mu_B B$

**总计：$2 + 2 + 2 = 6$ 条合法的跃迁谱线。**

注意 6 条线的频率偏移分别为 $+\frac{5}{3}, +1, +\frac{1}{3}, -\frac{1}{3}, -1, -\frac{5}{3}$（单位 $\mu_B B$），**每一条都错开了**——谁也没有重合！这正是因为上下能级的 $g_j$ 不同（$4/3$ vs $2/3$），导致分裂间距不对称。

#### 为什么叫"反常"？

历史上，洛伦兹用经典电子论（不考虑自旋）预言：无论怎么分裂，所有 $\Delta m_j = +1$ 的线会重合成一条，$\Delta m_j = -1$ 的线也会重合成一条，最终**只看到干净的 3 条线**（正常塞曼效应）。

然而实验中却看到了 6 条线（甚至更多）。原因在于电子自旋的存在导致 $g_S \approx 2 \neq g_L = 1$，使得不同能级的朗德因子 $g_j$ 截然不同。由于分裂间距的不对称，原本在经典理论中应该重合的谱线全部错开了。这种因自旋导致的"谱线数大于 3"的现象被称为"反常"塞曼效应——它在历史上极为有力地证明了**电子自旋的存在**。

> [!tip] "反常"才是普遍情况
> "正常"三分裂只是一个特例（当 $s = 0$ 或 $g_j$ 恰好等于 1 时）。只要存在自旋贡献（$s \neq 0$），就一定是"反常"的。今天的我们应该把"反常"理解为常态，"正常"反而是特殊情况。

### 正常塞曼三线的选择定则与偏振

正常塞曼效应（normal Zeeman effect）可以看成一个最干净的特例：上下两个能级的有效 $g$ 因子相同，或者等效地说能量移动只正比于同一个磁量子数 $m$：

$$
\Delta E_m=\mu_B B\,m.
$$

如果一个跃迁的上、下能级分别记为 $m_u$ 与 $m_l$，那么光子的频率移动来自上下能级移动之差：

$$
h\Delta\nu
=\Delta E_{m_u}-\Delta E_{m_l}
=\mu_B B(m_u-m_l)
=\mu_B B\,\Delta m.
$$

因此

$$
\Delta\nu=\frac{\mu_B B}{h}\Delta m.
$$

由于电偶极跃迁的 [[Selection-Rules|选择定则]] 是

$$
\Delta m=0,\pm 1,
$$

所以只会出现三组频率：

$$
\Delta\nu=0,\qquad
\Delta\nu=+\frac{\mu_B B}{h},\qquad
\Delta\nu=-\frac{\mu_B B}{h}.
$$

> [!tip] 为什么三条线间隔相等？
> 因为正常塞曼效应中每个 $m$ 子能级的能量移动是等差数列：相邻 $m$ 之间差一个 $\mu_B B$。跃迁只允许 $\Delta m=0,\pm1$，所以光谱线只偏移 $0,\pm\mu_B B/h$，自然形成等间距三分裂。

三条线的偏振性质为：

- $\Delta m=0$：$\pi$ 线，线偏振（电场振动方向平行于外磁场方向）。
- $\Delta m=+1$：$\sigma^+$ 线，沿磁场方向观察时表现为左旋圆偏振。
- $\Delta m=-1$：$\sigma^-$ 线，沿磁场方向观察时表现为右旋圆偏振。

> [!warning] 偏振描述依赖观察方向
> 严格说，$\sigma^\pm$ 的“左旋/右旋圆偏振”是沿磁场方向观察时的说法；若从垂直于磁场方向观察，$\sigma$ 线会表现为线偏振，且电场振动方向垂直于磁场方向。$\pi$ 线沿磁场方向观察时通常看不到，因为它的电偶极辐射方向性在该方向上没有辐射强度。

把玻尔磁子

$$
\mu_B=\frac{e\hbar}{2m_e}
$$

代入 $\Delta\nu=\mu_B B/h$，并使用 $h=2\pi\hbar$，得到 SI 制下的正常塞曼分裂间隔：

$$
\Delta\nu_L=\frac{\mu_B B}{h}
=\frac{e\hbar B}{2m_e}\cdot\frac{1}{2\pi\hbar}
=\frac{eB}{4\pi m_e}.
$$

在高斯 cgs 制中，由于磁矩定义多一个 $1/c$，常写为

$$
\Delta\nu_L=\frac{eB}{4\pi m_e c}.
$$

> [!info] 符号说明
> 这个 $\Delta\nu_L$ 也常被称为 Larmor frequency（拉莫尔频率）对应的普通频率版本。若使用角频率，则 $\omega_L=2\pi\nu_L$。

**正常塞曼效应的最终图像：**

- 中间的 $\pi$ 线：$\Delta m=0$，不发生频率偏移；
- 两侧的 $\sigma^+$ 与 $\sigma^-$ 线：$\Delta m=\pm1$，分别偏移 $\pm\Delta\nu_L$；
- 三条线间隔相等，间隔大小为

$$
\Delta\nu_L=\frac{\mu_B B}{h}.
$$

---

## 强磁场极限：Paschen-Back 效应

当外磁场足够强，使得 Zeeman 相互作用远大于自旋-轨道耦合能（$\mu_B B \gg \Delta E_{SO}$）时，外磁场的"力"足以撕裂自旋-轨道耦合。此时 $\mathbf{L}$ 和 $\mathbf{S}$ 各自独立地绕外场进动，不再被"锁定"在 $\mathbf{J}$ 的方向上。

好量子数从 $(j, m_j)$ 变回 $(m_l, m_s)$——就像精细结构不存在一样！

$$
\Delta E = \mu_B B(m_l + 2m_s)
$$

> [!tip] 关键转变
> 弱场极限：$\mathbf{L}$ 和 $\mathbf{S}$ 耦合形成 $\mathbf{J}$，$\mathbf{J}$ 绕 $\mathbf{B}$ 进动。
> 强场极限：$\mathbf{L}$ 和 $\mathbf{S}$ 各自独立绕 $\mathbf{B}$ 进动，自旋-轨道耦合变成微扰。
>
> 这个转变是连续的，中间区域（Zeeman 能量与自旋-轨道耦合可比时）需要精确对角化 Hamiltonian，没有简单的解析公式。

### Paschen-Back 分裂的具体例子

**$l = 1$（$p$ 态），$s = 1/2$**：

所有 $(m_l, m_s)$ 组合：

| $m_l$ | $m_s$ | $m_l + 2m_s$ | 能量偏移 |
|:-----:|:-----:|:------------:|:--------:|
| $+1$ | $+1/2$ | $+2$ | $+2\mu_B B$ |
| $+1$ | $-1/2$ | $0$ | $0$ |
| $0$ | $+1/2$ | $+1$ | $+\mu_B B$ |
| $0$ | $-1/2$ | $-1$ | $-\mu_B B$ |
| $-1$ | $+1/2$ | $0$ | $0$ |
| $-1$ | $-1/2$ | $-2$ | $-2\mu_B B$ |

能级劈开为 5 条线（$m_l + 2m_s = +2, +1, 0, -1, -2$），注意 $m_l + 2m_s = 0$ 的态是二重简并的（$m_l = 1, m_s = -1/2$ 和 $m_l = -1, m_s = +1/2$）。

> [!info] Paschen-Back 效应的光谱
> 选择定则变为 $\Delta m_l = 0, \pm 1$（$\Delta m_s = 0$），光谱线变为 **3 条**（即"正常"三分裂），因为 $\Delta m_s = 0$ 的限制意味着只有 $m_l$ 变化贡献光谱位移。这就是为什么在强场下"反常"效应消失，回归"正常"塞曼效应。

### 弱场 → 强场的演化

两个极端之间有一个连续的过渡区域。以 $2P$ 态为例，随磁场增大：

1. **弱场**（$B \to 0$）：精细结构主导，$j$ 是好量子数。$j = 1/2$ 劈成 2 线，$j = 3/2$ 劈成 4 线
2. **中间场**：$j$ 不再严格是好量子数，能级出现"反交叉"（avoided crossing）
3. **强场**（$B \to \infty$）：Zeeman 主导，$m_l, m_s$ 是好量子数。劈成 5 线（$m_l + 2m_s = -2, -1, 0, +1, +2$）

---



## HTML interactive demo: double precession picture

This embedded tool explains the "double precession" picture above: $\mathbf{L}$ and $\mathbf{S}$ rapidly precess around $\mathbf{J}$ due to internal spin-orbit coupling, while $\mathbf{J}$ as a whole slowly precesses around the external magnetic field $\mathbf{B}_{\text{out}}$.

<iframe src="file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/Zeeman-Double-Precession-Interactive.html" width="100%" height="760" style="border:1px solid #d8dee9; border-radius:6px;"></iframe>

> [!tip] How to read the animation
> Focus on the two time scales: the inner motion $\mathbf{L},\mathbf{S}$ around $\mathbf{J}$ is fast, while the outer motion $\mathbf{J}$ around $\mathbf{B}_{\text{out}}$ is slow. The weak-field condition $B_{\text{out}} \ll B_{\text{in}}$ means that internal coupling locks $\mathbf{L}$ and $\mathbf{S}$ into $\mathbf{J}$ first; the external field can only slowly drag the whole $\mathbf{J}$.

---

## Python 可视化

### 能级分裂图

下面的图同时展示弱场（反常塞曼）和强场（Paschen-Back）两种极限下 $2P$ 态的能级分裂。

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

COLORS = {
    'blue': '#4C78A8', 'orange': '#F58518', 'green': '#54A24B',
    'red': '#E45756', 'purple': '#72B7B2',
}

fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5.5), sharey=True)

# ── Left: Weak-field (Anomalous Zeeman) ──
ax1.set_title(r'弱场极限：反常塞曼效应', fontsize=13, fontweight='bold')
ax1.set_xlim(-1, 5)
ax1.set_xticks([])
ax1.set_ylabel(r'能量偏移 $(\mu_B B)$', fontsize=12)
ax1.grid(axis='y', alpha=0.3, ls=':')

# Unperturbed 2P level
ax1.hlines(0, 0, 1.2, colors='#999', linewidths=2)
ax1.text(1.4, 0, r'$2P$（未分裂）', fontsize=10, color='#666')

# j=1/2 (g=2/3), mj = +1/2, -1/2
g_j_half = 2.0 / 3.0
mj_half = [0.5, -0.5]
E_half = [g_j_half * mj for mj in mj_half]
for mj_val, E_val in zip(mj_half, E_half):
    x_start = 2.5
    x_end = 3.5
    ax1.hlines(E_val, x_start, x_end, color=COLORS['blue'], linewidth=2.5)
    ax1.text(x_end + 0.15, E_val, rf'$j=\frac{{1}}{{2}},\ m_j={mj_val:+.1f}$',
             va='center', fontsize=9, color=COLORS['blue'])
ax1.text(3.0, 1.05, r'$g_j = \frac{2}{3}$', fontsize=11, ha='center',
         color=COLORS['blue'], fontweight='bold')

# j=3/2 (g=4/3), mj = +3/2, +1/2, -1/2, -3/2
g_j_three_half = 4.0 / 3.0
mj_three_half = [1.5, 0.5, -0.5, -1.5]
E_three_half = [g_j_three_half * mj for mj in mj_three_half]
for mj_val, E_val in zip(mj_three_half, E_three_half):
    x_start = 2.5
    x_end = 3.5
    ax1.hlines(E_val, x_start, x_end, color=COLORS['orange'], linewidth=2.5)
    ax1.text(x_end + 0.15, E_val,
             rf'$j=\frac{{3}}{{2}},\ m_j={mj_val:+.1f}$',
             va='center', fontsize=9, color=COLORS['orange'])
ax1.text(3.0, 2.3, r'$g_j = \frac{4}{3}$', fontsize=11, ha='center',
         color=COLORS['orange'], fontweight='bold')

ax1.set_ylim(-2.7, 3.0)

# ── Right: Strong-field (Paschen-Back) ──
ax2.set_title(r'强场极限：Paschen-Back 效应', fontsize=13, fontweight='bold')
ax2.set_xlim(-1, 5)
ax2.set_xticks([])

# Unperturbed 2P level
ax2.hlines(0, 0, 1.2, colors='#999', linewidths=2)
ax2.text(1.4, 0, r'$2P$（未分裂）', fontsize=10, color='#666')

# ml + 2ms values: +2, +1, 0, -1, -2
# E = (ml + 2ms) * mu_B * B → in units of mu_B B
strong_levels = [
    (+2, [r'$(m_l{=}1,\, m_s{=}{+}\frac{1}{2})$']),
    (+1, [r'$(m_l{=}0,\, m_s{=}{+}\frac{1}{2})$']),
    (0,  [r'$(m_l{=}1,\, m_s{=}{-}\frac{1}{2})$',
          r'$(m_l{=}{-}1,\, m_s{=}{+}\frac{1}{2})$']),
    (-1, [r'$(m_l{=}0,\, m_s{=}{-}\frac{1}{2})$']),
    (-2, [r'$(m_l{=}{-}1,\, m_s{=}{-}\frac{1}{2})$']),
]

for E_val, labels in strong_levels:
    x_start = 2.5
    x_end = 3.5
    color = COLORS['red'] if len(labels) == 1 else COLORS['green']
    ax2.hlines(E_val, x_start, x_end, color=color, linewidth=2.5)
    label_text = ', '.join(labels)
    if len(labels) > 1:
        label_text += '  [二重简并]'
    ax2.text(x_end + 0.15, E_val, label_text,
             va='center', fontsize=8, color=color)

ax2.text(3.0, 2.3, r'$g_l{=}1,\ g_s{=}2$', fontsize=11, ha='center',
         color=COLORS['red'], fontweight='bold')

plt.suptitle(r'$l{=}1$（$p$ 态）在磁场中的 Zeeman 分裂', fontsize=14, fontweight='bold')
plt.tight_layout()
plt.show()
```

### 光谱线分裂图

下面的图展示 $2P_{3/2} \to 2S_{1/2}$ 跃迁在弱场和强场下的光谱线模式。

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

COLORS = {
    'blue': '#4C78A8', 'orange': '#F58518', 'green': '#54A24B',
    'red': '#E45756', 'purple': '#72B7B2',
}

fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(11, 5), sharey=True)

# ── Left: Weak-field spectral lines ──
ax1.set_title(r'弱场：反常塞曼谱线', fontsize=13, fontweight='bold')
ax1.set_xlim(-4.5, 4.5)
ax1.set_xlabel(r'频率偏移 $(\propto \mu_B B)$', fontsize=11)

# g_{3/2} = 4/3, g_{1/2} = 2/3
g32 = 4.0 / 3.0
g12 = 2.0 / 3.0

# Delta m_j = -1: sigma^- (right, positive shift convention)
weak_sigma_minus = [
    (-1.5, -0.5, 1.5),  # mj: 3/2 -> 1/2
    (-0.5, 0.5, -1.0),  # mj: 1/2 -> -1/2... wait
]

# Let me recalculate: E_upper - E_lower for each transition
# Upper: j=3/2, g=4/3, mj = 3/2, 1/2, -1/2, -3/2
# Lower: j=1/2, g=2/3, mj = 1/2, -1/2
# Selection: Delta mj = 0, +/-1

weak_lines = []
# Delta mj = +1 (sigma+)
for mj_up, mj_lo in [(1.5, 0.5), (0.5, -0.5)]:
    delta_E = g32 * mj_up - g12 * mj_lo
    weak_lines.append((delta_E, r'$\sigma^+$'))
for mj_up, mj_lo in [(-0.5, 0.5), (-1.5, -0.5)]:
    delta_E = g32 * mj_up - g12 * mj_lo
    weak_lines.append((delta_E, r'$\sigma^-$'))
# Delta mj = 0 (pi)
for mj_up, mj_lo in [(0.5, 0.5), (-0.5, -0.5)]:
    delta_E = g32 * mj_up - g12 * mj_lo
    weak_lines.append((delta_E, r'$\pi$'))

pi_color = COLORS['blue']
sigma_p_color = COLORS['red']
sigma_m_color = COLORS['green']

pol_colors = {r'$\sigma^+$': sigma_p_color,
              r'$\sigma^-$': sigma_m_color,
              r'$\pi$': pi_color}

for delta_E, pol in weak_lines:
    ax1.vlines(delta_E, -0.2, 0.8, color=pol_colors[pol], linewidth=2.5)

# Reference line
ax1.vlines(0, -0.4, 1.0, colors='#ccc', linewidths=1, linestyles='--')

# Legend
from matplotlib.lines import Line2D
legend_elements = [
    Line2D([0], [0], color=sigma_p_color, lw=2.5,
           label=r'$\sigma^+$ ($\Delta m_j = +1$)'),
    Line2D([0], [0], color=pi_color, lw=2.5,
           label=r'$\pi$ ($\Delta m_j = 0$)'),
    Line2D([0], [0], color=sigma_m_color, lw=2.5,
           label=r'$\sigma^-$ ($\Delta m_j = -1$)'),
]
ax1.legend(handles=legend_elements, frameon=False, fontsize=9, loc='upper right')

ax1.set_ylim(-0.5, 1.2)
ax1.set_yticks([])

# ── Right: Strong-field spectral lines ──
ax2.set_title(r'强场：正常塞曼三分裂', fontsize=13, fontweight='bold')
ax2.set_xlim(-4.5, 4.5)
ax2.set_xlabel(r'频率偏移 $(\propto \mu_B B)$', fontsize=11)

# Strong field: Delta ml = 0, +/-1 (Delta ms = 0)
# E_upper = ml + 2ms, E_lower = ml + 2ms (for 2S, l=0, ms=+/-1/2)
# Transitions: (ml_up, ms_up) -> (ml_lo, ms_lo), ms_up = ms_lo

strong_lines = []
for ms in [0.5, -0.5]:
    for ml_up, ml_lo, pol in [(1, 0, r'$\sigma^+$'), (0, 0, r'$\pi$'), (-1, 0, r'$\sigma^-$')]:
        delta_E = (ml_up + 2 * ms) - (0 + 2 * ms)  # = ml_up
        if pol == r'$\sigma^+$':
            strong_lines.append((1.0, pol))
        elif pol == r'$\pi$':
            strong_lines.append((0.0, pol))
        else:
            strong_lines.append((-1.0, pol))

# Actually each line appears twice (ms=+1/2 and ms=-1/2 give same delta_E)
# So only 3 distinct lines at -1, 0, +1
for delta_E, pol in [(1.0, r'$\sigma^+$'), (0.0, r'$\pi$'), (-1.0, r'$\sigma^-$')]:
    ax2.vlines(delta_E, -0.2, 0.8, color=pol_colors[pol], linewidth=2.5)
    ax2.text(delta_E, 0.9, pol, ha='center', fontsize=10, color=pol_colors[pol])

ax2.vlines(0, -0.4, 1.0, colors='#ccc', linewidths=1, linestyles='--')

plt.suptitle(r'$2P_{3/2} \to 2S_{1/2}$ 跃迁的 Zeeman 分裂', fontsize=14, fontweight='bold')
plt.tight_layout()
plt.show()
```

---

## 磁场强度的判据

如何判断一个实验处于弱场还是强场？关键是比较 Zeeman 能量和自旋-轨道耦合能量：

$$
\mu_B B \quad \text{vs.} \quad \Delta E_{SO} \sim \alpha^2 \times 13.6\ \mathrm{eV} / n^3
$$

| 条件 | 极限 | 好量子数 | 分裂模式 |
|------|------|----------|----------|
| $\mu_B B \ll \Delta E_{SO}$ | 弱场 | $(j, m_j)$ | 反常塞曼效应 |
| $\mu_B B \sim \Delta E_{SO}$ | 中间场 | 无简单好量子数 | 复杂混合 |
| $\mu_B B \gg \Delta E_{SO}$ | 强场 | $(m_l, m_s)$ | Paschen-Back 效应 |

> [!example] 数值估计
> 对氢原子 $n = 2$ 的精细结构分裂：$\Delta E_{SO} \sim 10^{-5}$ eV。对应磁场：
> $$B_{\mathrm{crit}} \sim \frac{\Delta E_{SO}}{\mu_B} \sim \frac{10^{-5}\ \mathrm{eV}}{5.79 \times 10^{-5}\ \mathrm{eV/T}} \approx 0.2\ \mathrm{T}$$
> 所以 $\sim 0.2$ T 的磁场就足以把氢原子 $n = 2$ 的精细结构推入 Paschen-Back 极限。对重原子（$Z$ 大，$\Delta E_{SO} \propto Z^4$），临界磁场要大得多。

---

## 正常塞曼效应 vs 反常塞曼效应

| 性质 | 正常塞曼效应 | 反常塞曼效应 |
|------|-------------|-------------|
| 出现条件 | $l = 0$（无轨道角动量）或 $g_j = 1$ | 一般情况（$s \neq 0$） |
| 分裂模式 | 等间距三分裂 | 不等间距多条线 |
| 光谱线数 | 3 条（$\sigma^+, \pi, \sigma^-$） | 通常 6 条或更多 |
| 物理原因 | $g_L = g_S = 1$ | $g_S \approx 2 \neq g_L = 1$ |
| 历史名称 | "正常"（Zeeman 1896） | "反常"（但其实更普遍！） |

> [!warning] "反常"才是正常的！
> 历史上把简单三分裂叫"正常"，复杂分裂叫"反常"。但自从发现电子自旋后我们知道，**反常塞曼效应才是普遍情况**——只有当 $s = 0$（无自旋贡献）或某些特殊的 $g_j = 1$ 情况下才会出现"正常"三分裂。正常塞曼效应是反常效应的一个特例。

---

## 与其他知识的联系

塞曼效应是角动量量子化和磁矩相互作用的直接体现。它与[[Fine-Structure|精细结构]]共同构成了理解原子光谱在外部扰动下行为的关键框架。

- [[Magnetic-Moment|磁矩]] — 塞曼效应的物理根源：磁矩在磁场中的能量
- [[Larmor-Precession|拉莫尔进动]] — Zeeman 分裂的经典图像：角动量绕磁场进动
- [[Magnetic-Quantum-Number|磁量子数]] — 塞曼效应直接展示了空间量子化
- [[Degeneracy|简并]] — 同一能量对应多个不同量子态
- [[Fine-Structure|精细结构]] — Zeeman 分裂叠加在精细结构之上
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 弱场/强场极限的分界线
- [[Quantum-Numbers|量子数]] — 塞曼效应改变了好量子数的选择
- [[Hyperfine-Structure|超精细结构]] — $g_F$ 因子与 $g_j$ 因子的类比
- [[Hydrogen-Atom-Model|氢原子模型]] — 塞曼效应修正了氢原子的库仑能级
- [[Stern-Gerlach-Experiment|施特恩-格拉赫实验]] — 空间量子化的直接实验证据
- [[Electron-Spin|电子自旋]] — 自旋磁矩对塞曼分裂的贡献
- [[Lande-g-Factor|朗德 g 因子]] — 分裂间距的决定参数
- [[Good-Quantum-Number|好量子数]] — 判断弱场 Zeeman 中为什么用 $(j,m_j)$、强场 Paschen-Back 中为什么改用 $(m_l,m_s)$ 的核心原则

---

## 典型应用场景

- **恒星磁场测量**：通过观测恒星光谱线的塞曼分裂，推断恒星表面的磁场强度和分布
- **原子钟**：[[Hyperfine-Structure|超精细结构]]的钟态编码利用 $m_F = 0$ 对一阶 Zeeman shift 不敏感的特性
- **中性原子量子比特**：利用特定的塞曼子态编码量子信息，磁场不敏感态提供长相干时间
- **磁光阱（MOT）**：利用塞曼分裂和偏振光实现激光冷却和原子俘获
- **斯特恩-盖拉赫实验**：原子束在梯度磁场中因不同 $m_j$ 的受力不同而分裂，直接证实了空间量子化
- **核磁共振（NMR）和 MRI**：核自旋在磁场中的 Zeeman 分裂是 NMR 的基础物理

---

## 📐 核心公式摘要

**核心公式：**

- Zeeman 能量（弱场）：$\Delta E = g_j\,\mu_B\,m_j\,B$
- Landé $g$ 因子：$\displaystyle g_j = 1 + \frac{j(j+1) - l(l+1) + s(s+1)}{2j(j+1)}$
- Paschen-Back 能量（强场）：$\Delta E = \mu_B B(m_l + 2m_s)$
- Zeeman Hamiltonian：$\hat{H}_Z = -\boldsymbol{\mu}\cdot\mathbf{B} = \frac{\mu_B B}{\hbar}(g_L\hat{L}_z + g_S\hat{S}_z)$
- 选择定则：$\Delta m_j = 0$（$\pi$ 偏振），$\Delta m_j = \pm 1$（$\sigma^{\pm}$ 偏振）
- 正常塞曼三线间隔：$\Delta\nu_L=\frac{\mu_B B}{h}$（SI 制）；高斯 cgs 制中 $\Delta\nu_L=\frac{eB}{4\pi m_e c}$
- 玻尔磁子：$\mu_B = \frac{e\hbar}{2m_e} \approx 9.274 \times 10^{-24}$ J/T

| 符号 | 含义 | 备注 |
|------|------|------|
| $g_j$ | Landé $g$ 因子 | 弱场极限下总角动量的有效磁效率 |
| $\mu_B$ | 玻尔磁子 | 原子磁矩的基本单位 |
| $g_L$ | 轨道 $g$ 因子 | $g_L = 1$ |
| $g_S$ | 自旋 $g$ 因子 | $g_S \approx 2.0023 \approx 2$ |
| $m_j$ | 总角动量投影量子数 | $m_j = -j, \ldots, +j$ |
| $m_l, m_s$ | 轨道和自旋投影量子数 | Paschen-Back 极限下的好量子数 |
| $\pi$ 偏振 | $\Delta m_j = 0$ 跃迁 | 沿磁场方向观测时不出现 |
| $\sigma^{\pm}$ 偏振 | $\Delta m_j = \pm 1$ 跃迁 | 圆偏振光 |

---

## 📝 更新记录

- 2026-06-05: 大幅扩充"选择定则与光谱线"小节：补充角动量守恒物理根源、$\pi$/$\sigma^\pm$ 偏振的几何图像与观测方向依赖、$2P_{3/2} \to 2S_{1/2}$ 六条谱线的逐条推导、以及"反常"命名的历史由来。
- 2026-06-05: 新增"原子能量的完整拆解：内部磁场 vs 外部磁场"小节——明确区分内磁场（自旋-轨道耦合驱动，$B_{\text{内}} \sim 10^{-1} \sim 10^{2}$ T）与外磁场（实验施加）对原子能量的各自贡献，补充双重进动（$\mathbf{L}$、$\mathbf{S}$ 绕 $\mathbf{J}$ 快速进动 + $\mathbf{J}$ 绕 $\mathbf{B}_{\text{外}}$ 缓慢进动）的物理图像。
- 2026-06-05: 补充正常塞曼效应中 $\Delta m=0,\pm1$ 对应的 $\pi,\sigma^+,\sigma^-$ 线、偏振方向与等间距分裂公式 $\Delta\nu_L=\mu_B B/h$。
- 2026-06-05: 链接新建 [[Good-Quantum-Number|好量子数]] 笔记，明确弱场 Zeeman 中 $(n,l,j,m_j)$ 与强场 Paschen-Back 中 $(m_l,m_s)$ 的好量子数切换。
- 2026-06-03: 创建初稿——物理图像（对称性破缺、磁矩-磁场相互作用）、Landé $g$ 因子推导与物理意义、弱场/强场极限公式与具体数值示例、选择定则、光谱线模式、正常 vs 反常塞曼效应对比、Python 可视化（能级分裂图 + 光谱线图）、典型应用
- 2026-06-05: 修复 Python 可视化中 `rf-string` 的 `{=}` 语法错误，避免 Obsidian Execute Code 报错。
- 2026-06-05: 补充“简并”定义说明，并新建 [[Degeneracy|简并]] 概念页，帮助理解磁场如何打破简并。
- 2026-06-05: Added `tools/Zeeman-Double-Precession-Interactive.html`, an interactive HTML animation for the weak-field Zeeman double-precession picture.
