# MathPhysCore Vault — Agent Guidelines

## 这是什么

这是 Sihao 的**数理核心知识库**（Math & Physics Core Knowledge Vault），记录学过的数学和物理核心知识点。目标是形成一个可检索、可交叉引用的个人知识网络。

这是一个 **Obsidian markdown vault**，以下所有语法都是 Obsidian 原生支持的。

## Vault 结构

| 目录 | 用途 |
|------|------|
| `Knowledge Point/Math/` | 数学知识点（微积分、线性代数、概率统计、数学物理方法等） |
| `Knowledge Point/Physics/` | 物理知识点（量子力学、统计物理、电动力学、热力学等） |
| `Knowledge Point/Information Theory/` | 信息论知识点（熵、信道容量、编码定理等） |
| `tools/` | 模板文件（`Knowledge-Note-Template.md`）和交互式 HTML 工具 |
| `.agents/memory/` | 智能体记忆（用户画像、会话状态） |
| `.agents/skills/` | 自定义技能（knowledge-manager、vault-upgrade） |

## Obsidian 双链（Wiki-links）

Obsidian 的核心功能是用 `[[文件名]]` 在笔记之间建立双向链接。

### 基本双链

```
[[English-Name]]
```

- 链接到同 vault 内的另一篇笔记（按文件名匹配）
- 文件名不写 `.md` 后缀

### 带显示文本

```
[[English-Name|显示文本]]
```

示例：`[[Gaussian-Integral|高斯积分]]` → 在正文中只显示"高斯积分"四个字

### 嵌入笔记（Transclusion）`![[ ]]`

```
![[English-Name]]
```

- 将另一篇笔记的内容**直接嵌入**到当前笔记中渲染
- 常用于在总览笔记中引入多个子概念的完整内容
- 也可以只嵌入某个段落：`![[English-Name#段落标题]]`
- 或嵌入特定块：`![[English-Name^块ID]]`

### 嵌入块（Block Reference）`^块ID`

在段落末尾加 `^my-block-id` 标记块，然后通过 `[[English-Name^my-block-id]]` 引用：

```markdown
这是需要被引用的段落 ^definition-1
```

然后在另一篇笔记：`[[Bose-Einstein-Distribution^definition-1]]`

## 双链策略

每次创建或更新笔记时，必须建立**双向链接**：

1. **新笔记 → 已有笔记**：在新笔记正文中用 `[[English-Name]]` 引用相关知识点（注意：**绝对不能**在双链外层包裹反引号 `` ` ``，否则 Obsidian 会将其渲染为行内代码从而使双链失效）
2. **已有笔记 → 新笔记**：在已有笔记末尾的"相关概念"部分添加 `[[English-Name]]`（同样**不能**包裹反引号）


长期目标：graph view 中每篇笔记至少有 1-2 条连接边。

## LaTeX 表格铁律

**绝对禁止**在 Markdown 表格单元格内使用 LaTeX 的 `\vert`、`\|` 或 `|` 符号作为数学内容。这会破坏 Markdown 表格解析器，导致渲染错乱。

**解决方案**：

| 情况 | 错误写法 | 正确写法 |
|------|----------|----------|
| 行列式 | `\|A\|` | `\det(A)` |
| 绝对值 | `\|x\|` | `\lvert x \rvert` |
| 范数 | `\|\|x\|\|` | `\lVert x \rVert` |
| 复杂公式 | 表格中塞入长公式 | **改用列表格式** |

改用列表格式的示例：
```markdown
**核心公式：**
- 一维基本：$\displaystyle \int_{-\infty}^{\infty} e^{-a x^2} dx = \sqrt{\frac{\pi}{a}}$
- $n$ 维多变量：$\displaystyle \int_{\mathbb{R}^n} e^{-\frac{1}{2}\mathbf{x}^T A \mathbf{x}} d^n\mathbf{x} = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}$
```

## Obsidian Callouts（标注框）

用 `> [!类型]` 创建醒目的标注框：

```markdown
> [!tip] 物理直觉
> 高斯积分无处不在，因为凡是出现 $e^{-x^2}$ 的地方几乎必然涉及归一化、概率或热力学权重。

