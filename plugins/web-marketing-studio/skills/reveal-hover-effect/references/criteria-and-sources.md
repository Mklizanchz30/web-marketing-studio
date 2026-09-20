# Criteria and sources

## Documented behavior

- [MDN: `mask-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image) documents image and gradient masks.
- [MDN: `radial-gradient()`](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient) documents radial gradient syntax used for the feathered reveal.
- [MDN: `requestAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame) documents display-timed callbacks.
- [MDN: pointermove](https://developer.mozilla.org/en-US/docs/Web/API/Element/pointermove_event) documents Pointer Events coordinate input.
- [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) documents the motion preference query.
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) supplies criteria for content on hover or focus, keyboard operation, focus, pointer cancellation, and non-text alternatives.

## Design heuristics

The radius, easing, and mask-stop values are starting points from the source effect. They are not browser or accessibility requirements. Tune them against component size, image detail, and interaction intent.

## Source lineage

This Skill is a substantial adaptation of `reveal-hover-effect` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation removes demo assets, narrows the effect boundary, and adds evidence, alternative-input, failure, and lifecycle guidance for ChatGPT Work.

