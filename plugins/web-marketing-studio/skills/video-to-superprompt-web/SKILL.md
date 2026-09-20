---
name: video-to-superprompt-web
description: Analyze an uploaded or linked screen recording, motion reference, product demo, or website video and turn it into an evidence-based, implementation-ready web prompt. Use for UI structure, animation, transitions, scroll behavior, assets, responsive behavior, or recreation briefs; do not use when no video or time-based frame sequence is available.
---

# Video to Web Superprompt

Convert what the video actually shows into a prompt a web builder can execute without pretending that hidden implementation details were observed.

## Establish the boundary

Determine:

- the accessible source: uploaded video, linked video, frame sequence, or screen recording;
- the requested relationship: faithful rebuild of owned or authorized work, functional reconstruction, or original adaptation;
- the target: page, application flow, component, animation system, or asset pack;
- the intended framework and delivery format when supplied.

If the media is inaccessible, request the file, a public URL, or a timestamped contact sheet. Do not invent scenes from a title or thumbnail.

For third-party references, reproduce general behavior and high-level visual grammar while changing source identity, proprietary copy/assets, and distinctive signature composition. Use `reference-originality-web` when the user wants an explicit comparison.

## Inspect the source efficiently

Use the capabilities available in ChatGPT Work:

1. Inspect the original file or URL when accessible.
2. If a code runtime and FFmpeg are available, record duration, dimensions, frame rate, and codec with `ffprobe`, then extract representative frames with timestamps.
3. Select frames around meaningful beats: initial state, navigation changes, section entrances, pinned or scrubbed sequences, mode changes, interaction feedback, and final state. Uniform sampling alone can miss fast transitions.
4. For long recordings, create a coarse pass first, then a dense pass around the important intervals.
5. Inspect audio or narration only when it affects the experience. State when audio was not available or not analyzed.

Keep temporary extraction files out of the final deliverable unless the user asks for an evidence pack.

## Build a timestamped evidence map

Record observations before writing the prompt:

| Time | Observed state or change | Confidence | Implementation inference |
|---|---|---|---|
| `00:00.0` | Visible layout, content, and state | High/medium/low | Plausible mechanism, labeled as inference |

Use direct language:

- **Observed:** visible in one or more frames.
- **Inferred:** a likely implementation that could produce the behavior.
- **Unknown:** not visible or not measurable from the supplied media.

Do not claim a library, easing curve, breakpoint, shader, DOM structure, or scroll API was used unless source code or other evidence confirms it.

## Analyze the experience in layers

- **Purpose and sequence:** user goal, story arc, screen or section order, and transition between states.
- **Layout:** viewport framing, grid, alignment, sticky or fixed regions, overlays, density, and content hierarchy.
- **Motion:** trigger, affected properties, direction, duration estimate, overlap, staging, easing character, interruption, loop, and exit.
- **Interaction:** scroll, pointer, keyboard, touch, drag, hover, tap, focus, and state persistence.
- **Visual language:** typography roles, color relationships, surfaces, borders, shadows, texture, icons, and media treatment.
- **Assets:** visible images, videos, illustrations, 3D objects, masks, textures, fonts, icons, and copy.
- **Responsive implications:** what can reflow, simplify, become swipeable, or require a static fallback.
- **Accessibility and performance:** reduced motion, pause/stop controls where required, keyboard paths, readable contrast, loading strategy, rendering cost, and fallbacks.

## Choose mechanisms conservatively

Recommend the simplest mechanism that can reproduce the observed behavior:

- CSS transitions or keyframes for local state changes and simple loops;
- Web Animations API for programmatic timelines tied to DOM elements;
- Intersection Observer for visibility-triggered work;
- `requestAnimationFrame` for continuous JavaScript rendering that genuinely needs per-frame updates;
- a justified motion library for orchestration, interruption, or scroll timelines already used by the project;
- canvas or WebGL only when the reference depends on rendering that DOM/CSS cannot reasonably provide;
- `video.currentTime` scrubbing only when the reference visibly behaves like a frame sequence or scrubbed video.

Label these as implementation choices, not discoveries from the video.

## Produce the asset map

For each required asset, state:

- visible role and timestamp;
- supplied filename or URL when known;
- reuse permission or provenance status when known;
- required replacement or generation prompt;
- dimensions, crop, transparency, loop, or poster requirement;
- fallback when the asset is unavailable.

Never convert a reference logo, commercial image, or source copy into a production asset without authorization.

## Write the superprompt

Default to one paste-ready fenced `text` block after a compact evidence summary. Include:

1. target experience and reference boundary;
2. known inputs and unresolved assumptions;
3. route, viewport, and content scope;
4. global design language;
5. section-by-section or state-by-state anatomy;
6. motion and interaction specifications with triggers and exits;
7. asset map and generation/replacement needs;
8. responsive behavior;
9. accessibility and reduced-motion behavior;
10. performance constraints and cleanup expectations;
11. technical choices and prohibited shortcuts;
12. observable acceptance tests tied back to timestamps.

For every major beat, specify purpose, layout, visible content, observed transition, proposed mechanism, responsive behavior, and fallback. Be concrete enough to build, but do not inflate the prompt with repeated adjectives.

## Verify before delivery

- Every important claim maps to a frame, time range, source file, or explicit inference.
- Asset paths and URLs exist or are labeled `[NEEDS ASSET]`.
- The prompt distinguishes faithful behavior from original adaptation.
- Mobile, keyboard, reduced motion, loading, and static fallbacks are covered.
- No unobserved library, exact duration, breakpoint, or effect is presented as fact.
- Acceptance tests cover the beginning, at least one transition, the main interaction, and the final state.

## Output modes

- **Prompt only:** evidence summary plus one paste-ready prompt.
- **Implementation brief:** prompt plus build sequence and QA checklist.
- **Evidence pack:** timestamp table, selected frames, asset map, and prompt.
- **Implementation:** perform the requested build after the prompt, then verify against the timestamp map.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when explaining the workflow or making current technical claims.
