# LLM Agent Operating Config

A drop-in global behavior config for AI coding and reasoning agents — the rules that make an
agent lead with the bottom line, stay honest, challenge a weak plan *before* executing it, and
keep its changes surgical. One philosophy, ported to each platform's own config file:
[`CLAUDE.md`](CLAUDE.md) for Claude Code, [`AGENTS.md`](AGENTS.md) for Codex and Antigravity, and
[`CURSOR-RULES.md`](CURSOR-RULES.md) for Cursor.

Use it if you want your agent to behave like a candid senior collaborator that pushes back —
not a compliant assistant that agrees and charges ahead. It is the kind of file people look for
as a "Karpathy CLAUDE.md", an "AGENTS.md example", or a "global instructions file to stop AI
agent sycophancy".

## What it helps with

- replacing the default agent personality with a candid, advisor-style one
- killing sycophancy, flattery, and silent assumptions
- forcing the agent to challenge the plan before writing code, then execute without relitigating
- keeping diffs surgical — only what the task requires, in the existing style
- a goal-driven loop: turn the task into a verifiable success check and loop until it passes
- a shared long-term memory protocol across Claude Code, Codex, and Cursor
- one source of behavior reused across agents instead of per-tool drift

## The five blocks

Every adapter carries the same five blocks:

- `communication` — bottom line first, concise, minimal formatting
- `honesty` — never flatter; name the better move; separate fact from judgment; state confidence
- `advisor` — at decision points, question the direction and the mindset, not just the implementation
- `execution` — think first, simplest artifact, surgical diffs, goal-driven verification loop
- `memory` — durable facts go to a shared long-term store; read before relevant tasks, write on decisions

## Adapters

One behavior, thin per-agent ports — the behavior is the source of truth; each file is the
platform-specific way to load it.

### Claude Code — [`CLAUDE.md`](CLAUDE.md)

A Karpathy-derived `CLAUDE.md` for Claude Code. Drop it at `~/.claude/CLAUDE.md` for global
behavior, or in a project root to scope it to one repo. It gives Claude Code a candid,
advisor-style default — bottom-line-first answers, no sycophancy, challenge the plan before
writing code, surgical diffs, and a goal-driven verification loop — a more opinionated take on
the popular community CLAUDE.md files, with honesty and memory blocks added.

### Codex & Antigravity — [`AGENTS.md`](AGENTS.md)

The `AGENTS.md` counterpart of the same config, supported by Codex and Antigravity.
*   **Codex:** Drop it at `~/.agents/AGENTS.md` (or a project root) for identical behavior in Codex and other agents that read `AGENTS.md`.
*   **Antigravity:** Drop it at `~/.gemini/config/AGENTS.md` (globally) or `.agents/AGENTS.md` (in your project root).

### Cursor — [`CURSOR-RULES.md`](CURSOR-RULES.md)

The Cursor port of the same config. Cursor has no global `AGENTS.md`, so paste it into **Cursor Settings → Rules → User Rules** for global behavior across every project, or save it as a `.cursor/rules/*.mdc` file to scope it to one repo. Applies to Agent chat (not Tab or inline edit).

## How to use

The five blocks are independent — keep all of them or drop the ones you don't want. See the
adapter for your agent above for its install path (global, or project-scoped by pasting it into a
project-level config file).

## Lineage

This config stands on prior work and says so:

- **Andrej Karpathy** — January 2026 observations (on X) on shifting to agent-based coding and
  the recurring failure modes of LLM coding agents: acting on unchecked assumptions, not
  managing confusion, not seeking clarification.
- **Community CLAUDE.md projects** that distilled those observations into a structured config —
  e.g. [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)
  (MIT) and its four principles: think before coding, simplicity first, surgical changes,
  goal-driven execution.
- **My extensions** — an always-on honesty stance, an advisor mode for strategy and decision
  points, a shared cross-agent memory protocol, an explicit challenge-the-plan-before-execute
  precedence, and per-agent adapters so the same philosophy travels across Claude Code, Codex,
  Cursor, and Antigravity.

## License

MIT — see [LICENSE](../../LICENSE).