> [!warning] 常见错误
> 不要忘记 Jacobian $r$！极坐标变换必须包含 $r\,dr\,d\theta$。

> [!info] 补充背景
> 这个概念的前置知识是 [[Method-of-Separation-of-Variables|分离变量法]]。

> [!danger] 严重错误
> $U = e^{iH}$ 而不是 $U = e^{H}$。必须加 $i$ 因子。

> [!question] 思考
> 为什么氢原子的能量只依赖主量子数 $n$？

> [!example] 数值例子
> $E_1 = -13.6\ \mathrm{eV}$，$E_2 = -3.40\ \mathrm{eV}$
```

**常用类型：** `note` `info` `tip` `warning` `danger` `question` `example` `quote`

在本 vault 中的推荐用法：

| Callout 类型 | 使用场景 |
|-------------|---------|
| `[!tip]` | 物理直觉、核心类比、记忆技巧 |
| `[!warning]` | 易错点、边界条件、常见误解 |
| `[!info]` | 补充背景知识、前置知识回顾 |
| `[!danger]` | 严重的常见错误 |
| `[!question]` | 值得深入思考的问题 |
| `[!example]` | 典型应用实例、数值计算 |

## YAML Frontmatter / Obsidian Properties

每篇笔记必须包含 YAML 头部（Obsidian 中称为 Properties）：

```yaml
---
subject:
  - Math         # 或 Physics
topic:
  - Calculus      # 子领域
source: "Griffiths QM, Ch.4"  # 来源（教材/课程/self-authored）
comprehension: vague  # 理解程度：don't understand / vague / getting there / understood
aliases:
  - 别名1
  - Alias2
status: Draft     # Draft → WIP → Evergreen（或 Archive 归档）
date: 2026-05-19
tags:
  - Math
  - Integration
---
```

各字段说明：

| 字段 | 必填 | 说明 |
|------|------|------|
| `subject` | ✅ | 学科：`Math` 或 `Physics`（数组） |
| `topic` | ✅ | 子领域，如 `Calculus`, `Linear Algebra`, `Quantum Mechanics` |
| `source` | ✅ | 笔记来源，如教材名 + 章节、课程名、或 "self-authored" |
| `comprehension` | ✅ | 理解程度追踪 |
| `aliases` | ✅ | 别名（Obsidian 搜索时能匹配到这些词） |
| `status` | ✅ | `Draft` → `WIP` → `Evergreen`（或 `Archive` 归档） |
| `date` | ✅ | 创建日期 `YYYY-MM-DD` |
| `tags` | ✅ | 详细标签，Obsidian 的 tag pane 会用 |

## 理解程度（Comprehension）

| 级别 | 含义 |
|------|------|
| `don't understand` | 完全不理解，需要从头学习 |
| `vague` | 有模糊印象，但不能独立阐述 |
| `getting there` | 能理解主要思路，细节还需巩固 |
| `understood` | 能独立、完整地解释这个概念 |

> [!danger] comprehension 字段：用户专属！
> `comprehension` 值 **只能由用户（Sihao）手动修改**。AI 助理在创建或升级笔记时，**绝对禁止**自动修改 `comprehension` 的值——即使 AI 认为用户的理解程度应该变化。理解程度是用户对自己学习状态的主观判断，AI 无权代替。AI 创建新笔记时，`comprehension` 必须设为默认值 `vague`，之后由用户自行更新。

## 文件命名规则（必须遵守）

格式：**纯英文** `English-Name.md`

- 只使用英文（字母、数字、连字符、空格）
- 中文别名写在 YAML frontmatter 的 `aliases` 字段中
- 避免特殊字符（`/ \ : * ? " < > |`）

| ✅ 正确 | ❌ 错误 |
|---------|--------|
| `Gaussian-Integral.md` | `高斯积分.md` |
| `Method-of-Separation-of-Variables.md` | `分离变量法 (Method).md` |
| `Fourier-Transform.md` | `Fourier变换.md` |

## 笔记内容规范

