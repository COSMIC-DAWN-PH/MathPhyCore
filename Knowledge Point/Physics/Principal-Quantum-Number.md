---
subject:
  - Physics
topic:
  - Quantum Mechanics
aliases:
  - 主量子数
  - 主量子数 n
  - Principal quantum number
source: "self-authored (量子力学基础)"
comprehension: understood
status: WIP
date: 2026-05-25
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Quantum_Numbers
---

# Principal Quantum Number

主量子数（principal quantum number）记为 $n$，是标记原子束缚态能级与壳层的量子数。它首先决定电子波函数的径向尺度和能量主层级，并进一步限制[[Azimuthal-Quantum-Number|角量子数]] $l$ 的可取值。

> [!info] 核心图像
> $n$ 像是在说电子波函数“整体有多大、能级有多高”。在氢原子中，$n$ 越大，电子平均离原子核越远，能量越接近电离极限 $E=0$。

---

## 定义与取值

主量子数只能取正整数：

$$
n=1,2,3,\cdots
$$

它是三种空间量子数中最外层的标签。给定 $n$ 后，允许的角量子数为：

$$
l=0,1,2,\cdots,n-1
$$

因此 $n$ 不只是一个能级编号，也决定这一壳层中有多少种可能的轨道角动量状态。

---

## 氢原子能级

对非相对论氢原子，能量只依赖主量子数 $n$：

$$
E_n=-\frac{13.6\ \mathrm{eV}}{n^2}
$$

更一般地，对核电荷数为 $Z$ 的类氢离子：

$$
E_n=-\frac{Z^2\,13.6\ \mathrm{eV}}{n^2}
$$

这意味着：

- $n=1$ 是基态，能量最低；
- $n$ 越大，$E_n$ 越接近 $0$；
- 当 $n\to\infty$ 时，电子接近电离状态。

> [!warning] 氢原子与多电子原子不同
> 氢原子的能量只依赖 $n$ 是一个特殊结果。多电子原子中，由于电子间相互作用和屏蔽效应，同一 $n$ 下不同 $l$ 的能量通常不再相同。

### 能量公式从哪里来

这个 $1/n^2$ 结构可以先从 [[Hydrogen-Atom-Model|氢原子模型]] 的 Bohr 假设看出来。核心假设是：原子存在不辐射的定态轨道，允许轨道满足角动量量子化 $m_evr=n\hbar$，不同定态之间跃迁时满足 $h\nu=E_i-E_f$。

具体推导路线是：

1. 库仑力提供向心力：

$$
\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r^2}=\frac{m_ev^2}{r}
$$

2. 电子轨道角动量被量子化：

$$
m_evr=n\hbar
$$

3. 两式联立得到允许半径：

$$
r_n=a_0n^2
$$

4. 总能量为动能加库仑势能：

$$
E=K+V=-\frac{1}{2}\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

代入 $r_n\propto n^2$，就得到

$$
E_n\propto-\frac{1}{n^2}
$$

更完整的推导见 [[Hydrogen-Atom-Model|氢原子模型]]。在现代量子力学中，这个能级不是来自电子真的沿圆轨道运动，而是来自库仑势下定态薛定谔方程的束缚态本征值；Bohr 假设是通向正确结果的半经典桥梁。

---

## 壳层与轨道数量

固定 $n$ 时，允许的 $l$ 值共有 $n$ 个：

$$
l=0,1,\cdots,n-1
$$

每个 $l$ 又允许 $2l+1$ 个[[Magnetic-Quantum-Number|磁量子数]] $m_l$。所以第 $n$ 层的空间轨道总数为：

$$
\sum_{l=0}^{n-1}(2l+1)=n^2
$$

如果考虑电子自旋，则每个空间轨道可容纳两个电子，因此第 $n$ 层最多容纳：

$$
2n^2
$$

个电子。

---

## 径向节点

在氢原子轨道中，主量子数也和径向节点数有关。给定 $n,l$，径向节点数为：

$$
N_{\mathrm{radial}}=n-l-1
$$

径向节点是波函数径向部分 $R_{nl}(r)$ 改变符号的位置，反映电子概率分布在半径方向上的振荡结构。

> [!tip] 记忆方式
> $n$ 是“总层数感”，$l$ 吃掉一部分角向结构，剩下的 $n-l-1$ 就体现在径向节点上。

---

## 与其他量子数的关系

主量子数、角量子数、磁量子数的关系是：

$$
n=1,2,3,\cdots
$$

$$
l=0,1,\cdots,n-1
$$

$$
m_l=-l,-l+1,\cdots,l
$$

例如 $n=3$ 时：

- $l=0$：$3s$，$m_l=0$
- $l=1$：$3p$，$m_l=-1,0,1$
- $l=2$：$3d$，$m_l=-2,-1,0,1,2$

---

## 相关概念

- [[Quantum-Numbers|量子数]]
- [[Hydrogen-Atom-Model|氢原子模型]]
- [[Azimuthal-Quantum-Number|角量子数]]
- [[Magnetic-Quantum-Number|磁量子数]]
- [[Method-of-Separation-of-Variables|分离变量法]]
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 精细结构打破纯 $n$ 简并

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $n$ | 主量子数 | $n=1,2,3,\cdots$ |
| $E_n$ | 氢原子能级 | $E_n=-13.6\ \mathrm{eV}/n^2$ |
| $E_n$ | 类氢离子能级 | $E_n=-Z^2 13.6\ \mathrm{eV}/n^2$ |
| $N_{\mathrm{radial}}$ | 径向节点数 | $n-l-1$ |
| 第 $n$ 层空间轨道数 | 固定 $n$ 的轨道数 | $n^2$ |
| 第 $n$ 层最多电子数 | 考虑自旋后 | $2n^2$ |

---

## 📝 更新记录

- 2026-05-27: 补充氢原子能级公式的来源，并链接到 [[Hydrogen-Atom-Model|氢原子模型]] 专题笔记。
- 2026-05-25: 创建初稿，说明主量子数的取值、能级意义、壳层容量与其他量子数的关系。
