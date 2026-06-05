---
subject:
  - Math
  - Physics
topic:
  - Study-Roadmap
aliases:
  - 学习路径
  - 学习计划
  - Study Roadmap
  - 知识图谱
status: WIP
date: 2026-06-01
tags:
  - Study-Roadmap
  - Math
  - Physics
---

# Study Roadmap (学习路径)

> 全局学习路径，记录各学科领域的知识点完成情况与学习顺序。点击复选框可直接切换完成状态。

---

## 一、数学 Math

### 微积分 Calculus

- [x] [[Gaussian-Integral|高斯积分]] — 数学物理最核心积分，概率/场论/统计物理的基石
- [ ] Multivariable-Calculus（多元微积分）— 梯度、散度、旋度，Green/Gauss/Stokes 定理
- [ ] Complex-Analysis（复变函数）— 留数定理、解析延拓，物理中计算积分的利器
- [ ] Fourier-Analysis（Fourier 分析）— Fourier 级数/变换，信号处理与量子力学的共同语言

### 线性代数 Linear Algebra

- [x] [[Unitary-Matrix|酉矩阵]] — 复空间保距变换，量子力学时间演化的数学基础
- [ ] Eigenvalues-Eigenvectors（特征值与特征向量）— 对角化、谱定理，所有线性物理问题的核心
- [ ] Hermitian-Matrix（Hermitian 矩阵）— 量子力学可观测量的数学载体，$U=e^{iH}$ 生成酉矩阵
- [ ] Matrix-Diagonalization（矩阵对角化）— Jordan 标准型、相似变换，解耦多体问题的关键
- [ ] Tensor-Product（张量积）— 多体量子系统的数学语言

### 偏微分方程 PDE

- [x] [[Method-of-Separation-of-Variables|分离变量法]] — PDE 最经典的解法，本征函数展开的起点
- [ ] Green-Function（Green 函数）— 非齐次方程的点源响应，场论传播子的数学原型
- [ ] Sturm-Liouville-Theory（Sturm-Liouville 理论）— 分离变量法的严格数学基础，本征函数正交完备性
- [ ] Special-Functions（特殊函数）— Legendre、Bessel、Hermite 多项式，球谐函数

---

## 二、物理 Physics

### 经典力学 Classical Mechanics

- [x] [[Torque|力矩]] — 角动量变化的驱动者
- [ ] Lagrangian-Mechanics（Lagrange 力学）— 最小作用量原理，广义坐标，分析力学的入口
- [ ] Hamiltonian-Mechanics（Hamilton 力学）— 相空间、正则方程，经典→量子的桥梁
- [ ] Normal-Mode-Analysis（简正模式）— 耦合振子的对角化，经典→量子场论的对应
- [ ] Central-Force-Motion（有心力运动）— 开普勒问题、散射，为氢原子量子力学铺垫

### 电动力学 Electrodynamics

- [x] [[Magnetic-Moment|磁矩]] — 电流回路与自旋磁矩
- [ ] [[Force-on-Magnetic-Dipole-in-Gradient-Field|磁矩在梯度磁场中的受力]] — 梯度磁场中磁偶极子受力推导
- [ ] Maxwells-Equations（Maxwell 方程组）— 电磁场的统一理论，微分/积分形式
- [ ] Electromagnetic-Wave（电磁波）— 波动方程、辐射、波导
- [ ] Radiation（辐射）— 加速电荷辐射，Larmor 公式的推广

### 原子与量子物理 Atomic & Quantum Physics

**基础量子力学**

- [x] [[Commutation-Relation|对易关系]] — $[\hat{A},\hat{B}]=\hat{A}\hat{B}-\hat{B}\hat{A}$，量子不确定性的代数根源
- [x] [[Quantum-Numbers|量子数]] — $n, l, m_l, m_s, j, m_j$ 全景
- [ ] [[Good-Quantum-Number|好量子数]] — 当前哈密顿量下能稳定标记量子态的量子数；用对易关系判断
- [x] [[Principal-Quantum-Number|主量子数]] — 决定能级，$E_n \propto -1/n^2$
- [x] [[Azimuthal-Quantum-Number|角量子数]] — 轨道角动量，$l=0,1,\ldots,n-1$
- [x] [[Magnetic-Quantum-Number|磁量子数]] — 角动量投影，$m=-l,\ldots,l$
- [x] [[Hydrogen-Atom-Model|氢原子模型]] — 最简单的原子，量子力学的"果蝇"
- [x] [[Larmor-Precession|拉莫尔进动]] — 磁矩在外磁场中的经典进动
- [ ] Schrodinger-Equation（Schrödinger 方程）— 量子力学的基本方程，态演化的核心
- [ ] Variational-Method（变分法）— 基态能量估算，Hartree-Fock 的起点
- [ ] Scattering-Theory（散射理论）— Born 近似、分波法，实验与理论的接口

