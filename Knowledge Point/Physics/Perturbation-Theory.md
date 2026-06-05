---
subject:
  - Physics
topic:
  - Quantum Mechanics
source: "Griffiths QM, Ch.6"
comprehension: vague
aliases:
  - 微扰论
  - 定态微扰论
  - 含时微扰论
  - Perturbation Theory
status: Draft
date: 2026-06-04
tags:
  - Quantum_Mechanics
  - Approximation_Method
  - Atomic_Physics
  - Perturbation
---

# Perturbation-Theory（微扰论）

> 当精确求解薛定谔方程不可行时，微扰论提供了一套系统的方法：把"小修正"逐级加入已知解中，得到近似能量和波函数。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 微扰论就像"在已知答案旁边微调"。如果哈密顿量 $H = H_0 + \lambda V$ 中 $V$ 很小，那么 $H$ 的本征态应该和 $H_0$ 的本征态"差不多"，只是有微小偏移——我们逐级计算这个偏移量。

真实物理系统很少能精确求解。氢原子的精细结构、Stark 效应、AC Stark shift 等，都是在已知的"未扰动"解（如库仑势的精确解）上叠加一个"小扰动"项来处理的。

---

## 核心定义与公式

### 一、定态微扰论（Time-independent Perturbation Theory）

适用于：哈密顿量 $H = H_0 + \lambda V$，其中 $\lambda V$ 是与时间无关的小修正。

**已知条件**：$H_0$ 的本征方程可精确求解：

$$
H_0 |n^{(0)}\rangle = E_n^{(0)} |n^{(0)}\rangle
$$

#### 非简并微扰论

假设 $E_n^{(0)}$ 是非简并的，将能量和波函数展开为 $\lambda$ 的幂级数：

$$
E_n = E_n^{(0)} + \lambda E_n^{(1)} + \lambda^2 E_n^{(2)} + \cdots
$$

$$
|n\rangle = |n^{(0)}\rangle + \lambda |n^{(1)}\rangle + \lambda^2 |n^{(2)}\rangle + \cdots
$$

**一阶能量修正**：

$$
E_n^{(1)} = \langle n^{(0)} | V | n^{(0)} \rangle
$$

> 物理含义：一阶修正是扰动在未扰动态上的"平均值"（期望值）。

**二阶能量修正**：

$$
E_n^{(2)} = \sum_{m \neq n} \frac{|\langle m^{(0)} | V | n^{(0)} \rangle|^2}{E_n^{(0)} - E_m^{(0)}}
$$

> 分母 $E_n^{(0)} - E_m^{(0)}$ 越小（能级越接近），贡献越大——这就是**能级排斥**（level repulsion）的来源。

**一阶波函数修正**：

$$
|n^{(1)}\rangle = \sum_{m \neq n} \frac{\langle m^{(0)} | V | n^{(0)} \rangle}{E_n^{(0)} - E_m^{(0)}} |m^{(0)}\rangle
$$

#### 简并微扰论

当 $E_n^{(0)}$ 有简并时，一阶能量修正需要在简并子空间内对角化矩阵：

$$
(W)_{ij} = \langle n_i^{(0)} | V | n_j^{(0)} \rangle, \quad i,j = 1, 2, \ldots, d
$$

其中 $\{|n_i^{(0)}\rangle\}$ 张成简并子空间。对角化 $W$ 得到的本征值即为一阶修正。

### 二、含时微扰论（Time-dependent Perturbation Theory）

适用于：$H = H_0 + V(t)$，其中 $V(t)$ 是随时间变化的微扰。

**一阶跃迁概率**（Fermi's Golden Rule 的来源）：

系统在 $t=0$ 处于 $|i\rangle$，$t$ 时刻跃迁到 $|f\rangle$ 的概率振幅：

$$
c_f^{(1)}(t) = \frac{1}{i\hbar} \int_0^t \langle f | V(t') | i \rangle e^{i\omega_{fi}t'} dt'
$$

其中 $\omega_{fi} = (E_f^{(0)} - E_i^{(0)})/\hbar$。

**Fermi's Golden Rule**（常微扰极限 $t \to \infty$）：

$$
\Gamma_{i \to f} = \frac{2\pi}{\hbar} |\langle f | V | i \rangle|^2 \, \rho(E_f)
$$

其中 $\rho(E_f)$ 是终态的态密度。

---

## 关键性质

- **收敛性**：微扰级数通常是**渐近级数**，不一定收敛——只取前几项即可
- **适用条件**：扰动矩阵元 $\langle m|V|n\rangle$ 远小于能级间距 $|E_n^{(0)} - E_m^{(0)}|$
- **二阶修正永远使基态能量降低**：因为所有 $E_0^{(0)} - E_m^{(0)} < 0$，所以 $E_0^{(2)} < 0$
- **能级排斥**：两个能级越靠近，二阶修正把它们推得越开

> [!warning] 常见错误
> 简并情形不能直接套用非简并公式——分母为零会发散！必须先在简并子空间内对角化微扰矩阵。

> [!warning] 适用边界
> 当微扰矩阵元与能级间距相当时，微扰论失效，需用变分法或数值方法。

---

## 与其他知识的联系

- [[Fine-Structure|精细结构]] — 自旋-轨道耦合作为微扰修正氢原子能级
- [[Zeeman-Effect|塞曼效应]] — 外磁场作为微扰，引起能级分裂（Zeeman 分裂）
- [[Hyperfine-Structure|超精细结构]] — 核磁矩与电子磁矩的相互作用作为微扰
- [[Hydrogen-Atom-Model|氢原子模型]] — 未扰动系统（$H_0$）的精确解
- [[Commutation-Relation|对易关系]] — 微扰论中常用对易关系简化矩阵元计算

---

## 典型应用场景

- **Stark 效应**：外电场对原子能级的修正（线性 Stark 效应、二次 Stark 效应）
- **AC Stark shift**：交流电场（激光）引起的动态能级位移，量子计算中用于寻址
- **精细结构**：相对论修正 + 自旋-轨道耦合作为 $H_0$ 的微扰
- **超精细结构**：核自旋效应作为微扰修正
- **Casimir 效应**：量子真空涨落的微扰计算

> [!info] 在量子计算中的角色
> 中性原子量子计算中，AC Stark shift 利用失谐激光产生可控的能级位移，是**单比特寻址**和**虚拟 Z 门**的物理基础。其理论推导正是含时微扰论的直接应用。

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\omega_{fi}$ | Bohr 频率 | $(E_f^{(0)} - E_i^{(0)}) / \hbar$ |

含 bra-ket 记号的公式（无法安全放入表格单元格）：

- **一阶能量修正** $E_n^{(1)}$：$\langle n^{(0)} \lvert V \rvert n^{(0)} \rangle$
- **二阶能量修正** $E_n^{(2)}$：$\displaystyle\sum_{m \neq n} \frac{\lvert \langle m^{(0)} \lvert V \rvert n^{(0)} \rangle \rvert^2}{E_n^{(0)} - E_m^{(0)}}$
- **跃迁速率** $\Gamma_{i \to f}$（Fermi's Golden Rule）：$\displaystyle\frac{2\pi}{\hbar} \lvert \langle f \lvert V \rvert i \rangle \rvert^2 \rho(E_f)$

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 定态微扰论（非简并 + 简并）、含时微扰论、Fermi's Golden Rule
