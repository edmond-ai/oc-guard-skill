# oc-guard-skill

Safe config guard for OpenClaw.

- Run `plan` to preview changes and risk.
- Run `apply --confirm` to execute high-risk changes.
- Includes backup + rollback and bilingual execution receipts.

## Features

- Natural language to guarded config proposal (`plan`)
- High-risk confirmation gate (`apply --confirm`)
- Validation for channels/bindings/agents/models references
- Auto backup before apply
- Auto rollback on restart/health failure
- Bilingual receipt output with 12-char signature

## Included Files

- `SKILL.md`
- `scripts/oc-guard`
- `templates/proposal.template.json`
- `docs/SAFETY.md`
- `CHANGELOG.md`

## Not Included

- Any personal config (`~/.openclaw/openclaw.json`)
- Any logs/backups/runtime artifacts
- Any API keys, tokens, app secrets

## Prerequisites

- Python 3.9+
- OpenClaw CLI
- OpenCode CLI

## Install

```bash
chmod +x scripts/oc-guard
mkdir -p ~/.local/bin
ln -sf "$PWD/scripts/oc-guard" ~/.local/bin/oc-guard
```

## Environment Overrides

`oc-guard` supports these optional environment variables:

- `OPENCLAW_HOME`
- `OCGUARD_CONFIG_PATH`
- `OCGUARD_BACKUP_DIR`
- `OCGUARD_OPENCLAW_BIN`
- `OCGUARD_OPENCODE_BIN`
- `OCGUARD_RECEIPT_SECRET`
- `OCGUARD_RECEIPT_SECRET_FILE`

## Usage

```bash
oc-guard plan "add a new feishu bot and bind it to github agent"
oc-guard apply --confirm "add a new feishu bot and bind it to github agent"
```

Or with proposal file:

```bash
oc-guard plan --proposal /tmp/openclaw-config-proposal.json
oc-guard apply --confirm --proposal /tmp/openclaw-config-proposal.json
```

## Output Contract

Every command returns:

- `【执行回执 | Execution Receipt】`
- executor / operation / request id / status / 12-char signature
- `【本次内容 | Details】`

If not executed, return:

- `【模型说明-未执行】`

## Security Notes

Never share runtime data from:

- `~/.openclaw/**`
- `/tmp/openclaw*`
- `/tmp/oc-guard-*`

Keep path references in docs if needed, but do not publish real file contents.

## License

MIT