**方法与工具**

- [ ] [[Perturbation-Theory|Perturbation-Theory（微扰论）]] — Stark 效应、AC Stark shift 的理论基础
- [ ] [[Angular-Momentum-Coupling|Angular-Momentum-Coupling（角动量耦合）]] — CG 系数，$\mathbf{J}=\mathbf{J}_1+\mathbf{J}_2$
- [ ] [[Selection-Rules|选择定则]] — 跃迁矩阵元非零的量子数条件

**原子能级结构**

- [ ] [[Spin-Orbit-Coupling|自旋-轨道耦合]] — 精细结构的来源，$\Delta E \propto \mathbf{L}\cdot\mathbf{S}$
- [ ] [[Electron-Spin|电子自旋]] — 内禀角动量 $s=1/2$，泡利矩阵，自旋磁矩
- [ ] [[Fine-Structure|Fine-Structure（精细结构）]] — 自旋-轨道 + 相对论修正的完整图景
- [ ] [[Hyperfine-Structure|超精细结构]] — 核自旋与电子角动量耦合，21 cm 线，原子钟
- [ ] [[Lamb-Shift|兰姆移位]] — QED 修正，$2S_{1/2}$ 与 $2P_{1/2}$ 的简并打破
- [ ] [[Alkali-Metal-Doublet|碱金属双线结构]] — 贯穿轨道效应 + 自旋-轨道耦合 → $D_1$/$D_2$ 线
- [ ] [[Lande-g-Factor|朗德 g 因子]] — 塞曼分裂间距的决定参数
- [ ] [[Zeeman-Effect|塞曼效应]] — 外磁场中能级分裂，正常/反常/Paschen-Back

**实验与操控**

- [ ] [[Stern-Gerlach-Experiment|施特恩-格拉赫实验]] — 空间量子化的直接实验证据

**中性原子量子计算相关**

- [ ] [[Doppler-Cooling|Doppler 冷却与磁光阱]] — 辐射压力减速原子，MOT 三维囚禁
- [ ] [[Optical-Tweezers|光镊]] — 偶极梯度力囚禁单原子，可编程量子比特阵列
- [ ] [[AC-Stark-Effect|AC Stark 效应]] — 光场引起的动态能级位移，光镊囚禁势与光移
- [ ] [[Rydberg-Atom|Rydberg 原子]] — 高激发态 $n \sim 50$，巨大偶极矩，标度律 $n^{11}$
- [ ] [[Van-der-Waals-Interaction|van der Waals 相互作用]] — Rydberg 原子间 $C_6/R^6$ 相互作用

### 统计物理 Statistical Physics

- [x] [[Bose-Einstein-Distribution|玻色-爱因斯坦分布]] — 玻色子统计，光子/声子的热力学
- [x] [[Ising-Model|伊辛模型]] — 统计力学的"果蝇"，相变与临界现象
- [x] [[Spontaneous-Symmetry-Breaking|自发对称破缺]] — 有序相的判据，朗道理论
- [ ] Boltzmann-Distribution（玻尔兹曼分布）— 经典统计的基础，配分函数
- [ ] Partition-Function（配分函数）— 所有热力学量的生成函数
- [ ] Phase-Transition（相变）— 一级/二级相变，临界指数，标度律
- [ ] Fermi-Dirac-Distribution（费米-狄拉克分布）— 费米子统计，金属电子论、白矮星

### 信息论 Information Theory

- [ ] Shannon-Entropy（香农熵）— 信息的度量，$H=-\sum p_i \log p_i$
- [ ] Channel-Capacity（信道容量）— Shannon 定理，极限传输速率
- [ ] Quantum-Information（量子信息）— 量子比特、量子纠缠、von Neumann 熵

---

## 🤔 学习疑问 Learning Questions

> 学习过程中遇到的未解决问题。解决后打勾并移到底部"已解决"区域。

**待解决**

