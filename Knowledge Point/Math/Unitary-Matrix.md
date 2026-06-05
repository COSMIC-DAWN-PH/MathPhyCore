---
subject:
  - Math
topic:
  - Linear Algebra
aliases:
  - 酉矩阵
  - Unitary Matrix
  - 幺正矩阵
  - 酉变换
  - Unitary Transformation
source: "self-authored (线性代数与量子力学)"
comprehension: understood
status: WIP
date: 2026-06-01
tags:
  - Math
  - Linear-Algebra
  - Matrix
  - Quantum-Mechanics
  - Group-Theory
---

# Unitary Matrix (酉矩阵)

> 酉矩阵是复向量空间中的"保距变换"——它保持内积、范数和角度不变，是正交矩阵在复数域的自然推广。量子力学中一切不改变概率的时间演化都由酉矩阵/酉算子描述。

---

## 数学直觉

在实向量空间 $\mathbb{R}^n$ 中，正交矩阵 $O$（满足 $O^T O = I$）表示**旋转和反射**：它保持向量长度和向量之间的夹角。

在复向量空间 $\mathbb{C}^n$ 中，我们同样需要一种"不改变内积"的变换——这就是**酉矩阵**。区别仅在于：复内积涉及共轭，所以转置 $T$ 升级为**共轭转置** $\dagger$：

$$\langle \mathbf{u}, \mathbf{v} \rangle = \mathbf{u}^\dagger \mathbf{v} = \sum_i \overline{u_i} v_i$$

> [!tip] 物理直觉
> 在量子力学中，态矢量 $\vert\psi\rangle$ 的模方 $\langle\psi\vert\psi\rangle$ 是总概率（必须等于 1）。任何合法的物理演化 $U$ 必须保证 $\langle U\psi\vert U\psi\rangle = \langle\psi\vert\psi\rangle$，这等价于 $U^\dagger U = I$——即 $U$ 是酉算子。

> [!info] 术语由来
> "酉"（unitary）源自拉丁语 *unitas*（统一、单位），强调其保持"单位长度"的性质。中文有时也译作"幺正矩阵"。

---

## 核心定义与公式

### 定义

一个 $n \times n$ 复矩阵 $U$ 称为**酉矩阵 (Unitary Matrix)**，若满足以下等价条件之一：

$$\boxed{U^\dagger U = U U^\dagger = I_n}$$

即 $U^\dagger = U^{-1}$（共轭转置等于逆矩阵）。

其中 $U^\dagger \equiv (U^*)^T = \overline{U}^T$ 是 $U$ 的共轭转置（Hermitian conjugate）。

### 等价表述

| 表述 | 含义 |
|------|------|
| $U^\dagger U = I$ | 列向量构成 $\mathbb{C}^n$ 的标准正交基 |
| $U U^\dagger = I$ | 行向量构成 $\mathbb{C}^n$ 的标准正交基 |
| $\langle U\mathbf{x}, U\mathbf{y}\rangle = \langle\mathbf{x},\mathbf{y}\rangle$ | 保持内积（对所有 $\mathbf{x},\mathbf{y}\in\mathbb{C}^n$） |
| $\lVert U\mathbf{x} \rVert = \lVert \mathbf{x} \rVert$ | 保持范数（对所有 $\mathbf{x}\in\mathbb{C}^n$） |
| $U^{-1} = U^\dagger$ | 逆等于共轭转置 |

用列向量表示 $U = [\mathbf{u}_1\; \mathbf{u}_2\; \cdots\; \mathbf{u}_n]$：

$$\mathbf{u}_i^\dagger \mathbf{u}_j = \delta_{ij} \quad \Longleftrightarrow \quad \text{各列互相正交且模长为 1}$$

---

## 关键性质

### 1. 谱性质（特征值）

所有特征值都位于复平面的单位圆上：

$$\lambda_i = e^{i\theta_i}, \quad \theta_i \in \mathbb{R}$$

> [!warning] 常见错误
> 正交矩阵的实特征值只能是 $\pm 1$（因为 $O^T O = I$ 且 $O$ 是实矩阵 → 若 $\lambda$ 是实特征值，则 $\lambda = \pm 1$）。但**酉矩阵的特征值可以是单位圆上的任意复数** $e^{i\theta}$，不限于 $\pm 1$。

