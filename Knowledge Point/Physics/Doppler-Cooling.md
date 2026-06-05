---
subject:
  - Physics
topic:
  - Atomic Physics
  - AMO Physics
source: "Foot Atomic Physics, Ch.10; Metcalf & van der Straten"
comprehension: vague
aliases:
  - Doppler 冷却
  - Doppler cooling
  - 磁光阱
  - MOT
  - laser cooling
  - 激光冷却
status: Draft
date: 2026-06-04
tags:
  - Atomic_Physics
  - Laser_Cooling
  - AMO
  - Experimental_Physics
---

# Doppler-Cooling（Doppler 冷却与磁光阱）

> 用激光的辐射压力把原子从室温（$\sim 300$ K, $v \sim 300$ m/s）减速到 $\mu$K 量级（$v \sim$ cm/s），是中性原子量子计算的**第一步**——先抓住原子，才能操控它。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> 想象一个向你飞来的球，你不断地扔球去"撞"它——每次碰撞都会减慢它的速度。激光光子就像这些"球"，原子吸收光子获得动量反冲。关键技巧：**红失谐**激光让迎面飞来的原子优先吸收光子（多普勒效应使频率上移至共振），而离去的原子几乎不吸收——于是原子被"减速"了。

---

## 核心定义与公式

### 1. 辐射压力（散射力）

二能级原子在激光场中，吸收光子后沿光传播方向获得动量 $\hbar \mathbf{k}$，自发辐射后随机方向发射。平均效果是原子沿激光方向获得一个稳恒的力：

$$
F_{\text{scatt}} = \hbar k \cdot \Gamma_{\text{scatt}}
$$

其中散射率为：

$$
\Gamma_{\text{scatt}} = \frac{\Gamma}{2} \cdot \frac{s}{1 + s + (2\Delta/\Gamma)^2}
$$

- $\Gamma$：激发态自然线宽
- $s = I/I_{\text{sat}}$：饱和参数（激光强度/饱和强度）
- $\Delta = \omega_L - \omega_0$：失谐量（红失谐 $\Delta < 0$）

> [!info] 饱和强度
> Rb-87 的 $D_2$ 线（780 nm）：$I_{\text{sat}} \approx 1.67$ mW/cm$^2$，$\Gamma/2\pi \approx 6.07$ MHz。

### 2. Doppler 冷却原理

考虑一维情况，原子以速度 $v$ 运动。由于多普勒效应，原子"感受到"的激光频率为：

$$
\omega_{\text{atom}} = \omega_L - \mathbf{k} \cdot \mathbf{v}
$$

**关键设置**：两束对射激光，都**红失谐**（$\omega_L < \omega_0$）。

- 原子向右运动（$v > 0$）→ 右行激光（反向）的 Doppler 频移使其更接近共振 → 吸收更多光子 → 获得向左的力
- 原子向右运动 → 左行激光（同向）的 Doppler 频移使其更远离共振 → 吸收更少光子

净效果：原子速度被阻尼，等效于一个粘滞力：

$$
F_{\text{net}} \approx -\alpha v \quad \text{（小速度极限）}
$$

其中阻尼系数：

$$
\alpha = -\frac{8\hbar k^2 s (2\Delta/\Gamma)}{[1 + s + (2\Delta/\Gamma)^2]^2}
$$

> 冷却条件：$\Delta < 0$（红失谐），此时 $\alpha > 0$。

### 3. Doppler 极限温度

Doppler 冷却能达到的最低温度（Doppler limit）：

$$
T_D = \frac{\hbar \Gamma}{2 k_B}
$$

对于 Rb-87：$T_D \approx 146$ $\mu$K。

> [!tip] 为什么有温度极限？
> Doppler 冷却靠吸收和自发辐射。自发辐射是随机方向的，引入动量扩散（加热）。当冷却速率与扩散速率达到平衡时，温度不再下降——这就是 Doppler 极限。

### 4. 磁光阱（MOT）

**问题**：一维 Doppler 冷却只能在 1D 方向减速原子，实际需要三维。

**MOT 的解决方案**：

1. **三对对射红失谐激光**：覆盖 $x, y, z$ 三个方向
2. **不均匀磁场**（反亥姆霍兹线圈）：在中心为零，向外增大

磁场使不同位置的原子发生不同的 Zeeman 分裂。结合圆偏振激光，使得：
- 位置偏离中心的原子**优先吸收指向中心的光**
- 原子被"推"向中心（位置相关的力）
- 同时 Doppler 效应继续减速

净效果：**位置和速度都被约束**，原子被囚禁在磁场零点附近。

**典型参数**（Rb-87）：
- 温度：$\sim 100$ $\mu$K
- 原子数：$10^6 \sim 10^9$
- 囚禁时间：秒量级

> [!info] MOT 是一切的起点
> 中性原子量子计算的第一步几乎总是 MOT：先把原子从蒸气中"抓住"并冷却，然后转移到光镊或其他囚禁势中。

---

## 关键性质

- **Doppler 冷却极限**：$T_D = \hbar\Gamma/2k_B$，对 Rb 约 146 $\mu$K
- **低于 Doppler 极限**需要亚 Doppler 冷却（Sisyphus 冷却、CPT 冷却等），可达 $\sim 1$ $\mu$K
- **MOT 提供 3D 囚禁**：但只能做"大云"囚禁，不能实现单原子分辨
- **从 MOT 到光镊**：MOT 冷却后的原子被加载到光镊阵列中，实现单原子操控

> [!warning] MOT 不够冷
> MOT 温度（$\sim 100$ $\mu$K）对于光镊装载来说太热了——需要进一步冷却到 $\sim 10$ $\mu$K 甚至更低。通常在 MOT 之后进行偏振梯度冷却（PGC）。

---

## 与其他知识的联系

- [[Optical-Tweezers|光镊]] — MOT 冷却后的原子被加载到光镊阵列
- [[Larmor-Precession|拉莫尔进动]] — MOT 中原子自旋在磁场中的进动
- [[Zeeman-Effect|塞曼效应]] — MOT 利用 Zeeman 分裂实现位置相关的力
- [[Selection-Rules|选择定则]] — 激光冷却的跃迁必须满足选择定则
- [[Spin-Orbit-Coupling|自旋-轨道耦合]] — $D_2$ 线的多普勒冷却跃迁涉及自旋-轨道耦合
- [[Rydberg-Atom|Rydberg 原子]] — 冷却到 μK 量级是 Rydberg 激发的前提

---

## 典型应用场景

- **冷原子物理**：几乎所有冷原子实验的起点
- **原子钟**：冷原子提高时钟精度（Cs 原子钟、光晶格钟）
- **中性原子量子计算**：MOT → PGC → 光镊装载 → 单原子阵列
- **玻色-爱因斯坦凝聚**：MOT 冷却后再进一步蒸发冷却到 nK 量级

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $F_{\text{scatt}}$ | 散射力（辐射压力） | $\hbar k \cdot \Gamma_{\text{scatt}}$ |
| $\Gamma_{\text{scatt}}$ | 散射率 | $\frac{\Gamma}{2} \cdot \frac{s}{1+s+(2\Delta/\Gamma)^2}$ |
| $T_D$ | Doppler 极限温度 | $\hbar\Gamma / 2k_B$ |
| $I_{\text{sat}}$ | 饱和强度（Rb-87） | $\approx 1.67$ mW/cm$^2$ |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 辐射压力、Doppler 冷却原理、Doppler 极限、MOT 原理