- [ ] **好量子数在不同哈密顿量下变好/变坏的对易子推导** — 为什么中心力场中 $l,m_l,s,m_s$ 都是好量子数；加入自旋-轨道耦合后 $m_l,m_s$ 变坏而 $j,m_j$ 变好；弱 Zeeman 场中 $m_j$ 严格好而 $j$ 只是近似好？
  📎 相关：[[Good-Quantum-Number|好量子数]] · [[Commutation-Relation|对易关系]] · [[Spin-Orbit-Coupling|自旋-轨道耦合]] · [[Zeeman-Effect|塞曼效应]]

- [ ] **角动量耦合取值规则的根源** — 轨道与自旋耦合后 $j$ 为什么只能取 $|l-s|, |l-s|+1, \ldots, l+s$ 这些值？三角不等式背后的量子力学推导是什么？
  📎 相关：[[Angular-Momentum-Coupling|角动量耦合]] · [[Spin-Orbit-Coupling|自旋-轨道耦合]]

- [ ] **朗德 g 因子的量子力学推导** — $g_J = 1 + \frac{J(J+1)+S(S+1)-L(L+1)}{2J(J+1)}$ 这个公式具体怎么从 $\boldsymbol{\mu} = -\frac{\mu_B}{\hbar}(\mathbf{L}+2\mathbf{S})$ 推导出来？投影定理在这步中如何严格使用？
  📎 相关：[[Lande-g-Factor|朗德 g 因子]] · [[Magnetic-Moment|磁矩]] · [[Zeeman-Effect|塞曼效应]]

**已解决**

（暂无）

---

## 🔗 全局知识路线图

```
                        ┌─────────────┐
                        │  Linear     │
                        │  Algebra    │
                        └──────┬──────┘
                               │
              ┌────────────────┼────────────────┐
              ▼                ▼                ▼
       ┌──────────┐   ┌──────────────┐   ┌───────────┐
       │ Calculus │   │ PDE          │   │ Complex   │
       │ & Fourier│   │ (分离变量法,  │   │ Analysis  │
       │          │   │  Green函数)   │   │ (留数定理) │
       └────┬─────┘   └──────┬───────┘   └─────┬─────┘
            │                │                  │
            └────────┬───────┘──────────────────┘
                     ▼
            ┌─────────────────┐
            │  Classical      │
            │  Mechanics      │
            │  (Lagrange →    │
            │   Hamilton)     │
            └───────┬─────────┘
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
 ┌───────────┐ ┌─────────┐ ┌──────────┐
 │Electro-   │ │Statistical│ │ Quantum  │
 │dynamics   │ │Physics   │ │Mechanics │
 │(Maxwell,  │ │(Boltzmann│ │(Schrödinger│
 │ 辐射)     │ │ → 相变)  │ │ → 微扰论)│
 └─────┬─────┘ └────┬────┘ └────┬─────┘
       │            │            │
       └──────┬─────┘            │
              ▼                  ▼
        ┌───────────┐   ┌──────────────┐
        │ Atomic    │   │ Quantum      │
        │ Physics   │   │ Information  │
        │(精细/超精 │   │(纠缠、von    │
        │ 细/塞曼)  │   │ Neumann 熵)  │
        └───────────┘   └──────────────┘
```

---

## 三、创建时间线 Timeline

> 按笔记创建时间排列，用于复习回顾。越新的笔记排在越前面。

