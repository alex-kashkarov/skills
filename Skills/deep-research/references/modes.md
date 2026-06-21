# Deep Research Modes

## `socratic`

Use when the user has a vague idea or asks for guidance. Ask questions instead of producing answers. Move through:

1. Problem framing: what does the user actually want to know?
2. Method fit: what kind of evidence could answer it?
3. Evidence design: where would convincing evidence come from?
4. Counterarguments: what would reviewers challenge?
5. Research plan: summarize only when the user asks or is ready.

Avoid premature closure. Do not ask to “write it up” while the user is still exploring.

## `fact-check`

Use for specific claims. Output:

```markdown
Claim:
Verdict: supported | unsupported | mixed | misleading | unverifiable
Best evidence:
Why:
Confidence:
```

Each claim needs at least one source route. For important claims, require two independent routes.

## `quick`

Use for a short source-backed brief. Suggested output:

```markdown
Bottom line:
Key findings:
Evidence notes:
Contradictions/caveats:
References:
Best next step:
```

Default tier: `lite`, unless the user asks for decision support or the topic is high-stakes.

## `lit-review`

Use for literature mapping and synthesis. Include:

- Search strategy
- Inclusion/exclusion criteria
- Annotated bibliography
- Theme map
- Evidence gaps
- Contradictions
- Source matrix when useful

Default tier: `standard`. Use `thorough` for publication-oriented, systematic, or contested literature reviews.

## `full`

Use for comprehensive source-backed research. Include:

- Executive summary
- Research question and method
- Findings by theme
- Evidence quality assessment
- Counterarguments
- Limitations
- References

Default tier: `standard`. Use `thorough` when the answer will drive a material decision.

## `systematic-review`

Use when the user asks for PRISMA, systematic review, meta-analysis, risk of bias, or formal evidence synthesis.

Minimum protocol:

```markdown
PICOS/research question:
Databases:
Search strings:
Eligibility criteria:
Screening process:
Risk-of-bias tool:
Synthesis plan:
Registration recommendation:
```

Search at least two databases where feasible. Document screening counts and exclusion reasons. If meta-analysis is not feasible, explain why and use structured narrative synthesis.

Default tier: `thorough`.

## Approval Gate

Use the approval gate to prevent expensive wrong-direction research. Present:

```markdown
Mode:
Tier:
Sub-questions:
Source routes:
Verification plan:
```

Ask for approval when the tier is `standard` or `thorough`, when subagents are planned, or when the plan has more than two sub-questions. Skip only for small `lite` runs where the user clearly asked for immediate output.

If the user asks to adjust, change the plan and ask again. Do not ask more than two approval questions unless the user's revisions materially change the research direction.
