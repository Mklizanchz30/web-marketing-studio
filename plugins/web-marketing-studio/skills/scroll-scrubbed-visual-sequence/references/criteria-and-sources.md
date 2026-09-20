# Criteria and sources

## Documented behavior

- [GSAP ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/) documents `scrub`, pinning, refresh, callbacks, and cleanup concepts for GSAP implementations.
- [MDN: HTML video](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) documents media loading, playback, dimensions, and accessibility-related attributes.
- [MDN: Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) documents Canvas 2D capabilities.
- [MDN: `requestAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame) documents display-timed callbacks and the timestamp used for frame-rate-independent updates.
- [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) documents the user preference query.
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) supplies the accessibility criteria for keyboard access, meaningful sequence, focus, and animation from interactions.

## Engineering heuristics

The renderer decision table, nearby-frame preload order, finite pinning rule, and specific breakpoint test set are engineering heuristics. Adapt them to the content and prove behavior in the rendered page.

## Source lineage

This Skill is a substantial adaptation of `scroll-scrubbed-visual-sequence` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation removes demo coupling, adds authorization and evidence boundaries, and strengthens failure, cleanup, and semantic fallbacks for ChatGPT Work.

