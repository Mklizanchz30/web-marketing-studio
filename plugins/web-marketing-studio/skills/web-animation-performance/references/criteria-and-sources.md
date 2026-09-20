# Criteria and sources

Recheck browser compatibility for the project's supported browsers before relying on a particular API.

## Evidence-backed criteria

### Prefer compositor-friendly properties when they fit

**Criterion:** Prefer `transform` and `opacity` for motion when they achieve the design; measure before relying on other properties, and use `will-change` sparingly.

**Source:** [web.dev: How to create high-performance CSS animations](https://web.dev/articles/animations-guide).

The source explains rendering stages and recommends profiling. It does not mean every transform animation is cheap; large layers, filters, images, and many simultaneous elements can still be expensive.

### Drive continuous JavaScript animation with frame time

**Criterion:** Use `requestAnimationFrame` for per-frame browser animation, use its timestamp so motion does not speed up on high-refresh displays, and cancel pending frames when the loop should stop.

**Sources:**

- [MDN: `requestAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame)
- [MDN: `cancelAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelAnimationFrame)

Browsers commonly pause RAF in hidden tabs, but that does not stop offscreen work while the tab is visible.

### Detect visibility for appropriate work gating

**Criterion:** Use `IntersectionObserver` for element/viewport intersection and the Page Visibility API for document visibility. Do not treat either as a universal performance fix.

**Sources:**

- [MDN: Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)
- [MDN: Page Visibility API](https://developer.mozilla.org/en-US/docs/Web/API/Page_Visibility_API)

### Respect reduced-motion preferences

**Criterion:** Offer a reduced-motion presentation that preserves meaning and avoids unnecessary nonessential motion.

**Sources:**

- [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)
- [W3C: WCAG 2.2](https://www.w3.org/TR/WCAG22/)

### Persistent movement may require user control

**Criterion:** Check whether moving, blinking, scrolling, or auto-updating content requires pause, stop, hide, or timing control.

**Source:** [W3C: Understanding Pause, Stop, Hide](https://www.w3.org/WAI/WCAG21/Understanding/pause-stop-hide).

## Diagnostic heuristics

The evidence ladder, top/middle/bottom sampling, bounded idle tests, route-cycle counters, offscreen-work target, and remediation order are engineering heuristics. They should be adapted to the product and verified under the same pre/post scenario.

Do not publish a claimed percentage improvement unless it was measured with a documented tool, scenario, sample, and comparison method.

## Source lineage

This skill is a substantial adaptation of `optimize-web-animations` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. It removes dependence on a specific browser product, adds evidence levels and web fallbacks, separates diagnosis from authorized edits, and tightens measurement claims.
