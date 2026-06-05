---
subject:
  - Physics
topic:
  - Quantum Mechanics
  - Atomic Physics
source: "self-authored"
comprehension: vague
aliases:
  - 量子计算知识补充
  - QC 补充知识点
  - Quantum Computing Supplements
status: WIP
date: 2026-06-03
tags:
  - Quantum_Computing
  - Physics
  - Study-Plan
  - Neutral_Atom
---

# Quantum Computing Supplements (量子计算知识补充)

> 学习量子计算过程中发现需要补充的物理学知识点清单。每项标注学习状态和与量子计算的关联。

---

## 📋 知识补充清单

### 1. 理论基础（计算工具）

- [ ] [[Perturbation-Theory|Perturbation-Theory（微扰论）]] — Stark 效应、交流 Stark 效应（AC Stark shift）的理论基础

### 2. 角动量体系

- [ ] [[Angular-Momentum-Coupling|Angular-Momentum-Coupling（角动量耦合）]] — Clebsch-Gordan 系数，多粒子态的构造
- [ ] [[Electron-Spin|电子自旋]] — 内禀角动量 $s=1/2$，泡利矩阵，自旋磁矩

### 3. 原子能级结构

- [ ] [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 精细结构的核心机制，Rydberg 态能级结构
- [ ] [[Fine-Structure|Fine-Structure（精细结构）]] — 自旋-轨道 + 相对论修正的完整图景
- [ ] [[Lande-g-Factor|朗德 g 因子]] — 塞曼分裂间距的关键参数
- [ ] [[Alkali-Metal-Doublet|碱金属双线结构]] — 贯穿轨道效应 + 自旋-轨道耦合 → $D_1$/$D_2$ 线

### 4. 外场效应与超精细结构

- [ ] [[Zeeman-Effect|Zeeman-Effect（塞曼效应）]] — 外磁场中能级分裂，量子比特寻址与选择定则
- [ ] [[Hyperfine-Structure|超精细结构]] — 中性原子量子比特编码的基础，21 cm 线，原子钟原理
- [ ] [[Lamb-Shift|兰姆移位]] — QED 修正，$2S_{1/2}$ 与 $2P_{1/2}$ 的简并打破
- [ ] [[Selection-Rules|选择定则]] — 跃迁矩阵元非零的量子数条件，光谱与激光操控的基础

### 5. 原子操控与囚禁

- [ ] [[Doppler-Cooling|Doppler 冷却与磁光阱]] — 辐射压力减速原子，MOT 三维囚禁
- [ ] [[Optical-Tweezers|光镊]] — 偶极梯度力囚禁单原子，可编程量子比特阵列
- [ ] [[AC-Stark-Effect|AC Stark 效应]] — 光场引起的动态能级位移，光镊囚禁势与光移

### 6. Rydberg 物理（中性原子量子计算核心）

- [ ] [[Rydberg-Atom|Rydberg 原子]] — 高激发态 $n \sim 50$，巨大偶极矩，标度律 $n^{11}$
- [ ] [[Van-der-Waals-Interaction|van der Waals 相互作用]] — Rydberg 原子间 $C_6/R^6$ 相互作用


---

## 学习优先级建议

> [!tip] 中性原子平台路线图
> 如果你的重点是中性原子（Neutral Atom）量子计算，建议的学习顺序：
> 1. **微扰论** → 掌握计算工具（Stark 效应、AC Stark shift 等）
> 2. **角动量耦合 + 电子自旋** → 掌握量子数体系、泡利矩阵与 Clebsch-Gordan 系数
> 3. **自旋-轨道耦合 → 精细结构 → 碱金属双线** → 理解原子内禀能级结构与 Rydberg 态
> 4. **朗德 g 因子 → 塞曼效应 + 超精细结构** → 理解量子比特编码与外场寻址
> 5. **兰姆移位** → 理解 QED 修正对精密光谱的影响
> 6. **选择定则** → 理解哪些跃迁可以被激光驱动
> 7. **Doppler 冷却 → MOT → 光镊 → AC Stark 效应** → 理解原子囚禁与操控的实验工具链
> 8. **Rydberg 原子 → van der Waals 相互作用 → Rydberg 阻塞** → 理解两比特门的核心物理
> 9. **Rabi 振荡** → 理解激光操控原子态的物理（详见 QC 科研库 [[Rabi-Flopping]]）

---

## 📝 更新记录

- 2026-06-03: 创建初稿 — 初始条目（超精细结构、自旋-轨道耦合），其余待补充
- 2026-06-04: 补全所有知识条目笔记链接；创建 [[Perturbation-Theory]] 和 [[Angular-Momentum-Coupling]]；按学习依赖链重排顺序；标注 Rabi 振荡见 QC 科研库
- 2026-06-04: 新建 5 个笔记：[[Stern-Gerlach-Experiment]]、[[Electron-Spin]]、[[Lande-g-Factor]]、[[Alkali-Metal-Doublet]]、[[Lamb-Shift]]；清单扩至 11 项；路线图更新至 6 步
- 2026-06-04: 补全原子物理操控链：新建 [[Selection-Rules]]、[[Doppler-Cooling]]、[[Optical-Tweezers]]、[[AC-Stark-Effect]]、[[Rydberg-Atom]]、[[Van-der-Waals-Interaction]]；清单扩至 17 项；路线图更新至 9 步
