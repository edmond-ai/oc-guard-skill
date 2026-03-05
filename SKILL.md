---
name: oc_guard
description: Safe OpenClaw config planning/apply workflow with bilingual execution receipts.
---

# oc-guard Skill

## Purpose
All config-changing requests must go through `oc-guard`.
Do not directly edit `~/.openclaw/openclaw.json`.

## Hard Rules
1. Use `oc-guard plan` before apply.
2. High-risk changes require `oc-guard apply --confirm`.
3. Always return execution receipt first.
4. If command is not executed, return `【模型说明-未执行】`.
5. Never claim success without a real `oc-guard` receipt.

## Common Commands
- `oc-guard --help`
- `oc-guard plan "<requirement>"`
- `oc-guard apply --confirm "<requirement>"`
- `oc-guard plan --proposal <file>`
- `oc-guard apply --confirm --proposal <file>`
