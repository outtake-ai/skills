# Outtake agent skills

Public agent skills and plugins maintained by Outtake. Each skill lives in its own directory under `skills/`, and each plugin under `plugins/`.

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

## Install the Outtake Flash plugin

The plugin installs the Outtake Flash MCP server and the `outtake-flash` skill together. See [`plugins/outtake-flash`](plugins/outtake-flash) for what it runs and sends.

Claude Code:

```bash
claude plugin marketplace add outtake-ai/skills
claude plugin install outtake-flash@outtake
```

Codex:

```bash
codex plugin marketplace add outtake-ai/skills
codex plugin add outtake-flash@outtake
```

GitHub Copilot CLI:

```bash
copilot plugin marketplace add outtake-ai/skills
copilot plugin install outtake-flash@outtake
```

Gemini CLI:

```bash
gemini extensions install https://github.com/outtake-ai/skills
```

Kiro and other [Agent Plugins](https://agent-plugins.org) clients: import [`plugins/outtake-flash-agent-plugin`](plugins/outtake-flash-agent-plugin).

Sign in to Outtake when your client asks, then ask your agent to check `https://outtake.ai`.

## Privacy and support

- Privacy policy: https://flash.outtake.ai/privacy
- Support: support@outtake.ai

## License

MIT
