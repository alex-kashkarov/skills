# Playbooks

Reusable **operating configs and process docs** for AI agents — the always-on behavior, house
rules, and repeatable processes an agent loads, as opposed to the on-demand, invocable workflows
in [`Skills/`](../Skills). A playbook has no `SKILL.md`: it is meant to be installed or followed,
not triggered.

## Available playbooks

### [LLM Agent Operating Config](llm-agent-operating-config)

A Karpathy-derived global behavior config for AI coding and reasoning agents, with per-platform
adapters:
*   [`CLAUDE.md`](llm-agent-operating-config/CLAUDE.md) for Claude Code (install as `~/.claude/CLAUDE.md`).
*   [`AGENTS.md`](llm-agent-operating-config/AGENTS.md) for Codex (install as `~/.codex/AGENTS.md`) and Antigravity (install as `~/.gemini/config/AGENTS.md`).
*   [`CURSOR-RULES.md`](llm-agent-operating-config/CURSOR-RULES.md) for Cursor (paste into Cursor Settings → Rules → User Rules).

It gives an agent candid, advisor-style behavior: bottom-line-first answers, no sycophancy,
plan-challenge before code, surgical diffs, and a goal-driven verification loop.

## License

MIT — see [LICENSE](../LICENSE).
