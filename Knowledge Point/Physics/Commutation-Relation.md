---
subject:
  - Physics
topic:
  - Quantum Mechanics
source: "Griffiths Introduction to Quantum Mechanics, Ch.3 & Ch.4; Sakurai Modern Quantum Mechanics, Ch.1; 原子物理第四章"
comprehension: vague
aliases:
  - 对易关系
  - 对易子
  - Commutator
  - 正则对易关系
  - Canonical Commutation Relation
status: WIP
date: 2026-06-02
tags:
  - Physics
  - Quantum_Mechanics
  - Operator_Algebra
  - Angular_Momentum
  - Uncertainty_Principle
  - Lie_Algebra
---

# Commutation Relation (对易关系)

> 对易关系是量子力学的**代数骨架**——它用一个简单的表达式 $[A,B] = AB - BA$ 揭示了两个物理量是否可以同时精确测量，是一切量子不确定性、选择规则和守恒律的数学根源。

---

## 物理直觉

### 经典 vs 量子：测量顺序有关系吗？

在经典力学中，你先量位置再量动量，或者反过来，结果完全一样。经典物理量都是**可交换的数**：$xp = px$。

但在量子力学中，算符 $\hat{x}$ 和 $\hat{p}$ 不是普通的数——它们是作用在波函数上的**算符 (operator)**。当你依次作用两个算符时，顺序很重要：

$$\hat{x}\hat{p}\,\psi(x) \neq \hat{p}\hat{x}\,\psi(x)$$

**对易子 $[A,B]$ 正是测量"先 $A$ 后 $B$"与"先 $B$ 后 $A$"的差异。**

> [!tip] 核心直觉
> 对易子就像一个"顺序敏感度计"。$[A,B]=0$ 意味着两个物理量互不干扰、可以同时精确测量；$[A,B]\neq 0$ 意味着测量一个物理量会不可避免地扰动另一个——这就是量子不确定性的代数本质。

### 从对易子看世界

整个量子力学的代数结构可以浓缩为几个基本对易关系：

- **$[\hat{x},\hat{p}]=i\hbar$**：位置和动量不能同时精确 → Heisenberg 不确定性原理
- **$[\hat{L}_i,\hat{L}_j]=i\hbar\epsilon_{ijk}\hat{L}_k$**：角动量三个分量互相纠缠 → 不能同时确定所有分量
- **$[\hat{H},\hat{A}]=0$**：某个量与能量对易 → 它是守恒量（运动常数）

> [!info] 历史注记
> 对易关系的物理意义由 Werner Heisenberg (1925) 在矩阵力学中首先发现，后由 Dirac 用 Poisson 括号的对应关系 $\{q,p\}_{\text{PB}} = 1 \longrightarrow [\hat{q},\hat{p}]=i\hbar$ 给出了优雅的数学形式化。

---

## 核心定义与公式

### 对易子的定义

对任意两个算符 $\hat{A}$ 和 $\hat{B}$，**对易子 (commutator)** 定义为：

$$\boxed{[\hat{A},\hat{B}] \equiv \hat{A}\hat{B} - \hat{B}\hat{A}}$$

- 若 $[\hat{A},\hat{B}] = 0$，称 $\hat{A}$ 与 $\hat{B}$ **对易 (commute)**
- 若 $[\hat{A},\hat{B}] \neq 0$，称 $\hat{A}$ 与 $\hat{B}$ **不对易 (do not commute)**

> [!warning] 常见错误
> 对易子的结果本身也是一个**算符**，不是数！$[\hat{x},\hat{p}] = i\hbar$ 右边的 $i\hbar$ 实际上是 $i\hbar\hat{I}$（单位算符乘以常数），只不过我们通常省略 $\hat{I}$。

### 反对称性

由定义直接得到：

$$[\hat{A},\hat{B}] = -[\hat{B},\hat{A}]$$

特别地，$[\hat{A},\hat{A}] = 0$（任何算符与自身对易）。

---

## 基本对易关系

