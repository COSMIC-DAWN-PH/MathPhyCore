---
subject:
  - Physics
topic:
  - Quantum Mechanics
  - Atomic Physics
aliases:
  - 氢原子模型
  - Hydrogen atom model
  - Bohr model
  - Bohr atom
  - 氢原子能级
source: "Gemini 对话整理 + Griffiths QM + 原子物理第四章"
comprehension: getting there
status: WIP
date: 2026-05-27
tags:
  - Physics
  - Quantum_Mechanics
  - Atomic_Physics
  - Quantum_Numbers
  - Hydrogen_Atom
---

# Hydrogen Atom Model

氢原子模型解释了为什么氢原子的束缚态能量是离散的，以及为什么非相对论近似下能量只依赖[[Principal-Quantum-Number|主量子数]] $n$：

$$
E_n=-\frac{13.6\ \mathrm{eV}}{n^2}
$$

最重要的物理图像是：电子被质子的库仑吸引束缚住，经典力学允许任意轨道能量，但量子条件只允许一组离散驻波状态。主量子数 $n$ 就是这些离散能级的壳层编号。

---

## 模型设定

把氢原子近似为一个电子在质子产生的库仑势中运动。若暂时把质子看作固定在原点，电子势能为

$$
V(r)=-\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

电子总能量由动能和势能组成：

$$
E=K+V
$$

> [!info] 更精确的质量
> 严格地说，电子和质子都绕共同质心运动，因此电子质量 $m_e$ 应替换为约化质量 $\mu_r=\frac{m_em_p}{m_e+m_p}$。入门推导常先用 $m_e$，误差很小。

---

## Bohr 假设

Bohr 原子模型的关键不是把电子想成普通行星，而是在经典圆轨道上强行加入量子条件。它的基本假设通常写成三条：

### 1. 定态轨道假设

电子只能在某些允许轨道上运动。在这些轨道上，电子虽然有加速度，但不连续辐射电磁波，原子能量保持稳定。

> [!warning] 和经典电磁学的冲突
> 经典电磁学认为加速电荷应当连续辐射并损失能量。Bohr 的定态假设正是为了解释氢原子为什么稳定存在，它本身不是经典理论能推出的结论。

### 2. 角动量量子化假设

允许轨道必须满足

$$
m_evr=n\hbar,\qquad n=1,2,3,\cdots
$$

也就是轨道角动量只能取 $\hbar$ 的整数倍。这个整数 $n$ 后来发展为[[Principal-Quantum-Number|主量子数]]。

### 3. 跃迁频率假设

电子只在两个定态之间跃迁时吸收或发射光子，光子频率由能量差决定：

$$
h\nu=E_i-E_f
$$

因此，一旦得到定态能级 $E_n$，就能推出氢原子光谱线：

$$
\frac{1}{\lambda}=R_H\left(\frac{1}{n_f^2}-\frac{1}{n_i^2}\right),\qquad n_i>n_f
$$

这就是 Bohr 模型在原子物理中的核心成功：它不仅解释能级离散，还解释了氢原子光谱的 Rydberg 公式。

---

## Bohr 模型的半经典推导

Bohr 模型不是现代量子力学的完整理论，但它非常适合看清能量公式中的 $1/n^2$ 从哪里来。推导路线是：用经典库仑力确定圆轨道动力学，再用 Bohr 的角动量量子化假设筛选允许半径。

### 1. 库仑力提供向心力

假设电子绕质子做半径为 $r$ 的圆周运动。库仑吸引力提供向心力：

$$
\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r^2}=\frac{m_ev^2}{r}
$$

两边乘以 $r$：

$$
m_ev^2=\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

因此动能为

$$
K=\frac{1}{2}m_ev^2=\frac{1}{2}\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

势能为

$$
V=-\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

所以总能量是

$$
E=K+V=-\frac{1}{2}\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

> [!tip] 束缚态为什么能量为负
> 取 $r\to\infty$ 时 $E=0$ 作为自由电子的能量零点。氢原子中的电子被束缚在质子附近，所以总能量低于自由态，即 $E<0$。

### 2. 代入 Bohr 角动量量子化

由 Bohr 第二假设，电子轨道角动量只能取

$$
m_evr=n\hbar,\qquad n=1,2,3,\cdots
$$

这一步把原本连续可取的轨道半径变成离散值。由

$$
v=\frac{n\hbar}{m_er}
$$

代回向心力条件：

