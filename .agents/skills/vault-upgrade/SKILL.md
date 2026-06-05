---
name: vault-upgrade
description: 库升级工作流 — 扫描、升级、验证 MathPhysCore vault 的格式和内容标准
---

# Skill: Vault Upgrade (库升级工作流)

## 触发条件

当用户说出以下指令时触发此技能：
- "升级这个库"
- "apply new standards"
- "migrate to new format"
- "按新标准升级"
- "检查并升级所有笔记"

## 升级工作流

### Phase A: 扫描 Vault 构建清单

1. 列出 `Knowledge Point/Math/` 和 `Knowledge Point/Physics/` 下所有 `.md` 文件
2. 统计笔记数量、状态分布（Draft / WIP / Evergreen / Archive）
3. 检查 `Study-Roadmap.md` 中标记 ✅ 的笔记是否都有对应文件
4. 检查是否有空文件（0 字节）

输出格式：
```
## Vault 扫描报告
- 总笔记数：XX
- 状态分布：Draft X / WIP X / Evergreen X / Archive X
- 空文件：[列表]
- 缺失文件：[列表]
```

### Phase B: CLAUDE.md / AGENTS.md 升级检查清单

对照以下清单检查配置文件是否需要更新：

- [ ] 包含 `source` 和 `comprehension` YAML 字段说明
- [ ] 包含 Comprehension Levels 表
- [ ] 包含 Knowledge Maturity 表
- [ ] 包含 Readability Standard（可读性标准）
- [ ] 包含 LaTeX 表格铁律
- [ ] 包含 Skills 列表
- [ ] 包含 Agent Memory & User Profile section
- [ ] 包含专业 matplotlib 色板和 frameless legend 规范
- [ ] Python 图表规范包含 `plt.tight_layout()` 和 `plt.grid(alpha=0.3, ls=':')`
- [ ] Callout 类型表格完整

### Phase C: 逐篇笔记升级检查清单

对每篇笔记执行以下检查和修改：

| 检查项 | 操作 | 优先级 |
|--------|------|--------|
| `comprehension` 字段 | 检查是否存在；若缺失则设默认值 `vague`；**绝不修改已有值**（用户专属） | 高 |
| `source` 字段 | 添加到 YAML，标注来源（教材/课程/self-authored） | 高 |
| LaTeX `\|` 在 markdown 表格中 | 检查公式摘要表，如有 `\|` 冲突则改用列表格式 | 高 |
| `[[wiki-links]]` 被反引号包裹 | 移除反引号，恢复双链功能 | 高 |
| `## 📝 更新记录` section | 添加（如缺失） | 中 |
| 物理直觉在公式之前 | 验证，如不符则调整段落顺序 | 中 |
| Callouts 用于关键洞察 | 添加 `> [!tip]` / `> [!warning]` | 中 |
| 双向链接完整性 | 验证所有链接都有对应回链 | 低 |

### Phase D: 模板升级

检查 `tools/Knowledge-Note-Template.md` 是否需要更新：

- [ ] YAML 包含 `source` 和 `comprehension` 字段
- [ ] 包含 Callout 占位符
- [ ] 公式摘要区备注 LaTeX 表格铁律
- [ ] 包含更新记录 section

### Phase E: 用户画像创建/更新

检查 `.agents/memory/user_profile.json` 是否存在且完整：

- [ ] `user_metadata` 包含学业阶段和专业信息
- [ ] `math_background` 和 `physics_background` 记录已完成/待学知识点
- [ ] `vault_preferences` 包含语言、图表风格偏好

### Phase F: 质量验证

执行最终验证：

1. **YAML 验证**：所有 `.md` 文件的 YAML frontmatter 包含 `comprehension` 和 `source` 字段
2. **LaTeX 表格验证**：所有公式摘要表不含 LaTeX `|` 符号冲突
3. **双链验证**：所有 `[[wiki-links]]` 未被反引号包裹
4. **JSON 验证**：`.agents/memory/user_profile.json` 是合法 JSON
5. **Skills 验证**：AGENTS.md 引用的 skill 路径存在
6. **镜像验证**：`.agents/skills/` 和 `.claude/skills/` 内容一致

## 跨库引用检查

MathPhysCore 与 Quantum Computing 科研库之间可能有交叉引用：
- 检查笔记中是否有指向 Quantum Computing vault 的链接
- 确保跨库链接格式正确（使用 Obsidian 的 Vault 跨库链接语法或绝对路径）
