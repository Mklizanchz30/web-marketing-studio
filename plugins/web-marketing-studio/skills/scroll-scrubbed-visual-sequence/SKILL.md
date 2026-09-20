---
name: scroll-scrubbed-visual-sequence
description: Build reversible scroll-controlled visual transformations with a sticky or pinned stage and normalized progress using video, image sequences, canvas, SVG, DOM, or justified WebGL. Use for product assembly, before-and-after, interface walkthroughs, object rotation, diagrams, or photo sequences that must track native scrolling in both directions.
---

# Scroll-Scrubbed Visual Sequence

Turn one visual transformation into a deterministic scroll instrument. Keep the document usable without motion and keep the content independent of the renderer.

## Define the states first

List the visual states, copy stops, entry state, exit state, poster, and reduced-motion state before coding. Expose configuration for scroll distance, frame count or duration, crop, focal point, copy stops, overlay strength, and smoothing.

Use one normalized progress value from 0 to 1. Native scroll position is the source of truth. Never use wheel delta, autoplay, or elapsed time as the state source for a scrubbed sequence. The same scroll position must reproduce the same frame when moving forward or backward.

## Choose the least expensive suitable renderer

- **DOM/SVG:** diagrams, cards, UI states, accessible text, and vector transitions.
- **Video:** continuous photographic sequences; encode frequent keyframes and coalesce seeks.
- **Image sequence:** exact art-directed frames; load the current and nearby frames before the full set.
- **Canvas 2D:** procedural drawing or compositing; cap device pixel ratio and redraw only when progress changes.
- **WebGL:** depth, lighting, or real 3D camera behavior that cannot be achieved economically otherwise; provide a poster and dispose resources.

Keep essential headings, instructions, captions, and actions in semantic HTML rather than baking them into frames.

## Build the stage

1. Keep the section in normal document flow and give it finite scroll distance.
2. Use a sticky stage or a bounded pin that releases before the following section.
3. Calculate progress from measured section geometry and clamp it to 0–1.
4. Map progress to the renderer without easing first; add restrained smoothing only after correctness.
5. Refresh measurements after fonts, responsive images, and intrinsic media sizes settle.
6. Schedule reads and writes through a single animation-frame update.
7. Destroy listeners, observers, frames, media requests, triggers, and renderer resources on route change or unmount.

When the project already uses GSAP or requires coordinated pinning, use ScrollTrigger with `scrub`, `invalidateOnRefresh`, and owned cleanup. Do not add GSAP for a simple effect that a small dependency-free implementation can handle.

## Handle media and failure

- Reserve aspect ratio and keep a poster visible until the first valid frame paints.
- Clamp frame indexes and media time.
- Coalesce video seeks and discard stale image loads during fast scrolling.
- Pause decoding and rendering offscreen or while the document is hidden when that does not break state.
- Preserve the subject through deliberate `object-fit`, `object-position`, and mobile crops.
- If media or script fails, show a meaningful static state and keep all text and actions available.

## Preserve access

Do not trap scrolling, hijack the wheel, move keyboard focus, or require precise pointer input. If the sequence communicates ordered information, expose the same information as semantic text or an ordered list.

Under `prefers-reduced-motion: reduce`, remove pinning and scrubbing, restore ordinary document flow, and render the selected stable frame. Do not merely accelerate the animation.

## Verify

Test forward and reverse scroll, fast jumps, resize while active, deep-link or reload at an internal scroll position, missing or delayed media, reduced motion, keyboard order, 200% zoom, touch, route cleanup, and console errors. Inspect at representative mobile, tablet, and desktop widths.

Report the renderer, progress mapping, media strategy, fallback, reduced-motion behavior, and checks run. Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when explaining implementation requirements or source lineage.

