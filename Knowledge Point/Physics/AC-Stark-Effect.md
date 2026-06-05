---
subject:
  - Physics
topic:
  - Atomic Physics
  - Quantum Optics
source: "Foot Atomic Physics, Ch.12; Cohen-Tannoudji"
comprehension: vague
aliases:
  - AC Stark 效应
  - AC Stark shift
  - 光移
  - light shift
  - 动态 Stark 效应
  - dynamic Stark effect
status: Draft
date: 2026-06-04
tags:
  - Atomic_Physics
  - Quantum_Optics
  - Perturbation_Theory
  - Quantum_Computing
---

# AC-Stark-Effect（AC Stark 效应）

> 原子在**交变电场**（激光场）中的能级位移——与静态电场引起的 DC Stark 效应不同，AC Stark 效应通过**虚跃迁**图像来理解，是光镊囚禁、光移和单比特门的物理基础。

---

## 物理直觉 / 数学直觉

> [!tip] 核心直觉
> DC Stark 效应是静电场拉扯电子云产生的能级位移；AC Stark 效应是振荡电场（激光）的效果。原子在激光场中不断地"虚拟地"跃迁到激发态又立即返回基态——这种虚跃迁改变了基态的能量，就像微扰论的二阶修正。
>
> 对光镊来说，这个位移就是**囚禁势**——激光强的地方位移大（能量低），原子被"吸"过去。

---

## 核心定义与公式

### 1. 虚跃迁图像

原子在频率为 $\omega_L$ 的激光场中，基态 $|g\rangle$ 通过虚跃迁耦合到激发态 $|e\rangle$：

$$
|g\rangle \xrightarrow{\text{吸收 } \omega_L} |e\rangle \xrightarrow{\text{受激辐射}} |g\rangle
$$

这个虚过程对基态能量的二阶微扰修正为：

$$
\Delta E_g = \frac{|\langle e | \hat{d} \cdot \mathbf{E}_0 | g \rangle|^2}{4\hbar} \left[\frac{1}{\omega_L - \omega_0} + \frac{1}{\omega_L + \omega_0}\right]
$$

当 $\omega_L \ll \omega_0$（远红失谐）时，第二项可以忽略：

$$
\Delta E_g \approx \frac{|\langle e | \hat{d} \cdot \mathbf{E}_0 | g \rangle|^2}{4\hbar(\omega_L - \omega_0)}
$$

### 2. AC Stark shift 公式

对于二能级原子，AC Stark shift 为：

$$
\boxed{\Delta E_g = \frac{\hbar \Omega^2}{4\Delta}}
$$

其中：
- $\Omega = \langle e | d \cdot E_0 / \hbar | g \rangle$：拉比频率（$\Omega \propto E_0 \propto \sqrt{I}$）
- $\Delta = \omega_L - \omega_0$：失谐量

**关键结论**：
- 红失谐（$\Delta < 0$）：$\Delta E_g < 0$，基态能量**降低** → 原子被吸引到光强最大处（光镊）
- 蓝失谐（$\Delta > 0$）：$\Delta E_g > 0$，基态能量**升高** → 原子被排斥到光强最小处

### 3. AC Stark shift 与光强的关系

因为 $\Omega \propto E_0 \propto \sqrt{I}$，所以：

$$
\Delta E_g \propto \frac{I}{\Delta}
$$

这正是光镊囚禁势正比于光强的原因。

### 4. 多能级原子的 AC Stark shift

对于多能级原子，基态的 AC Stark shift 是所有虚跃迁的总和：

$$
\Delta E_g = \sum_e \frac{|\langle e | \hat{d} \cdot \mathbf{E}_0 | g \rangle|^2}{4\hbar} \left[\frac{1}{\omega_L - \omega_{eg}} + \frac{1}{\omega_L + \omega_{eg}}\right]
$$

> [!info] 折合质量修正
> 实际计算中，电子电荷 $e$ 应替换为 $e/2$（考虑约化质量），且需要对不同偏振分量求和。

### 5. 不同跃迁的贡献

以 Rb-87 为例，$5S_{1/2}$ 基态在 1064 nm 光镊中的 AC Stark shift 来自 $5S \to 5P$ 跃迁：

- $5S_{1/2} \to 5P_{1/2}$（$D_1$ 线，795 nm）
- $5S_{1/2} \to 5P_{3/2}$（$D_2$ 线，780 nm）

由于 $D_1$ 和 $D_2$ 距离 1064 nm 的失谐不同，它们对 AC Stark shift 的贡献不等——这会导致 $m_F$ 子能级的**差异光移**（differential light shift），影响量子比特的相干性。

---

## 关键性质

- **AC Stark shift 正比于光强，反比于失谐**
- **远红失谐时**：基态能量降低 → 光阱（光镊）
- **近共振时**：位移很大，但散射率也很高（加热）→ 一般避免近共振操作
- **远失谐的权衡**：失谐越大，光移越小，散射率越低，但需要更高功率才能达到同等阱深
- **微分光移**：不同超精细态的 AC Stark shift 不同，影响量子比特频率

> [!warning] 常见错误
> AC Stark shift ≠ DC Stark shift。DC 效应正比于 $E^2$（$\propto I$），但需要静电场；AC 效应正比于 $E^2/\Delta$，需要振荡场。两者物理机制不同，虽然数学形式类似。

---

## 与其他知识的联系

- [[Perturbation-Theory|微扰论]] — AC Stark shift 的理论推导基于二阶微扰论
- [[Hydrogen-Atom-Model|氢原子模型]] — DC Stark 效应的参考
- [[Zeeman-Effect|塞曼效应]] — DC Stark 效应的磁学类比
- [[Optical-Tweezers|光镊]] — AC Stark shift 是光镊囚禁势的物理起源
- [[Larmor-Precession|拉莫尔进动]] — AC Stark shift 引起的能级位移改变进动频率
- [[Fine-Structure|精细结构]] — 不同精细结构态的 AC Stark shift 不同

---

## 典型应用场景

- **光镊囚禁**：远红失谐光镊利用 AC Stark shift 产生囚禁势
- **单比特门**：通过控制 AC Stark shift 的时间积分实现 Z 旋转
- **光晶格**：周期性光场产生周期性 AC Stark shift，形成光晶格势
- **魔术波长光镊**：特定波长下两个超精细态的 AC Stark shift 相等，消除微分光移

> [!info] 魔术波长（magic wavelength）
> 在特定的光镊波长下，量子比特的两个超精细态经历完全相同的 AC Stark shift——微分光移为零，量子比特频率不受光镊影响。这对提高量子门保真度至关重要。

---

## 📐 核心公式摘要

| 符号 | 含义 | 公式 |
|------|------|------|
| $\Delta E_g$ | 基态 AC Stark shift | $\hbar\Omega^2/4\Delta$ |
| $\Omega$ | 拉比频率 | $\propto \sqrt{I}$，$\propto 1/\sqrt{\Delta}$ |
| $\Delta$ | 失谐 | $\omega_L - \omega_0$ |
| $\Delta E_g \propto$ | 光强依赖 | $I/\Delta$ |

---

## 📝 更新记录

- 2026-06-04: 创建初稿 — 虚跃迁图像、AC Stark shift 公式、多能级修正、魔术波长
