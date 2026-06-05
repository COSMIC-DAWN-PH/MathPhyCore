---
name: roadmap-update
description: 学习路径同步技能 — 根据知识点笔记的 YAML frontmatter 和内容相关性，自动同步更新 Study-Roadmap.md
---

# Skill: Roadmap Update (学习路径同步)

## Role

你是一名**知识路径规划师**，负责保持 `Study-Roadmap.md` 与 vault 中实际存在的知识点笔记严格同步。你通过读取每篇笔记的 YAML frontmatter 和内容中的双向链接，检测差异并生成更新方案。

## 触发条件

- "更新学习路径"
- "同步 roadmap"
- "update study roadmap"
- "roadmap 同步"
- "检查学习路径是否最新"

---

## 数据模型

### Roadmap Checkbox 列表格式

```markdown
### 子领域名称

- [x] [[English-Name|中文名]] — 简要描述
- [ ] English-Name（中文名）— 简要描述
```

- **`[x]`**（已勾选）= 用户已学习该知识点（**用户手动控制，永不自动勾选**）
- **`[ ]`**（未勾选）= 用户尚未学习（即使笔记文件已存在）

> [!info] Obsidian 交互性
> 使用 `- [x]` / `- [ ]` 格式，用户可在 Obsidian 中直接点击复选框切换完成状态，无需手动编辑 markdown。

> [!danger] 勾选语义 — 关键规则
> **`[x]`/`[ ]` 只反映用户的学习状态，不代表笔记是否已创建。** 笔记是否存在由 wikilink 有无体现：
> - `- [x] [[Name|中文名]]` — 已学习 + 笔记已创建
> - `- [ ] [[Name|中文名]]` — 未学习，但笔记已创建（有 wikilink）
> - `- [ ] Name（中文名）` — 未学习，笔记尚未创建（无 wikilink）
> **NEVER auto-check `[ ]` → `[x]`。勾选操作完全由用户在 Obsidian 中手动完成。**

### 笔记 YAML Frontmatter 关键字段

```yaml
subject:
  - Physics      # 或 Math — 决定归属哪个大类
topic:
  - Quantum Mechanics  # 决定归属哪个子领域表格
comprehension: vague    # 理解程度
status: WIP     # 笔记成熟度：Draft / WIP / Evergreen / Archive
aliases:
  - 中文名              # 用于 roadmap 的中文标注
```

### 从 YAML 到 Roadmap 的映射

| YAML `subject` | Roadmap 大类 |
|----------------|-------------|
| `Math` | `## 一、数学 Math` |
| `Physics` | `## 二、物理 Physics` |

| YAML `topic` | Roadmap 子领域 |
|--------------|---------------|
| `Calculus` | `### 微积分 Calculus` |
| `Linear Algebra` | `### 线性代数 Linear Algebra` |
| `PDE` | `### 偏微分方程 PDE` |
| `Classical Mechanics` | `### 经典力学 Classical Mechanics` |
| `Electrodynamics` | `### 电动力学 Electrodynamics` |
| `Atomic Physics` / `Quantum Mechanics` | `### 原子与量子物理 Atomic & Quantum Physics` |
| `Statistical Physics` | `### 统计物理 Statistical Physics` |
| `Information Theory` | `### 信息论 Information Theory` |

> [!warning] 合并规则
> `Atomic Physics` 和 `Quantum Mechanics` 在 roadmap 中合并为同一个子领域表 `### 原子与量子物理 Atomic & Quantum Physics`。映射时两者都归入此表。

### Roadmap 时间线表格格式

在 Study-Roadmap.md 中，除了按学科分类的 checkbox 列表外，还需要维护一个**按创建时间排列的复习时间线**，方便用户按时间回顾。

```markdown
## 三、创建时间线 Timeline

> 按笔记创建时间排列，用于复习回顾。越新的笔记排在越前面。

| 创建日期 | 笔记 | 学科 | 状态 | 理解 | 复习 |
|---------|------|------|------|------|------|
| 2026-06-04 | [[Rydberg-Atom\|Rydberg 原子]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-03-29 | [[Larmor-Precession\|拉莫尔进动]] | Physics | WIP | getting there | ✅ 已复习 |
```

**表格列定义**：

| 列 | 来源 | 说明 |
|----|------|------|
| 创建日期 | YAML `date` 字段 | 笔记创建日期，`YYYY-MM-DD` |
| 笔记 | `[[English-Name\|中文名]]` | 带 wikilink 的笔记名 |
| 学科 | YAML `subject` | `Math` 或 `Physics` |
| 理解 | YAML `comprehension` | `don't understand` / `vague` / `getting there` / `understood` |
| 复习 | 自动计算 | 基于创建日期和当前日期，按艾宾浩斯遗忘曲线建议 |

