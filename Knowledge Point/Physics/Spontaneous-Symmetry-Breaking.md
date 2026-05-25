---
subject:
  - Physics
topic:
  - Statistical Physics
  - Condensed Matter Physics
aliases:
  - 自发对称性破缺
  - 对称性破缺
  - Spontaneous Symmetry Breaking
  - Symmetry Breaking
status: Evergreen
date: 2026-05-25
tags:
  - Physics
  - Statistical_Physics
  - Condensed_Matter
  - Symmetry_Breaking
---

# Spontaneous Symmetry Breaking

> **Spontaneous Symmetry Breaking (SSB, 自发对称性破缺)** 是凝聚态物理、统计力学与粒子物理中最核心的统一物理图像之一。它描述了系统哈密顿量（物理规律）具有某种对称性，但在能量最低的基态或宏观热力学平衡态中，系统自发地“选择”了某种特定状态，从而使对称性在宏观层面上被隐藏或丧失的现象。

---

## 物理直觉

对称性破缺是理解自然界“无序到有序”相变的金钥匙。我们可以通过两个非常经典的图像来直观理解它的核心思想。

### 1. 显式对称性破缺 vs 自发对称性破缺

在物理学中，对称性破缺分为两类：
- **显式对称性破缺 (Explicit Symmetry Breaking)**：物理规律本身（哈密顿量）就不具有某种对称性。
  - *类比*：在 Ising 模型中，当加入外磁场 $h \neq 0$ 时，向上和向下的方向在能量上不再等价，对称性被外界强行打破。
- **自发对称性破缺 (Spontaneous Symmetry Breaking)**：物理规律本身（哈密顿量）具有完美的对称性，但**基态或物理实际所处的状态不再具有该对称性**。
  - *类比*：在零外场（$h = 0$）的 Ising 模型中，哈密顿量在自旋反转 $s_i \leftrightarrow -s_i$ 下是完全对称的。这意味着“全向上”和“全向下”两个有序基态具有完全相同的能量。当系统温度降至临界温度 $T_c$ 以下时，系统必须从这两个等价的基态中**选择其一**降温落下。一旦选择其中之一，自旋反转的对称性就在宏观上被打破了。

### 2. 经典力学类比：墨西哥帽与铅笔

> [!TIP] 经典图像 1：立在指尖的铅笔
> 想象一支完美的铅笔直立在桌面上，这是一个完全具有**旋转对称性 (Rotational Symmetry)** 的不稳定平衡态。由于热涨落或轻微扰动，铅笔必定会向某一特定的随机方向倒下。
> - **倒下前**：物理系统和方程在绕铅笔轴旋转时完全对称。
> - **倒下后**：铅笔指向了某个特定方向，原有的连续旋转对称性在桌面上自发破缺了。

> [!TIP] 经典图像 2：墨西哥帽势能面 (Mexican Hat Potential)
> 考虑一个圆形对称的“碗底”形状势能（连续旋转对称性 $U(1)$）：
> - 当系统处于高温时（对应势能面中心的单井形状），唯一的稳定基态在中心点 $x=0$，此时系统具有完美的旋转对称性。
> - 当系统降温并发生相变时，势能面转化为“墨西哥帽”形状（如图表所示，中心变成局部极大值，而圆环底部的无数个能量最低点构成了一条连续的简并轨道）。系统不能同时停在所有的最低点，它必须自发地滚落到环形谷底的**某一个特定点**。系统在这个特定点的状态不再是对称的，虽然整个墨西哥帽势能面依然是圆周对称的。这便是连续对称性自发破缺的图像，它直接导致了无质量的**南部-戈德斯通玻色子 (Nambu-Goldstone Boson)**（如固体中的声子、超流体中的第二声等）的产生。

---

## 核心定义与 Landau 相变理论

为了数学上严格刻画自发对称性破缺，Lev Landau 提出了**朗道相变理论 (Landau Theory of Phase Transitions)**。他指出，相变的本质就是对称性的变化，并引入了**序参量 (Order Parameter)** 来量化这一破缺程度。

### 1. 序参量 $M$
序参量是一个宏观物理量：
- 在高温对称相（无序相）中，序参量为零：$\langle M \rangle = 0$。
- 在低温对称破缺相（有序相）中，序参量不为零：$\langle M \rangle \neq 0$。