$$
m_e\left(\frac{n\hbar}{m_er}\right)^2=\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

整理得到允许半径

$$
r_n=\frac{4\pi\varepsilon_0\hbar^2}{m_ee^2}n^2
$$

定义 Bohr 半径

$$
a_0=\frac{4\pi\varepsilon_0\hbar^2}{m_ee^2}
$$

于是

$$
r_n=a_0n^2
$$

这解释了为什么 $n$ 越大，电子典型尺度越大。

### 3. 代回总能量

把 $r_n=a_0n^2$ 代入总能量

$$
E=-\frac{1}{2}\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}
$$

得到

$$
E_n=-\frac{m_ee^4}{2(4\pi\varepsilon_0)^2\hbar^2}\frac{1}{n^2}
$$

数值上

$$
E_n=-\frac{13.6\ \mathrm{eV}}{n^2}
$$

> [!example] 前几个能级
> $E_1=-13.6\ \mathrm{eV}$，$E_2=-3.40\ \mathrm{eV}$，$E_3=-1.51\ \mathrm{eV}$。随着 $n$ 增大，能级越来越密，并逐渐逼近电离极限 $E=0$。

### 4. 由能级差得到光谱线

由 Bohr 第三假设，从高能级 $n_i$ 跃迁到低能级 $n_f$ 时发射光子：

$$
h\nu=E_{n_i}-E_{n_f}
$$

由于

$$
E_n=-\frac{13.6\ \mathrm{eV}}{n^2}
$$

所以

$$
h\nu=13.6\ \mathrm{eV}\left(\frac{1}{n_f^2}-\frac{1}{n_i^2}\right)
$$

再用 $\nu=c/\lambda$，得到氢原子谱线的 Rydberg 形式：

$$
\frac{1}{\lambda}=R_H\left(\frac{1}{n_f^2}-\frac{1}{n_i^2}\right)
$$

其中 $n_i>n_f$。例如 $n_f=2$ 的一系列跃迁对应 Balmer 系，在可见光谱中最常见。

---

## 类氢离子

对核电荷数为 $Z$、只含一个电子的类氢离子，库仑势变为

$$
V(r)=-\frac{1}{4\pi\varepsilon_0}\frac{Ze^2}{r}
$$

同样推导可得

$$
r_n=\frac{a_0}{Z}n^2
$$

能级变为

$$
E_n=-\frac{Z^2\,13.6\ \mathrm{eV}}{n^2}
$$

核电荷越大，电子束缚越强，轨道尺度越小，能级绝对值越大。

---

## 薛定谔方程中的来源：量子化的自然涌现

现代量子力学中，氢原子能级来自定态薛定谔方程。与 Bohr 模型的**强制量子化**不同，薛定谔方程中的量子化完全是**自然涌现**的——它来自波函数必须在物理上合理（有限、归一化、不发散）这一边界条件。

### 第一步：建立定态薛定谔方程

在球坐标系 $(r, \theta, \phi)$ 下，单电子氢原子的哈密顿量为：

$$
\hat{H} = -\frac{\hbar^2}{2\mu}\nabla^2 - \frac{e^2}{4\pi\varepsilon_0 r}
$$

定态薛定谔方程 $\hat{H}\psi = E\psi$ 展开为：

$$
\left[-\frac{\hbar^2}{2\mu}\nabla^2 - \frac{e^2}{4\pi\varepsilon_0 r}\right]\psi(r,\theta,\phi) = E\psi(r,\theta,\phi)
$$

> [!info] 约化质量 $\mu$
> 严格来说，电子和质子都绕共同质心运动，电子质量 $m_e$ 应替换为约化质量 $\mu = \frac{m_e m_p}{m_e + m_p} \approx m_e$（误差约 $0.05\%$）。更精确地说，$13.6\ \mathrm{eV}$ 中的质量应该用 $\mu$，而非 $m_e$。

### 第二步：[[Method-of-Separation-of-Variables|分离变量]]——剥离径向方程

库仑势 $V(r) = -\frac{e^2}{4\pi\varepsilon_0 r}$ 是**中心力场**（只依赖 $r$），因此问题具有球对称性。我们可以将波函数写成径向部分和角向部分的乘积：

$$
\psi_{nlm}(r,\theta,\phi) = R_{nl}(r)\,Y_l^m(\theta,\phi)
$$

