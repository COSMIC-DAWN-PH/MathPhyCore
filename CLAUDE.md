# MathPhysCore Knowledge Vault — Claude Guidelines

> This is an **Obsidian markdown vault** for math and physics core knowledge points.
> **ALWAYS read `AGENTS.md` before performing any work in this vault** — it contains the complete specification for all formatting, naming, linking, and workflow rules.

## Quick Reference

### Vault Structure

| Folder | Purpose |
|--------|---------|
| `Knowledge Point/Math/` | Math knowledge points (calculus, linear algebra, PDE, mathematical physics methods) |
| `Knowledge Point/Physics/` | Physics knowledge points (quantum mechanics, statistical physics, electrodynamics) |
| `tools/` | Templates (`Knowledge-Note-Template.md`) and interactive HTML tools |
| `.agents/memory/` | Agent memory (user profile, session state) |
| `.agents/skills/` | Custom skills (knowledge-manager, vault-upgrade, roadmap-update) |

### Naming & Syntax Rules

- **File names**: Always `English-Name.md` (Chinese aliases go in YAML `aliases` field)
- **Wiki-links**: `[[English-Name]]` or `[[English-Name|Chinese Display Name]]` — NEVER wrap in backticks (breaks Obsidian indexing)
- **Embeds**: `![[English-Name]]` for transclusion, `![[English-Name#Section]]` for partial embed
- **Block references**: `^block-id` at paragraph end, then `[[English-Name^block-id]]` to reference
- **LaTeX**: Inline `$...$`, block `$$...$$`. Never use `\begin{equation}`

#### LaTeX Table Iron Rule

**ABSOLUTELY FORBIDDEN**: Using LaTeX `|`, `\|`, `\vert`, or `\lvert\rvert` inside Markdown table cells. This breaks the Markdown table parser.

**Solutions when formulas contain `|` symbols**:
- Determinants: use `\det(A)` instead of `|A|`
- Absolute value: use `\lvert x \rvert` instead of `|x|`
- Norms: use `\lVert x \rVert` instead of `||x||`
- If formula is too complex, **convert the table to a bullet list**:

```markdown
**Core formulas:**
- Basic 1D: $\displaystyle \int_{-\infty}^{\infty} e^{-a x^2} dx = \sqrt{\frac{\pi}{a}}$
- $n$-dimensional: $\displaystyle \int_{\mathbb{R}^n} e^{-\frac{1}{2}\mathbf{x}^T A \mathbf{x}} d^n\mathbf{x} = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}$
```

### YAML Frontmatter (Required)

Every note must have:
```yaml
---
subject:
  - Math  # or Physics
topic:
  - Calculus  # sub-field
source: "Griffiths QM, Ch.4"  # textbook/course/self-authored
comprehension: vague  # don't understand / vague / getting there / understood
aliases:
  - Chinese Name
status: Draft  # Draft -> WIP -> Evergreen (or Archive)
date: YYYY-MM-DD
tags:
  - Tag1
  - Tag2
---
```

| Field | Required | Description |
|-------|----------|-------------|
| `subject` | ✅ | Discipline: `Math` or `Physics` |
| `topic` | ✅ | Sub-field |
| `source` | ✅ | Origin: textbook + chapter, course name, or "self-authored" |
| `comprehension` | ✅ | Understanding level tracking |
| `aliases` | ✅ | Chinese aliases for Obsidian search |
| `status` | ✅ | Note maturity |
| `date` | ✅ | Creation date `YYYY-MM-DD` |
| `tags` | ✅ | Detailed tags |

### Comprehension Levels

| Level | Meaning |
|-------|---------|
| `don't understand` | No understanding, need to learn from scratch |
| `vague` | Fuzzy impression, cannot explain independently |
| `getting there` | Understand main ideas, details need reinforcement |
| `understood` | Can explain the concept independently and completely |

> [!danger] comprehension 字段：用户专属！
> `comprehension` 值 **只能由用户（Sihao）手动修改**。AI 助理在创建或升级笔记时，**绝对禁止**自动修改 `comprehension` 的值——即使 AI 认为用户的理解程度应该变化。理解程度是用户对自己学习状态的主观判断，AI 无权代替。AI 创建新笔记时，`comprehension` 必须设为默认值 `vague`，之后由用户自行更新。

### Knowledge Maturity

| Status | Meaning |
|--------|---------|
| `Draft` | Just created, incomplete, may only have title and notes |
| `WIP` | Work In Progress — mostly complete, still adding details, charts, and links |
| `Evergreen` | Content complete, accurate, long-term reference |
| `Archive` | No longer maintained, possibly outdated, kept for reference |

### Note Content Standards

