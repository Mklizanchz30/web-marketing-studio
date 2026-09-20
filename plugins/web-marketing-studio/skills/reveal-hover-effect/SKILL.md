---
name: reveal-hover-effect
description: Build cursor-following spotlight reveals that expose a second aligned image through a feathered radial mask, with touch, keyboard, reduced-motion, and loading fallbacks. Use for hover-to-color, before-and-after, x-ray, material, texture, product-detail, or illustrated hero effects.
---

# Reveal Hover Effect

Build a local image reveal, not a page-wide cursor gimmick. Essential information must remain available without hover.

## Establish the contract

1. Prepare two images with identical dimensions, composition, crop, and focal point.
2. Keep the base image visible.
3. Stack the alternate image directly above it.
4. Apply a feathered radial CSS mask to the alternate image.
5. Track pointer coordinates in the component's local coordinate space.
6. Ease the rendered position and radius through one requestAnimationFrame loop.
7. Collapse the mask on pointer exit, pointer cancellation, and window blur.

Prefer CSS masks to per-frame canvas data URLs. Keep `object-fit` and `object-position` identical on both layers; small mismatches become obvious within the spotlight.

## Use deliberate defaults

| Parameter | Starting value |
|---|---|
| Desktop radius | 260 px |
| Compact radius | 140–220 px |
| Position easing | 0.10 |
| Radius easing | 0.14 |
| Full-opacity core | Through 40% of radius |
| Edge | Fully transparent at 100% |

Treat these as tuning heuristics. Keep the native cursor unless the design has a strong reason to replace it.

## Track safely

Convert `clientX` and `clientY` through `getBoundingClientRect()`. Page coordinates drift after scrolling. On the first pointer move, initialize the eased position under the pointer so the reveal does not sweep from the component center.

Run the animation loop only while the position or radius is unsettled. Recalculate local coordinates on scroll and resize while active. Use one state and one loop per component, and return a cleanup that removes listeners, disconnects observers, and cancels the frame.

## Preserve access and alternative input

- Default coarse pointers to the complete base image.
- If the alternate image carries unique information, add a labeled toggle or comparison control for touch and keyboard users plus a visible description.
- Keep the overlay decorative when both layers communicate the same subject.
- Do not reveal navigation, pricing, instructions, or required copy only through hover.
- Under `prefers-reduced-motion: reduce`, remove trailing interpolation and optional parallax. A direct reveal or stable toggle may remain if it does not cause motion discomfort.

## Handle performance and compatibility

Animate component-scoped custom properties from one requestAnimationFrame loop. Mask only the needed component, stop when idle, reserve image dimensions, use responsive sources, and test both `mask-*` and `-webkit-mask-*` behavior for supported Safari versions. Use `will-change` only on the masked overlay and only when justified.

## Verify

Check pixel alignment at every breakpoint, first entry, first move without entry, pointer exit, cancellation, window blur, scroll while hovered, resize, touch fallback, keyboard alternative, reduced motion, loading failure, idle-loop stop, route cleanup, and console output. Inspect the effect at representative mobile and desktop sizes.

Report the two-image contract, fallback behavior, accessibility alternative, and checks run. Read [references/criteria-and-sources.md](references/criteria-and-sources.md) for platform sources and lineage.

