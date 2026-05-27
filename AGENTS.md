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
| `tools/` | 模板文件 |

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

## Obsidian Callouts（标注框）

用 `> [!类型]` 创建醒目的标注框：

```
> [!note] 标题
> 内容

> [!warning]
> 不需要标题也可以

> [!tip] 记忆技巧
> 用某种类比来记住这个公式

> [!danger] 常见错误
> 容易把符号弄反

> [!info]
> 补充背景信息
```

**常用类型：** `note` `info` `tip` `warning` `danger` `question` `example` `quote`

在本 vault 中的推荐用法：

| Callout 类型 | 使用场景 |
|-------------|---------|
| `[!info]` | 补充背景知识 |
| `[!tip]` | 记忆技巧、物理类比 |
| `[!warning]` | 易错点、边界条件 |
| `[!danger]` | 常见的严重错误 |
| `[!question]` | 值得深入思考的问题 |
| `[!example]` | 典型应用实例 |

## YAML Frontmatter / Obsidian Properties

每篇笔记必须包含 YAML 头部（Obsidian 中称为 Properties）：

```yaml
---
subject:
  - Math         # 或 Physics
topic:
  - Calculus      # 子领域
aliases:
  - 别名1
  - Alias2
status: Draft     # Draft → In-Progress → Evergreen
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
| `aliases` | ✅ | 别名（Obsidian 搜索时能匹配到这些词） |
| `status` | ✅ | `Draft` → `In-Progress` → `Evergreen` |
| `date` | ✅ | 创建日期 `YYYY-MM-DD` |
| `tags` | ✅ | 详细标签，Obsidian 的 tag pane 会用 |

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

1. **物理直觉优先** — 先讲核心物理/数学图像，再给公式
2. **公式用 KaTeX** — `$...$` 行内，`$$...$$` 行间（不用 `\begin{equation}`）
3. **双链交叉引用** — `[[English-Name]]` 关联其他知识点（注意：**绝对不能**在双链外包围反引号 `` ` ``，以免破坏 Obsidian 的双链索引机制）
4. **Callout 标注** — 用 `> [!tip]` 等做重点标注
5. **核心公式表** — 结尾用 `## 📐 核心公式摘要` 总结关键公式
6. **层级结构** — `#` → `##` → `###`，不要跳级


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
plt.plot(x, y)
plt.xlabel('$x$')
plt.ylabel('$y$')
plt.title('示例')
plt.grid(alpha=0.3)
plt.tight_layout()
plt.show()
```

**注意事项：**
- 含数学公式的标签用 raw string + `$...$` 包裹（如 `r'能量差 $\varepsilon - \mu$'`）
- 中文字体优先 `Microsoft YaHei`（Win11 自带）
- 用 `plt.tight_layout()` 避免裁切
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

## 知识点成熟度

| 状态 | 含义 |
|------|------|
| `Draft` | 刚创建，内容不完整，可能只有标题和少量笔记 |
| `In-Progress` | 内容基本完整，还在补充细节和双链 |
| `Evergreen` | 内容完整、准确，可长期参考 |

## 更新记录

- 每次修改笔记后，如果内容有较大变动，在文件末尾追加 `## 📝 更新记录`
- 格式：`YYYY-MM-DD: [改动说明]`

## Obsidian 交互式 HTML / iframe

当需要在笔记中嵌入动态、可交互的物理图像时，可以在 `tools/` 下创建独立 HTML 文件，并用 `<iframe>` 嵌入笔记。

重要经验：

- iframe 的 `src` 不要优先使用相对路径，例如 `../../tools/example.html`，因为 Obsidian 的 HTML iframe 路径解析不一定按当前笔记文件位置处理。
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
