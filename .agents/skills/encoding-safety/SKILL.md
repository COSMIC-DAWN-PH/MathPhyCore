---
name: encoding-safety
description: Prevent encoding/mojibake regressions when Codex creates or edits Markdown notes, AGENTS.md/CLAUDE.md instructions, or interactive HTML/iframe tools in this Obsidian vault, especially when Chinese text, CJK UI labels, LaTeX, or Windows PowerShell file writes are involved.
---

# Encoding Safety

Use this skill whenever editing or generating Markdown, HTML, JavaScript, or project instructions that may contain non-ASCII text in this vault.

## Non-negotiable rule

Never embed Chinese/CJK text directly inside a PowerShell here-string or shell command payload. The command transport may turn it into question marks before Python or the editor sees it.

## Safe write patterns

Prefer one of these patterns:

1. ASCII-only generated artifacts when acceptable, especially for HTML UI labels.
2. Python file writes with Unicode escapes such as `"\\u53cc\\u91cd"`, then write with `encoding="utf-8"`.
3. Base64-encoded UTF-8 payloads decoded inside Python before writing.
4. Read existing UTF-8 text from a file and transform it, instead of retyping non-ASCII text in the shell command.
5. For small Markdown patches, use `apply_patch` only when the patch text is known to survive intact; otherwise use Unicode escapes/base64.

## Required validation after writing

After any write that could affect CJK text:

- Re-read the changed file with `encoding="utf-8"`.
- Check the exact edited region, not just file existence.
- Search for mojibake markers: `three consecutive question marks`, replacement character `U+FFFD`, and unexpected long runs of `?`.
- For HTML/JS, run `node --check` on extracted scripts when JavaScript is present.
- Confirm `<meta charset="utf-8">` exists in standalone HTML tools.

Minimal validation logic: read the file as UTF-8, print the edited slice, then test whether three consecutive question marks or `U+FFFD` appears.

## Obsidian HTML iframe tools

For `tools/*.html` embedded in notes:

- Include `<meta charset="utf-8">`.
- Use absolute `file:///C:/Personal%20Profile/Profile/MathPhysCore/tools/...html` iframe paths in notes.
- If CJK UI text is not essential, prefer English/ASCII UI labels to eliminate encoding risk.
- If CJK UI text is essential, generate the file via Unicode escapes or base64 and validate rendered text by re-reading the file.

## If mojibake is found

1. Stop editing the affected region further.
2. Reconstruct the intended text from context or user selection.
3. Rewrite using a safe write pattern above.
4. Validate before responding to the user.