### 1. 正则对易关系 (Canonical Commutation Relation)

这是量子力学**最基本**的对易关系——从经典力学的正则变量 $(x, p)$ 通过"正则量子化"得到：

$$\boxed{[\hat{x},\hat{p}] = i\hbar}$$

**直接验证**（在位置表象中）：

$$[\hat{x},\hat{p}]\psi = \hat{x}\hat{p}\psi - \hat{p}\hat{x}\psi = x\left(-i\hbar\frac{\partial\psi}{\partial x}\right) - \left(-i\hbar\frac{\partial}{\partial x}\right)(x\psi)$$

$$= -i\hbar x\frac{\partial\psi}{\partial x} + i\hbar\left(\psi + x\frac{\partial\psi}{\partial x}\right) = i\hbar\psi$$

> [!tip] 物理意义
> $[\hat{x},\hat{p}] = i\hbar$ 是 Heisenberg 不确定性原理 $\Delta x\,\Delta p \geq \hbar/2$ 的代数根源。这个 $\hbar$ 是量子世界与经典世界的分界线——当 $\hbar \to 0$ 时，$[\hat{x},\hat{p}] \to 0$，回到经典力学。

**三维推广**：

$$[\hat{x}_i, \hat{p}_j] = i\hbar\,\delta_{ij}$$

$$[\hat{x}_i, \hat{x}_j] = 0, \qquad [\hat{p}_i, \hat{p}_j] = 0$$

其中 $i,j = 1,2,3$（或 $x,y,z$），$\delta_{ij}$ 是 Kronecker delta。

### 2. 角动量对易关系 (Angular Momentum Commutation Relations)

**一般角动量**（不特指轨道或自旋）的三个分量满足：

$$\boxed{[\hat{J}_i, \hat{J}_j] = i\hbar\,\epsilon_{ijk}\,\hat{J}_k}$$

其中 $\epsilon_{ijk}$ 是 Levi-Civita 符号（完全反对称张量）。

展开写出三个独立关系：

$$[\hat{J}_x, \hat{J}_y] = i\hbar\,\hat{J}_z$$

$$[\hat{J}_y, \hat{J}_z] = i\hbar\,\hat{J}_x$$

$$[\hat{J}_z, \hat{J}_x] = i\hbar\,\hat{J}_y$$

> [!tip] 物理直觉
> 角动量的 $x$ 分量和 $y$ 分量不对易！这意味着你不能同时精确知道 $J_x$ 和 $J_y$。但角动量**大小**算符 $\hat{J}^2$ 与任意一个分量对易：
> $$[\hat{J}^2, \hat{J}_i] = 0$$
> 所以 $J^2$ 和 $J_z$ 可以同时精确确定——这就是量子力学中我们选择 $z$ 轴作为量子化轴的原因。

**轨道角动量**（$\hat{\mathbf{L}} = \hat{\mathbf{r}} \times \hat{\mathbf{p}}$）和**自旋角动量** $\hat{\mathbf{S}}$ 各自独立满足上述关系：

$$[\hat{L}_i, \hat{L}_j] = i\hbar\,\epsilon_{ijk}\,\hat{L}_k, \qquad [\hat{L}^2, \hat{L}_i] = 0$$

$$[\hat{S}_i, \hat{S}_j] = i\hbar\,\epsilon_{ijk}\,\hat{S}_k, \qquad [\hat{S}^2, \hat{S}_i] = 0$$

而且轨道与自旋之间**互相对易**：

$$[\hat{L}_i, \hat{S}_j] = 0$$

### 3. Pauli 矩阵对易关系

Pauli 矩阵 $\sigma_x, \sigma_y, \sigma_z$ 是自旋 $1/2$ 系统的基本构建块（见 [[Unitary-Matrix|酉矩阵]]），它们满足：

$$\boxed{[\sigma_i, \sigma_j] = 2i\,\epsilon_{ijk}\,\sigma_k}$$

这是因为自旋算符 $\hat{S}_i = \frac{\hbar}{2}\sigma_i$，代入角动量对易关系即可验证。

