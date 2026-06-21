# Deep Research

An open-source agent skill for rigorous source-backed research, fact-checking, literature reviews, evidence synthesis, and research planning.

The skill gives AI agents a disciplined workflow for scoping research questions, choosing an appropriate research depth, searching multiple source routes, verifying evidence, handling contradictions, and producing cited briefs or reports. It is designed for Codex and compatible skill runners working on market research, competitive research, policy research, technical research, academic research, source verification, and PRISMA-style systematic review planning.

## What It Helps With

- Produce source-backed research briefs and full reports.
- Fact-check specific claims with evidence-based verdicts.
- Verify sources, citations, provenance, dates, and bibliographic details.
- Create literature reviews, annotated bibliographies, source matrices, and evidence syntheses.
- Research markets, competitors, policies, technical claims, academic topics, and decision-critical questions.
- Plan systematic reviews using PRISMA-style search, screening, and evidence-quality thinking.

## Core Framework

The skill guides an agent through a research workflow:

```text
choose mode -> choose tier -> approve plan -> search -> verify -> synthesize -> adversarial check -> cite
```

## Research Modes

- `socratic`: clarify vague ideas and turn them into researchable questions.
- `fact-check`: verify specific claims with verdicts and citations.
- `quick`: produce a concise source-backed brief.
- `lit-review`: map literature, themes, gaps, and source quality.
- `full`: produce a comprehensive research report.
- `systematic-review`: plan or structure PRISMA-style review work.

## Research Tiers

- `lite`: fast, narrow, low-stakes research with a small set of strong sources.
- `standard`: default depth for meaningful research, comparisons, and literature reviews.
- `thorough`: deeper research for high-stakes, disputed, technical, academic, legal, medical, financial, or decision-critical questions.

## Files

- [SKILL.md](SKILL.md) - agent-facing instructions and trigger description.
- [references/modes.md](references/modes.md) - research modes, output shapes, and transition rules.
- [references/source-verification.md](references/source-verification.md) - evidence grading, citation verification, and source-quality checks.
- [references/failure-paths.md](references/failure-paths.md) - recovery paths when research stalls or evidence is weak.
- [agents/openai.yaml](agents/openai.yaml) - OpenAI/Codex-facing metadata.

## Example Prompts

```text
Use the deep-research skill to produce a source-backed brief on the market for AI sales enablement tools.
```

```text
Use the deep-research skill to fact-check these claims and separate supported, mixed, misleading, and unverifiable statements.
```

```text
Use the deep-research skill to create a literature review and evidence matrix for retrieval-augmented generation evaluation methods.
```

```text
Use the deep-research skill to plan a PRISMA-style systematic review for studies on AI tutoring outcomes.
```

## License

MIT. See the repository [LICENSE](../../LICENSE).
