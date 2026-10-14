# Outtake agent skills

Public agent skills maintained by Outtake. Each skill lives in its own directory under `skills/`.

## Install a skill

Use the skill name from the table below:

```bash
npx skills add outtake-ai/skills --skill <skill-name>
```

Add `--global` and one or more `--agent` flags to choose where the skill is installed.

## Available skills

| Skill | Purpose |
| --- | --- |
| `outtake-flash` | Check unfamiliar links with Outtake Flash before an agent opens or fetches them. |

Install Outtake Flash globally for Cursor, Claude Code, and Codex:

```bash
npx skills add outtake-ai/skills --skill outtake-flash --global --agent cursor --agent claude-code --agent codex --yes
```

## License

MIT