常用的具体形式：

$$[\sigma_x, \sigma_y] = 2i\sigma_z, \qquad [\sigma_y, \sigma_z] = 2i\sigma_x, \qquad [\sigma_z, \sigma_x] = 2i\sigma_y$$

> [!warning] 对易 vs 反对易
> Pauli 矩阵除了对易子，还经常用到**反对易子** $\{A,B\} = AB + BA$：
> $$\{\sigma_i, \sigma_j\} = 2\delta_{ij}I$$
> 对易子和反对易子分别提取了 $AB$ 的反对称部分和对称部分。两者互补，合起来完全确定了 $AB$ 的代数结构。

---

## 对易子的运算法则

对易子满足一系列重要代数恒等式，使复杂算符的对易子可以化简：

### 1. 双线性 (Bilinearity)

$$[\alpha\hat{A} + \beta\hat{B},\, \hat{C}] = \alpha[\hat{A},\hat{C}] + \beta[\hat{B},\hat{C}]$$

其中 $\alpha, \beta$ 是复常数。

### 2. Leibniz 法则（"乘积法则"）

$$\boxed{[\hat{A},\, \hat{B}\hat{C}] = [\hat{A},\hat{B}]\hat{C} + \hat{B}[\hat{A},\hat{C}]}$$

> [!tip] 记忆技巧
> 这与微积分的乘积法则 $(fg)' = f'g + fg'$ 完全类比！把对易子 $[\hat{A}, \cdot]$ 看作一种"导数"，它满足 Leibniz 律。这不只是类比——在数学上，满足 Leibniz 律的线性映射称为**导子 (derivation)**。

### 3. Jacobi 恒等式

$$\boxed{[\hat{A},[\hat{B},\hat{C}]] + [\hat{B},[\hat{C},\hat{A}]] + [\hat{C},[\hat{A},\hat{B}]] = 0}$$

> [!info] 李代数
> 双线性、反对称、满足 Jacobi 恒等式——这三个性质正是**李代数 (Lie algebra)** 的公理。所以量子力学的算符对易关系定义了一个李代数。角动量对易关系对应的就是 $\mathfrak{su}(2)$ 李代数，这将量子力学与群论深刻地联系起来。

### 4. 常用计算技巧

对 $f(\hat{x})$ 和 $\hat{p}$ 的对易子：

$$[\hat{p},\, f(\hat{x})] = -i\hbar\, f'(\hat{x})$$

$$[f(\hat{x}),\, \hat{p}] = i\hbar\, f'(\hat{x})$$

这可以从 $[\hat{x}, \hat{p}] = i\hbar$ 和 Leibniz 法则反复使用得到。

---

## 与不确定性原理的关系

对易关系是 Heisenberg 不确定性原理的精确数学表述。对任意两个 Hermitian 算符 $\hat{A}, \hat{B}$，**Robertson 不等式**给出：

$$\boxed{\Delta A \cdot \Delta B \geq \frac{1}{2}\lvert\langle[\hat{A},\hat{B}]\rangle\rvert}$$

其中 $\Delta A = \sqrt{\langle\hat{A}^2\rangle - \langle\hat{A}\rangle^2}$ 是均方根不确定度。

| 对易关系 | 不确定性原理 |
|----------|-------------|
| $[\hat{x},\hat{p}] = i\hbar$ | $\Delta x\cdot\Delta p \geq \hbar/2$ |
| $[\hat{L}_x,\hat{L}_y] = i\hbar\hat{L}_z$ | $\Delta L_x\cdot\Delta L_y \geq \frac{\hbar}{2}\lVert\langle L_z\rangle\rVert$ |
| $[\hat{A},\hat{B}] = 0$ | $\Delta A\cdot\Delta B \geq 0$（无限制，可同时精确测量） |

> [!tip] 物理直觉
> 对易子越大，不确定性下界越高。$[\hat{x},\hat{p}]=i\hbar$ 中的 $\hbar$ 是不确定性的"最小单位"。如果两个算符对易，不确定性不施加任何约束——它们可以有共同本征态，同时精确确定。

