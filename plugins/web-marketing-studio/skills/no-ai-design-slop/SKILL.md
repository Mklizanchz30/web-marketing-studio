---
name: no-ai-design-slop
description: Prevent and remove generic AI-style design defaults, incoherent visual choices, and established UI defects while creating or revising websites, apps, screenshots, mockups, and frontend code. Use as a passive quality gate or for an authorized cleanup; preserve the existing art direction instead of forcing a neutral redesign.
---

# No AI Design Slop

Judge the artifact, not whether AI created it. A technique is not slop by itself. Treat a choice as suspect when it is generic, repeated without purpose, conflicts with the local system, communicates nothing useful, or harms comprehension, trust, access, or task completion.

## Preserve scope and direction

Read the brief, current interface, design tokens, components, brand assets, and supplied references before changing anything. Identify the product, audience, primary task, primary action, content hierarchy, and visual thesis.

For a narrow edit, correct the requested surface without widening the task. For a formal read-only review, use `$audit-ai-design-slop`. For a full page or redesign, read [references/pattern-library.md](references/pattern-library.md) and apply only relevant patterns.

## Apply the quality gates

Check each new or changed decision:

- **System:** Does it inherit the established type, palette, spacing, radius, icon, and motion language?
- **Hierarchy:** Is the most important content or action obvious without decorative labels?
- **Composition:** Are alignment, proximity, overlap, negative space, and crops intentional at each viewport?
- **Typography:** Are roles readable and distinct without forced tracking, scale, or ornamental treatment?
- **Material:** Does every gradient, glow, blur, glass layer, border, shadow, and texture have a job?
- **Product truth:** Are copy, media, metrics, logos, testimonials, and states specific and honest?
- **Interaction:** Are required hover, focus, active, loading, empty, error, disabled, selected, and success states present?
- **Access and motion:** Do semantics, focus, contrast, reflow, touch, and reduced-motion behavior remain intact?

## Use the removal test

For each suspect element:

1. Name the exact pattern or component.
2. State the information, state, action, hierarchy, or brand role it provides.
3. Remove it mentally.
4. Delete or consolidate it if clarity improves without losing that role.
5. If deletion creates a real loss, make the smallest correction using the existing system.
6. Add a replacement only when the interface needs one.

Default to subtraction. Do not compensate for removing one effect by adding another.

## Protect useful character

Do not erase density, asymmetry, humor, expressive type, vivid color, or motion merely because it is unusual. Do not prescribe a new font, palette, layout, library, or art direction unless the user authorized a redesign. Do not turn every block into a card or every improvement into decoration.

Never invent customers, testimonials, ratings, metrics, awards, product screens, activity, or logos. Never expose essential information only through hover or motion.

## Verify the result

Inspect the rendered interface at relevant viewports. Confirm that text does not clip or overflow, controls remain labeled and reachable, focus is visible, required states work, the primary flow remains clear, and every decorative layer has a defensible role.

Report the material removals or corrections and the demonstrated reason for each. Do not return an AI-authorship guess or a generic taste score.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when distinguishing accessibility requirements from design heuristics.

