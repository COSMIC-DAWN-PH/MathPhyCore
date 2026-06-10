# MathPhysCore — 数理核心知识库

一个基于 **Obsidian** 构建的数学与物理核心知识点知识库，面向物理专业学生的学习与复习。

## 目录结构

```
MathPhysCore/
├── Knowledge Point/
│   ├── Math/        # 数学知识点（微积分、线性代数、PDE、数学物理方法等）
│   └── Physics/     # 物理知识点（量子力学、统计物理、电动力学、冷原子物理等）
├── tools/           # 笔记模板 + 可视化交互工具（HTML）
├── AGENTS.md        # AI 协作规范（格式、命名、链接规则）
└── .agents/         # Agent 记忆与自定义技能
```

## 知识点覆盖

**物理**（32+ 篇）：
- 量子力学：量子数、角动量耦合、微扰论、氢原子模型、简并度等
- 电磁学 / 原子物理：Larmor 进动、精细结构、超精细结构、Lamb 位移、Landé g 因子
- 统计物理：Bose-Einstein 分布、Ising 模型
- 冷原子 / AMO：AC Stark 效应、多普勒冷却、光镊

**数学**（3 篇，持续扩展中）：
- Gaussian 积分、分离变量法、酉矩阵

## 笔记规范

每篇笔记遵循统一格式：

- **YAML Frontmatter**：学科、子领域、来源、理解程度、状态、标签
- **物理/数学直觉优先**：先讲是什么、为什么，再推公式
- **完整推导**：每一步都有解释，不跳步
- **Wiki-link 双向链接**：知识点之间相互引用，形成知识网络
- **核心公式摘要表**：方便快速查阅
- **更新日志**：记录笔记的演变

理解程度（`comprehension`）分为四级：

| 等级 | 含义 |
|------|------|
| `don't understand` | 完全不懂，需要从头学习 |
| `vague` | 有模糊印象，无法独立阐述 |
| `getting there` | 理解核心思想，细节需加强 |
| `understood` | 可以独立、完整地讲解 |

> 详细规范见 [AGENTS.md](./AGENTS.md)。

## 交互工具

`tools/` 目录下包含用 HTML + JavaScript 实现的交互式可视化工具：

- **Quantum Numbers Interactive** — 量子数可视化
- **Larmor Precession Interactive** — Larmor 进动动画
- **Zeeman Double Precession** — Zeeman 效应双重进动
- **Hyperfine Coupling Interactive** — 超精细耦合交互演示

工具通过 iframe 嵌入对应笔记中，可在 Obsidian 内直接交互。

## 使用方式

1. 克隆仓库
   ```bash
   git clone https://github.com/COSMIC-DAWN-PH/MathPhyCore.git
   ```
2. 用 Obsidian 打开 `MathPhysCore` 文件夹作为 Vault
3. 安装推荐插件：**Execute Code**（用于运行笔记中的 Python 代码块生成图表）
4. 开始浏览知识点，通过双向链接自由探索知识网络

## AI 协作

本知识库支持 AI Agent 协助创建和升级知识点笔记。所有 AI 行为遵循 [AGENTS.md](./AGENTS.md) 中的规范，包括格式一致性、命名规则和编码安全。AI 不会修改用户的理解程度（`comprehension`）字段。

## License

本知识库内容仅供个人学习使用。
