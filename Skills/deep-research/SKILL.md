---
name: deep-research
description: Rigorous multi-source research workflow for Codex and compatible agent skill runners. Use when the user asks for deep research, literature review, systematic review, evidence synthesis, fact-checking, source verification, research-question scoping, policy analysis, competitive or market research requiring citations, or a source-backed brief/report. Supports quick briefs, full reports, literature reviews, fact checks, Socratic research scoping, PRISMA-style systematic review planning, lite/standard/thorough research tiers, approval gates before large research runs, citation discipline, contradiction handling, and adversarial evidence review.
---

# Deep Research

Deep Research is a Codex-compatible AI agent skill for source-backed research, evidence synthesis, literature reviews, fact-checking, market research, policy research, technical research, academic research, and PRISMA-style systematic review planning.

## Purpose

Use this skill to run disciplined research, not generic web browsing. Prefer it when accuracy depends on source quality, citation traceability, contradiction handling, or an explicit research process.

Use Codex tools directly. Do not assume external pipeline hooks, slash commands, passport files, or skill-specific scripts exist unless they are present in the current environment.

## Operating Rules

1. Start by classifying the mode: `socratic`, `fact-check`, `quick`, `lit-review`, `full`, or `systematic-review`.
2. Select a research tier: `lite`, `standard`, or `thorough`.
3. State assumptions and the research question before collecting sources.
4. Present a brief plan and ask for approval before source collection when the run is `standard`/`thorough`, uses subagents, or will materially consume time.
5. Use web search for current, niche, high-stakes, or source-dependent claims. Prefer primary sources, official data, peer-reviewed papers, and reputable databases.
6. Verify source existence and bibliographic details before citing. Gray zone means fail: if a source cannot be confirmed, do not use it as evidence.
7. Separate evidence from judgment. Label confidence and assumptions explicitly.
8. Include counterevidence and contradictions. Do not cherry-pick.
9. Every substantive factual claim in final research output needs a citation or a clear "uncited judgment/inference" label.
10. Use subagents when available for parallel source gathering, adversarial critique, or independent verification; keep final synthesis in the main agent.
11. Stop before Phase 2 when the research question or scope is materially ambiguous and a bad assumption would change the answer.

## Mode Selection

- `socratic`: User has a vague idea, asks to be guided, or is unsure what to research. Ask questions; do not jump to a report.
- `fact-check`: User provides specific claims to verify. Output claim-by-claim verdicts.
- `quick`: User needs a concise source-backed brief. Use fewer sources, but still verify them.
- `lit-review`: User needs literature mapping, annotated bibliography, themes, gaps, or source matrix.
- `full`: User has a clear question and wants a comprehensive report.
- `systematic-review`: User asks for PRISMA, systematic review, meta-analysis, formal screening, risk of bias, or GRADE-style evidence synthesis.

For details, read `references/modes.md`.

## Research Tier

Choose the smallest tier that can answer the question honestly:

- `lite`: fast answer, narrow fact-check, quick brief, or low-stakes overview. Target 3-6 strong sources and verify central claims against at least one source route.
- `standard`: default for meaningful research, comparisons, policy/market questions, and literature reviews. Target 6-12 sources and use at least two independent source routes for central claims.
- `thorough`: use for high-stakes, systematic-review-like, disputed, technical, legal/medical/financial, or decision-critical research. Target 12+ sources where available, use multiple source families, actively search for counterevidence, and verify central claims independently.

Escalate the tier when the user asks for more rigor, the evidence is contradictory, the topic is high-stakes, or early searching shows weak/fragmented sources. Downgrade only with an explicit note about what rigor is being traded away.

## Workflow

### 1. Scope

Produce a brief research frame:

```markdown
Research question:
Scope:
Out of scope:
Key definitions:
Assumptions:
Mode:
Tier:
Planned source types:
```

For vague topics, switch to `socratic` and ask 1-2 focused questions at a time until the user can state what they want to know.

### 2. Plan and Approval Gate