- 属于不同特征值的特征向量互相正交：若 $\lambda_i \neq \lambda_j$，则 $\mathbf{v}_i^\dagger \mathbf{v}_j = 0$
- 代数重数 = 几何重数（酉矩阵可对角化）

### 2. 行列式

$$\det U = e^{i\varphi} = \prod_{k=1}^n e^{i\theta_k}$$

即 $|\det U| = 1$。特别地，$\det U = +1$ 的酉矩阵构成**特殊酉群** $SU(n)$。

### 3. 代数性质

- **封闭性**：若 $U, V$ 是酉矩阵，则 $UV$ 也是酉矩阵
- **存在单位元**：$I_n$ 是酉矩阵
- **存在逆元**：$U^{-1} = U^\dagger$ 也是酉矩阵
- **结合律**：矩阵乘法自然满足

→ 全体 $n$ 阶酉矩阵构成**酉群 (Unitary Group)**，记作 $U(n)$。这是一个紧致李群。

> [!info] 三个重要的矩阵群
> | 群 | 定义 | 维数 (实李群) |
> |----|------|---------------|
> | $U(n)$ | $\{U \in \mathbb{C}^{n\times n}: U^\dagger U = I\}$ | $n^2$ |
> | $SU(n)$ | $\{U \in U(n): \det U = 1\}$ | $n^2 - 1$ |
> | $O(n)$ | $\{O \in \mathbb{R}^{n\times n}: O^T O = I\}$ | $n(n-1)/2$ |

### 4. 保范性（几何本质）

$$\|U\mathbf{x}\|^2 = (U\mathbf{x})^\dagger (U\mathbf{x}) = \mathbf{x}^\dagger U^\dagger U \mathbf{x} = \mathbf{x}^\dagger \mathbf{x} = \|\mathbf{x}\|^2$$

这意味着 $U$ 是**等距同构 (isometry)**：它将球面映射到自身。

---

## 谱分解（Spectral Theorem for Unitary Matrices）

任何酉矩阵 $U$ 可以酉对角化：

$$\boxed{U = V \Lambda V^\dagger}$$

其中：
- $V$ 也是酉矩阵（其列是 $U$ 的特征向量）
- $\Lambda = \operatorname{diag}(e^{i\theta_1}, e^{i\theta_2}, \ldots, e^{i\theta_n})$

> [!tip] 记忆技巧
> 酉矩阵的谱分解 = 在某个正交基下，酉变换只不过是**对每个基向量单独乘以一个相位因子** $e^{i\theta_k}$。这就像"旋转"分解到各个独立方向上。

---

## 与 Hermitian 矩阵的深刻联系

这是量子力学中最重要的数学事实之一：

> **每一个酉矩阵 $U$ 都可以写成一个 Hermitian 矩阵 $H$ 的矩阵指数：**
>
> $$\boxed{U = e^{iH},\qquad H^\dagger = H}$$

反之，若 $H$ 是 Hermitian 矩阵，则 $e^{iH}$ 一定是酉矩阵：

$$(e^{iH})^\dagger = e^{-iH^\dagger} = e^{-iH} = (e^{iH})^{-1}$$

这就是为什么在量子力学中，**Hamiltonian（能量算符，Hermitian）生成的时间演化 $U(t) = e^{-iHt/\hbar}$ 一定是酉的**。

| 数学对象 | 物理角色 | 对应关系 |
|----------|----------|----------|
| Hermitian 矩阵 $H$ | 可观测物理量（能量、动量等） | $H$ 的特征值 $\in \mathbb{R}$（实数 = 可测量） |
| 酉矩阵 $U = e^{iH}$ | 时间演化、对称变换 | $U$ 的特征值 $\in$ 单位圆（保概率） |

> [!danger] 常见错误
> 上述公式写为 $U = e^{iH}$ 而不是 $U = e^{H}$。若 $H$ 是 Hermitian，则 $e^{H}$ 是正定的但**不是酉的**。必须加 $i$ 因子使指数为反 Hermitian ($iH$ 满足 $(iH)^\dagger = -iH$)，此时指数才得到酉矩阵。

