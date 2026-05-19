# Jan's Cursor Rules

**v0.2.1**

A curated set of `.mdc` rule files for [Cursor](https://cursor.sh) that shape AI assistant behavior toward careful, minimal, high-quality code.

## What's in here

### Rules (`.mdc` files)

| File | Purpose |
|------|---------|
| `cursor-assistant.mdc` | Core behavioral guidelines — thinking before coding, simplicity, surgical changes, goal-driven execution |
| `safety.mdc` | Guards against destructive filesystem and git operations; package-manager detection before installs |
| `python.mdc` | Python-specific conventions and tooling standards |
| `curios.mdc` | Cross-project conversation memory via Curios MCP (requires [Curios](https://github.com/jbrusevich/curios) installed) |
| `memory-bank.mdc` | Memory-bank documentation pattern for session continuity (optional; not part of the default global set) |

### Skills (`skills/` directory)

| Skill | Purpose |
|-------|---------|
| `skills/grill-me/` | Relentless iterative interview that stress-tests a plan before any code is written — an explicit, structured version of "challenge me" |
| `skills/code-audit/` | Thorough code audit from a senior engineer perspective covering correctness, architecture, performance, security, simplicity, and configurability — produces a prioritized issue report and implementation plan |
| `skills/extended-plan/` | Audit-proof development planning in Cursor's native `.plan.md` format — explores the codebase read-only, decomposes the task into steps, and stress-tests each step against all code-audit dimensions before any code is written |

## Philosophy

The two rules I care about most are:

1. **Fix things at the cause, not the symptom.**
2. **Challenge me.** Evaluate my suggestions from all angles and push back when warranted.

The remaining guidelines (simplicity first, surgical changes, goal-driven execution) are heavily influenced by Andrej Karpathy's observations on LLM coding pitfalls, as packaged in [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills).

## Usage

Copy the `.mdc` files you want into your project's `.cursor/rules/` directory, or use this repo as a reference to build your own.

For skills, copy the folder you want into `~/.cursor/skills/` (global) or `.cursor/skills/` (project-scoped). Invoke `grill-me` explicitly by referencing it in chat when you want to think through a plan before writing any code. Invoke `code-audit` when you want a thorough review of a file, module, or full project before making changes. Invoke `extended-plan` when planning a feature implementation — it produces a step-by-step plan pre-checked against all audit dimensions.

## License & Disclaimer

[MIT License](LICENSE) — [Disclaimer](DISCLAIMER.md)
