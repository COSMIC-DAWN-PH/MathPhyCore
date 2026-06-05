---
subject:
  - Physics
topic:
  - Quantum Mechanics
aliases:
  - 角量子数
  - 方位量子数
  - 轨道角动量量子数
  - Azimuthal quantum number
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

# Azimuthal Quantum Number

角量子数（azimuthal quantum number），也常叫轨道角动量量子数，记为 $l$。它决定电子轨道角动量的大小、原子轨道的角向形状，并限制[[Magnetic-Quantum-Number|磁量子数]] $m_l$ 的可取值。

> [!info] 核心图像
> $l$ 描述的不是电子像小球一样绕核运动的经典轨道半径，而是波函数角向结构的复杂程度。$l=0$ 的 $s$ 态没有轨道角动量；$l$ 越大，角向节点和方向性越明显。

---

## 定义与取值

给定[[Principal-Quantum-Number|主量子数]] $n$ 后，角量子数只能取：

$$
l=0,1,2,\cdots,n-1
$$

因此 $l$ 永远不能等于或大于 $n$。

角量子数对应轨道角动量算符平方 $\hat L^2$ 的本征值：

$$
\hat L^2Y_l^m=l(l+1)\hbar^2Y_l^m
$$

所以轨道角动量大小为：

$$
L=\sqrt{l(l+1)}\hbar
$$

---

## 轨道字母

角量子数和轨道符号的对应关系为：

| $l$ | 轨道符号 | 名称 | 角动量大小 |
|---:|:---:|:---|:---|
| 0 | $s$ | sharp | $0$ |
| 1 | $p$ | principal | $\sqrt{2}\hbar$ |
| 2 | $d$ | diffuse | $\sqrt{6}\hbar$ |
| 3 | $f$ | fundamental | $\sqrt{12}\hbar$ |
| 4 | $g$ | 后续按字母延伸 | $\sqrt{20}\hbar$ |

因此 $n=3,l=2$ 对应 $3d$ 子壳层；$n=2,l=1$ 对应 $2p$ 子壳层。

---

## 角节点

角量子数还决定角节点数：

$$
N_{\mathrm{angular}}=l
$$

角节点是波函数角向部分为零的面或锥面，会影响轨道形状：

- $s$ 轨道：$l=0$，无角节点，角向分布球对称；
- $p$ 轨道：$l=1$，1 个角节点，呈现方向性；
- $d$ 轨道：$l=2$，2 个角节点，角向结构更复杂。

> [!tip] 记忆方式
> $l$ 可以看成“角向复杂度计数器”：$l$ 越大，球面上的波函数花纹越复杂，角节点越多。

---

## 与磁量子数的关系

给定 $l$ 后，磁量子数必须满足：

$$
m_l=-l,-l+1,\cdots,0,\cdots,l-1,l
$$

所以每个 $l$ 子壳层包含：

$$
2l+1
$$

个不同的 $m_l$ 状态，也就是 $2l+1$ 个空间轨道。

例如：

- $l=0$：$m_l=0$，1 个 $s$ 轨道；
- $l=1$：$m_l=-1,0,1$，3 个 $p$ 轨道；
- $l=2$：$m_l=-2,-1,0,1,2$，5 个 $d$ 轨道。

---

## 与主量子数的关系

主量子数 $n$ 限制角量子数 $l$，因此不同壳层能容纳的子壳层不同：

| $n$ | 允许的 $l$ | 子壳层 |
|---:|:---|:---|
| 1 | 0 | $1s$ |
| 2 | 0, 1 | $2s,2p$ |
| 3 | 0, 1, 2 | $3s,3p,3d$ |
| 4 | 0, 1, 2, 3 | $4s,4p,4d,4f$ |

> [!danger] 常见严重错误
> 不要把 $l$ 理解成“第几个轨道”。$l$ 是角动量大小的量子数；轨道的完整空间标签至少需要 $(n,l,m_l)$。

---

## 相关概念

- [[Quantum-Numbers|量子数]]
- [[Hydrogen-Atom-Model|氢原子模型]]
- [[Principal-Quantum-Number|主量子数]]
- [[Magnetic-Quantum-Number|磁量子数]]
- [[Method-of-Separation-of-Variables|分离变量法]]
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — $l$ 决定自旋-轨道耦合的有无与强度

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $l$ | 角量子数 | $l=0,1,\cdots,n-1$ |
| $\hat L^2$ | 轨道角动量平方本征值 | $\hat L^2Y_l^m=l(l+1)\hbar^2Y_l^m$ |
| $L$ | 轨道角动量大小 | $L=\sqrt{l(l+1)}\hbar$ |
| $N_{\mathrm{angular}}$ | 角节点数 | $l$ |
| 子壳层轨道数 | 固定 $l$ 的 $m_l$ 个数 | $2l+1$ |

---

## 📝 更新记录

- 2026-05-25: 创建初稿，说明角量子数的物理意义、轨道字母、角节点和与 $n,m_l$ 的关系。