1. **物理直觉优先** — 先讲核心物理/数学图像，再给公式。用 Callout 标注核心洞察
2. **公式用 KaTeX** — `$...$` 行内，`$$...$$` 行间（不用 `\begin{equation}`）
3. **双链交叉引用** — `[[English-Name]]` 关联其他知识点（注意：**绝对不能**在双链外包围反引号 `` ` ``，以免破坏 Obsidian 的双链索引机制）
4. **Callout 标注** — 用 `> [!tip]` 等做重点标注
5. **核心公式表** — 结尾用 `## 📐 核心公式摘要` 总结关键公式（注意 LaTeX 表格铁律）
6. **层级结构** — `#` → `##` → `###`，不要跳级
7. **更新记录** — 文件末尾追加 `## 📝 更新记录`

### 可读性标准（Readability Standard）

**核心原则**：每篇知识笔记必须写到"看完就能懂"的水平。读者读完后应该能够清晰地说出"这个知识点在说什么"。

具体要求：
1. **物理图像先行**：每个概念先用日常直觉或类比解释"它是什么、为什么重要"，再进入数学。
2. **数学推导完整**：公式不能跳步。每一步推导都要说明"我在做什么、为什么可以这样做"。
3. **自包含可理解**：笔记内部应能独立理解，不依赖外部资料。
4. **联系实际**：每个概念都要说明"它在物理学中用在哪里"。
5. **图表辅助**：关键流程、对比、演化趋势用 Python matplotlib 图表可视化。

## 知识点成熟度

| 状态 | 含义 |
|------|------|
| `Draft` | 刚创建，内容不完整，可能只有标题和少量笔记 |
| `WIP` | Work In Progress，内容基本完整，还在补充细节、图表和双链 |
| `Evergreen` | 内容完整、准确，可长期参考 |
| `Archive` | 归档，不再维护，内容可能过时但保留参考 |

## Python 图表（替代 Mermaid）

所有图表统一用 **Python + matplotlib** 绘制，配合 Obsidian Execute Code 插件在笔记内实时渲染。

```python
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False

x = np.linspace(0, 10, 200)
y = np.sin(x)

plt.figure(figsize=(8, 4))
plt.plot(x, y, label=r'Sine Wave $y = \sin(x)$', color='#4C78A8')
plt.xlabel(r'Time $x$ (s)')
plt.ylabel(r'Amplitude $y$')
plt.title('Sine Wave Coherent Dynamics')
plt.grid(alpha=0.3, ls=':')
plt.legend(frameon=False)
plt.tight_layout()
plt.show()
```

**专业色板（Tableau 10）：**

```python
COLORS = {
    'blue':    '#4C78A8',
    'orange':  '#F58518',
    'green':   '#54A24B',
    'red':     '#E45756',
    'purple':  '#72B7B2',
    'brown':   '#EECA3B',
    'pink':    '#B279A2',
    'gray':    '#FF9DA6',
    'yellow':  '#9D755D',
    'cyan':    '#BAB0AC',
}
```

**注意事项（必须严格遵守）：**
- 含数学公式的标签用 raw string + `$...$` 包裹（如 `r'能量差 $\varepsilon - \mu$'`）
- 中文字体优先 `Microsoft YaHei`（Win11 自带）
- 用 `plt.tight_layout()` 避免裁切
- 用 `plt.grid(alpha=0.3, ls=':')` 添加柔和网格
- 用 `plt.legend(frameon=False)` 去掉图例边框
- Python 代码块必须做语法自检，尤其检查 raw string / f-string / rf-string 是否闭合。常见错误如 `rf'$n={ni}$` 少了末尾引号，必须写成 `rf'$n={ni}$'`。写入笔记前优先用目标 Python 解释器运行或至少用 `ast.parse` 检查代码块。
- 如果使用 3D matplotlib（`projection='3d'` / `Axes3D`），Obsidian Execute Code 可能会在代码块后自动追加空的 `plt.plot()`；必须在 `plt.show()` 前把当前轴切回透明 2D 轴，避免触发 `Axes3D.plot()` 缺少 `xs`、`ys` 参数的错误。推荐模板：

```python
plt.tight_layout()

# Obsidian Execute Code may append an empty plt.plot() after this block.
# Keep a transparent 2D axes current so that appended call does not hit Axes3D.plot().
compat_ax = fig.add_axes([0, 0, 1, 1], frameon=False)
compat_ax.set_axis_off()
plt.show()
```

