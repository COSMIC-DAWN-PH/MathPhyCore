---
subject:
  - Physics
topic:
  - Quantum Mechanics
aliases:
  - 量子数
  - 氢原子量子数
  - 原子轨道量子数
  - Quantum numbers
status: In-Progress
date: 2026-05-25
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Quantum_Numbers
---

# Quantum Numbers

量子数（quantum numbers）是一组用来标记原子中电子量子态的离散标签。对中心势场，尤其是氢原子问题，最常用的一组空间量子数是：[[Principal-Quantum-Number|主量子数]] $n$、[[Azimuthal-Quantum-Number|角量子数]] $l$、[[Magnetic-Quantum-Number|磁量子数]] $m_l$。

> [!info] 核心图像
> $n$ 决定电子波函数的整体能量尺度与径向大小；$l$ 决定轨道角动量大小与轨道形状；$m_l$ 决定角动量在选定 $z$ 轴上的投影方向。三者不是平级随便选的标签，而是有严格嵌套关系。

---

## 物理直觉：三层标签

可以把三种量子数理解成对同一个电子态的三层描述：

1. **第 1 层：壳层大小与能量**  
   [[Principal-Quantum-Number|主量子数]] $n$ 标记电子属于第几层壳层。$n$ 越大，典型半径越大，氢原子能级越接近 $0$。

2. **第 2 层：轨道形状与角动量大小**  
   在固定 $n$ 后，[[Azimuthal-Quantum-Number|角量子数]] $l$ 标记子壳层，例如 $s,p,d,f$。它决定轨道角动量大小：
   $$
   L=\sqrt{l(l+1)}\hbar
   $$

3. **第 3 层：空间取向**  
   在固定 $l$ 后，[[Magnetic-Quantum-Number|磁量子数]] $m_l$ 标记角动量沿 $z$ 轴的投影：
   $$
   L_z=m_l\hbar
   $$

---

## 物理图像：从壳层到投影

最直接的图像是：

- $n$ 像“半径层级”：决定电子云主要分布在多大的尺度上；
- $l$ 像“形状类型”：决定电子云是球对称的 $s$ 型，还是有方向性的 $p,d,f$ 型；
- $m_l$ 像“投影刻度”：在选定 $z$ 轴后，角动量投影只能落在若干个离散刻度上。

> [!tip] 一个有用的心像
> 先想象一组同心壳层，这是 $n$；每个壳层里有不同形状的波函数花纹，这是 $l$；当外部磁场或测量轴选定一个方向时，这些角动量状态沿该方向只能有离散投影，这是 $m_l$。

更严格地说，电子不是沿经典轨道绕核运动的小球，所谓“轨道”是波函数概率云。量子数描述的是波函数的允许形状和角动量本征值，而不是一条确定的运动轨迹。

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

fig, axes = plt.subplots(1, 3, figsize=(13, 4))

# 1. n: shell scale
ax = axes[0]
theta = np.linspace(0, 2*np.pi, 400)
for n, color in [(1, '#4C78A8'), (2, '#F58518'), (3, '#54A24B')]:
    r = n
    ax.plot(r*np.cos(theta), r*np.sin(theta), lw=2.5, color=color, label=fr'$n={n}$')
ax.scatter([0], [0], s=80, color='black', label='原子核')
ax.set_aspect('equal')
ax.set_title('主量子数 $n$：壳层尺度')
ax.set_xlabel('$x$')
ax.set_ylabel('$y$')
ax.set_xlim(-3.4, 3.4)
ax.set_ylim(-3.4, 3.4)
ax.grid(alpha=0.25)
ax.legend(loc='upper right')

# 2. l: angular shapes, shown as polar probability sketches
ax = axes[1]
theta = np.linspace(0, 2*np.pi, 800)
shapes = [
    (np.ones_like(theta), '$l=0$ : s', '#4C78A8'),
    (np.abs(np.cos(theta)), '$l=1$ : p', '#F58518'),
    (np.abs(np.cos(2*theta)), '$l=2$ : d', '#54A24B'),
]
offsets = [-2.2, 0, 2.2]
for (rho, label, color), x0 in zip(shapes, offsets):
    x = x0 + rho*np.cos(theta)
    y = rho*np.sin(theta)
    ax.plot(x, y, lw=2.2, color=color)
    ax.text(x0, -1.45, label, ha='center', fontsize=11)
ax.set_aspect('equal')
ax.set_title('角量子数 $l$：角向形状')
ax.set_xlim(-3.6, 3.6)
ax.set_ylim(-1.8, 1.8)
ax.axis('off')

# 3. m_l: discrete Lz projections for fixed l=2
ax = axes[2]
l = 2
m_values = np.arange(-l, l + 1)
for m in m_values:
    ax.hlines(m, 0, 1.0, color='#4C78A8', lw=3)
    ax.text(1.08, m, fr'$m_l={m}$', va='center', fontsize=11)
ax.axvline(0, color='black', lw=1)
ax.set_title(r'磁量子数 $m_l$：$L_z=m_l\hbar$')
ax.set_xlim(-0.2, 1.9)
ax.set_ylim(-2.6, 2.6)
ax.set_xticks([])
ax.set_yticks(m_values)
ax.set_ylabel(r'$L_z/\hbar$')
ax.grid(axis='y', alpha=0.25)

