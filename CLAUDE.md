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

### Naming & Syntax Rules

- **File names**: Always `English-Name.md` (Chinese aliases go in YAML `aliases` field)
- **Wiki-links**: `[[English-Name]]` or `[[English-Name|Chinese Display Name]]` — NEVER wrap in backticks (breaks Obsidian indexing)
- **Embeds**: `![[English-Name]]` for transclusion, `![[English-Name#Section]]` for partial embed
- **Block references**: `^block-id` at paragraph end, then `[[English-Name^block-id]]` to reference
- **LaTeX**: Inline `$...$`, block `$$...$$`. Never use `\begin{equation}`

### YAML Frontmatter (Required)

Every note must have:
```yaml
---
subject:
  - Math  # or Physics
topic:
  - Calculus  # sub-field
aliases:
  - Chinese Name
status: Draft  # Draft -> In-Progress -> Evergreen
date: YYYY-MM-DD
tags:
  - Tag1
  - Tag2
---
```

### Note Content Standards

1. **Physical/mathematical intuition first** — explain "what" and "why" before formulas
2. **Core formula table** at end: `## ...` with Symbol / Meaning / Formula columns
3. **Callout annotations**: `> [!tip]`, `> [!warning]`, `> [!info]`, `> [!danger]`, `> [!question]`, `> [!example]`
4. **Bidirectional linking**: Every new note must link to related existing notes AND be linked back from them
5. **Update log**: Append `## ...` section at end for significant changes

### Python Plotting

All charts use **Python + matplotlib** (no Mermaid). This vault supports CJK fonts:
```python
plt.rcParams['font.sans-serif'] = ['Microsoft YaHei', 'SimHei']
plt.rcParams['axes.unicode_minus'] = False
```
- Use `plt.tight_layout()` to avoid clipping
- Labels with math: raw string + `$...$` (e.g., `r'Energy $\varepsilon - \mu$'`)
- Plots should be self-explanatory (complete title, axis labels, legend)

### Interactive HTML Tools

Embed interactive tools in notes using iframe with absolute `file:///` URL (spaces encoded as `%20`):
```html
<iframe src="file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/example.html" width="100%" height="680"></iframe>
```

### Related Vault

The user also maintains a **Quantum Computing** research vault at `C:\Personal Profile\Profile\ScienceResearch\Quantum Computing\` focused on neutral-atom Rydberg platforms. Cross-vault references may be relevant for physics content.
