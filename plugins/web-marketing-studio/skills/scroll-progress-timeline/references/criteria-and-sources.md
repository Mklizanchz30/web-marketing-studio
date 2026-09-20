# Criteria and sources

## Documented behavior

- [MDN: CSS transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) documents transform behavior used for compositor-friendly line scaling.
- [MDN: Intersection Observer](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API) documents asynchronous intersection observation.
- [MDN: ResizeObserver](https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver) documents element-size observation.
- [MDN: `aria-current`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-current) documents the current-item state and the `step` token.
- [GSAP ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/) documents continuous progress and pinning when GSAP is selected.
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) supplies criteria for meaningful sequence, keyboard use, focus, reflow, and target size.

## Engineering heuristics

Measuring point centers, choosing a layout from content weight, and collapsing alternation to a left rail are implementation heuristics. Validate them in the actual design rather than presenting them as standards.

## Source lineage

This Skill is a substantial adaptation of `scroll-progress-timeline` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation removes demo coupling and adds scope, semantic, responsive, and verification guidance for ChatGPT Work.

