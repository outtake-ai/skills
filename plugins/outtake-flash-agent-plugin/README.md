# Outtake Flash (Agent Plugins format)

This is the Outtake Flash plugin in the open [Agent Plugins 1.0](https://agent-plugins.org) format, for clients that read it, such as Kiro. For Claude Code, Codex, Cursor, and GitHub Copilot, use [`plugins/outtake-flash`](../outtake-flash) instead.

Outtake Flash checks an unfamiliar link before your agent opens it, signs in, or pays. It returns a verdict (`safe`, `suspicious`, `unsafe`, `inconclusive`, or `not_live`) with the evidence behind it.

The plugin adds two things to your agent:

- The Flash MCP server at `https://armor.outtake.ai/mcp`, using Streamable HTTP and OAuth. It has one read-only tool, `scan_url`.
- The `outtake-flash` skill. It tells the agent to call `scan_url` before opening an unfamiliar link, and to warn you and wait for your approval when a link is `unsafe` or `suspicious`.

## Install

Kiro: open the Powers panel, choose Add Custom Power, and import this folder. From the Kiro CLI, run `kiro-cli powers install <path-to-this-folder>`.

Sign in when the client asks. Then ask your agent to check `https://outtake.ai`. Setup is complete when it returns a verdict.

## What the plugin runs and sends

The plugin runs no local code, hooks, or commands. It only configures the remote MCP server and adds the skill.

When the agent calls `scan_url`, the client sends the link and a short description of what you are trying to do to `armor.outtake.ai`, with your OAuth token. Flash fetches and analyzes the link on Outtake's servers. Scans are associated with your Outtake account and are not listed in the public Live feed.

## Privacy, terms, and support

- Privacy policy: https://flash.outtake.ai/privacy
- Terms of service: https://flash.outtake.ai/terms
- Support: support@outtake.ai

## License

MIT