- 图尽量能独立说明问题（标题、轴标签、图例完整）

> 本 vault **不再使用 Mermaid 图表**，所有曲线图/分布图/统计图均由 Python 生成。

## 更新记录

每次修改笔记后，如果内容有较大变动，在文件末尾追加 `## 📝 更新记录`：

```markdown
## 📝 更新记录

- 2026-06-01: 初始创建
- 2026-06-05: 添加 Python 图表
```

格式：`YYYY-MM-DD: [改动说明]`

## Custom Skills (on-demand, invoke via `/`)

| Skill | File | Trigger |
|---|---|---|
| **knowledge-manager** | `.agents/skills/knowledge-manager/SKILL.md` | 创建/升级知识点笔记：frontmatter 规范、双向链接、公式摘要、理解程度追踪 |
| **vault-upgrade** | `.agents/skills/vault-upgrade/SKILL.md` | "升级这个库"、"apply new standards"、"migrate to new format" |
| **encoding-safety** | `.agents/skills/encoding-safety/SKILL.md` | Prevent mojibake when writing Markdown/HTML with Chinese/CJK text; validate UTF-8 and iframe tools |

## 🧠 智能体长期记忆与用户画像 (Agent Memory & User Profile)

任何进入本笔记库的 AI 助理，**在生成任何物理推导、编写讲义或解释概念前，必须率先读取并在内存中加载** `.agents/memory/user_profile.json`。

AI 助理必须根据该画像中所记录的用户学业阶段与物理背景，动态调整所有技术内容的解释深度：
- **严格适配知识边界**：绝不引入超出用户当前学习进度的数学或物理大山。
- **语言与绘图风格偏好**：严格遵循用户在 `vault_preferences` 中设置的双语分工与 CJK matplotlib 绘图审美风格。

## Obsidian 交互式 HTML / iframe

当需要在笔记中嵌入动态、可交互的物理图像时，可以在 `tools/` 下创建独立 HTML 文件，并用 `<iframe>` 嵌入笔记。

重要经验：

- iframe 的 `src` 不要优先使用相对路径，因为 Obsidian 的 HTML iframe 路径解析不一定按当前笔记文件位置处理。
- 本地 HTML iframe 优先使用绝对 `file:///` URL。
- Windows 路径中的空格必须 URL 编码为 `%20`。
- 示例：

```html
<iframe src="file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/Quantum-Numbers-Interactive.html" width="100%" height="680" style="border:1px solid #d8dee9; border-radius:6px;"></iframe>
```

如果 iframe 仍不能渲染，优先检查：

1. Obsidian 插件是否允许 iframe / HTML / JavaScript。
2. `file:///` 路径是否真实存在。
3. 路径中的空格、中文或特殊字符是否已正确 URL 编码。
4. 如本地 file iframe 被限制，可改用本地 HTTP 服务，例如 `http://127.0.0.1:8765/tools/example.html`。

## Commands

- **Skills**: Type `/` in chat and select the skill name, or describe the task naturally
- **File creation**: Use `create_file` for new markdown notes; follow the YAML frontmatter and section conventions from existing notes


## Encoding Safety / Mojibake Prevention

Critical project rule for all agents working in this vault:

- Do not write Chinese/CJK text by embedding it directly inside PowerShell here-strings or shell command payloads. In this environment, that path can silently convert non-ASCII characters into `?`, causing mojibake in Markdown notes and HTML tools.
- For any Markdown/HTML/JS file that needs CJK text, use one of these safe patterns: Python Unicode escapes, base64-decoded UTF-8 payloads, or transform existing UTF-8 text read from disk.
- If CJK UI text is not essential in an interactive HTML tool, prefer ASCII/English labels to eliminate encoding risk.
- Standalone HTML tools must include `<meta charset="utf-8">`.
- After writing any file that may contain CJK text, re-read the edited region with UTF-8 and check for `three consecutive question marks`, unexpected long runs of `?`, and `U+FFFD` replacement characters before responding.
- For HTML containing JavaScript, extract scripts and run `node --check` when possible.

Project skill backup: `.agents/skills/encoding-safety/SKILL.md` contains the detailed workflow and must be used for future Markdown/HTML writes involving CJK text or iframe tools.
