---
name: web-animation-performance
description: Diagnose, fix, and verify web animation performance, offscreen work, long-session slowdown, and cleanup risks in attached code, a Site, or an accessible page. Use for janky motion, high CPU/GPU use, canvas or WebGL loops, CSS animations, GSAP, timers, observers, route leaks, or reduced-motion issues; do not use for purely aesthetic motion critique.
---

# Web Animation Performance

Measure the real experience when possible, identify the owner of the work, make the smallest effective change, and repeat the same test. Do not claim a performance improvement from source inspection or a successful build alone.

## Confirm the task mode

- **Diagnose:** inspect, measure, explain causes, and recommend fixes without editing.
- **Fix:** inspect, implement, and verify the requested changes.
- **Source-only review:** use when no runnable page or browser instrumentation is available; label all conclusions accordingly.

Record the exact route or file, viewport, device assumptions, interaction sequence, and test duration. Preserve unrelated user changes.

## Use an evidence ladder

State the strongest evidence available:

1. **Runtime trace:** browser performance recording, frame timing, long tasks, paint/layout evidence, memory or allocation data, and reproducible interaction.
2. **Runtime observation:** animation state, DOM/canvas counts, page visibility, observer state, debug markers, route cycles, or bounded sampling.
3. **Source review:** code paths and cleanup risks only.

Never report source review as a measured speedup. When a metric is unavailable, say so and use the next evidence level.

## Establish a repeatable baseline

When a runnable page is available:

1. Load a fresh session and wait for the same settled state.
2. Test at least one representative desktop viewport and one mobile viewport when the layout changes.
3. Exercise the reported path: initial load, scroll, hover/drag/tap, modal or route change, background/foreground, and return.
4. Sample the top, middle, and lower page on long documents.
5. For long-session or leak reports, use a bounded idle interval and repeated route/component mount cycles.
6. Record console errors and the visible behavior before changing code.

Capture only metrics the environment can actually expose. A tab crash or rising counter is evidence of a problem, not proof of a particular cause until isolated.

## Find continuous and expensive work

Search attached code or the Site for:

- CSS animations and transitions, including `::before` and `::after`;
- Web Animations API instances;
- `requestAnimationFrame`, recursive timers, intervals, and debounced loops;
- scroll, pointer, resize, visibility, and global listeners;
- `IntersectionObserver`, `ResizeObserver`, and `MutationObserver`;
- GSAP timelines/tweens, motion libraries, and scroll plugins;
- canvas, WebGL, Three.js, particle, shader, and physics loops;
- video, audio, animated images, and frame-sequence scrubbing;
- blur, backdrop-filter, large shadows, masks, filters, and oversized fixed layers;
- async asset loaders that may finish after unmount;
- repeated component mounts or route changes without symmetrical cleanup.

Identify the smallest component, hook, stylesheet, or renderer that owns the work.

## Fix in priority order

### 1. Stop duplication and leaks

- cancel every scheduled RAF before restart and on teardown;
- clear timers and intervals;
- remove listeners with the same function reference and options;
- disconnect observers and subscriptions;
- kill owned timelines and animations;
- stop media streams and pause detached media;
- dispose textures, geometries, materials, render targets, and renderers owned by the component;
- guard async completion after disposal and release late-loaded resources;
- make React effects safe under development remount behavior.

### 2. Stop work when it cannot help the user

- use `IntersectionObserver` to pause decorative or nonessential offscreen work;
- use the Page Visibility API for background-tab behavior that `IntersectionObserver` does not cover;
- pause CSS animation tracks, including animated pseudo-elements;
- cancel JavaScript render loops rather than hiding only their canvas;
- resume without spawning a second loop;
- cap elapsed delta after a pause so physics or scroll state does not jump.

Do not pause essential progress, media, or state synchronization without understanding product behavior.

### 3. Reduce per-frame cost

- prefer `transform` and `opacity` when they produce the required effect;
- avoid animating layout or paint-heavy properties unless the measured design requires them;
- reduce simultaneous blur, backdrop-filter, large shadow, mask, and full-screen repaint work;
- cap canvas/WebGL pixel ratio and scale particle, post-processing, or physics quality to device conditions;
- avoid forcing layout by interleaving DOM reads and writes;
- use the RAF timestamp for time-based motion and high-refresh displays;
- use `will-change` sparingly and remove it when no longer useful.

### 4. Respect user preference and interruption

- implement `prefers-reduced-motion` behavior that preserves meaning without unnecessary movement;
- provide pause/stop controls for qualifying persistent or auto-updating motion;
- ensure focus, keyboard use, and touch do not depend on animation completing;
- keep transitions interruptible where the interaction can reverse or change quickly.

## Verify with the same scenario

Repeat the baseline route, viewport, interaction sequence, wait time, and route cycles.

Verify:

- visible motion still communicates the intended state;
- decorative offscreen work is paused or absent;
- CSS, WAAPI, RAF, canvas/WebGL, timers, and media are each checked through the mechanism that owns them;
- returning onscreen resumes once, without speed-up or duplicate loops;
- background/foreground and reduced-motion behavior work;
- component and route cycles return DOM/canvas/media counts to a stable baseline, allowing explained app behavior;
- no fresh console errors, broken interactions, or layout regressions appear;
- project checks pass when code was changed.

If heap or allocation tools are unavailable, report that memory leakage was not proven or cleared. Stable observable counts and correct cleanup reduce risk but are not a heap proof.

## Report directly

Lead with the outcome, then provide:

1. tested scope and evidence level;
2. baseline findings;
3. root causes tied to owners;
4. changes made or recommended;
5. before/after evidence using the same scenario;
6. checks run and remaining limitations.

Use exact measurements only when captured. Prefer `not measured` to an invented FPS, CPU reduction, or memory improvement.

## Common failure modes

- Removing all motion to make a test pass.
- Pausing a whole page when only one effect is expensive.
- Assuming CSS `animation-play-state` stops JavaScript or WebGL loops.
- Assuming background-tab RAF throttling handles offscreen work in the active tab.
- Adding `will-change` everywhere.
- Testing only the hero of a long page.
- Using a screenshot or successful build as performance evidence.
- Running unbounded stress tests or attributing a crash without isolation.
- Fixing symptoms in a child element while the parent loop continues.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when explaining the technical basis or when browser behavior may have changed.
