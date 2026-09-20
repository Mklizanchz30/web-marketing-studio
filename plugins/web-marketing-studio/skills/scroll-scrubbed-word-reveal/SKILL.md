---
name: scroll-scrubbed-word-reveal
description: Reveal marked-up text word by word as scroll progress advances while preserving semantic links, emphasis, responsive wrapping, natural reading order, and reduced-motion readability. Use for headlines, quotes, manifestos, product statements, or editorial passages where scrolling should pace comprehension rather than simulate typing.
---

# Scroll-Scrubbed Word Reveal

Make reading progress visible without replacing real text, flattening meaningful markup, or depending on a fixed line count.

## Preserve the source text

Keep one untouched semantic text source in the DOM. Traverse text nodes with `TreeWalker` and split only non-whitespace tokens. Skip scripts, styles, form controls, and elements marked not to split. Preserve whitespace nodes and inline elements such as links, emphasis, strong text, marks, and language spans.

Do not overwrite the container with `textContent` or generated `innerHTML`. Store enough original state to restore the subtree during cleanup. If generated visual tokens are hidden from assistive technology, retain an equivalent unsplit accessible copy.

Never split by rendered lines. Wrapping must remain free to change with width, language, zoom, and font loading.

## Map scroll progress to tokens

Use one normalized section-progress value from 0 to 1. Derive each token's local progress from its index and the total token count. Keep the scroll mapping linear; apply any easing only to the visual interpolation.

Expose opacity, blur, offset, overlap, and scroll span as configuration. Useful starting ranges are:

| Parameter | Starting range |
|---|---|
| Hidden opacity | 0.12–0.30 |
| Blur | 4–10 px |
| Vertical offset | 0.08–0.22 em |
| Reveal span | 120–220% of viewport |
| Token overlap | 10–30% |

Treat these as tuning heuristics, not fixed requirements. Scale scroll distance from content length and reading intent.

Use GSAP ScrollTrigger when the project already uses GSAP or needs shared timeline and refresh behavior. Otherwise use measured scroll progress with one requestAnimationFrame update. Do not add a typing cursor, autoplay, random delay, or scroll hijacking unless explicitly requested.

## Keep the passage readable

- Keep essential links usable throughout the relevant reading state.
- Style semantic accents on their source element rather than token numbers.
- Keep the final state identical to normal readable typography.
- Use real document flow; pin only for a short justified reading beat.
- Under `prefers-reduced-motion: reduce`, remove pinning, blur, transforms, and interpolation, and show every word immediately.
- Do not announce every token through a live region.

## Clean up and verify

Kill owned triggers, remove listeners, cancel frames, and restore the original subtree on route change or unmount. Refresh geometry after fonts load when start or end positions depend on text layout.

Test punctuation, repeated spaces, inline links and emphasis, long words, translations, dynamic text changes, 200% zoom, mobile and desktop widths, forward and reverse scrolling, reduced motion, JavaScript failure, keyboard focus, reading order, teardown, and console errors.

Report the tokenization approach, scroll mapping, accessible source, reduced-motion behavior, and checks run. Read [references/criteria-and-sources.md](references/criteria-and-sources.md) for implementation sources and lineage.

