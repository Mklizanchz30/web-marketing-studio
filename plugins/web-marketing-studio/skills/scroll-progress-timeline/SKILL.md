---
name: scroll-progress-timeline
description: Turn an ordered process into a data-driven vertical or horizontal scroll story with a base line, progress fill, active steps, responsive collapse, semantic fallback, and reduced-motion behavior. Use for service processes, onboarding, checkout, roadmaps, recipes, case studies, histories, or narratives where progress should become visible while scrolling.
---

# Scroll Progress Timeline

Use one progress line to connect ordered information. The sequence must be complete, readable, and navigable before animation is added.

## Model semantic steps

Keep steps in structured data and render them as an ordered list with real headings. The line, dots, active state, and media enhance the list; they do not replace it. Use real anchors when users may jump to steps.

## Choose the layout from the content

- Use a left rail for long copy, uneven heights, or mixed media.
- Use centered alternation only when both sides have enough width and similar visual weight.
- Use a horizontal timeline only for short steps with keyboard-safe overflow.
- Use pinned chapters only when each step controls a distinct visual state and the pin can remain finite.
- Collapse to a single reading rail on narrow screens; do not preserve alternation at the expense of order.

## Measure the progress line

1. Render a quiet base line behind every point.
2. Place one fill line above it with the correct transform origin.
3. Measure from the center of the first point to the center of the last point.
4. Normalize the viewport anchor between those coordinates and clamp to 0–1.
5. Apply `scaleY(progress)` or `scaleX(progress)`.
6. Activate a step when the progress head crosses that step's measured center.
7. Recalculate after fonts, images, resizing, orientation changes, and relevant content mutation.

Batch geometry reads and DOM writes in one animation frame. Use IntersectionObserver for discrete entry states. Use normalized scroll measurement or GSAP ScrollTrigger when the line must fill continuously or coordinate pinned media.

## Handle state and navigation

Keep inactive steps readable. Use `aria-current="step"` only when the active item genuinely represents the current step; do not announce passive scroll updates with a live region. Preserve focus, add appropriate scroll margin for sticky headers, and update URLs or history only after an explicit user action.

If dots are interactive, render them as labeled links or buttons with visible focus. Never make a decorative dot the only control.

## Reduce motion

Under `prefers-reduced-motion: reduce`, remove scrubbed interpolation, blur, and pinning. Show the full line or stable reached states in ordinary document flow while preserving all content and controls.

## Verify

Test uneven card heights, long translations, missing media, different step counts, direct anchor navigation, fast forward and reverse scrolling, 200% zoom, keyboard order, reduced motion, delayed fonts and images, route cleanup, and console errors at representative mobile, tablet, and desktop widths. The active step and progress head must agree at every boundary.

Report the chosen layout, activation rule, responsive collapse, reduced-motion behavior, and checks run. Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when explaining implementation criteria or source lineage.