---

## 与经典力学的联系：Poisson 括号

Dirac 发现了量子对易子与经典 Poisson 括号之间的深刻对应：

$$\boxed{[\hat{A},\hat{B}] \longleftrightarrow i\hbar\{A,B\}_{\text{PB}}}$$

其中经典 Poisson 括号定义为：

$$\{A,B\}_{\text{PB}} = \sum_k \left(\frac{\partial A}{\partial q_k}\frac{\partial B}{\partial p_k} - \frac{\partial A}{\partial p_k}\frac{\partial B}{\partial q_k}\right)$$

验证：经典力学中 $\{x,p\}_{\text{PB}} = 1$，对应量子力学 $[\hat{x},\hat{p}] = i\hbar \cdot 1 = i\hbar$。

| 经典力学 | 量子力学 |
|----------|----------|
| $\{A,B\}_{\text{PB}}$ | $\frac{1}{i\hbar}[\hat{A},\hat{B}]$ |
| $\{A,H\}_{\text{PB}} = 0$（守恒量） | $[\hat{A},\hat{H}] = 0$（守恒量） |
| $\{x,p\}_{\text{PB}} = 1$ | $[\hat{x},\hat{p}] = i\hbar$ |
| Poisson 括号满足 Jacobi 恒等式 | 对易子满足 Jacobi 恒等式 |

> [!info] 正则量子化
> Dirac 的对应关系提供了从经典力学过渡到量子力学的系统方法——**正则量子化 (canonical quantization)**：将经典 Poisson 括号替换为 $[\cdot,\cdot]/(i\hbar)$。这是构造量子理论最常用的方法之一。

---

## 关键应用

### 1. 同时对角化定理

**定理**：两个 Hermitian 算符 $\hat{A}$ 和 $\hat{B}$ 有共同本征态系（即可以同时对角化），**当且仅当** $[\hat{A},\hat{B}] = 0$。

这就是为什么：
- $\hat{L}^2$ 和 $\hat{L}_z$ 可以同时确定（$[\hat{L}^2,\hat{L}_z]=0$）→ 球谐函数 $Y_l^m$ 同时是两者的本征态
- $\hat{x}$ 和 $\hat{p}$ 不能同时确定（$[\hat{x},\hat{p}]=i\hbar\neq 0$）→ 不存在同时是位置和动量本征态的态

> 相关笔记：[[Quantum-Numbers|量子数]] — $n,l,m_l$ 三个量子数分别标记一组互相对易的算符 $(\hat{H},\hat{L}^2,\hat{L}_z)$ 的共同本征值。

### 2. 守恒量的判据

在 Heisenberg 绘景中，算符的时间演化方程为：

$$\frac{d\hat{A}}{dt} = \frac{1}{i\hbar}[\hat{A},\hat{H}] + \frac{\partial\hat{A}}{\partial t}$$

若 $\hat{A}$ 不显含时间且 $[\hat{A},\hat{H}]=0$，则 $\frac{d\hat{A}}{dt} = 0$，即 $\hat{A}$ 是**运动常数 (constant of motion)**。

例如：
- $[\hat{L}^2,\hat{H}] = 0$（中心力场中）→ 角动量守恒
- $[\hat{p},\hat{H}] = 0$（自由粒子）→ 动量守恒

### 3. 升降算符方法：纯代数推导角动量谱

角动量的升降算符是量子力学中最优雅的代数工具之一——它**不需要知道波函数的具体形式**，仅从对易关系出发就能推导出角动量的全部本征值谱。这个方法由 Dirac 提出，是量子力学代数方法的典范。

#### 构造升降算符

角动量的三个分量 $J_x, J_y, J_z$ 两两不对易，但我们**不是**要与这种"纠缠"为敌，而是利用它。Dirac 极其天才地将 $J_x$ 和 $J_y$ 组合成两个新的算符：

$$\hat{J}_+ = \hat{J}_x + i\hat{J}_y \quad \text{（升算符）}$$

