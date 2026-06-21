# Agent Skills and Playbooks

Open-source skills, playbooks, and reusable workflows for AI coding agents and reasoning agents.

This repository collects practical agent skills that help tools such as Codex, Claude, Cursor, and other LLM agents perform specialized work with better structure, clearer decisions, and less generic output.

## Skills

### [Landing Page Architect](Skills/landing-page-architect)

Create, audit, or rewrite product and service landing pages using a conversion-focused structure, offer diagnosis, block-by-block copywriting, proof, risk reduction, and CTA guidance.

Landing Page Architect is an AI agent skill for Codex and compatible skill runners that need to turn an offer brief into a clear landing page, audit an existing page for conversion bottlenecks, or improve page sections such as the hero, value proposition, product demo, service explanation, testimonials, pricing, FAQ, objection handling, and call to action.

Use it for:

- product landing pages
- service landing pages
- SaaS, AI tools, developer tools, and startups
- demo-request, waitlist, trial, consultation, and lead-generation pages
- landing page audits and conversion bottleneck diagnosis
- hero section rewrites, value propositions, CTA copy, social proof, testimonials, pricing sections, FAQs, objection handling, and risk reducers
- landing page copywriting, landing page optimization, conversion copywriting, SaaS marketing, product marketing, and lead generation

The skill helps an agent structure a page around the visitor beliefs required for conversion:

```text
understand the offer -> see relevance -> picture how it works -> believe the claim -> feel safe acting -> know the next step
```

Useful for prompts such as "create a landing page for this SaaS product", "audit this landing page for conversion bottlenecks", "rewrite my hero section and CTA", "turn this offer brief into a landing page", "write a service landing page for a consulting offer", "improve the proof, FAQ, pricing, and risk-reducer sections", "create a landing page for an AI tool or developer tool", or "diagnose whether this page has confusion, abstraction, or commitment friction".

Key references: [minimum offer brief](Skills/landing-page-architect/references/playbook.md#minimum-offer-brief), [complete first-version structure](Skills/landing-page-architect/references/playbook.md#complete-first-version-structure), [adaptation rules](Skills/landing-page-architect/references/playbook.md#adaptation-rules), [offer-type emphasis](Skills/landing-page-architect/references/playbook.md#offer-type-emphasis), [bottleneck structures](Skills/landing-page-architect/references/playbook.md#bottleneck-structures), and [block quality checks](Skills/landing-page-architect/references/playbook.md#block-quality-checks).

### [Deep Research](Skills/deep-research)

Run rigorous source-backed research with modes for quick briefs, fact-checking, literature reviews, full reports, Socratic scoping, and systematic-review planning.

Deep Research is an AI agent skill for Codex and compatible skill runners that need reliable, citation-backed answers instead of generic web summaries. It helps agents scope a research question, choose an appropriate depth tier, search multiple source routes, verify sources, handle contradictory evidence, synthesize findings, and produce a cited brief or report.

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

Useful for prompts such as "do deep research on this market", "fact-check these claims", "write a literature review", "compare competitors with sources", "verify this policy argument", "find academic evidence for this technical claim", or "plan a PRISMA-style systematic review".

Key references: [research modes](Skills/deep-research/references/modes.md), [source verification](Skills/deep-research/references/source-verification.md), and [failure paths](Skills/deep-research/references/failure-paths.md).

## Repository Structure

```text
Skills/
  landing-page-architect/
    README.md
    SKILL.md
    agents/openai.yaml
    references/playbook.md
  deep-research/
    README.md
    SKILL.md
    agents/openai.yaml
    references/modes.md
    references/source-verification.md
    references/failure-paths.md
```

## License

MIT. See [LICENSE](LICENSE).
