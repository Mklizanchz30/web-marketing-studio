# Criteria and sources

## Evidence-backed criteria

### Work from accessible source files

**Criterion:** Use the attached source file and provide explicit output structure and review criteria; report what was created and checked.

**Source:** [OpenAI: Work with files](https://learn.chatgpt.com/docs/artifacts-viewer).

This supports a file-first workflow in ChatGPT Work. It does not guarantee that every video codec can be previewed directly, so use frame extraction or ask for an alternate file when needed.

### Inspect video metadata and frames reproducibly

**Criterion:** Record media metadata before analysis and use documented FFmpeg filters for frame selection or extraction when the runtime supports them.

**Sources:**

- [FFmpeg: ffprobe documentation](https://ffmpeg.org/ffprobe.html)
- [FFmpeg: filter documentation](https://ffmpeg.org/ffmpeg-filters.html)

Frame sampling is evidence collection, not proof of the original implementation. Fast transitions can fall between sampled frames.

### Implement video with explicit behavior and fallbacks

**Criterion:** Specify sources, poster, preload behavior, controls, captions or text alternatives where applicable, and fallback content.

**Source:** [MDN: The video element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video).

### Control motion and autoplay-like movement

**Criterion:** Provide reduced-motion behavior and a way to pause, stop, or hide qualifying moving content when WCAG requires it.

**Sources:**

- [W3C: WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [W3C: Understanding Pause, Stop, Hide](https://www.w3.org/WAI/WCAG21/Understanding/pause-stop-hide)
- [W3C: Using `prefers-reduced-motion`](https://www.w3.org/WAI/WCAG21/Techniques/css/C39.html)

## Analysis heuristics

These practices improve coverage but are not standards:

- coarse sampling followed by dense sampling around transitions;
- a timestamped observation/inference table;
- choosing the simplest implementation mechanism that matches the visible behavior;
- mapping acceptance tests back to specific moments in the reference;
- treating exact timing estimates from a screen recording as approximate unless measured.

## Source lineage

This skill is a substantial adaptation of `video-to-superprompt` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. It removes dependence on a specific local browser, adds ChatGPT Work fallbacks, separates observation from inference, and adds provenance, accessibility, and verification boundaries.