---

## 与其他矩阵类型的关系

| 矩阵类型 | 定义 | 关系 |
|----------|------|------|
| **正交矩阵** $O$ | $O^T O = I$（实矩阵） | 实酉矩阵 = 正交矩阵：$U(n) \cap \mathbb{R}^{n\times n} = O(n)$ |
| **Hermitian 矩阵** $H$ | $H^\dagger = H$ | $e^{iH}$ 是酉矩阵 |
| **正规矩阵 (Normal)** $N$ | $N^\dagger N = N N^\dagger$ | 酉矩阵是正规矩阵的特例 |
| **幺模酉矩阵** | $\det U = 1$ | 构成 $SU(n)$ |

**Venn 式关系**：

$$\text{酉矩阵} \;\subset\; \text{正规矩阵}$$

$$\text{正交矩阵} = \text{酉矩阵} \cap \text{实矩阵}$$

---

## 典型实例

### 例 1：一维酉矩阵 = 相位因子

$n=1$ 时：$U = [u]$ 是 $1 \times 1$ 复矩阵。条件 $U^\dagger U = \overline{u}u = |u|^2 = 1$ 给出：

$$U = e^{i\theta}, \quad U(1) \cong \text{单位圆上的点}$$

$SU(1) = \{1\}$（平凡群）。

### 例 2：Pauli 矩阵

Pauli 矩阵既是 Hermitian 又是酉的（$\sigma_k^\dagger = \sigma_k$ 且 $\sigma_k^2 = I$）：

$$\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix},\quad
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix},\quad
\sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$

它们的 [对易关系](../Physics/Commutation-Relation.md) $[\sigma_i,\sigma_j]=2i\epsilon_{ijk}\sigma_k$ 生成 $SU(2)$ 的李代数：任何 $SU(2)$ 群元可写为

$$U = e^{i\theta\,\mathbf{n}\cdot\boldsymbol{\sigma}} = \cos\theta\,I + i\sin\theta\,(\mathbf{n}\cdot\boldsymbol{\sigma})$$

其中 $\mathbf{n}$ 是单位向量，$\boldsymbol{\sigma} = (\sigma_x, \sigma_y, \sigma_z)$。

### 例 3：二维一般酉矩阵

$U(2)$ 最一般的参数化（4 个实参数）：

$$U = e^{i\alpha}\begin{pmatrix}
e^{i\phi}\cos\theta & e^{i\psi}\sin\theta \\
-e^{-i\psi}\sin\theta & e^{-i\phi}\cos\theta
\end{pmatrix}$$

其中 $\alpha, \phi, \psi \in [0, 2\pi)$，$\theta \in [0, \pi/2]$。去掉整体相位 $e^{i\alpha}$（令 $\det U = 1$）即得 $SU(2)$ 的一般形式。

---

## 在量子力学中的核心应用

### 1. 时间演化算符

薛定谔绘景中，态矢量随时间演化为：

$$\vert\psi(t)\rangle = U(t)\vert\psi(0)\rangle, \quad U(t) = e^{-iHt/\hbar}$$

$U(t)$ 的酉性保证了概率守恒：$\langle\psi(t)\vert\psi(t)\rangle = \langle\psi(0)\vert\psi(0)\rangle = 1$。

> 相关笔记：[[Larmor-Precession|Larmor Precession (拉莫尔进动)]] — 自旋在外磁场中的演化 $U(t) = e^{-i\omega t\,\sigma_z/2}$ 是 $SU(2)$ 酉变换的经典实例。

### 2. 表象变换（Change of Basis）

从表象 $A$ 到表象 $B$ 的变换由一个酉矩阵实现：

$$\vert\psi\rangle_B = U \vert\psi\rangle_A, \quad \hat{O}_B = U \hat{O}_A U^\dagger$$

酉变换保持算符的谱（本征值）和所有物理可观测量不变。

### 3. 量子门（Quantum Gates）

在量子计算中，所有合法的量子逻辑门都是酉矩阵：

| 门 | 矩阵 | 群 |
|----|------|-----|
| Hadamard $H$ | $\frac{1}{\sqrt{2}}\begin{pmatrix}1&1\\1&-1\end{pmatrix}$ | $U(2)$ |
| CNOT | $\begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{pmatrix}$ | $U(4)$ |
| 任意单 qubit 门 | 任意 $U(2)$ 元素 | $U(2)$ |

