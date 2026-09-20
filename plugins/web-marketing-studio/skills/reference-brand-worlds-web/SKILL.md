---
name: reference-brand-worlds-web
description: Create original web-ready brand directions, campaign worlds, or image-generation prompts from supplied visual references without copying the source identity. Use for moodboards, key visuals, art direction, multi-brand concept sets, or reference-informed website imagery; do not use for legal clearance or exact replication of a third-party brand.
---

# Reference-Informed Brand Worlds for Web

Turn references into a new visual system with its own meaning, identity, and composition. Treat references as evidence of desired qualities, not as templates to trace.

## Inspect and label the inputs

View every supplied image before proposing or generating anything. Assign each a role, for example:

- `Reference 1 — atmosphere and material`
- `Reference 2 — composition and density`
- `Reference 3 — current concept to preserve`
- `Brand assets — exact owned elements`

Record what the user owns, has permission to reuse, wants preserved, and wants changed. Do not move third-party reference images into reusable plugin assets or imply permission that was not supplied.

If the user asks for finished imagery, use the available image-generation tool and follow its reference-image and save rules. If the user asks only for prompts or art direction, do not generate assets unasked.

## Choose a relationship mode

Do not assign fake numerical similarity percentages. Choose and state one qualitative mode:

- **Principle-only:** retain abstract mood, contrast, density, material, or pacing; change the visual identity and composition completely.
- **Related family:** retain a selected set of high-level relationships while creating a new palette, subjects, typography, environment, and arrangement. Default for "inspired by, not copied."
- **Close study:** use only for the user's own or authorized work. Preserve more of the system while still changing the requested elements and avoiding accidental source-brand residue.

If the request targets a third-party commercial identity, keep it in principle-only or related-family territory even when the user asks to get closer.

## Separate grammar from identity

Create two lists before prompting.

### Transferable visual grammar

- emotional temperature and narrative tone;
- depth, density, scale contrast, and rhythm;
- medium, texture, lighting, and material qualities;
- palette relationships rather than sampled swatches;
- type roles and placement logic rather than copied letterforms;
- balance of people, product, architecture, nature, and negative space;
- motion or sequencing principles when the output is for a website.

### Source-specific elements to replace

- names, logos, wordmarks, slogans, proprietary icons, packaging, and product shapes;
- recognizable people, poses, wardrobe, choreography, or scene staging;
- distinctive motif combinations and object arrangements;
- source copy, numbers, interface data, and photography;
- a recognizable foreground/background silhouette or signature composition;
- exact type treatment, palette, crop, or texture stack when their combination identifies the source.

The distinction is a creative risk-control method, not a legal ruling.

## Define the new brand before the image

Specify:

- exact name and spelling;
- audience, offer, and promise;
- emotional territory;
- new environment;
- human behavior or ritual;
- one ownable motif;
- web placement: hero, section backdrop, campaign card, social crop, or texture;
- required safe areas and responsive crops;
- whether typography belongs in the generated image or in HTML/CSS.

When exact text matters, prefer generating an image plate without text and typesetting the wordmark in code or a design tool. If text is generated inside the image, inspect spelling, count, placement, and legibility before accepting it.

## Build distinct concept sets

For a multi-direction set, keep only the constraints that must unify the campaign, such as aspect ratio, medium, or emotional temperature. Vary each concept across meaning, environment, subject action, motif, composition, and type logic.

Use a matrix:

| Direction | Brand promise | World | Human ritual | Ownable motif | Composition | Type role |
|---|---|---|---|---|---|---|

Reject color swaps and renamed copies. Each direction must remain recognizable in grayscale and without its name through composition and motif, while still belonging to the requested family.

## Write one prompt per concept

Use this spine and adapt it to the image tool:

```text
OUTPUT
- Asset type, aspect ratio, target web placement, and safe areas.

REFERENCE ROLES
- Identify each input and the qualities to study.

NEW BRAND
- Exact name if text is required, audience, offer, promise, and emotional territory.

ORIGINAL WORLD
- New environment, subjects, action, ritual, and ownable motif.

VISUAL GRAMMAR TO CARRY
- Selected high-level relationships: medium, depth, density, lighting, palette relationship, and type scale.

COMPOSITION
- New focal hierarchy, camera/framing, spatial arrangement, negative space, and responsive crop plan.

TEXT
- Exact text once, or explicitly no embedded text and reserve a typesafe area.

REPLACE
- Source logos, names, people, objects, copy, letterforms, motif arrangement, and signature composition.

QUALITY CHECKS
- Brand meaning is visible; no extra marks; usable crop; correct aspect; materially distinct identity.
```

Avoid vague commands such as "same style" or "85% similar." Name the specific transferable qualities and the specific elements that must change.

## Iterate surgically

When revising:

1. keep the accepted brand meaning and successful elements;
2. name the single decision family to change;
3. restate the reference boundary;
4. generate a new version without overwriting an accepted one;
5. compare the result against both the brief and source-specific exclusion list.

Do not solve resemblance risk by recoloring alone. Change the subject, arrangement, motif, typography, and narrative relationship that creates the overlap.

## Validate the output

- The new brand has its own meaning and visual anchor.
- No source logo, slogan, packaging, people, or proprietary data remains.
- The composition and motif arrangement are materially new.
- Embedded text, if any, is exact, singular, and legible.
- Web safe areas and alternate crops are viable.
- Different concepts are meaningfully distinct from one another.
- The result does not claim a measurable similarity score or legal clearance.

For commercial release involving recognizable third-party material, report the remaining provenance or clearance questions and recommend qualified review when risk is material.

## Output modes

- **Art-direction brief:** visual DNA, exclusion list, concept matrix, and recommended direction.
- **Prompt pack:** one complete prompt per concept plus web crop requirements.
- **Generated assets:** create, inspect, iterate, and hand off the selected outputs.
- **Website handoff:** prompts plus placement, crop, responsive, loading, and text-overlay guidance.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when explaining originality criteria or current image-generation capabilities.
