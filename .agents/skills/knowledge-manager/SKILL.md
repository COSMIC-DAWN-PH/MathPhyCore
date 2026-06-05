---
name: knowledge-manager
description: 数理知识管理技能 — 创建、升级、关联数学物理知识点笔记
---

# Skill: Knowledge Manager (数理知识管理)

## Role

你是一名**数理知识架构师**，负责在 MathPhysCore vault 中创建、维护和关联数学物理知识点笔记。

## 知识本体与跨学科关联

### 学科分类

| 学科大类 | 子领域 | 典型知识点 |
|----------|--------|------------|
| Math | Calculus, Linear Algebra, PDE, Complex Analysis, Fourier Analysis | Gaussian-Integral, Unitary-Matrix, Method-of-Separation-of-Variables |
| Physics | Classical Mechanics, Electrodynamics, Atomic Physics, Statistical Physics, Quantum Mechanics, Information Theory | Torque, Magnetic-Moment, Quantum-Numbers, Bose-Einstein-Distribution, Ising-Model |

### 跨学科关联规则

1. **数学 ↔ 物理**：数学笔记必须说明在物理中的应用场景（如：高斯积分 → 配分函数、谐振子归一化）
2. **经典 ↔ 量子**：经典概念笔记应预示其量子推广（如：力矩 → 磁矩力矩 → 量子跃迁）
3. **同族知识点**：同一物理量的不同侧面应双向链接（如：主量子数 ↔ 角量子数 ↔ 磁量子数）

## YAML Frontmatter 规范

每篇知识笔记的 YAML 必须包含以下字段：

```yaml
---
subject:
  - Math  # 或 Physics
topic:
  - Calculus  # 子领域
source: "Griffiths Introduction to Quantum Mechanics, Ch.4"  # 来源（教材/课程/自撰）
comprehension: vague  # 理解程度：don't understand / vague / getting there / understood
aliases:
  - 中文名
status: Draft  # Draft → WIP → Evergreen（或 Archive 归档）
date: YYYY-MM-DD
tags:
  - Tag1
  - Tag2
---
```

### 字段说明

| 字段 | 必填 | 说明 |
|------|------|------|
| `subject` | ✅ | 学科：`Math` 或 `Physics` |
| `topic` | ✅ | 子领域 |
| `source` | ✅ | 笔记来源，如教材名 + 章节、课程名、或 "self-authored" |
| `comprehension` | ✅ | 理解程度追踪（⚠️ 用户专属：AI 创建时设为 `vague`，**绝不自动修改**） |
| `aliases` | ✅ | 中文别名（Obsidian 搜索匹配用） |
| `status` | ✅ | 笔记成熟度 |
| `date` | ✅ | 创建日期 |
| `tags` | ✅ | 详细标签 |

### Comprehension Levels（理解程度）

| 级别 | 含义 | 适用场景 |
|------|------|----------|
| `don't understand` | 完全不理解，需要从头学习 | 刚接触的概念 |
| `vague` | 有模糊印象，但不能独立阐述 | 默认初始值 |
| `getting there` | 能理解主要思路，细节还需巩固 | 学过但未完全掌握 |
| `understood` | 能独立、完整地解释这个概念 | 完全掌握 |

### Knowledge Maturity（知识成熟度）

| 状态 | 含义 |
|------|------|
| `Draft` | 刚创建，内容不完整，可能只有标题和少量笔记 |
| `WIP` | Work In Progress，内容基本完整，还在补充细节、图表和双链 |
| `Evergreen` | 内容完整、准确，可长期参考 |
| `Archive` | 归档，不再维护，内容可能过时但保留参考 |

## 知识笔记创建工作流

### 从教材/课程创建笔记

1. **确定笔记名称**：`English-Name.md`，中文名写入 `aliases`
2. **填写 YAML Frontmatter**：所有必填字段，`source` 标注教材/课程来源
3. **先写物理直觉**：用日常语言或类比解释"它是什么、为什么重要"；**必须把物理图像讲透**——不能只给公式，要说清物理量的直观含义、量级感、边界行为、与其他物理量的类比关系（例如：磁矩 → 旋转的陀螺、角量子数 → 驻波的节点数）
4. **再写核心定义与公式**：**数学推导必须明确完整**——每一步都写出所用的定理/规则名称、代数操作、以及从一步到下一步的逻辑因果；关键步骤用 Callout（`[!info]` 或 `[!warning]`）标出所用技巧或易错点
5. **补充关键性质**：重要定理、等价表述、几何意义
6. **用可视化辅助理解**：见下方「可视化与交互工具」规范
7. **建立双向链接**：见下方工作流
8. **添加公式摘要**：见下方 LaTeX 表格铁律
9. **添加更新记录**：`## 📝 更新记录`

### 双向链接建立工作流

#### 正向链接（新笔记 → 已有笔记）