**复习列的自动计算规则**：

| 条件 | 复习标记 |
|------|---------|
| 创建 ≤ 7 天 | `⬜ 7天后` |
| 创建 8–14 天 | `⬜ 14天后` |
| 创建 15–30 天 | `⬜ 30天后` |
| 创建 31–90 天 | `⬜ 90天后` |
| 创建 > 90 天 | `⬜ 已过期` |
| comprehension = `understood` | `✅ 已掌握` |

> [!danger] comprehension 只读规则
> roadmap-update skill 只**读取** `comprehension` 的值用于显示和计算复习标记，**绝不修改**它。comprehension 只能由用户（Sihao）手动在 Obsidian 中修改。

> [!info] 复习标记的用途
> 复习列是**建议性**的，帮助用户发现"该复习的旧笔记"。用户可在 Obsidian 中手动编辑此列来标记实际复习状态。

**排序规则**：
- 默认按创建日期**从新到旧**（最新的在最上面）
- 同一日期内，按文件名字母序排列
- 仅包含 `status` 不为 `Archive` 的笔记

---

## 工作流

### Phase 1: 扫描 — 构建笔记清单

1. 列出 `Knowledge Point/Math/` 和 `Knowledge Point/Physics/` 下所有 `.md` 文件
2. 读取每篇笔记的 YAML frontmatter，提取：
   - `subject` → 决定大类
   - `topic` → 决定子领域
   - `aliases[0]` → 中文名
   - `status` → 笔记成熟度
   - `comprehension` → 理解程度
   - `date` → 创建日期（用于时间线排序和复习建议）
3. 扫描笔记内容中的 `## 相关概念` 或类似 section，提取所有 `[[wiki-links]]`

输出：笔记清单表

```
| 文件名 | subject | topic | 中文名 | status | comprehension | date |
|--------|---------|-------|--------|--------|---------------|------|
```

### Phase 2: 对比 — 检测差异

将笔记清单与现有 roadmap 逐项对比，检测以下差异类型：

#### 差异 A：笔记已存在，roadmap 未收录

笔记文件存在于 vault 中，但 roadmap 中没有对应的行。

**操作**：在对应子领域中添加 `- [ ] [[Name|中文名]] — 描述`（不勾选，保留 wikilink）。勾选由用户手动控制。

#### 差异 B：笔记已存在但缺少 wikilink

roadmap 中标记为 `[ ]`（未勾选），且 vault 中已有对应文件，但 roadmap 行中缺少 wikilink。

**操作**：仅补全 wikilink `[[Name|中文名]]`，**不改变勾选状态**（`[ ]` 保持 `[ ]`）。勾选由用户手动控制。

#### 差异 C：roadmap 已勾选，但笔记文件不存在

roadmap 中有 `[x]` 行且带 wikilink，但目标文件已被删除或移动。

**操作**：将 `- [x]` 改为 `- [ ]`，移除 wikilink。报告给用户确认。

#### 差异 D：跨学科关联 — 笔记在其他子领域有强关联

扫描笔记内容中的 `[[wiki-links]]` 和 `## 相关概念` section，检测：
- 如果笔记 A 链接到笔记 B，且 A 和 B 属于**不同子领域**
- 则笔记 A 的知识点可能应在 B 的子领域中以 `参见` 行出现

**操作**：在关联子领域表中添加一行，使用格式：
```
| 📎 | [[English-Name\|中文名]] | （参见 {原属子领域}）|
```

> [!tip] 📎 标记
> 📎 表示"跨领域参见"，不是该子领域的核心知识点，而是有关联的内容。它帮助学习者发现跨学科联系。

#### 差异 E：YAML `topic` 值不在已知映射中

笔记的 `topic` 字段值无法映射到 roadmap 中现有的子领域。

**操作**：报告给用户，建议：
- 如果该 topic 有足够的笔记（≥ 2 篇），创建新子领域 section
- 否则，建议归入最接近的已有子领域

### Phase 3: 更新 — 执行 Roadmap 修改

按优先级顺序执行更新：

1. **差异 A**（新增行 + wikilink，`[ ]` 不勾选）：高优先级，补录缺失笔记
2. **差异 B**（补全 wikilink，不改变 `[ ]` 状态）：高优先级，确保链接完整
3. **差异 C**（`[x]` → `[ ]`，报告用户确认）：高优先级，修正失效链接
4. **差异 D**（📎 跨领域参见）：中优先级，添加关联行
5. **差异 E**（新子领域）：低优先级，需用户确认

> [!danger] 绝不自动勾选
> 差异 A 和差异 B 中，新增或补全的行一律使用 `[ ]`（不勾选）。只有用户在 Obsidian 中手动点击才能变为 `[x]`。