其中 $Y_l^m(\theta,\phi)$ 是球谐函数，直接给出[[Azimuthal-Quantum-Number|角量子数]] $l$ 和[[Magnetic-Quantum-Number|磁量子数]] $m$。

> [!tip] 球谐函数的来源
> 球坐标系中的 Laplacian $\nabla^2$ 可以分离为径向部分 $R(r)$ 和角向部分（球谐函数 $Y_l^m$）。角向部分满足球面 Laplace 方程，其解自动给出 $l$ 和 $m$ 的量子化——这与氢原子的库仑势无关，只与空间的球对称性有关。

将分离变量解代入薛定谔方程，角向部分自动满足归一化条件后被约掉，我们得到**径向薛定谔方程**：

$$
-\frac{\hbar^2}{2\mu r^2}\frac{d}{dr}\left(r^2\frac{dR}{dr}\right) + \left[\frac{\hbar^2 l(l+1)}{2\mu r^2} - \frac{e^2}{4\pi\varepsilon_0 r}\right]R = ER
$$

> [!tip] 有效势能的物理图像
> 方程中括号里的部分可以看作**有效势能** $V_{\text{eff}}(r)$：
> $$V_{\text{eff}}(r) = \underbrace{-\frac{e^2}{4\pi\varepsilon_0 r}}_{\text{库仑吸引}} + \underbrace{\frac{\hbar^2 l(l+1)}{2\mu r^2}}_{\text{离心势（排斥）}}$$
>
> 离心势 $\propto l(l+1)/r^2$ 来自角动量。$l$ 越大，离心势越强，电子被"推离"原子核越远——这就是为什么高角动量的电子更"外层"。

### 第三步：处理渐近行为——波函数在极端条件下的表现

为了求解这个微分方程，我们先考察在极端条件下（$r \to 0$ 和 $r \to \infty$）波函数长什么样。

**束缚态条件**：电子被原子核束缚住不飞走，要求总能量 $E < 0$（取 $E = 0$ 为电离极限）。

#### 当 $r \to \infty$ 时（远离原子核）

离心势和库仑势都趋于零，方程近似为：

$$
\frac{d^2R}{dr^2} \approx \frac{2\mu |E|}{\hbar^2} R
$$

定义 $\kappa = \sqrt{2\mu |E|}/\hbar$，解为指数形式：

$$
R(r) \sim e^{-\kappa r} \quad \text{或} \quad R(r) \sim e^{+\kappa r}
$$

> [!warning] 波函数在无穷远处必须衰减
> $e^{+\kappa r}$ 在 $r \to \infty$ 时发散到无穷大——这代表电子在宇宙边缘被找到的概率无穷大，物理上荒谬，也无法归一化。因此**必须选择 $e^{-\kappa r}$**。这个边界条件将最终"卡出"能量的离散值。

#### 当 $r \to 0$ 时（靠近原子核）

库仑势远强于离心势（$\sim 1/r$ 主导 $\sim 1/r^2$），方程的解趋近于：

$$
R(r) \sim r^l
$$

> [!info] 为什么是 $r^l$？
> 当 $r$ 很小时，$r^2 \frac{d^2R}{dr^2}$ 项和 $l(l+1)R$ 项必须平衡。代入 $R \sim r^{\alpha}$，得到 $\alpha(\alpha-1) = l(l+1)$，解为 $\alpha = l+1$ 或 $\alpha = -l$。$\alpha = -l$ 在 $r \to 0$ 时发散（对 $l > 0$），物理上不允许。因此 $R(r) \sim r^l$。

### 第四步：级数展开与"截断"——量子化的真正来源

结合两个极限行为，我们将径向波函数**猜想**为以下形式：

$$
R(r) = r^l e^{-\kappa r}\, u(r)
$$

其中 $u(r)$ 是一个待求的关于 $r$ 的函数。

**将这个 ansatz 代回径向方程**，经过代数运算（略去中间步骤），得到 $u(r)$ 满足的方程，可以用**幂级数**求解：

$$
u(r) = \sum_{k=0}^{\infty} c_k r^k
$$

代入方程后，可以得到相邻系数之间的**递推关系**。

**这就是见证奇迹的时刻：**

