# Jan's Cursor Rules

**v0.1.1**

A curated set of `.mdc` rule files for [Cursor](https://cursor.sh) that shape AI assistant behavior toward careful, minimal, high-quality code.

## What's in here

| File | Purpose |
|------|---------|
| `cursor-assistant.mdc` | Core behavioral guidelines — thinking before coding, simplicity, surgical changes, goal-driven execution |
| `safety.mdc` | Guards against destructive filesystem and git operations |
| `python.mdc` | Python-specific conventions and tooling standards |
| `memory-bank.mdc` | Memory-bank documentation pattern for session continuity |

## Philosophy

The two rules I care about most are:

1. **Fix things at the cause, not the symptom.**
2. **Challenge me.** Evaluate my suggestions from all angles and push back when warranted.

The remaining guidelines (simplicity first, surgical changes, goal-driven execution) are heavily influenced by Andrej Karpathy's observations on LLM coding pitfalls, as packaged in [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills).

## Usage

Copy the `.mdc` files you want into your project's `.cursor/rules/` directory, or use this repo as a reference to build your own.

## License & Disclaimer

[MIT License](LICENSE) — [Disclaimer](DISCLAIMER.md)
