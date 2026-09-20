# Criteria and sources

## Documented behavior

- [MDN: `Document.createTreeWalker`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTreeWalker) documents filtered DOM traversal and `NodeFilter.SHOW_TEXT`.
- [MDN: `requestAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame) documents display-timed callbacks.
- [GSAP ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/) documents scrubbed progress, refresh, and cleanup concepts when GSAP is selected.
- [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) documents the user preference query.
- [WAI: Page Structure](https://www.w3.org/WAI/tutorials/page-structure/) and [WCAG 2.2](https://www.w3.org/TR/WCAG22/) support the semantic, reading-order, reflow, keyboard, and motion requirements.

## Design heuristics

The numeric opacity, blur, offset, span, and overlap ranges are starting points inherited from the source technique. They are not standards. Tune them against the typeface, passage length, contrast, viewport, and reading speed.

## Source lineage

This Skill is a substantial adaptation of `scroll-scrubbed-word-reveal` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation removes demo coupling, clarifies semantic duplication and cleanup, and adds ChatGPT Work-compatible verification boundaries.