$$\hat{J}_- = \hat{J}_x - i\hat{J}_y \quad \text{（降算符）}$$

> [!tip] 为什么这样组合？
> 这个组合不是随意的——它是从 $[\hat{J}_z, \hat{J}_\pm]$ 的对易关系中自然涌现的"正确"组合。就像谐振子问题中 $a$ 和 $a^\dagger$ 的构造一样，升/降算符是角动量代数的**自然产物**。

#### 核心对易关系

利用 $[\hat{J}_x, \hat{J}_y] = i\hbar\hat{J}_z$ 和 $[\hat{J}_z, \hat{J}_x] = i\hbar\hat{J}_y$，可以验证：

$$\boxed{[\hat{J}_z, \hat{J}_\pm] = \pm\hbar\hat{J}_\pm}$$

> [!tip] 物理意义
> 这个对易关系的含义极其清晰：$\hat{J}_\pm$ 作用在 $\hat{J}_z$ 的本征态 $|j,m\rangle$ 上时，会把**磁量子数 $m$ 精确地升高或降低 $1$ 个单位**：
> $$\hat{J}_\pm|j,m\rangle = c_\pm\,|j,m\pm 1\rangle$$
>
> 这就是"升降算符"名字的由来——它们像电梯一样，每按一次就精确地升或降一格。而且**不存在能让 $m$ 变化半格的算符**——在这个代数系统中，步长 $1$ 是绝对的。

#### 边界条件：为什么梯子有天花板和地板？

既然可以一格一格往上爬，那 $m$ 能无限增大吗？答案是否定的。物理上有两个硬约束：

**约束 1**：角动量在 $z$ 轴上的投影（直角边）绝对不能超过角动量的总长度（斜边）。数学上要求：

$$J_z^2 \leq J^2 \implies m^2\hbar^2 \leq j(j+1)\hbar^2$$

**约束 2**：如果升算符 $\hat{J}_+$ 作用在某个态上使其"超出天花板"，量子力学会判定**状态毁灭**（等于零向量）：

$$\hat{J}_+|j,m_{\max}\rangle = 0$$

> [!danger] 关键推导：为什么 $m_{\max} = j$？
> 将 $\hat{J}_+|j,m_{\max}\rangle = 0$ 代入升算符的性质，可以严格证明：
>
> 1. **最高态必须是** $m_{\max} = j$——这意味着角动量投影的最大值恰好等于角动量量子数 $j$
> 2. **最低态必须是** $m_{\min} = -j$——对称地，降算符的"地板"在 $-j$
> 3. **$2j$ 必须是整数**——从 $m_{\max}$ 降到 $m_{\min}$，每步减 $1$，必须恰好走完 $2j$ 步（整数步），不能是半步。这解释了为什么 $j$ 只能取整数或半整数（$0, 1/2, 1, 3/2, 2, \ldots$），而绝对不能是 $1/3$ 或 $0.14$

#### 完整推导：从对易关系到本征值谱

**第一步**：设定起始态 $|j,m\rangle$，它是 $\hat{J}^2$ 和 $\hat{J}_z$ 的共同本征态：

$$\hat{J}^2|j,m\rangle = j(j+1)\hbar^2|j,m\rangle, \qquad \hat{J}_z|j,m\rangle = m\hbar|j,m\rangle$$

**第二步**：证明 $\hat{J}^2$ 与升降算符对易——$[\hat{J}^2, \hat{J}_\pm] = 0$。因此 $\hat{J}_\pm|j,m\rangle$ 仍然是 $\hat{J}^2$ 的本征态，本征值不变（$j$ 不变），只是 $m$ 变了。

**第三步**：利用 $[\hat{J}_z, \hat{J}_\pm] = \pm\hbar\hat{J}_\pm$，可以证明：

$$\hat{J}_z(\hat{J}_\pm|j,m\rangle) = (m \pm 1)\hbar(\hat{J}_\pm|j,m\rangle)$$