Before collecting sources, present a compact plan:

```markdown
Plan:
Mode:
Tier:
Sub-questions:
Source routes:
Verification plan:
Estimated effort:
```

Ask for approval before continuing unless all are true: tier is `lite`, no subagents are planned, source collection is small, and the user already clearly asked for immediate execution. If the user says to adjust, revise the plan once and ask again. If the user says to proceed, execute without relitigating.

### 3. Search

Build a reproducible search plan:

```markdown
Databases/sources:
Search strings:
Date range:
Languages:
Inclusion criteria:
Exclusion criteria:
```

Use at least two independent source routes for non-trivial research, such as official data plus scholarly literature, or primary documentation plus reputable reporting.

Tier defaults:

- `lite`: 1-2 source routes, targeted searches, stop when the answer is adequately supported.
- `standard`: 2-3 source routes, explicit counterevidence search, source matrix for central claims.
- `thorough`: 3+ source routes, broader keyword variants, formal exclusion notes, deeper contradiction handling.

### 4. Verify

Before synthesis, create a compact evidence table:

```markdown
Source:
Type:
Verified by:
Evidence grade:
Relevant claim(s):
Limitations/conflicts:
Use / caveat / reject:
```

Read `references/source-verification.md` when source quality, citations, DOI checks, policy claims, or academic evidence grading matter.

Tier defaults:

- `lite`: verify every central claim used in the bottom line.
- `standard`: verify central claims and the strongest counterclaim.
- `thorough`: verify central claims, counterclaims, key numbers/dates, and citation metadata.

### 5. Synthesize

Group findings by answer-relevant themes, not by source. Explicitly handle:

- Convergent findings
- Contradictory findings
- Evidence quality differences
- Missing evidence
- Alternative explanations
- Practical implications

### 6. Adversarial Check

Before finalizing, run a Devil’s Advocate pass:

```markdown
Strongest counterargument:
Weakest supported claim:
Likely bias in source selection:
Evidence overreach:
What would change the conclusion:
```

If a critical flaw invalidates the conclusion, stop and explain the flaw instead of polishing a bad report.

### 7. Final Output

Match the output to the mode:

- `fact-check`: claim table with verdicts: `supported`, `unsupported`, `mixed`, `unverifiable`, or `misleading`.
- `quick`: concise brief with key findings, source notes, caveats, and next research steps.
- `lit-review`: themes, annotated bibliography, gaps, and source matrix.
- `full`: executive summary, method, findings, discussion, limitations, references.
- `systematic-review`: protocol, search strategy, screening counts, study table, risk-of-bias plan/results, synthesis approach, limitations.
- `socratic`: research plan summary only when the user asks to summarize or move forward.

For `standard` and `thorough`, include a short method note with mode, tier, source routes, and verification limits.

## Subagent Pattern

When subagents are available and the task is large enough, split work like this:

- Researcher A: primary/official sources and data.
- Researcher B: scholarly literature and reviews.
- Researcher C: contrary evidence, critiques, and failure cases.
- Verifier: source existence, citation accuracy, provenance, and quality.
- Main agent: reconciles all evidence and writes the final answer.

Do not let subagents write the final synthesis independently. Their outputs are evidence inputs, not conclusions.

## Failure Handling

Read `references/failure-paths.md` when a workflow stalls, sources are weak, the question is too broad, evidence contradicts the conclusion, or verification fails.

Core defaults:

- Fewer than 3 usable sources: expand search or narrow the claim.
- Only low-quality sources: downgrade confidence and label the output exploratory.
- Unverified citation: remove it or mark it unusable.
- Critical contradiction: report the contradiction; do not hide it.
- User asks for certainty beyond the evidence: refuse the certainty and give the evidence-bounded answer.

## Resource Map

- `references/modes.md`: mode definitions, output shapes, and transition rules.
- `references/source-verification.md`: source grading, citation verification, evidence hierarchy, and predatory-source checks.
- `references/failure-paths.md`: recovery rules for common research breakdowns.
