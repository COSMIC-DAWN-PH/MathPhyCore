---
subject:
  - Physics
topic:
  - Atomic Physics
  - Electromagnetism
aliases:
  - 拉莫尔进动
  - Larmor precession
  - Larmor frequency
  - 拉莫尔频率
source: Gemini 对话整理 (原子物理)
comprehension: getting there
status: WIP
date: 2026-05-27
tags:
  - Physics
  - Atomic_Physics
  - Electromagnetism
  - Magnetic_Moment
  - Angular_Momentum
  - Precession
---

# Larmor Precession

拉莫尔进动（Larmor Precession）描述的是：带有[[Magnetic-Moment|磁矩]]和角动量的系统放进外磁场后，角动量矢量不会简单地倒向磁场方向，而是绕着磁场方向做圆锥形旋转。

最核心的图像是：外磁场 $\mathbf{B}$ 对磁矩 $\boldsymbol{\mu}$ 施加[[Torque|力矩]]，力矩改变角动量 $\mathbf{J}$ 的方向，但在理想无耗散情况下不改变 $\mathbf{J}$ 的大小，于是 $\mathbf{J}$ 的端点沿圆周运动。

---

## 物理图像

设磁矩与总角动量满足

$$
\boldsymbol{\mu} = \gamma \mathbf{J}
$$

其中 $\gamma$ 是旋磁比（gyromagnetic ratio）。外磁场给磁矩的力矩为

$$
\boldsymbol{\tau} = \boldsymbol{\mu} \times \mathbf{B}
$$

而力矩又等于角动量变化率：

$$
\frac{d\mathbf{J}}{dt} = \boldsymbol{\tau}
$$

合并可得

$$
\frac{d\mathbf{J}}{dt} = \gamma \mathbf{J} \times \mathbf{B}
$$

这说明 $\mathbf{J}$ 的变化方向总是同时垂直于 $\mathbf{J}$ 和 $\mathbf{B}$。所以它不是把 $\mathbf{J}$ 拉长或压短，而是不断把 $\mathbf{J}$ 的方向“侧向推开”，形成绕 $\mathbf{B}$ 的进动。

> [!tip] 直觉记忆
> 拉莫尔进动像一个倾斜陀螺的轴绕竖直方向转圈。这里“重力力矩”换成了磁力矩，竖直方向换成了外磁场方向。

---

## 拉莫尔频率

若外磁场取为

$$
\mathbf{B} = B \hat{\mathbf{z}}
$$

则角动量绕 $z$ 轴以角频率

$$
\omega_L = -\gamma B
$$

进动。很多教材也写作大小形式：

$$
|\omega_L| = |\gamma|B
$$

符号决定旋转方向：正旋磁比和负旋磁比的进动方向相反。

> [!warning] 符号约定容易混
> 有些书把进动方程写成 $\frac{d\mathbf{J}}{dt}=\boldsymbol{\Omega}\times\mathbf{J}$，此时 $\boldsymbol{\Omega}=-\gamma\mathbf{B}$。如果只记大小，容易在判断顺时针或逆时针时出错。

---

## 为什么不是直接对齐磁场

磁矩在磁场中的能量是

$$
U = -\boldsymbol{\mu}\cdot\mathbf{B}
$$

从能量看，磁矩确实“想要”和磁场同向。但在没有阻尼或弛豫机制时，力矩只负责改变角动量方向，系统不会自动损失能量，于是夹角保持不变，只发生进动。

真正的对齐需要耗散过程。例如在核磁共振、电子顺磁共振或自旋动力学中，常用纵向弛豫、横向弛豫来描述磁化强度如何逐渐回到平衡方向。

> [!info] 和量子态的关系
> 在量子力学里，外磁场选定了一个特殊的量子化方向。角动量投影由[[Magnetic-Quantum-Number|磁量子数]]标记，能级因磁矩与磁场相互作用而分裂。拉莫尔进动可以看作相位随时间演化在经典极限下的矢量图像。

---

## 交互式动态图

下面的动态图把外磁场固定在竖直方向，角动量矢量 $\mathbf{J}$ 绕磁场做圆锥进动。可以调节磁场强度 $B$、旋磁比 $\gamma$ 和初始夹角 $\theta$。

<iframe src="file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/Larmor-Precession-Interactive.html" width="100%" height="700" style="border:1px solid #d8dee9; border-radius:6px;"></iframe>

如果 iframe 在当前 Obsidian 设置中没有渲染，可以直接打开：[Larmor Precession Interactive](../../tools/Larmor-Precession-Interactive.html)

---

## Python 静态图

下面这段 Python 代码用于画出进动圆锥和角动量端点轨迹，适合在 Obsidian Execute Code 中直接运行。

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