即 $\hat{J}_\pm|j,m\rangle$ 是 $\hat{J}_z$ 的本征态，本征值从 $m\hbar$ 变为 $(m\pm 1)\hbar$。

**第四步**：利用归一化条件确定系数。计算 $\langle j,m|\hat{J}_\mp\hat{J}_\pm|j,m\rangle$，可以得到：

$$|\hat{J}_\pm|j,m\rangle|^2 = \hbar^2(j \mp m)(j \pm m + 1)$$

因此升/降算符的完整作用结果为：

$$\boxed{\hat{J}_\pm|j,m\rangle = \hbar\sqrt{(j \mp m)(j \pm m + 1)}\,|j,m\pm 1\rangle}$$

**第五步**：施加边界条件。

$$\hat{J}_+|j,m_{\max}\rangle = 0 \implies (j - m_{\max})(j + m_{\max} + 1) = 0$$

因为 $j + m_{\max} + 1 > 0$（$m_{\max} \geq 0$ 时显然；$m_{\max} < 0$ 时 $j > 0$ 也保证），所以必须 $m_{\max} = j$。

同理，$\hat{J}_-|j,m_{\min}\rangle = 0 \implies m_{\min} = -j$。

**第六步**：最终结论——角动量的完整本征值谱。

$$\boxed{m = -j,\ -j+1,\ \ldots,\ j-1,\ j}$$

共 $2j + 1$ 个取值，步长严格为 $1$，从 $-j$ 到 $+j$。而 $j$ 的取值可以是任意非负整数或半整数。

> [!tip] 代数的美
> 整个推导**没有用到任何波函数的具体形式**。我们只用了对易关系 $[\hat{J}_i, \hat{J}_j] = i\hbar\epsilon_{ijk}\hat{J}_k$ 这一条公理，就推导出了角动量的全部谱性质。这就是量子力学代数方法的力量——它适用于**所有**满足角动量对易关系的物理系统，无论是轨道角动量、自旋角动量，还是任意角动量。
>
> 这也是为什么角动量对易关系对应 $\mathfrak{su}(2)$ 李代数——整个谱结构完全由李代数的结构决定。

#### 关于轨道角动量 $m$ 必须是整数的几何补充

对于**轨道角动量** $\hat{\mathbf{L}} = \hat{\mathbf{r}} \times \hat{\mathbf{p}}$，除了代数方法给出的 $m = -l, \ldots, l$（步长为 $1$），还有一个非常直观的几何解释。

电子绕 $z$ 轴转动的波函数包含相位因子 $e^{im\phi}$（$\phi$ 是方位角）。当电子绕 $z$ 轴转完整一圈（$\phi \to \phi + 2\pi$），波函数必须回到自身（**单值性条件**）：

$$e^{im(\phi + 2\pi)} = e^{im\phi} \implies e^{i \cdot 2\pi m} = 1$$

在数学上，这要求 **$m$ 必须是整数**。这从三维空间的旋转对称性再次印证了为什么轨道角动量的投影必须一格一格地跳。

> [!question] 为什么自旋可以是半整数？
> 轨道角动量 $m$ 必须是整数（来自波函数单值性），但自旋角动量 $s$ 和 $m_s$ 可以是半整数（如电子 $s = 1/2$）。这是因为自旋不是"绕轴转动"的空间运动，而是粒子的**内禀自由度**——它不需要满足 $e^{im \cdot 2\pi} = 1$ 的约束。自旋角动量没有经典对应。

### 4. 选择规则

对易关系决定了哪些量子跃迁是"允许的"。例如，电偶极跃迁的选择规则 $\Delta l = \pm 1$、$\Delta m = 0, \pm 1$ 可以从角动量对易关系和 Wigner-Eckart 定理推导出来。

---

## 知识图谱：对易关系的全景

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

fig, ax = plt.subplots(figsize=(12, 8))