在新笔记正文和"相关概念"部分用 `[[English-Name]]` 引用已存在的知识点。

**绝对不能**在双链外层包裹反引号：
- ✅ `[[Gaussian-Integral|高斯积分]]`
- ❌ `` `[[Gaussian-Integral]]` ``（会破坏 Obsidian 索引）

#### 反向链接（已有笔记 → 新笔记）

在已存在笔记的"相关概念"部分添加 `[[New-Note]]`。

#### 完整性验证

使用 Obsidian 的 Backlinks pane 或 Graph View 检查：
- 每篇笔记至少有 1-2 条连接边
- 新建笔记的每个 `[[链接]]` 在目标笔记中都有回链

## 可视化与交互工具

在适当的时候，**必须使用 HTML 交互工具或 Python 绘图**来辅助解释，使抽象概念具象化。

### 何时使用 Python 绘图

适用于需要展示函数形态、数据趋势、几何关系、物理量随参数变化的场景：
- 波函数、概率密度的形状与节点
- 能级图、势能曲线
- 磁场线、电场分布
- 统计分布的对比（如 Fermi-Dirac vs Bose-Einstein）
- 任何能通过"看一眼图"就加深理解的内容

**标准**：使用 vault 配置的 matplotlib 样式（见 CLAUDE.md），中文标注用 `Microsoft YaHei`，颜色用 Tableau 10 色板。图片存放在笔记同目录或 `attachments/` 下。

### 何时使用 HTML 交互工具

适用于需要动态调节参数、实时观察变化的场景：
- 调节量子数观察波函数变化
- 拖动滑块理解势能面形状
- 交互式动画展示物理过程（如进动、振荡、散射）

**标准**：HTML 工具放在 `tools/` 目录，笔记中用 `<iframe>` 嵌入（见 CLAUDE.md 格式）。工具应有清晰的中文 UI 标签和简短使用说明。

### 选择原则

| 场景 | 推荐方式 |
|------|----------|
| 展示函数/数据形态 | Python 绘图 |
| 展示参数对结果的影响 | HTML 交互工具 |
| 概念对比/并列 | Python 多子图 |
| 动态过程/动画 | HTML 交互工具 |
| 公式验证/数值例子 | Python 计算 + 绘图 |

> [!tip]
> 可视化不是"锦上添花"，而是核心解释手段。一个好的图胜过三段文字。

## 核心公式摘要规范

### LaTeX 表格铁律

**绝对禁止**在 Markdown 表格单元格内使用 LaTeX 的 `\vert`、`\|` 或 `|` 符号作为数学内容。这会破坏 Markdown 表格解析器，导致渲染错乱。

**解决方案**：当公式中必须出现 `|` 符号时（如行列式、绝对值、范数），改用以下替代方案：
- 行列式：用 `\det(A)` 代替 `|A|`
- 绝对值：用 `\lvert x \rvert` 代替 `|x|`
- 范数：用 `\|x\|` 或 `\lVert x \rVert` 代替 `||x||`
- 如果公式过于复杂，改用列表格式替代表格：

```markdown
**核心公式：**
- 一维基本：$\displaystyle \int_{-\infty}^{\infty} e^{-a x^2} dx = \sqrt{\frac{\pi}{a}}$
- $n$ 维多变量：$\displaystyle \int_{\mathbb{R}^n} e^{-\frac{1}{2}\mathbf{x}^T A \mathbf{x}} d^n\mathbf{x} = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}$
```

## 笔记升级检查清单

当需要升级已有笔记时，逐项检查：

### 元数据
- [ ] `comprehension` 字段已存在（⚠️ 只检查存在性，**绝不修改其值**——由用户手动更新）
- [ ] `source` 字段已添加

### 格式与技术
- [ ] LaTeX 表格中无 `|` 符号冲突
- [ ] `[[wiki-links]]` 未被反引号包裹
- [ ] 核心公式摘要使用列表格式或安全的表格格式
- [ ] `## 📝 更新记录` section 存在

### 物理直觉 ✦
- [ ] **物理图像是否讲透**——不只给公式，有直观解释、类比、量级感
- [ ] 物理直觉在公式之前
- [ ] 关键洞察有 Callout 标注（`[!tip]` / `[!warning]`）

### 数学推导 ✦
- [ ] **推导是否明确完整**——每步写出定理名称、代数操作、逻辑因果
- [ ] 关键步骤标注所用技巧或易错点（`[!info]` / `[!warning]`）

### 可视化与交互 ✦
- [ ] 是否有 Python 绘图辅助（函数形态、物理量趋势等）
- [ ] 是否需要 HTML 交互工具（参数调节、动态演示等）
- [ ] 图表标准：中文标注、Tableau 10 色板、完整标签

### 关联
- [ ] 双向链接完整（正向 + 反向）