### 4. 对角化与简正模式

Hermitian 矩阵的酉对角化 $H = U \Lambda U^\dagger$ 是求解量子系统（以及经典耦合谐振子）的核心技术。

---

## Python 可视化：酉矩阵效应

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

# 生成随机的 2×2 酉矩阵
# 方法：对随机复矩阵做 QR 分解，Q 即为酉矩阵
rng = np.random.default_rng(42)
A = rng.normal(0, 1, (2, 2)) + 1j * rng.normal(0, 1, (2, 2))
Q, R = np.linalg.qr(A)
# 归一化相位使 det 在单位圆上
U = Q

# 验证酉性
print(f"U^† U =\n{np.round(Q.conj().T @ Q, 12)}")
print(f"det(U) = {np.linalg.det(U):.6f}, |det(U)| = {abs(np.linalg.det(U)):.6f}")
print(f"Eigenvalues = {np.linalg.eigvals(U)}")
print(f"|Eigenvalues| = {[abs(ev) for ev in np.linalg.eigvals(U)]}")

# 生成一组单位向量（在单位圆上的 2D 复向量 → 等价于四维实空间中的点）
# 可视化：展示原向量和酉变换后向量在 C^2 中的关系
# 简化：展示随机实二维向量经过 SU(2) 型酉变换的效果
theta = np.linspace(0, 2*np.pi, 200)
vecs = np.array([np.cos(theta), np.sin(theta)])  # 单位圆上的点 (实数化处理)

# 构造一个 SU(2) 变换：U = exp(i α n·σ)
alpha = np.pi/3
n_vec = np.array([0, 0, 1])  # 绕 z 轴
pauli_x = np.array([[0, 1], [1, 0]], dtype=complex)
pauli_y = np.array([[0, -1j], [1j, 0]], dtype=complex)
pauli_z = np.array([[1, 0], [0, -1]], dtype=complex)
U_su2 = (np.cos(alpha) * np.eye(2, dtype=complex)
         + 1j * np.sin(alpha) * (n_vec[0]*pauli_x + n_vec[1]*pauli_y + n_vec[2]*pauli_z))

# 作用在实向量上 -> 得到复向量，取其实部和虚部分别可视化
transformed = U_su2 @ vecs.astype(complex)

fig, axes = plt.subplots(1, 3, figsize=(16, 5))

# 图 1：原向量 (单位圆)
axes[0].plot(vecs[0], vecs[1], 'b-', linewidth=2, label=r'Original vectors $\mathbf{v}$')
axes[0].quiver(0, 0, vecs[0, 30], vecs[1, 30], angles='xy', scale_units='xy',
               scale=1, color='blue', width=0.008)
axes[0].set_xlim(-1.5, 1.5); axes[0].set_ylim(-1.5, 1.5)
axes[0].set_aspect('equal')
axes[0].set_xlabel('$x_1$'); axes[0].set_ylabel('$x_2$')
axes[0].set_title(r'Original (unit circle in $\mathbb{R}^2$)', fontsize=12)
axes[0].grid(alpha=0.3)
axes[0].legend(fontsize=10)

# 图 2：特征值在单位圆上
evals = np.linalg.eigvals(U_su2)
circle = plt.Circle((0, 0), 1, fill=False, color='gray', linestyle='--', linewidth=1)
axes[1].add_artist(circle)
axes[1].scatter(evals.real, evals.imag, s=120, c='#e74c3c', zorder=5,
                edgecolors='darkred', linewidths=1.5)
for i, ev in enumerate(evals):
    axes[1].annotate(rf'$e^{{i\theta_{i+1}}}$', (ev.real, ev.imag),
                     textcoords="offset points", xytext=(10, -15 if i==0 else 10),
                     fontsize=10, color='darkred')
