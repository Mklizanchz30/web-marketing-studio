---
name: web-technique-to-skill
description: Turn a proven visual or interaction technique from working web code into a reusable Skill by isolating its mechanism, constraints, failure modes, verified stack, lifecycle, accessibility behavior, and optional demo. Use when an effective page, canvas scene, shader, scroll effect, layout system, or hover interaction should become reusable rather than remain trapped in one project.
---

# Web Technique to Skill

Start from working code and observed behavior, not from a style description. Extract one mechanism per Skill. Do not package an entire project's brand, client content, or unrelated effects.

## Define the mechanism

Write one sentence naming the condition that makes the effect work. It should remain true after changing the subject, palette, copy, and layout. If it does not, it describes staging rather than a reusable mechanism.

Search the target plugin or Skill collection for the nearest existing Skill. Extend the existing Skill when it already owns the mechanism; otherwise state the boundary against it in the new description.

## Verify the implementation stack

Inspect imports, renderer construction, contexts, and runtime behavior. Record separately:

1. runtime or framework;
2. renderer or browser API;
3. technique library, if any;
4. interface layer, when different from the effect layer.

Do not infer WebGL, shaders, Canvas, or Three.js from appearance. State notable absences when they prevent misuse.

## Separate mechanism from staging

Classify source material:

| Class | Destination | Examples |
|---|---|---|
| Mechanism | Skill instructions | state model, formulas, ordering, budgets, lifecycle |
| Staging | Optional demo | owned palette, copy, layout, atmosphere, art direction |
| Incidental | Exclude | project selectors, one-off paths, irrelevant component names |

Do not transfer client brands, licensed fonts, purchased imagery, third-party media, private data, or assets whose rights are unclear. Preserve only the smallest owned asset set needed to prove the mechanism.

## Capture the knowledge that code alone does not explain

For every important rule, state the failure it prevents. Carry verified numbers instead of adjectives: timing, easing, sizes, spacing, thresholds, device-pixel-ratio caps, frame budgets, instance counts, and formulas. Mark values that are starting heuristics rather than requirements.

Keep expensive gotchas, especially:

- color-space or tone-mapping mismatch;
- layout measured before fonts or media settle;
- stacking or clipping contexts;
- correct operations executed in the wrong order;
- browser-specific behavior;
- cleanup, remount, and background-tab failures.

State actual cost only after measurement. If measurement is unavailable, describe the suspected cost and evidence level without claiming a bottleneck.

## Include access and lifecycle

Specify semantics, keyboard and touch behavior, visible focus, meaningful alternatives, and reduced-motion presentation. A visual technique must have a designed stable state rather than disappearing.

For continuous work, define offscreen and document-hidden behavior, time-step clamping where relevant, device-pixel-ratio limits, resize handling, zero-size guards, cleanup, and resource disposal.

## Package the Skill

Create the smallest useful structure:

```text
<skill-name>/
  SKILL.md
  agents/openai.yaml
  references/criteria-and-sources.md
  demo/                     # only when visual proof materially helps
  assets/                   # only for necessary owned output assets
  scripts/                  # only for repeated deterministic work
```

Use lowercase hyphenated names. Keep `SKILL.md` focused on decisions and reusable workflow. Put detailed standards, provenance, parameter tables, or implementation notes in references. Do not add a README or changelog inside an individual Skill unless the packaging target requires it.

Create `agents/openai.yaml` with a clear display name, a 25–64 character short description, and a short default prompt that explicitly names `$skill-name`. Keep implicit invocation enabled unless the user asks for explicit-only behavior.

If a visual demo is necessary, make it self-contained or use the smallest justified local asset bundle. Show the mechanism on the first screen, expose only meaningful controls, preserve the approved owned staging, and identify the verified stack visibly. Do not weaken reference fidelity by replacing owned procedural assets with rough approximations.

## Validate

Use the available Skill initializer and validator when present. Inspect frontmatter, links, file names, placeholders, and UI metadata. Run any added scripts. When browser access is available, verify the demo at representative mobile and desktop sizes, exercise the complete interaction forward and backward, test reduced motion and keyboard behavior, and confirm a clean console.

If browser validation is unavailable, say that the result received source-only validation. Do not claim visual fidelity or working interaction from code inspection alone.

Preserve unrelated user changes. When working in a Git-backed target, stage and commit only the files created or changed for this Skill. When the user requested a plugin update, run plugin validation after Skill validation.

## Handoff

Report the mechanism sentence, skill boundary, verified stack, included resources, provenance, tests, and limitations. Read [references/criteria-and-sources.md](references/criteria-and-sources.md) for packaging sources and lineage.