> *例子*：在铁磁相变中，序参量是宏观磁化强度 $M$；在 Bose-Einstein 凝聚 (BEC) 或超流中，序参量是凝聚态波函数（宏观波函数）的振幅 $\psi$。

### 2. 朗道自由能展开 (Landau Free Energy Expansion)
在相变点 $T_c$ 附近，序参量 $M$ 通常很小。朗道假设系统的 Helmholtz 自由能 $F(T, M)$ 可以关于序参量 $M$ 进行泰勒级数展开。

对于具有反转对称性 $M \leftrightarrow -M$ 的系统（例如 Ising 体系），自由能必须是 $M$ 的偶函数：
$$ F(T, M) = F_0(T) + A(T) M^2 + B(T) M^4 - hM $$

为了保证系统在 $M \to \infty$ 时的热力学稳定性，高阶项系数必须满足：
$$ B(T) = b > 0 $$

朗道的核心假设是：二次项系数 $A(T)$ 在临界温度 $T_c$ 附近改变符号，最简单的线性形式为：
$$ A(T) = a(T - T_c), \quad (a > 0) $$

因此，在无外场（$h=0$）下，自由能展开为：
$$ F(T, M) = F_0 + a(T - T_c)M^2 + bM^4 $$

---

## 朗道理论的严格数学求解

我们通过最小化自由能 $\frac{\partial F}{\partial M} = 0$ 来求解系统在不同温度下的热力学稳定状态（以 $h=0$ 为例）：

$$ \frac{\partial F}{\partial M} = 2a(T - T_c)M + 4bM^3 = 2M \left[ a(T - T_c) + 2bM^2 \right] = 0 $$

### 1. 高温相：$T > T_c$
此时 $a(T - T_c) > 0$。特征方程的解分析如下：
- $M = 0$ 是唯一的实数解。
- 极值性质：由于 $\frac{\partial^2 F}{\partial M^2} = 2a(T-T_c) > 0$，所以 $M = 0$ 是自由能的**全局极小值点**。
- **物理图像**：系统处于高温无序态，保持完美的 $M \leftrightarrow -M$ 对称性。

### 2. 低温相：$T < T_c$
此时 $a(T - T_c) < 0$（记 $T_c - T > 0$）。特征方程有三个实数解：
- $M = 0$
- $M = \pm M_0 = \pm \sqrt{\frac{a(T_c - T)}{2b}}$

我们通过二阶导数判断其稳定性：
- 对于 $M = 0$：二阶导数 $\frac{\partial^2 F}{\partial M^2} = 2a(T-T_c) < 0$，说明此时 $M = 0$ 变成了**局部极大值点（不稳定平衡）**。
- 对于 $M = \pm M_0$：二阶导数为：
  $$ \frac{\partial^2 F}{\partial M^2}\Big|_{M_0} = 2a(T-T_c) + 12b M_0^2 = 2a(T-T_c) + 12b \left( \frac{a(T_c - T)}{2b} \right) = 4a(T_c - T) > 0 $$
  因此，这两个简并解 $M = \pm M_0$ 是自由能的**对称全局极小值点**。

> [!WARNING] 自发对称性破缺的发生
> 随着温度 $T$ 降到 $T_c$ 以下，系统不再稳定在 $M=0$ 的对称点。它必须跌落到 $+M_0$ 或 $-M_0$ 两个极小值中的一个。
> 尽管自由能公式 $F(M)$ 在 $M \leftrightarrow -M$ 下是对称的（双非对角势阱），但系统处于 $+M_0$（或 $-M_0$）的实际状态却破缺了这一反转对称性。这就是**自发对称性破缺**！
> 此时，序参量表现出如下的临界行为：
> $$ M_0 \propto (T_c - T)^{1/2} $$
> 这里的指数 $\beta = 1/2 = 0.5$ 是朗道平均场理论的**临界指数**。

---

## 📐 核心公式摘要