# Define nodes: (x, y, label, color)
nodes = [
    (6, 7.5, '对易关系\n[A,B]=AB-BA', '#4C78A8'),
    (2, 5.5, '正则对易关系\n[x,p]=iℏ', '#F58518'),
    (6, 5.5, '角动量对易关系\n[Jᵢ,Jⱼ]=iℏεᵢⱼₖJₖ', '#F58518'),
    (10, 5.5, 'Pauli 矩阵\n[σᵢ,σⱼ]=2iεᵢⱼₖσₖ', '#F58518'),
    (1, 3.5, 'Heisenberg\n不确定性原理', '#54A24B'),
    (3.5, 3.5, '正则量子化\n{,}_PB → [,]/iℏ', '#54A24B'),
    (6, 3.5, '同时对角化\n[ A,B]=0 ↔ 共同本征态', '#54A24B'),
    (8.5, 3.5, '升降算符\nJ± 的谱构造', '#54A24B'),
    (11, 3.5, 'SU(2) 李代数\n群论结构', '#54A24B'),
    (3, 1.5, '守恒量判据\n[A,H]=0 → dA/dt=0', '#72B7B2'),
    (6, 1.5, '选择规则\n跃迁矩阵元', '#72B7B2'),
    (9, 1.5, '自旋进动\nLarmor Precession', '#72B7B2'),
]

# Draw nodes
for x, y, label, color in nodes:
    bbox = dict(boxstyle='round,pad=0.4', facecolor=color, alpha=0.85, edgecolor='white', linewidth=1.5)
    ax.text(x, y, label, ha='center', va='center', fontsize=10,
            color='white', fontweight='bold', bbox=bbox)

# Define edges: (from_idx, to_idx)
edges = [
    (0, 1), (0, 2), (0, 3),
    (1, 4), (1, 5),
    (2, 6), (2, 7),
    (3, 8),
    (6, 9), (7, 10), (8, 11),
    (5, 9),
]

for i, j in edges:
    x1, y1 = nodes[i][0], nodes[i][1]
    x2, y2 = nodes[j][0], nodes[j][1]
    dx, dy = x2 - x1, y2 - y1
    length = np.sqrt(dx**2 + dy**2)
    # Shorten by node radius
    shrink = 0.45
    sx = x1 + dx/length * shrink
    sy = y1 + dy/length * shrink
    ex = x2 - dx/length * shrink
    ey = y2 - dy/length * shrink
    ax.annotate('', xy=(ex, ey), xytext=(sx, sy),
                arrowprops=dict(arrowstyle='->', color='#555555', lw=1.5))

ax.set_xlim(-0.5, 12.5)
ax.set_ylim(0.5, 8.5)
ax.set_aspect('equal')
ax.axis('off')
ax.set_title('对易关系的知识图谱：从定义到应用', fontsize=15, fontweight='bold', pad=15)

plt.tight_layout()