axes[1].axhline(0, color='gray', alpha=0.3); axes[1].axvline(0, color='gray', alpha=0.3)
axes[1].set_xlim(-1.3, 1.3); axes[1].set_ylim(-1.3, 1.3)
axes[1].set_aspect('equal')
axes[1].set_xlabel(r'$\mathrm{Re}(\lambda)$'); axes[1].set_ylabel(r'$\mathrm{Im}(\lambda)$')
axes[1].set_title(r'Eigenvalues of $U \in SU(2)$ lie on unit circle', fontsize=12)
axes[1].grid(alpha=0.3)

# 图 3：酉变换效果（取复向量模长验证保范性）
norms_before = np.sqrt(vecs[0]**2 + vecs[1]**2)
norms_after = np.abs(transformed[0])**2 + np.abs(transformed[1])**2
norms_after = np.sqrt(norms_after)

axes[2].plot(theta, norms_before, 'b-', linewidth=2.5, label=r'$\|\mathbf{v}\|$ (original)')
axes[2].plot(theta, norms_after, 'r--', linewidth=2.5, label=r'$\|U\mathbf{v}\|$ (after $U$)')
axes[2].set_xlabel(r'$\theta$ (angle on unit circle)', fontsize=12)
axes[2].set_ylabel('Norm', fontsize=12)
axes[2].set_title(r'Norm Preservation: $\|U\mathbf{v}\| = \|\mathbf{v}\| = 1$', fontsize=12)
axes[2].legend(fontsize=10)
axes[2].set_ylim(0.8, 1.2)
axes[2].grid(alpha=0.3)

plt.tight_layout()

# Obsidian Execute Code compatibility
compat_ax = fig.add_axes([0, 0, 1, 1], frameon=False)
compat_ax.set_axis_off()
plt.show()
```

---

## 📐 核心公式摘要

| 项目 | 公式 |
|------|------|
| 定义 | $U^\dagger U = U U^\dagger = I$，等价于 $U^{-1} = U^\dagger$ |
| 特征值 | $\lambda_k = e^{i\theta_k},\; \theta_k \in \mathbb{R}$（都在单位圆上） |
| 行列式 | $\det U = e^{i\varphi},\; \lvert\det U\rvert = 1$ |
| 谱分解 | $U = V \Lambda V^\dagger$，其中 $V$ 是酉矩阵，$\Lambda = \operatorname{diag}(e^{i\theta_k})$ |
| Hermitian → 酉 | $U = e^{iH}$（$H^\dagger = H$） |
| 酉 → Hermitian | $H = -i\ln U$（取主值分支） |
| 保内积 | $\langle U\mathbf{x}, U\mathbf{y}\rangle = \langle\mathbf{x}, \mathbf{y}\rangle$ |
| 保范数 | $\|U\mathbf{x}\| = \|\mathbf{x}\|$ |
| $SU(n)$ | $\{U \in U(n): \det U = 1\}$，维数 $n^2-1$ |
| Pauli 生成 $SU(2)$ | $U = e^{i\theta\,\mathbf{n}\cdot\boldsymbol{\sigma}} = \cos\theta\,I + i\sin\theta\,(\mathbf{n}\cdot\boldsymbol{\sigma})$ |

---

## 相关概念

- [[Gaussian-Integral|Gaussian Integral (高斯积分)]] — 多变量高斯积分中需要正交/酉对角化协方差矩阵
- [[Larmor-Precession|Larmor Precession (拉莫尔进动)]] — 自旋在外磁场中的时间演化是 $SU(2)$ 酉变换的物理实例
- 正交矩阵 (Orthogonal Matrix) — 酉矩阵在实数域的特例
- Hermitian 矩阵 (Hermitian Matrix) — 经指数映射 $e^{iH}$ 生成酉矩阵
- [[Commutation-Relation|对易关系 (Commutation Relation)]] — Pauli 矩阵的对易子 $[\sigma_i,\sigma_j]=2i\epsilon_{ijk}\sigma_k$ 定义了 $\mathfrak{su}(2)$ 李代数
- 正规矩阵 (Normal Matrix) — 酉矩阵是正规矩阵的子类

---

## 📝 更新记录

- 2026-06-02: 添加反向链接至 [[Commutation-Relation|对易关系]] — Pauli 矩阵对易关系
- 2026-06-01: 创建初稿 — 涵盖定义、性质、谱分解、与 Hermitian 的联系、量子力学应用、Python 可视化、核心公式表
