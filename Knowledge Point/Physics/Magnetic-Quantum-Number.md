---
subject:
  - Physics
topic:
  - Quantum Mechanics
aliases:
  - 磁量子数
  - 磁量子数 ml
  - 轨道磁量子数
  - Magnetic quantum number
source: "self-authored (量子力学基础)"
comprehension: understood
status: WIP
date: 2026-05-25
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Angular_Momentum
  - Quantum_Numbers
---

# Magnetic Quantum Number

磁量子数（magnetic quantum number）记为 $m_l$，用于标记轨道角动量在某个选定方向（通常是 $z$ 轴）上的投影。它决定同一[[Azimuthal-Quantum-Number|角量子数]] $l$ 下不同空间取向的量子态。

> [!info] 核心图像
> $m_l$ 不是说轨道真的像刚体一样指向某个确定方向，而是说角动量在测量轴上的投影只能取离散值。外加磁场选定一个方向后，不同 $m_l$ 状态会表现出不同能量，这就是塞曼效应的基础。

---

## 定义与取值

给定角量子数 $l$ 后，磁量子数只能取整数：

$$
m_l=-l,-l+1,\cdots,0,\cdots,l-1,l
$$

因此固定 $l$ 时共有：

$$
2l+1
$$

个可能的 $m_l$ 值。

磁量子数对应轨道角动量 $z$ 分量算符 $\hat L_z$ 的本征值：

$$
\hat L_zY_l^m=m_l\hbar Y_l^m
$$

因此：

$$
L_z=m_l\hbar
$$

---

## 为什么叫“磁”量子数

在没有外加磁场时，空间没有优先方向，同一 $l$ 下不同 $m_l$ 往往能量相同。但一旦加入沿 $z$ 方向的磁场 $\mathbf B$，磁场选定了空间方向，轨道磁矩和磁场相互作用，不同 $m_l$ 的能量会分裂。

轨道磁矩与角动量关系为：

$$
\boldsymbol{\mu}_L=-\frac{e}{2m_e}\mathbf L
$$

对应 $z$ 分量：

$$
\mu_{L,z}=-\mu_B m_l
$$

其中 $\mu_B$ 是玻尔磁子：

$$
\mu_B=\frac{e\hbar}{2m_e}
$$

这就是 $m_l$ 与磁场中能级分裂直接相关的原因。

---

## 与轨道取向的关系

固定 $l$ 时，不同 $m_l$ 表示同一角动量大小下不同的投影值：

$$
L=\sqrt{l(l+1)}\hbar,\qquad L_z=m_l\hbar
$$

例如 $l=1$ 的 $p$ 子壳层有：

$$
m_l=-1,0,1
$$

三个状态，通常对应三个 $p$ 轨道方向。需要注意，真实球谐函数 $Y_l^m$ 是复函数；化学中常用的 $p_x,p_y,p_z$ 是由 $m_l=\pm1,0$ 的复球谐函数线性组合得到的实轨道。

> [!warning] 常见错误
> $m_l$ 的最大值是 $l$，不是 $n$。例如 $n=3,l=1$ 时，$m_l$ 只能是 $-1,0,1$，不能取 $\pm2$。

---

## 与主量子数和角量子数的关系

完整取值链条为：

$$
n=1,2,3,\cdots
$$

$$
l=0,1,\cdots,n-1
$$

$$
m_l=-l,-l+1,\cdots,l
$$

所以 $m_l$ 是最内层的标签，必须先知道 $n$ 和 $l$ 才能判断它能取哪些值。

---

## 典型例子

### $s$ 子壳层

$$
l=0,\quad m_l=0
$$

只有 1 个空间轨道。

### $p$ 子壳层

$$
l=1,\quad m_l=-1,0,1
$$

共有 3 个空间轨道。

### $d$ 子壳层

$$
l=2,\quad m_l=-2,-1,0,1,2
$$

共有 5 个空间轨道。

---

## 相关概念

- [[Magnetic-Moment|磁矩]] — 磁量子数直接标记磁矩在 $z$ 方向的投影值
- [[Torque|力矩]] — 磁矩在外磁场中受力矩 $\vec{\tau}=\vec{\mu}\times\vec{B}$，与磁量子数能级分裂相关
- [[Larmor-Precession|拉莫尔进动]] — 外磁场中磁矩与角动量的经典进动图像
- [[Quantum-Numbers|量子数]]
- [[Hydrogen-Atom-Model|氢原子模型]]
- [[Principal-Quantum-Number|主量子数]]
- [[Azimuthal-Quantum-Number|角量子数]]
- [[Method-of-Separation-of-Variables|分离变量法]]
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 耦合后 $m_l$ 不再是好量子数
- [[Force-on-Magnetic-Dipole-in-Gradient-Field|磁矩在梯度磁场中的受力]] — 不同 $m_l$ 对应的 $\mu_z$ 差异导致斯特恩-盖拉赫实验中的束分裂
- [[Zeeman-Effect|塞曼效应]] — 外磁场中不同 $m_l$ 的能级分裂，磁量子数的直接物理体现
- [[Fine-Structure|精细结构]] — 精细结构打破了同一 $n$ 下不同 $l$ 的简并

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $m_l$ | 磁量子数 | $m_l=-l,-l+1,\cdots,l$ |
| $\hat L_z$ | 角动量 $z$ 分量本征值 | $\hat L_zY_l^m=m_l\hbar Y_l^m$ |
| $L_z$ | 轨道角动量投影 | $L_z=m_l\hbar$ |
| $\mu_{L,z}$ | 轨道磁矩投影 | $\mu_{L,z}=-\mu_Bm_l$ |
| 固定 $l$ 的状态数 | 磁量子数个数 | $2l+1$ |

---

## 📝 更新记录

- 2026-05-25: 创建初稿，说明磁量子数的取值、角动量投影、磁场意义和与其他量子数的关系。