# Obsidian Execute Code compatibility
compat_ax = fig.add_axes([0, 0, 1, 1], frameon=False)
compat_ax.set_axis_off()
plt.show()
```

---

## 与其他知识的联系

- [[Unitary-Matrix|酉矩阵]] — Pauli 矩阵的对易关系定义了 $\mathfrak{su}(2)$ 李代数，而 $SU(2)$ 酉矩阵 $e^{i\theta\mathbf{n}\cdot\boldsymbol{\sigma}}$ 正是由这些生成元指数化而来
- [[Quantum-Numbers|量子数]] — $n,l,m_l$ 分别标记 $[\hat{H},\hat{L}^2,\hat{L}_z]$ 这组互相对易的算符的共同本征值
- [[Azimuthal-Quantum-Number|角量子数]] — 角量子数 $l$ 来自 $\hat{L}^2$ 的本征值，其量子化由 $[\hat{L}_i,\hat{L}_j]$ 的代数结构决定
- [[Magnetic-Quantum-Number|磁量子数]] — 磁量子数 $m_l$ 的 $2l+1$ 个取值由升降算符 $\hat{L}_\pm$ 从对易关系导出
- [[Larmor-Precession|拉莫尔进动]] — 自旋在磁场中的进动由 $[\hat{S}_z,\hat{H}] \neq 0$ 驱动
- [[Hyperfine-Structure|超精细结构]] — Fermi 接触相互作用涉及 $\hat{\mathbf{S}}\cdot\hat{\mathbf{I}}$，其本征结构依赖于自旋对易关系
- [[Magnetic-Moment|磁矩]] — 磁矩 $\hat{\boldsymbol{\mu}} = \gamma\hat{\mathbf{J}}$ 满足与角动量相同的对易关系

---

## 典型应用场景

- **判断两个物理量能否同时精确测量**：计算 $[\hat{A},\hat{B}]$，若为零则可以
- **推导不确定性关系**：由 $[\hat{A},\hat{B}]$ 通过 Robertson 不等式得到不确定度下界
- **寻找守恒量**：检查 $[\hat{A},\hat{H}]$，为零则 $\hat{A}$ 守恒
- **构造量子态谱**：用升降算符从对易关系出发，纯代数地推导本征值
- **计算选择规则**：对易关系约束了跃迁矩阵元的非零条件
- **正则量子化**：从经典力学出发，将 Poisson 括号替换为对易子得到量子理论

---

## 📐 核心公式摘要

**核心对易关系：**

- 对易子定义：$[\hat{A},\hat{B}] = \hat{A}\hat{B} - \hat{B}\hat{A}$
- 正则对易关系：$[\hat{x},\hat{p}] = i\hbar$
- 三维推广：$[\hat{x}_i,\hat{p}_j] = i\hbar\delta_{ij}$，$[\hat{x}_i,\hat{x}_j] = 0$，$[\hat{p}_i,\hat{p}_j] = 0$
- 角动量对易关系：$[\hat{J}_i,\hat{J}_j] = i\hbar\epsilon_{ijk}\hat{J}_k$
- 角动量平方与分量：$[\hat{J}^2,\hat{J}_i] = 0$
- Pauli 矩阵：$[\sigma_i,\sigma_j] = 2i\epsilon_{ijk}\sigma_k$

**运算法则：**

- 反对称性：$[\hat{A},\hat{B}] = -[\hat{B},\hat{A}]$
- Leibniz 法则：$[\hat{A},\hat{B}\hat{C}] = [\hat{A},\hat{B}]\hat{C} + \hat{B}[\hat{A},\hat{C}]$
- Jacobi 恒等式：$[\hat{A},[\hat{B},\hat{C}]] + [\hat{B},[\hat{C},\hat{A}]] + [\hat{C},[\hat{A},\hat{B}]] = 0$

**不确定性原理与守恒律：**

- Robertson 不等式：$\Delta A\cdot\Delta B \geq \frac{1}{2}\lvert\langle[\hat{A},\hat{B}]\rangle\rvert$
- 守恒量判据：$[\hat{A},\hat{H}] = 0 \;\Longleftrightarrow\; \hat{A}$ 是运动常数
- Dirac 对应关系：$[\hat{A},\hat{B}] = i\hbar\{A,B\}_{\text{PB}}$

---

## 📝 更新记录

- 2026-06-05: 大幅扩展升降算符方法——完整六步代数推导（构造升降算符 → 核心对易关系 → 边界条件/天花板地板 → 升降系数公式 → 确定 $m_{\max}=j$ 和 $m_{\min}=-j$ → 角动量完整本征值谱），补充轨道角动量 $m$ 必须是整数的几何解释（波函数单值性条件），补充自旋半整数的物理原因
- 2026-06-02: 创建初稿 — 涵盖对易子定义、正则对易关系、角动量对易关系、Pauli 矩阵对易关系、运算法则、不确定性原理、经典对应、知识图谱可视化

## 相关概念

- [[Unitary-Matrix|酉矩阵]] — 对易关系决定哪些变换可以同时对角化
- [[Quantum-Numbers|量子数]] — 对易关系定义了哪些算符可以同时具有确定值
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — $\mathbf{L}\cdot\mathbf{S}$ 改变了哪些算符对易，$L_z,S_z$ 不再是好量子数
