---
name: audit-ai-design-slop
description: Audit websites, apps, screenshots, mockups, and frontend code for harmful generic design defaults, repeated AI-style clichés, deceptive proof, and established UI defects. Use for an evidence-backed anti-slop review or removal-first improvement plan; remain read-only unless the user separately authorizes implementation.
---

# Audit AI Design Slop

Produce a diagnostic audit that identifies the smallest set of removals or corrections with the largest demonstrated impact. Judge the artifact, not whether AI created it.

## Preserve the boundary

- Do not assign a numeric slop score.
- Do not condemn a technique in isolation.
- Do not prescribe a new visual system unless the user asks for redesign options.
- Do not edit files or publish changes during an audit-only request.
- Mark anything outside the inspected evidence as unknown.

Use `$no-ai-design-slop` when the user asks to implement corrections. For a full page or site, read [../no-ai-design-slop/references/pattern-library.md](../no-ai-design-slop/references/pattern-library.md) and apply only relevant entries.

## Inspect evidence

Use the strongest material available: rendered pages, screenshots, recordings, responsive states, source, tokens, copy, assets, and runtime errors. Record the actual screen, route, viewport, state, and interaction inspected.

Every finding must cite a concrete component, location, behavior, or line of copy. Do not convert a generic tendency into a finding without evidence.

## Classify and prioritize

Use one class:

- **Quality defect:** established usability, accessibility, content, responsive, performance, or runtime failure.
- **Slop pattern:** repeated default or decorative convention with no useful role that weakens hierarchy, identity, or trust.

Use priority:

- **P0:** blocks completion, creates severe access failure, or presents deceptive proof.
- **P1:** materially harms comprehension, trust, navigation, or interaction.
- **P2:** repeated pattern or inconsistency that weakens hierarchy and specificity.
- **P3:** minor polish problem with limited impact.

Return five to eight findings by default. Group repeated symptoms under the root cause.

## Apply the removal test

For every candidate, state its current job. Recommend removal or consolidation when clarity improves without losing information, state, action, hierarchy, or brand meaning. Otherwise recommend the smallest correction using the existing system. Add a replacement only when deletion would create a real loss.

## Output

```md
## Verdict
One concise paragraph naming the dominant root causes and first correction.

## Checked scope
- Artifact, route, screen, state, and viewport actually inspected

## Findings
| Priority | Class | Pattern | Evidence | Harm | Remove or fix |
|---|---|---|---|---|---|

## Unknowns
- Important states or behavior that could not be verified
```

Omit empty sections. Lead with evidence, not taste. End with the single removal or correction that would produce the largest improvement.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) before citing standards or presenting a heuristic as a criterion.

