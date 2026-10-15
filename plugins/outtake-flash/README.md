# Outtake Flash plugin

Outtake Flash checks an unfamiliar link before your agent opens it, signs in, or pays. It returns a verdict (`safe`, `suspicious`, `unsafe`, `inconclusive`, or `not_live`) with the evidence behind it.

The plugin adds two things to your agent:

- The Flash MCP server at `https://armor.outtake.ai/mcp`, using Streamable HTTP and OAuth. It has one read-only tool, `scan_url`.
- The `outtake-flash` skill. It tells the agent to call `scan_url` before opening an unfamiliar link, and to warn you and wait for your approval when a link is `unsafe` or `suspicious`.

## Install

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

Cursor: install Outtake Flash from the Cursor Marketplace, or import `outtake-ai/skills` as a team marketplace under Dashboard → Plugins & MCPs.

## Sign in

The first scan needs an Outtake account. Sign in when the client asks, or start it yourself:

- Claude Code: run `/mcp` and select the Flash server.
- Codex: `codex mcp login flash`.
- Cursor: open Cursor Settings → Tools & MCP and sign in next to `flash`.

Then ask your agent to check `https://outtake.ai`. Setup is complete when it returns a verdict.

## What the plugin runs and sends

The plugin runs no local code, hooks, or commands. It only configures the remote MCP server and adds the skill.

When the agent calls `scan_url`, the client sends the link and a short description of what you are trying to do to `armor.outtake.ai`, with your OAuth token. Flash fetches and analyzes the link on Outtake's servers. Scans are associated with your Outtake account and are not listed in the public Live feed.

## Privacy, terms, and support

- Privacy policy: https://flash.outtake.ai/privacy
- Terms of service: https://flash.outtake.ai/terms
- Support: support@outtake.ai

## License

MIT
