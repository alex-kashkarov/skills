# Landing Page Architect

An open-source agent skill for creating, auditing, and rewriting product and service landing pages.

The skill gives AI agents a concrete workflow for landing page strategy, conversion copywriting, and page structure. It is designed for SaaS products, AI tools, developer tools, startups, professional services, local services, high-ticket offers, waitlist pages, demo-request pages, trial pages, consultation pages, and lead-generation pages.

## What It Helps With

- Choose a landing page structure for a new product or service.
- Write a strong first version of a landing page block by block.
- Audit an existing landing page for conversion bottlenecks.
- Improve hero copy, value propositions, CTAs, product demos, service explanations, proof, pricing clarity, FAQs, and risk reducers.
- Adapt the page for products, services, AI tools, developer tools, high-ticket offers, and lead-generation funnels.

## Core Framework

The skill structures a landing page around the beliefs a visitor needs before converting:

```text
Orient: I understand what this is.
Match: This is for me.
Demonstrate: I can picture how it works.
Prove: I believe the claim.
De-risk: I feel safe acting.
Convert: I know the next step.
```

## Default Landing Page Structure

For a first version, the skill uses this structure:

1. Hero: offer, audience, outcome, and primary CTA.
2. Concrete example: product UI, service deliverable, sample output, demo, workflow, or before/after.
3. Benefits and use cases: specific outcomes tied to real jobs, pains, or situations.
4. How it works: input, process, and output.
5. Credibility proof: testimonial, review, metric, case study, portfolio, certification, founder expertise, or real artifact.
6. Decision details: pricing, trial, timeline, setup effort, deliverables, specs, integrations, compatibility, support, or fit criteria.
7. Risk reducers and FAQ: objections about cost, time, privacy, security, quality, refund, implementation, switching, or what happens after clicking.
8. Final CTA: the same primary action with reassurance.

## Files

- [SKILL.md](SKILL.md) - agent-facing instructions and trigger description.
- [references/playbook.md](references/playbook.md) - detailed landing page creation and audit playbook.
- [agents/openai.yaml](agents/openai.yaml) - OpenAI/Codex-facing metadata.

## Example Prompts

```text
Use the landing-page-architect skill to create a first landing page for a B2B SaaS product that turns sales call transcripts into CRM-ready follow-ups.
```

```text
Use the landing-page-architect skill to audit this landing page and identify whether the main issue is confusion, abstraction, or commitment friction.
```

```text
Use the landing-page-architect skill to rewrite the hero, proof section, pricing cue, FAQ, and CTA for a high-ticket consulting offer.
```

## License

MIT. See the repository [LICENSE](../../LICENSE).
