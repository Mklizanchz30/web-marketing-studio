# Criteria and sources

## Standards

Use [WCAG 2.2](https://www.w3.org/TR/WCAG22/) only when the evidence supports a specific accessibility finding. Relevant criteria commonly include contrast, reflow, content on hover or focus, keyboard access, no keyboard trap, focus visible and not obscured, target size, labels, error identification, and name/role/value.

Use [WAI: Page Structure](https://www.w3.org/WAI/tutorials/page-structure/) when evaluating semantic headings and regions. Use [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) to verify the platform preference mechanism; the final experience still requires human evaluation.

## Heuristics

Slop-pattern classification, the removal test, five-to-eight finding limit, and P2/P3 visual priorities are audit heuristics rather than external standards. Identify them as such. Do not cite WCAG to justify a purely aesthetic preference.

## Source lineage

This Skill is a substantial adaptation of `audit-ai-design-slop` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation clarifies read-only authorization, evidence scope, source boundaries, and the difference between standards and editorial judgment.

