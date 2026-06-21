# Agent Skills and Playbooks

Open-source skills, playbooks, and reusable workflows for AI coding agents and reasoning agents.

This repository collects practical agent skills that help tools such as Codex, Claude, Cursor, and other LLM agents perform specialized work with better structure, clearer decisions, and less generic output.

## Skills

### [Landing Page Architect](Skills/landing-page-architect)

Create, audit, or rewrite product and service landing pages using a conversion-focused structure.

Use it for:

- product landing pages
- service landing pages
- SaaS, AI tools, developer tools, and startups
- demo-request, waitlist, trial, consultation, and lead-generation pages
- landing page audits, rewrites, value propositions, CTAs, proof sections, FAQs, and risk reducers

The skill helps an agent structure a page around the visitor beliefs required for conversion:

```text
understand the offer -> see relevance -> picture how it works -> believe the claim -> feel safe acting -> know the next step
```

### [Deep Research](Skills/deep-research)

Run rigorous source-backed research with modes for quick briefs, fact-checking, literature reviews, full reports, Socratic scoping, and systematic-review planning.

Use it for:

- deep research and source-backed briefs
- fact-checking and source verification
- literature reviews and evidence synthesis
- market, competitive, policy, technical, or academic research
- PRISMA-style systematic review planning

The skill guides an agent through a disciplined research workflow:

```text
choose mode -> choose tier -> approve plan -> search -> verify -> synthesize -> adversarial check -> cite
```

## Repository Structure

```text
Skills/
  landing-page-architect/
    SKILL.md
    agents/openai.yaml
    references/playbook.md
  deep-research/
    SKILL.md
    agents/openai.yaml
    references/modes.md
    references/source-verification.md
    references/failure-paths.md
```

## License

MIT. See [LICENSE](LICENSE).
