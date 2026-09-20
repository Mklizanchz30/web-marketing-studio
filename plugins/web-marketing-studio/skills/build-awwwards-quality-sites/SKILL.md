---
name: build-awwwards-quality-sites
description: Art-direct and implement distinctive, premium, motion-led marketing, editorial, portfolio, and landing websites. Use when the user asks for an Awwwards-quality, cinematic, high-concept, interactive, or visually exceptional site; treat the phrase as a quality target, never as an award claim.
---

# Build Awwwards-Quality Sites

Build a complete site whose concept, typography, media, layout, and motion express one coherent idea. Preserve the user's product, content, platform, and conversion goal. Do not turn a narrow edit into a redesign.

## Establish the direction

Inspect the supplied brief, current site, brand assets, screenshots, recordings, and code before proposing a direction. Extract principles from references—hierarchy, pacing, contrast, composition, material, and motion—without copying their identity, copy, assets, or source.

Write a compact internal direction before implementation:

- visual thesis and intended audience response;
- primary page goal and action;
- hero focal element;
- type roles, palette, spacing, and shape language;
- section sequence and narrative;
- media and provenance plan;
- motion narrative and reduced-motion state;
- rendering stack, including whether WebGL is justified.

Use `$reference-brand-worlds-web` when several references must become an original design world. Use `$reference-originality-web` when similarity risk needs a dedicated audit. Apply `$no-ai-design-slop` as the implementation quality gate.

## Build an honest asset system

- Prefer supplied, original, generated-for-purpose, or properly licensed media. Record provenance.
- Do not present generated people, fictional testimonials, logos, metrics, awards, clients, or partnerships as real evidence.
- Use real product or service imagery when the page depends on proof. Do not substitute decorative mockups for functionality.
- Give every image a deliberate crop, focal point, responsive size, loading strategy, and appropriate alternative text.
- Preserve a complete static composition when media, JavaScript, animation, or WebGL is unavailable.

## Compose the first viewport

The first viewport must explain what the site is, establish its visual idea, and expose the primary action. Make it the strongest authored moment without delaying access to navigation, copy, or controls.

Use one dominant focal device: art-directed media, type composition, restrained interaction, video, or a justified 3D scene. Avoid stacking effects that perform the same decorative job.

## Choreograph motion

- Motion must explain hierarchy, continuity, causality, depth, or narrative progression.
- Use CSS for simple local states. Use a timeline or scroll system only when coordination requires it.
- Choose one owner for each animated property and one smooth-scroll engine at most.
- Keep scroll position, not wheel delta or elapsed time, as the source of truth for scrubbed sequences.
- Do not split semantic links or meaningful inline markup to create word effects.
- Under `prefers-reduced-motion: reduce`, remove nonessential scrubbing, pinning, parallax, and trailing motion; render a designed stable state.
- Keep keyboard, touch, coarse-pointer, focus, visibility-change, and interruption behavior complete.

Use the specialized scroll Skills in this plugin when the requested mechanism matches them. Use `$web-animation-performance` when the task includes jank, offscreen work, or cleanup risk.

## Add WebGL only when it earns its cost

Use WebGL or Three.js only when spatial depth, material response, displacement, or a real 3D camera supports the central idea. Keep semantic content outside the canvas. Cap device pixel ratio, pause offscreen and hidden work, avoid per-frame allocation, provide a poster, handle failure, and dispose every owned resource.

## Complete the site

Do not stop at a hero concept. Include the sections, navigation, conversion path, forms or controls, error states, final action, and footer required by the user's goal. Resolve desktop and mobile composition independently rather than collapsing desktop into one long generic stack.

Reject:

- copied reference identity or layout;
- unsupported award or recognition claims;
- generic gradients, glass, bento grids, icon tiles, or motion used by reflex;
- fake proof and ornamental logo walls;
- hidden-at-rest content that fails when scripts do;
- continuously animated offscreen work;
- visual polish that obscures weak copy, unclear actions, or broken states.

## Verify before handoff

Run the production build and the project's checks. Inspect the rendered result at relevant desktop and mobile widths. Verify keyboard order, visible focus, touch behavior, 200% zoom or equivalent reflow, reduced motion, media fallbacks, JavaScript failure behavior where practical, cleanup, and console output.

Report the implemented concept, asset provenance, motion stack, WebGL decision, checks run, and remaining limitations. Never claim award recognition or measured performance without evidence.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when explaining the quality bar, accessibility, performance, or source lineage.