| 创建日期 | 笔记 | 学科 | 状态 | 理解 | 复习 |
|---------|------|------|------|------|------|
| 2026-06-05 | [[Good-Quantum-Number\|好量子数]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[AC-Stark-Effect\|AC Stark 效应]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Alkali-Metal-Doublet\|碱金属双线结构]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Angular-Momentum-Coupling\|角动量耦合]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Doppler-Cooling\|Doppler 冷却]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Electron-Spin\|电子自旋]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Lande-g-Factor\|朗德 g 因子]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Lamb-Shift\|兰姆移位]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Optical-Tweezers\|光镊]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Perturbation-Theory\|微扰论]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Rydberg-Atom\|Rydberg 原子]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Selection-Rules\|选择定则]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Stern-Gerlach-Experiment\|施特恩-格拉赫实验]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-04 | [[Van-der-Waals-Interaction\|van der Waals 相互作用]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-03 | [[Fine-Structure\|精细结构]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-03 | [[Force-on-Magnetic-Dipole-in-Gradient-Field\|磁矩在梯度磁场中的受力]] | Physics | WIP | getting there | ⬜ 7天后 |
| 2026-06-03 | [[Spin-Orbit-Coupling\|自旋-轨道耦合]] | Physics | Draft | don't understand | ⬜ 7天后 |
| 2026-06-03 | [[Zeeman-Effect\|塞曼效应]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-02 | [[Commutation-Relation\|对易关系]] | Physics | WIP | vague | ⬜ 14天后 |
| 2026-06-02 | [[Hyperfine-Structure\|超精细结构]] | Physics | Evergreen | getting there | ⬜ 14天后 |
| 2026-06-01 | [[Unitary-Matrix\|酉矩阵]] | Math | WIP | understood | ✅ 已掌握 |
| 2026-05-27 | [[Hydrogen-Atom-Model\|氢原子模型]] | Physics | WIP | getting there | ⬜ 30天后 |
| 2026-05-27 | [[Larmor-Precession\|拉莫尔进动]] | Physics | WIP | getting there | ⬜ 30天后 |
| 2026-05-27 | [[Magnetic-Moment\|磁矩]] | Physics | WIP | getting there | ⬜ 30天后 |
| 2026-05-27 | [[Torque\|力矩]] | Physics | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Azimuthal-Quantum-Number\|角量子数]] | Physics | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Gaussian-Integral\|高斯积分]] | Math | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Ising-Model\|伊辛模型]] | Physics | Evergreen | getting there | ⬜ 30天后 |
| 2026-05-25 | [[Magnetic-Quantum-Number\|磁量子数]] | Physics | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Method-of-Separation-of-Variables\|分离变量法]] | Math | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Principal-Quantum-Number\|主量子数]] | Physics | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Quantum-Numbers\|量子数]] | Physics | WIP | understood | ✅ 已掌握 |
| 2026-05-25 | [[Spontaneous-Symmetry-Breaking\|自发对称破缺]] | Physics | Evergreen | getting there | ⬜ 30天后 |
| 2026-05-18 | [[Bose-Einstein-Distribution\|玻色-爱因斯坦分布]] | Physics | Evergreen | getting there | ⬜ 90天后 |

---

## 📝 更新记录

- 2026-06-05: 同步 roadmap — 新增 [[Good-Quantum-Number|好量子数]] 未勾选学习项；新增 1 条待解决学习疑问（好量子数对易子推导）；时间线新增 1 条。
- 2026-06-05: 新增"学习疑问"追踪区 — 添加 2 条待解决疑问（角动量耦合取值规则 + 朗德 g 因子推导）；在 [[Spin-Orbit-Coupling|自旋-轨道耦合]] 和 [[Lande-g-Factor|朗德 g 因子]] 笔记中标注 `[!question]` callout
- 2026-06-05: 基于原子物理第四章材料升级 5 篇笔记——[[Hydrogen-Atom-Model|氢原子模型]]（薛定谔方程五步推导）、[[Angular-Momentum-Coupling|角动量耦合]]（p 轨道算例 + 态数守恒 + 量子矢量模型）、[[Commutation-Relation|对易关系]]（升降算符完整谱构造）、[[Spin-Orbit-Coupling|自旋-轨道耦合]]（视角切换 + 磁铁类比 + 2P 劈裂计算）、[[Magnetic-Moment|磁矩]]（均匀场中运动行为 + 电动机原理）；LaTeX 表格违规修复 7 个文件 10 处；skills 镜像同步
- 2026-06-04: 同步 roadmap — 新增 13 篇笔记收录、修正 6 条 wikilink、时间线更新 33 条（按创建时间排列）
- 2026-06-02: 表格转为交互式 checkbox 列表格式，支持 Obsidian 内直接点击切换状态
- 2026-06-02: 同步 roadmap — 新增 [[Commutation-Relation|对易关系]]（差异 A：笔记存在但未收录）
- 2026-06-03: 同步 roadmap — 状态字段 In-Progress → WIP（跟随 vault status 体系更新：Draft/WIP/Evergreen/Archive）
- 2026-06-03: 同步 roadmap — 更新 [[Hyperfine-Structure|超精细结构]] 描述补充 $^{87}$Rb 量子比特内容；笔记存在 ↔ 勾选状态解耦规则确立（用户手动控制勾选）
- 2026-06-03: 新增 [[Spin-Orbit-Coupling|自旋-轨道耦合]] 笔记，roadmap 补充 wikilink（笔记已创建但勾选由用户控制）
- 2026-06-03: 新增 [[Force-on-Magnetic-Dipole-in-Gradient-Field|磁矩在梯度磁场中的受力]] 笔记，roadmap 补充 wikilink（笔记已创建但勾选由用户控制）
- 2026-06-01: 创建全局学习路径，涵盖数学（微积分/线性代数/PDE）和物理（经典力学/电动力学/原子物理/统计物理/信息论）所有分支