> [!danger] 级数发散的灾难
> 如果允许这个幂级数**无限延伸**下去（$k \to \infty$），数学分析表明，级数最终会表现得像 $e^{2\kappa r}$。
>
> 这意味着总的径向波函数：
> $$R(r) = r^l e^{-\kappa r} \cdot e^{2\kappa r} = r^l e^{+\kappa r} \xrightarrow{r \to \infty} \infty$$
>
> **波函数在无穷远处发散！** 电子在宇宙边缘出现的概率无穷大，完全无法归一化——这在物理上是不可接受的。

**唯一的拯救方案：** 这个幂级数必须在某一项之后**突然停止**，变成一个有限项的多项式。也就是说，必须存在一个最大的非负整数 $n_r$（称为**径向量子数**），使得从 $k = n_r$ 之后的所有系数都为零：

$$
c_{n_r + 1} = 0
$$

> [!tip] 截断条件 = 量子化的数学根源
> 根据递推公式，要让 $c_{n_r+1} = 0$，方程中的参数（能量 $E$ 和角动量 $l$）必须满足一个极其苛刻的**代数条件**。这个条件直接将能量 $E$ 锁定在了一系列**离散的值**上！
>
> 物理上：波函数为了在全空间可归一化，强迫级数截断，从而自然地"卡"出了离散的能级。截断后的 $u(r)$ 就是**拉盖尔多项式**（Laguerre polynomial），记为 $L_{n_r}^{2l+1}(\rho)$，其中 $\rho = 2\kappa r$。

### 第五步：主量子数 $n$ 的诞生

截断条件将 $n_r$（径向节点数）和 $l$（角量子数）联系起来。为了符号更简洁，物理学上定义了**主量子数** $n$：

$$
n = n_r + l + 1
$$

因为 $n_r \geq 0$、$l \geq 0$，所以 $n$ 必须是**正整数**：

$$
n = 1, 2, 3, \ldots
$$

> [!tip] $n$ 的物理含义
> $n$ 本质上是对径向波动多项式最高次幂的一种计数。$n_r = n - l - 1$ 是径向波函数的**节点数**（波函数穿过零的次数）。$n$ 越大，波函数振荡越多、分布越广、能量越高。

将截断条件中的参数整理后，就得到了对应于不同 $n$ 的**能量本征值**：

$$
E_n = -\left(\frac{\mu e^4}{32\pi^2\varepsilon_0^2\hbar^2}\right)\frac{1}{n^2}
$$

将所有常数（约化质量、基本电荷、普朗克常数等）代入计算，前面的常数项正好等于 $13.6\ \mathrm{eV}$：

$$
\boxed{E_n = -\frac{13.6\ \mathrm{eV}}{n^2}}
$$

同时量子数的取值范围自然涌现为：

$$
n = 1, 2, 3, \ldots \qquad l = 0, 1, \ldots, n-1 \qquad m = -l, -l+1, \ldots, l
$$

这就是[[Quantum-Numbers|量子数]]层级关系的严格数学来源。

> [!question] 深入思考
> 对比 Bohr 模型和薛定谔方程，两者的能量公式完全相同（$E_n = -13.6/n^2$ eV），但物理图像完全不同：
> - **Bohr 模型**：强行假设 $L = n\hbar$（角动量量子化），然后推导出能量公式
> - **薛定谔方程**：不需要预先假设量子化，量子化是**波函数归一化条件**的自然结果
>
> 这种"殊途同归"暗示了什么深层的物理？为什么角动量量子化假设恰好能给出正确答案？

### 与 Bohr 模型的完整对比

| | Bohr 模型（半经典） | 薛定谔方程（正统量子力学） |
|---|---|---|
| **量子化来源** | 强制假设 $L = n\hbar$ | 波函数归一化条件自然涌现 |
| **物理图像** | 电子沿确定圆轨道运动 | 电子以概率云（轨道）分布 |
| **轨道形状** | 圆形轨道 | $s$ 态球形，$p$ 态哑铃形… |
| **角动量** | $L = n\hbar$（不允许 $L=0$） | $L = \sqrt{l(l+1)}\hbar$（允许 $l=0$） |
| **能量公式** | $E_n = -13.6/n^2$ eV | $E_n = -13.6/n^2$ eV（完全相同！） |
| **多电子原子** | 完全失败 | 可以处理（Hartree-Fock 等） |
| **精细结构** | 无法描述 | 自然包含（加相对论修正后） |