| 物理符号 | 物理含义 | 公式/表达式 |
| :--- | :--- | :--- |
| $M$ | 系统的有序相序参量 | $M = 0 \ (T > T_c)$， $M \neq 0 \ (T < T_c)$ |
| $F(T, M)$ | 朗道自由能展开式（零外场，偶对称） | $F(T, M) = F_0 + a(T-T_c)M^2 + bM^4$ |
| $M_0$ | 低温对称破缺相的稳定序参量 | $M_0 = \pm \sqrt{\frac{a(T_c - T)}{2b}} \quad (T < T_c)$ |
| $F_{min}$ | 低温对称破缺相的平衡自由能 | $F(T, M_0) = F_0 - \frac{a^2(T_c-T)^2}{4b}$ |
| $\beta$ | 朗道平均场理论临界指数 | $M \propto (T_c - T)^\beta \implies \beta = 1/2$ |

---

## 🎨 朗道自由能曲线变化图 (双阱势演化)

以下 Python 代码绘制了朗道自由能在不同温度下的变化曲线。它直观展示了当温度从 $T > T_c$ 降至 $T < T_c$ 时，自由能曲线如何从**单阱势**（对称稳定）演化为**双阱势**（对称破缺，出现简并的最低能量态）。

```python
import matplotlib.pyplot as plt
import numpy as np

# Landau Free Energy parameters: F(M) = A*M^2 + B*M^4
# Let B = 1.0. We vary A to simulate different temperatures.
# A > 0  => T > Tc (High Temperature)
# A = 0  => T = Tc (Critical Temperature)
# A < 0  => T < Tc (Low Temperature, Spontaneous Symmetry Breaking)

b_coeff = 1.0
m_vals = np.linspace(-1.5, 1.5, 500)

def landau_free_energy(m, a_coeff, b_coeff):
    return a_coeff * m**2 + b_coeff * m**4

# Different temp states represented by parameter A = a*(T - Tc)
states = [
    (0.8, 'T > Tc (High Temp, Symmetric Phase)', '#e74c3c', '-'),
    (0.0, 'T = Tc (Critical Temp)', '#7f8c8d', '--'),
    (-0.8, 'T < Tc (Low Temp, Symmetry Broken)', '#1f77b4', '-'),
]

plt.figure(figsize=(8.5, 5.5))

for a_val, label, color, style in states:
    f_vals = landau_free_energy(m_vals, a_val, b_coeff)
    plt.plot(m_vals, f_vals, color=color, linestyle=style, linewidth=2.5, label=label)
    
    # Draw equilibrium ground states (minima)
    if a_val < 0:
        # Minima at M = +- sqrt(-A / 2B)
        m_min = np.sqrt(-a_val / (2.0 * b_coeff))
        f_min = landau_free_energy(m_min, a_val, b_coeff)
        plt.scatter([-m_min, m_min], [f_min, f_min], color='#2c3e50', s=100, zorder=5)
        # Highlight SSB rolling down path
        plt.annotate('SSB Ground States', xy=(m_min, f_min), xytext=(m_min - 0.2, f_min + 0.15),
                     arrowprops=dict(arrowstyle="->", color='#2c3e50', lw=1.5), fontsize=10, color='#2c3e50')
        plt.annotate('', xy=(-m_min, f_min), xytext=(-m_min + 0.2, f_min + 0.15),
                     arrowprops=dict(arrowstyle="->", color='#2c3e50', lw=1.5))

# Vertical line representing M = 0 symmetry point
plt.axvline(x=0, color='gray', linestyle=':', alpha=0.5, linewidth=1)
plt.axhline(y=0, color='gray', linestyle=':', alpha=0.5, linewidth=1)

# Style formatting
plt.xlabel(r'Order Parameter $M$', fontsize=12)
plt.ylabel(r'Landau Free Energy $F(M) - F_0$', fontsize=12)
plt.title('Landau Free Energy: Spontaneous Symmetry Breaking', fontsize=13, fontweight='bold')
plt.xlim(-1.5, 1.5)
plt.ylim(-0.3, 0.8)
plt.grid(alpha=0.25, ls=':')
plt.legend(frameon=False, loc='upper center', fontsize=10)
plt.tight_layout()
plt.show()
```

---

## 相关概念

- [[Ising-Model|Ising Model (伊辛模型)]]
- [[Bose-Einstein-Distribution|Bose-Einstein Distribution (玻色-爱因斯坦分布)]]


---

## 📝 更新记录

- 2026-05-25: 创建初稿，详尽补充显式破缺与自发破缺的区别、朗道自由能展开的物理图像及严格求解，并配备高颜值 Landau 双阱势演化图表。