theta = np.deg2rad(35)
J = 1.0
phi = np.linspace(0, 2 * np.pi, 240)

x = J * np.sin(theta) * np.cos(phi)
y = J * np.sin(theta) * np.sin(phi)
z = np.full_like(phi, J * np.cos(theta))

fig = plt.figure(figsize=(7, 6))
ax = fig.add_subplot(111, projection='3d')

ax.plot(x, y, z, color='#3366aa', lw=2, label='precession path')
ax.plot([0, x[35]], [0, y[35]], [0, z[35]], color='#c96b1b', lw=3, label=r'angular momentum $\mathbf{J}$')
ax.quiver(0, 0, 0, 0, 0, 1.25, color='#b84644', linewidth=2.5, arrow_length_ratio=0.12, label=r'magnetic field $\mathbf{B}$')

for a in np.linspace(0, 2 * np.pi, 32):
    ax.plot([0, J * np.sin(theta) * np.cos(a)],
            [0, J * np.sin(theta) * np.sin(a)],
            [0, J * np.cos(theta)],
            color='#d8dee9', lw=0.6, alpha=0.7)

ax.set_xlabel('$J_x$')
ax.set_ylabel('$J_y$')
ax.set_zlabel('$J_z$')
ax.set_title('Larmor Precession Cone')
ax.legend()
ax.set_box_aspect((1, 1, 1))
ax.view_init(elev=22, azim=35)
plt.tight_layout()

# Obsidian Execute Code may append an empty plt.plot() after this block.
# Keep a transparent 2D axes current so that appended call does not hit Axes3D.plot().
compat_ax = fig.add_axes([0, 0, 1, 1], frameon=False)
compat_ax.set_axis_off()
plt.show()
```

---

## 典型应用

### 核磁共振与磁共振成像

原子核自旋在静磁场中以拉莫尔频率进动。若施加频率匹配的射频场，就能发生共振吸收，这正是 NMR 和 MRI 的基本物理图像。

$$
\omega_0 = |\gamma|B_0
$$

### 电子顺磁共振

未成对电子的磁矩也会在外磁场中进动。因为电子的旋磁比远大于多数原子核，电子顺磁共振通常工作在更高频率范围。

### 原子能级分裂

在外磁场中，不同磁量子数对应的能量不同。这与[[Quantum-Numbers|量子数]]、[[Magnetic-Quantum-Number|磁量子数]]和磁矩相互作用密切相关。

---

## 相关概念

- [[Magnetic-Moment|磁矩]] — 拉莫尔进动的主体是磁矩与角动量耦合的系统
- [[Torque|力矩]] — 外磁场对磁矩施加力矩，导致角动量方向变化
- [[Magnetic-Quantum-Number|磁量子数]] — 外磁场方向上的角动量投影量子化
- [[Quantum-Numbers|量子数]] — 描述原子量子态的一组离散标签
- [[Unitary-Matrix|Unitary Matrix (酉矩阵)]] — 自旋在外磁场中的时间演化算符 $U(t) = e^{-i\omega t\sigma_z/2}$ 是 $SU(2)$ 酉变换的经典实例
- [[Study-Roadmap|Study Roadmap (学习路径)]] — 拉莫尔进动是超精细结构与塞曼效应的物理基础
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 自旋在轨道运动产生的等效磁场中进动
- [[Force-on-Magnetic-Dipole-in-Gradient-Field|磁矩在梯度磁场中的受力]] — 进动平均消除横向力项，是该受力简化公式的关键物理机制
- [[Zeeman-Effect|塞曼效应]] — 弱场极限下角动量绕外磁场做拉莫尔进动，产生 Zeeman 分裂
- [[Fine-Structure|精细结构]] — 拉莫尔进动的经典图像是理解自旋-轨道耦合（精细结构来源之一）的基础

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\boldsymbol{\mu}$ | 磁矩 | $\boldsymbol{\mu}=\gamma\mathbf{J}$ |
| $\boldsymbol{\tau}$ | 磁场对磁矩的力矩 | $\boldsymbol{\tau}=\boldsymbol{\mu}\times\mathbf{B}$ |
| $\mathbf{J}$ | 角动量 | $\frac{d\mathbf{J}}{dt}=\boldsymbol{\tau}$ |
| $\omega_L$ | 拉莫尔角频率 | $\omega_L=-\gamma B$ |
| $U$ | 磁矩在磁场中的能量 | $U=-\boldsymbol{\mu}\cdot\mathbf{B}$ |

---

## 📝 更新记录

- 2026-05-27: 创建拉莫尔进动笔记，加入物理图像、拉莫尔频率、应用、Python 静态图和交互式动态图。