plt.suptitle('三个空间量子数的物理图像', fontsize=15, fontweight='bold')
plt.tight_layout()
plt.show()
```

---

## 交互式可视化

下面这个交互图可以直接拖动 $n,l,m_l$，观察三者如何相互约束。它用三块图像分别表示壳层尺度、角向形状和角动量投影。

<iframe src="file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/Quantum-Numbers-Interactive.html" width="100%" height="680" style="border:1px solid #d8dee9; border-radius:6px;"></iframe>

如果 iframe 在当前 Obsidian 设置中没有渲染，可以直接打开：[Quantum Numbers Interactive](../../tools/Quantum-Numbers-Interactive.html)

---

## 取值关系

三个量子数的允许取值必须从外到内依次决定：

$$
n=1,2,3,\cdots
$$

给定 $n$ 后：

$$
l=0,1,2,\cdots,n-1
$$

给定 $l$ 后：

$$
m_l=-l,-l+1,\cdots,0,\cdots,l-1,l
$$

> [!warning] 常见错误
> 不能先随便选 $m_l$ 再选 $l$，也不能让 $l=n$。正确关系是 $n$ 限制 $l$，$l$ 再限制 $m_l$。

---

## 轨道字母与量子数

化学与原子物理中常用字母表示 $l$：

| $l$ | 子壳层符号 | 常见名称 | $m_l$ 个数 |
|---:|:---:|:---|---:|
| 0 | $s$ | s 轨道 | 1 |
| 1 | $p$ | p 轨道 | 3 |
| 2 | $d$ | d 轨道 | 5 |
| 3 | $f$ | f 轨道 | 7 |
| 4 | $g$ | g 轨道 | 9 |

一般地，固定 $l$ 时，磁量子数有：

$$
2l+1
$$

个可能取值，因此同一个子壳层包含 $2l+1$ 个空间轨道。

---

## 例子：前几层壳层

### $n=1$

允许：

$$
l=0,\quad m_l=0
$$

所以只有 $1s$ 一个空间轨道。

### $n=2$

允许：

$$
l=0,1
$$

- $l=0$：$2s$，$m_l=0$，1 个轨道
- $l=1$：$2p$，$m_l=-1,0,1$，3 个轨道

所以 $n=2$ 壳层共有 $1+3=4$ 个空间轨道。

### $n=3$

允许：

$$
l=0,1,2
$$

- $3s$：1 个轨道
- $3p$：3 个轨道
- $3d$：5 个轨道

所以 $n=3$ 壳层共有 $1+3+5=9$ 个空间轨道。

---

## 简并度关系

固定 $n$ 时，所有可能的 $(l,m_l)$ 组合数为：

$$
\sum_{l=0}^{n-1}(2l+1)=n^2
$$

这说明第 $n$ 层壳层有 $n^2$ 个空间轨道。如果再考虑电子自旋量子数 $m_s=\pm \frac{1}{2}$，每个空间轨道可容纳两个自旋态，于是最多可容纳：

$$
2n^2
$$

个电子。

> [!info] 氢原子中的特殊简并
> 对非相对论氢原子，能量只依赖 $n$，所以同一 $n$ 下不同 $l,m_l$ 的状态能量相同。这是库仑势的特殊对称性导致的。对多电子原子，屏蔽效应和电子间相互作用会让能量明显依赖 $l$。

---

## 与角动量算符的关系

这三个量子数来自定态薛定谔方程在球坐标下的分离变量。对中心势：

$$
\psi_{nlm}(r,\theta,\phi)=R_{nl}(r)Y_l^m(\theta,\phi)
$$

其中：

- $n$ 主要来自径向方程与束缚态边界条件；
- $l$ 来自角向方程，是 $\hat L^2$ 的本征值标签；
- $m_l$ 来自方位角 $\phi$ 方程，是 $\hat L_z$ 的本征值标签。

对应本征方程是：

$$
\hat L^2 Y_l^m=l(l+1)\hbar^2Y_l^m
$$

$$
\hat L_zY_l^m=m_l\hbar Y_l^m
$$

---

## 典型应用场景

- 标记氢原子波函数：$\psi_{nlm}(r,\theta,\phi)$
- 判断原子轨道种类：$1s,2p,3d,\cdots$
- 计算壳层与子壳层可容纳态数
- 理解塞曼效应中能级在磁场中的分裂
- 理解角动量量子化与球谐函数 [[Method-of-Separation-of-Variables|分离变量法]] 的联系

---

## 相关概念

- [[Principal-Quantum-Number|主量子数]]
- [[Azimuthal-Quantum-Number|角量子数]]
- [[Magnetic-Quantum-Number|磁量子数]]
- [[Larmor-Precession|拉莫尔进动]]
- [[Method-of-Separation-of-Variables|分离变量法]]

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $n$ | 主量子数 | $n=1,2,3,\cdots$ |
| $l$ | 角量子数 | $l=0,1,\cdots,n-1$ |
| $m_l$ | 磁量子数 | $m_l=-l,-l+1,\cdots,l$ |
| $L$ | 轨道角动量大小 | $L=\sqrt{l(l+1)}\hbar$ |
| $L_z$ | 轨道角动量 $z$ 分量 | $L_z=m_l\hbar$ |
| 子壳层轨道数 | 固定 $l$ 的 $m_l$ 数量 | $2l+1$ |
| 第 $n$ 层空间轨道数 | 固定 $n$ 的 $(l,m_l)$ 数量 | $n^2$ |
| 第 $n$ 层最多电子数 | 考虑自旋后 | $2n^2$ |

---

## 📝 更新记录

- 2026-05-25: 添加交互式 HTML 可视化，用滑块展示 $n,l,m_l$ 的取值约束与物理图像。
- 2026-05-25: 创建初稿，整理主量子数、角量子数、磁量子数的层级关系与取值约束。
