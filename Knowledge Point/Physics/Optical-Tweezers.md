---
subject:
  - Physics
topic:
  - Atomic Physics
  - AMO Physics
source: "Browaeys & Lahaye, Science 370, 1309 (2020)"
comprehension: vague
aliases:
  - 光镊
  - optical tweezers
  - 光阱
  - 光镊阵列
status: Draft
date: 2026-06-04
tags:
  - Atomic_Physics
  - AMO
  - Experimental_Physics
  - Quantum_Computing
  - Neutral_Atom
  - Optical_Tweezer
---

# Optical-Tweezers（光镊）

> 用高度聚焦的激光束产生的**偶极梯度力**囚禁单个中性原子——这是目前中性原子量子计算最主流的量子比特寄存器平台。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 光镊就像一根"光学的手指"：强聚焦的激光在焦点处产生最强的电场，中性原子被电场梯度"拉"向光强最大处（红失谐情况下）。单个原子就像被困在光强"山丘"的顶端，被周围的光场"包裹"住。

---

## 核心定义与公式

### 1. 偶极梯度力

原子在非均匀光场中受到的力来自**感应偶极矩**与**电场梯度**的相互作用：

$$
\mathbf{F}_{\text{dip}} = \frac{1}{2}\text{Re}[\alpha(\omega)] \nabla |\mathbf{E}|^2
$$

其中 $\alpha(\omega)$ 是原子的极化率（与频率相关）。

对于二能级原子：

$$
\alpha(\omega) = \frac{6\pi\epsilon_0 c^3}{\omega_0^3} \cdot \frac{\Gamma}{\omega_0 - \omega - i\Gamma/2}
$$

红失谐（$\omega < \omega_0$）时：$\text{Re}[\alpha] > 0$ → 原子被吸引到光强最大处（焦点）。

蓝失谐（$\omega > \omega_0$）时：$\text{Re}[\alpha] < 0$ → 原子被排斥到光强最小处。

> [!warning] 红失谐 vs 蓝失谐光镊
> 实验中主要用**红失谐**光镊（$\omega < \omega_0$），原子在焦点处被囚禁。蓝失谐光镊可以用来实现"墙"型囚禁（原子在暗处），但在中性原子量子计算中较少使用。

### 2. 势阱深度

光镊的囚禁势：

$$
U(\mathbf{r}) = -\frac{1}{2}\text{Re}[\alpha(\omega)] |\mathbf{E}(\mathbf{r})|^2
$$

对于高斯光束，焦点处的势阱深度：

$$
U_0 = -\frac{\text{Re}[\alpha]}{2\epsilon_0 c} \cdot \frac{2P}{\pi w_0^2}
$$

其中 $P$ 是激光功率，$w_0$ 是光束腰半径。

**典型参数**：
- 光镊波长：~1064 nm（远红失谐于 Rb 的 780 nm $D_2$ 线）
- 光镊功率：$\sim 100$ mW
- 腰半径：$w_0 \sim 1$ $\mu$m
- 势阱深度：$k_B \times 1$ mK 量级

### 3. 谐振子近似

在阱底附近，囚禁势近似为各向异性谐振子：

$$
U(\mathbf{r}) \approx U_0 + \frac{1}{2}m\omega_r^2(x^2 + y^2) + \frac{1}{2}m\omega_z^2 z^2
$$

径向和轴向频率通常差异很大（$\omega_r \gg \omega_z$），因为光镊是细长形的。

### 4. 从 MOT 到单原子光镊

**装载流程**：
1. MOT 冷却并囚禁大量原子（$10^7$ 量级，温度 $\sim 100$ $\mu$K）
2. 偏振梯度冷却（PGC）进一步冷却到 $\sim 10$ $\mu$K
3. 打开光镊阵列（通常用 AOM 或 SLM 产生）
4. 原子随机落入光镊（每个镊子最多一个原子——**光辅助碰撞阻塞**）
5. 成像检测：用荧光成像检查每个位置是否有原子
6. 遗弃空位，留下规则的单原子阵列

> [!info] 光辅助碰撞阻塞
> 当两个原子同时落入同一个光镊时，近共振光散射的光子被两个原子关联吸收和辐射，导致它们获得足够的动能逃逸——每个光镊自然只留下一个原子。

---

## 关键性质

- **单原子分辨**：每个光镊位置可以独立成像和操控
- **可编程阵列**：用空间光调制器（SLM）或声光偏转器（AOM）可以任意排列原子
- **相干操控**：光镊中的原子可以进行拉比振荡、Rydberg 激发、两比特门
- **阵列规模**：目前实验已实现 $>1000$ 个原子的有序阵列
- **长相干时间**：超精细量子比特在光镊中的相干时间可达秒量级

> [!warning] 装载效率
> 单次装载成功率通常 $<100\%$（$\sim 50-80\%$），需要通过成像-遗弃循环来获得完美的阵列。

---

## 与其他知识的联系

- [[Doppler-Cooling|Doppler 冷却]] — 光镊装载前的原子冷却
- [[AC-Stark-Effect|AC Stark 效应]] — 光镊的囚禁势本质上是 AC Stark 位移
- [[Rydberg-Atom|Rydberg 原子]] — 光镊中的原子通过 Rydberg 激发实现两比特门
- [[Rydberg-Blockade|Rydberg 阻塞]] — 阻塞效应是两比特门的物理基础
- [[CZ-Gate|CZ 门]] — 利用 Rydberg 阻塞在光镊阵列中实现两比特门
- [[Selection-Rules|选择定则]] — Rydberg 激发路径受选择定则约束
- [[Hyperfine-Structure|超精细结构]] — 量子比特编码在超精细态上

---

## 典型应用场景

- **中性原子量子计算**：光镊阵列是最主流的量子比特寄存器平台
- **量子模拟**：用光镊阵列模拟 Ising 模型、Heisenberg 模型等
- **单原子光谱**：单原子级别的精密光谱测量
- **量子气体显微镜**：结合高分辨成像实现单原子分辨

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\mathbf{F}_{\text{dip}}$ | 偶极梯度力 | $\frac{1}{2}\text{Re}[\alpha]\nabla|\mathbf{E}|^2$ |
| $U(\mathbf{r})$ | 囚禁势 | $-\frac{1}{2}\text{Re}[\alpha]|\mathbf{E}|^2 / \epsilon_0 c$ |
| $\alpha(\omega)$ | 原子极化率 | $\propto \Gamma/(\omega_0 - \omega)$ |
| $\omega_r, \omega_z$ | 径向/轴向囚禁频率 | 由 $U_0$ 和 $w_0$ 决定 |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 偶极梯度力、势阱深度、谐振子近似、MOT 到单原子的流程