1. **Physical/mathematical intuition first** — explain "what" and "why" before formulas
2. **Complete derivations** — every step explained, no skipped reasoning
3. **Self-contained** — notes should be independently understandable
4. **Connected to applications** — each concept linked to its use in physics
5. **Visual aids** — key processes, comparisons, trends visualized with Python matplotlib
6. **Core formula table** at end: `## 📐 核心公式摘要` with Symbol / Meaning / Formula columns
7. **Callout annotations**: `> [!tip]`, `> [!warning]`, `> [!info]`, `> [!danger]`, `> [!question]`, `> [!example]`
8. **Bidirectional linking**: Every new note must link to related existing notes AND be linked back from them
9. **Update log**: Append `## 📝 更新记录` section at end for significant changes

### Obsidian Callouts Reference

| Type | Usage in this vault | Example |
|------|---------------------|---------|
| `[!tip]` | Physical intuition, core analogies, memory tricks | `> [!tip] 拉莫尔进动像陀螺的轴绕竖直方向转圈` |
| `[!warning]` | Common mistakes, boundary conditions, misconceptions | `> [!warning] 不要忘记 Jacobian $r$！` |
| `[!info]` | Background knowledge, prerequisite review | `> [!info] 历史注记：最早由 de Moivre (1733) 遇到` |
| `[!danger]` | Serious common errors | `> [!danger] $U = e^{iH}$ 而不是 $U = e^{H}$` |
| `[!question]` | Questions worth deep thinking | `> [!question] 为什么能量只依赖 $n$？` |
| `[!example]` | Typical applications, numerical examples | `> [!example] $E_1=-13.6$ eV, $E_2=-3.40$ eV` |

### Update Log Format

```markdown
## 📝 更新记录

- YYYY-MM-DD: [description of change]
- YYYY-MM-DD: [description of change]
```

Append at end of file for significant changes.

### Python Plotting

All charts use **Python + matplotlib** (no Mermaid). This vault supports CJK fonts:
```python
plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False
```

**Professional plot standards:**
- Use `plt.tight_layout()` to avoid clipping
- Use `plt.grid(alpha=0.3, ls=':')` for subtle grid
- Use `plt.legend(frameon=False)` for frameless legends
- Labels with math: raw string + `$...$` (e.g., `r'Energy $\varepsilon - \mu$'`)
- Plots should be self-explanatory (complete title, axis labels, legend)

**Professional color palette (Tableau 10):**
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

**3D plot Obsidian compatibility:**
```python
plt.tight_layout()
# Obsidian Execute Code may append an empty plt.plot() after this block.
# Keep a transparent 2D axes current so that appended call does not hit Axes3D.plot().
compat_ax = fig.add_axes([0, 0, 1, 1], frameon=False)
compat_ax.set_axis_off()
plt.show()
```


### Encoding Safety / Mojibake Prevention

Critical project rule:

- Do not write Chinese/CJK text by embedding it directly inside PowerShell here-strings or shell command payloads; this can silently turn non-ASCII text into `?`.
- For CJK Markdown/HTML/JS writes, use Python Unicode escapes, base64-decoded UTF-8 payloads, or transform existing UTF-8 text read from disk.
- If CJK UI labels are not essential in `tools/*.html`, prefer ASCII/English labels.
- Standalone HTML tools must include `<meta charset="utf-8">`.
- After writing, re-read the edited region with UTF-8 and check for three consecutive question marks, long unexpected `?` runs, and `U+FFFD` replacement characters.
- For HTML with JavaScript, run `node --check` on extracted scripts when possible.

Use `.agents/skills/encoding-safety/SKILL.md` for the detailed workflow whenever editing Markdown/HTML that may contain CJK text.

### Interactive HTML Tools

Embed interactive tools in notes using iframe with absolute `file:///` URL (spaces encoded as `%20`):
```html
<iframe src="file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/example.html" width="100%" height="680" style="border:1px solid #d8dee9; border-radius:6px;"></iframe>
```

### Available Skills

| Skill | Trigger | Description |
|-------|---------|-------------|
| **knowledge-manager** | Creating/upgrading knowledge notes | 数理知识架构师 — frontmatter, bidirectional links, formula tables, comprehension tracking |
| **roadmap-update** | "更新学习路径", "同步 roadmap" | 根据笔记 YAML frontmatter 和内容相关性自动同步 Study-Roadmap.md |
| **vault-upgrade** | "升级这个库", "apply new standards" | Vault-wide scan, upgrade, and verification workflow |
| **encoding-safety** | Markdown/HTML writes with Chinese/CJK text, iframe tools | Prevent mojibake; use safe UTF-8 write patterns and validation |

### Agent Memory & User Profile

Before generating any content, **read `.agents/memory/user_profile.json`** to understand the user's:
- Education level and major
- Math/physics background (completed vs. planned topics)
- Vault preferences (language style, matplotlib settings, callout preferences)

Adapt explanation depth to the user's knowledge boundary.

### Related Vault

The user also maintains a **Quantum Computing** research vault at `C:\Personal Profile\Profile\ScienceResearch\Quantum Computing\` focused on neutral-atom Rydberg platforms. Cross-vault references may be relevant for physics content.
