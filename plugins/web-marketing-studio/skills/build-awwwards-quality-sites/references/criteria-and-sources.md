# Criteria and sources

## Standards and documented platform behavior

- Accessibility requirements come from [WCAG 2.2](https://www.w3.org/TR/WCAG22/), especially text alternatives, reflow, contrast, keyboard access, visible focus, content on hover or focus, and animation from interactions.
- Reduced-motion behavior is based on [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion).
- Performance reporting should use current user-centered metrics described by [web.dev: Web Vitals](https://web.dev/articles/vitals); do not invent scores or improvements.
- CSS animation performance guidance is documented in [web.dev: High-performance CSS animations](https://web.dev/articles/animations-guide).
- When GSAP is used, pinning, scrub, refresh, and lifecycle behavior should follow [GSAP ScrollTrigger documentation](https://gsap.com/docs/v3/Plugins/ScrollTrigger/).

## Editorial heuristics

The visual thesis, one-focal-device rule, coherence test, rejection of decorative stacking, and requirement for an authored first viewport are design heuristics. They are not W3C conformance criteria and should be adapted to the product and verified in the rendered result.

“Awwwards-quality” is used only as a user-supplied craft target. It does not imply submission, nomination, recognition, or endorsement by Awwwards.

## Source lineage

This Skill is a substantial adaptation of `build-awwwards-quality-sites` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation removes unavailable-service assumptions, separates standards from taste heuristics, preserves user authorization boundaries, and adds ChatGPT Work-compatible evidence and verification rules.

