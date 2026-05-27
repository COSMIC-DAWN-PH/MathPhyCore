---
subject:
  - Physics
topic:
  - Classical Mechanics
aliases:
  - 力矩
  - torque
  - 转矩
status: In-Progress
date: 2026-05-27
tags:
  - Physics
  - Classical_Mechanics
  - Rotational_Dynamics
  - Angular_Momentum
---

# Torque

力矩（Torque）是改变物体**转动**状态的原因，正如力是改变物体**平动**状态的原因一样。你可以把它理解为"使物体绕某个轴或点发生旋转的效应"。

---

## 定义与公式

力矩（通常用 $\vec{\tau}$ 或 $\vec{M}$ 表示）定义为作用力 $\vec{F}$ 与力臂（从转动参考点到力的作用点的位矢 $\vec{r}$）的叉乘：

$$
\vec{\tau} = \vec{r} \times \vec{F}
$$

由此可拆解出三个关键点：

### 大小

$$
\tau = r F \sin\theta
$$

其中 $\theta$ 是 $\vec{r}$ 和 $\vec{F}$ 之间的夹角。

### 方向

力矩是一个矢量，方向由右手定则决定：右手四指从 $\vec{r}$ 方向弯向 $\vec{F}$ 方向，大拇指所指的方向即为力矩方向（垂直于 $\vec{r}$ 和 $\vec{F}$ 所在的平面）。

### 直觉体验

> [!tip] 推门的类比
> 想象推一扇门：推门轴附近（$r$ 小）需要极大的力才能推开；推门把手（$r$ 最大）就很轻松。同时，垂直于门面推（$\sin 90° = 1$）效果最好，平行于门面推（$\sin 0° = 0$）门绝对转不动。

---

## 力矩与转动的关系

在牛顿力学中，力矩之于转动，就如同力之于平动：

- **平动的牛顿第二定律**：$\vec{F} = \frac{d\vec{p}}{dt}$（力是动量随时间的变化率）
- **转动的牛顿第二定律**：$\vec{\tau} = \frac{d\vec{L}}{dt}$（力矩是**角动量**随时间的变化率）

只要一个系统不受外力矩（$\vec{\tau} = 0$），它的角动量就守恒；而只要你想改变一个物体的旋转状态（让它转得更快、更慢，或改变旋转轴），就必须施加力矩。

> [!info] 与磁矩的关联
> 磁矩在外磁场中受到的力矩为 $\vec{\tau} = \vec{\mu} \times \vec{B}$，这是力矩公式在电磁学中的重要应用。详见 [[Magnetic-Moment|磁矩]]。

---

## 量纲与单位

| 项目 | 结果 |
|------|------|
| 量纲 | $\text{M} \cdot \text{L}^2 \cdot \text{T}^{-2}$（长度 $\times$ 力：$\text{L} \cdot \text{MLT}^{-2}$） |
| SI 单位 | $\text{N} \cdot \text{m}$（牛顿米） |

> [!danger] 力矩单位不能写成焦耳
> 虽然力矩（$\text{N} \cdot \text{m}$）和能量/功（焦耳 $\text{J}$，也是 $\text{N} \cdot \text{m}$）在量纲和基本单位上完全相同，但它们在物理上是截然不同的概念：功是标量（力与位移的**点乘**），而力矩是矢量（位矢与力的**叉乘**）。力矩的单位只写成 $\text{N} \cdot \text{m}$，绝不能写成 $\text{J}$。

---

## 相关概念

- [[Magnetic-Moment|磁矩]] — 磁矩在外磁场中受力矩作用
- [[Magnetic-Quantum-Number|磁量子数]] — 与磁矩的磁场效应密切相关
- [[Quantum-Numbers|量子数]]
- [[Spontaneous-Symmetry-Breaking|自发对称性破缺]] — 角动量守恒与对称性的深层联系

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\vec{\tau}$ | 力矩 | $\vec{\tau} = \vec{r} \times \vec{F}$ |
| $\tau$ | 力矩大小 | $\tau = rF\sin\theta$ |
| $\vec{\tau}$ | 力矩与角动量的关系 | $\vec{\tau} = \frac{d\vec{L}}{dt}$ |
| SI 单位 | 牛顿米 | $\text{N} \cdot \text{m}$（不可写为 $\text{J}$） |

---

## 📝 更新记录

- 2026-05-27: 从 Gemini 对话整理创建，涵盖定义、物理意义、量纲单位及易错点。
