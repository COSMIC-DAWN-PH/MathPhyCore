---
subject:
  - Physics
topic:
  - Quantum Mechanics
  - Atomic Physics
source: "Self-authored"
comprehension: vague
aliases:
  - 简并
  - Degeneracy
  - 能级简并
status: Draft
date: 2026-06-05
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Degeneracy
---

# Degeneracy (简并)

简并（degeneracy）指的是：**两个或更多不同的量子态，具有完全相同的能量**。

> [!tip] 物理图像
> 你可以把能量想成“高度”，量子态想成站在不同位置的人。
> 如果几个人站在**同一高度**，但位置不同，那就是简并。
> 能量这一把“尺子”暂时分不出它们的差别。

## 核心定义

如果一组互不相同的量子态 $\lvert \psi_1 \rangle, \lvert \psi_2 \rangle, \ldots$ 满足

$$
E_1 = E_2 = \cdots = E
$$

那么它们就称为**简并态**，这个共同能量称为**简并能级**。

### 简并度

**简并度**（degeneracy degree）是指同一个能级上态的个数。

例如：

- 若同一能量下有 2 个不同态，则简并度为 2
- 若同一能量下有 3 个不同态，则简并度为 3
- 若完全没有别的态共享这个能量，则称为**非简并**

> [!warning] 不要混淆
> “简并”说的是**能量相同**，不是说波函数长得一样。
> 这些态通常是不同的，只是它们的能量碰巧相同。

## 在原子物理里的例子

在没有外场时，原子哈密顿量往往具有旋转对称性，因此能量常常不依赖磁量子数 $m$。例如在氢原子里，固定 $n,l$ 后，允许的

$$
m=-l,-l+1,\ldots,l
$$

共有

$$
2l+1
$$

个态，它们在不考虑外磁场时通常是简并的。

这正是 [[Magnetic-Quantum-Number|磁量子数]] 和 [[Zeeman-Effect|Zeeman 效应]] 能联系起来的地方：一旦加上外磁场，这种简并就可能被打破。

## 简并为什么会被打破？

如果哈密顿量加入了一个新的扰动项，比如外磁场项、晶体场项，或者自旋-轨道耦合项，那么原来对称的条件被破坏，原本同能量的态就可能分裂到不同能级。

这也是 [[Zeeman-Effect|Zeeman 效应]] 的核心：**外磁场把原本简并的能级劈开**。

## 与 Zeeman 效应的关系

- 在无磁场时，同一个 $l$ 下的多个 $m$ 态简并
- 加入外磁场后，这些态的能量开始依赖 $m$
- 原来的简并被解除，出现能级分裂

## 📐 核心公式摘要

- 简并的数学表达：$E_1=E_2=\cdots$
- 磁量子数取值：$m=-l,-l+1,\ldots,l$
- 简并度：$2l+1$

## 相关概念

- [[Magnetic-Quantum-Number]]
- [[Zeeman-Effect]]
- [[Quantum-Numbers]]

## 📝 更新记录

- 2026-06-05: 新建简并概念页，补充定义、简并度、原子物理例子，并与 [[Zeeman-Effect]]、[[Magnetic-Quantum-Number]] 建立互链。