> [!warning] Bohr 模型只是半经典图像
> Bohr 模型能给出氢原子能级和 Bohr 半径，但不能正确描述轨道形状、角动量精细结构、选择定则和多电子原子。真正的轨道来自薛定谔方程的波函数解，而不是电子沿确定圆轨道运动。
>
> 但 Bohr 的核心洞见——"经典物理在原子尺度需要量子化条件"——被保留在了正统量子力学中，变成了更为深刻的对易关系 $[\hat{x}, \hat{p}] = i\hbar$。

---

## 为什么能量只依赖 n

在非相对论氢原子中，能量只依赖 $n$，而不依赖[[Azimuthal-Quantum-Number|角量子数]] $l$ 和[[Magnetic-Quantum-Number|磁量子数]] $m$。这不是一般中心势的普遍结论，而是库仑势 $V(r)\propto -1/r$ 的特殊对称性导致的。

因此，同一 $n$ 下不同 $l,m$ 的状态在理想氢原子中简并。加入外磁场、自旋轨道耦合、相对论修正或 Lamb 位移后，这些简并会被部分打破。

---

## Python 图表

下面的图展示氢原子能级随 $n$ 增大逐渐逼近 $0$ 的结构。

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

n = np.arange(1, 8)
E = -13.6 / n**2

plt.figure(figsize=(7, 4.5))
for ni, Ei in zip(n, E):
    plt.hlines(Ei, 0.15, 0.85, color='#3366aa', linewidth=2.5)
    plt.text(0.9, Ei, rf'$n={ni}$', va='center', fontsize=10)

plt.axhline(0, color='#b84644', linestyle='--', linewidth=1.5, label='ionization limit')
plt.xlim(0, 1.25)
plt.ylim(-14.5, 1)
plt.xticks([])
plt.ylabel('Energy (eV)')
plt.title('Hydrogen Atom Energy Levels')
plt.grid(axis='y', alpha=0.25)
plt.legend()
plt.tight_layout()
plt.show()
```

---

## 相关概念

- [[Principal-Quantum-Number|主量子数]] — 氢原子能级的主要编号
- [[Quantum-Numbers|量子数]] — 氢原子束缚态的完整标签
- [[Azimuthal-Quantum-Number|角量子数]] — 由角向方程与径向方程共同限制
- [[Magnetic-Quantum-Number|磁量子数]] — 角动量在选定方向上的投影
- [[Method-of-Separation-of-Variables|分离变量法]] — 求解氢原子薛定谔方程的关键数学方法
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 精细结构的来源，修正纯库仑能级
- [[Fine-Structure|精细结构]] — 三个相对论修正合并后的统一能级修正公式

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $V(r)$ | 氢原子库仑势 | $V(r)=-\frac{1}{4\pi\varepsilon_0}\frac{e^2}{r}$ |
| $L_n$ | Bohr 角动量量子化 | $m_evr=n\hbar$ |
| $a_0$ | Bohr 半径 | $a_0=\frac{4\pi\varepsilon_0\hbar^2}{m_ee^2}$ |
| $r_n$ | Bohr 模型允许半径 | $r_n=a_0n^2$ |
| $E_n$ | 氢原子能级 | $E_n=-\frac{13.6\ \mathrm{eV}}{n^2}$ |
| $E_n$ | 类氢离子能级 | $E_n=-\frac{Z^2\,13.6\ \mathrm{eV}}{n^2}$ |
| $h\nu$ | Bohr 跃迁频率条件 | $h\nu=E_i-E_f$ |
| $\lambda$ | 氢原子谱线 | $\frac{1}{\lambda}=R_H\left(\frac{1}{n_f^2}-\frac{1}{n_i^2}\right)$ |
| $\psi_{nlm}$ | 氢原子定态波函数 | $\psi_{nlm}=R_{nl}Y_l^m$ |

---

## 📝 更新记录

- 2026-06-05: 大幅扩展薛定谔方程推导——五步完整推导：(1) 定态薛定谔方程建立，(2) 分离变量与径向方程（含有效势能物理图像），(3) 渐近行为分析（$r\to\infty$ 指数衰减、$r\to 0$ 幂次行为），(4) 级数展开与截断条件（量子化的真正来源），(5) 主量子数 $n$ 的诞生。新增 Bohr 模型与薛定谔方程完整对比表、深入思考问题。
- 2026-05-27: 补充 Bohr 三条假设、由能级差推出 Rydberg 光谱公式，并修复 Python 图表字符串闭合错误。
- 2026-05-27: 创建氢原子模型笔记，补充 Bohr 半经典推导、类氢离子推广、薛定谔方程来源和能级图。