**更新时遵循的格式规则**：

- 已有笔记使用勾选 + wikilink：`- [x] [[English-Name|中文名]] — 描述`
- 待学笔记不勾选：`- [ ] English-Name（中文名）— 描述`
- 已有 wikilink 的待学笔记保留链接：`- [ ] [[English-Name|中文名]] — 描述`
- 跨领域参见使用 📎 标记：`- [ ] 📎 [[English-Name|中文名]] — （参见 XXX）`
- 描述取笔记中的一句话总结（通常是标题后的 blockquote），截取前 30 字，用 `—` 分隔
- 同一子领域内，`[x]` 行排在 `[ ]` 行前面
- 📎 行排在所有 `[x]` 和 `[ ]` 行之后

### Phase 4: 更新 — 维护时间线表格

在 `Study-Roadmap.md` 的 `## 三、创建时间线 Timeline` section 中：

1. **重建整张表格**：每次同步时，从所有笔记的 YAML `date` 字段重新生成时间线表格
2. **按日期降序排列**：最新创建的笔记排在最上面
3. **计算复习标记**：根据当前日期和笔记创建日期，按"复习列自动计算规则"填充复习列
4. **排除 Archive 笔记**：`status: Archive` 的笔记不列入时间线

生成示例：

```markdown
## 三、创建时间线 Timeline

> 按笔记创建时间排列，用于复习回顾。越新的笔记排在越前面。

| 创建日期 | 笔记 | 学科 | 状态 | 理解 | 复习 |
|---------|------|------|------|------|------|
| 2026-06-04 | [[Rydberg-Atom\|Rydberg 原子]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-06-03 | [[Fine-Structure\|精细结构]] | Physics | Draft | vague | ⬜ 7天后 |
| 2026-05-27 | [[Larmor-Precession\|拉莫尔进动]] | Physics | WIP | getting there | ⬜ 14天后 |
| 2026-03-29 | [[Gaussian-Integral\|高斯积分]] | Math | Evergreen | understood | ✅ 已掌握 |
```

> [!warning] 不要自动修改"复习"列的用户手动标记
> 如果用户已在表格中手动编辑了某行的复习列（如改为"✅ 已复习"），同步时保留用户的修改，不覆盖。只对**未被用户修改**的行（保持 `⬜ X天后` 格式的行）重新计算。

### Phase 5: 更新记录

在 `Study-Roadmap.md` 的 `## 📝 更新记录` section 追加：

```markdown
- YYYY-MM-DD: 同步 roadmap — 新增 X 篇、修正状态 X 篇、跨领域关联 X 条、时间线更新 X 条
```

### Phase 6: 验证

最终验证：

**学科分类部分**：
1. 所有 `- [x]` 行的 wikilink 目标文件存在
2. `- [ ]` 行仅在已有笔记文件时保留 wikilink
3. 同一笔记不出现在同一子领域的多行中（📎 行除外）
4. 每个子领域至少有 1 个 checkbox 项

**时间线部分**：
5. 时间线表格包含所有 `status` ≠ `Archive` 的笔记
6. 按创建日期降序排列（最新在最上面）
7. 复习列已正确计算（未被用户手动修改的行）
8. 用户手动编辑过的复习列标记未被覆盖

**通用**：
9. 更新记录已追加

---

## 用户画像联动

当 `.agents/memory/user_profile.json` 存在时：

1. **comprehension 同步**：如果 roadmap 中某知识点的笔记 comprehension 为 `understood`，在更新报告中标注"已掌握"
2. **学习建议**：根据 roadmap 中 ✅ 的分布，建议下一步学习目标（优先 ⬜ 中与已掌握知识点关联最紧密的）

---

## 输出报告格式

```
## Roadmap 同步报告

### 扫描结果
- 笔记总数：XX
- Roadmap 条目数：XX

### 差异检测
| 差异类型 | 数量 | 详情 |
|----------|------|------|
| A: 笔记存在，roadmap 未收录 | X | [列表] |
| B: roadmap ⬜ → 应为 ✅ | X | [列表] |
| C: roadmap ✅ → 文件缺失 | X | [列表] |
| D: 跨领域关联 | X | [列表] |
| E: 未知 topic | X | [列表] |

### 执行操作
- [列表每项具体修改]

### 时间线更新
- 时间线表格总行数：XX
- 需复习的笔记（创建 > 7 天且未标记"已掌握"）：X 篇
- 最近创建的笔记：[列出最近 3 篇]

### 学习建议
- [基于 comprehension 和 roadmap 分布的建议]
```

> [!info] 交互模式
> 默认情况下，先输出报告，等用户确认后再执行修改。如果用户明确说"直接更新"或"自动同步"，可跳过确认直接执行。
