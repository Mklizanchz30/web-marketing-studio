---
name: design-first-ui-prompting-web
description: Turn a vague website or web-app idea into a precise, implementation-ready UI brief or generation prompt for ChatGPT Work, Sites, or a code-producing model. Use for new pages, redesigns, component flows, responsive behavior, design-system direction, or prompt refinement; do not use for image-only art direction or performance debugging.
---

# Design-First UI Prompting for Web

Translate intent into decisions a builder can implement and a reviewer can verify. Produce the smallest complete specification; do not bury the task in aesthetic adjectives.

## Establish the brief

Extract the available facts before proposing a design:

- product, service, or workflow;
- intended user and their primary task;
- page or screen type;
- success condition;
- supplied copy, data, brand assets, references, and design-system constraints;
- target surface, framework, breakpoints, and technical limits;
- required actions, states, and integrations;
- what must stay unchanged.

Separate supplied facts, design decisions, and unresolved assumptions. Ask only questions whose answers would materially change the result. When the user wants immediate progress, state compact assumptions and continue.

Use the user's language. Preserve exact copy only when the user marks it exact; otherwise improve it and flag substantive meaning changes.

## Convert references into usable direction

For each reference, state its role: layout, density, typography, color, imagery, motion, or interaction. Do not tell the builder to make the result merely "like" a reference.

Extract reusable principles and identify source-specific elements that must not be copied, including logos, branded copy, proprietary illustrations, distinctive compositions, and product data. If the user wants an originality audit rather than a design brief, use `reference-originality-web`.

## Make decisions in the right order

1. **User task and information architecture:** Define what the user must understand or complete and the content order that supports it.
2. **Interaction model:** Define controls, navigation, feedback, empty/loading/error/success states, and what changes after each action.
3. **Responsive structure:** Describe stacking, reflow, overflow, touch behavior, and priority changes at narrow and wide viewports. Do not reduce responsiveness to one mobile breakpoint.
4. **Visual system:** Specify typography roles, spacing rhythm, color roles, surfaces, borders, imagery, and icon treatment. Prefer semantic roles over arbitrary values unless a real design system supplies tokens.
5. **Motion:** Add motion only when it clarifies state, continuity, hierarchy, or feedback. Specify trigger, property, duration or spring character, interruption behavior, exit, and reduced-motion fallback.
6. **Implementation constraints:** Name the framework or libraries only when known or justified. Reuse the existing system before introducing a new dependency.
7. **Acceptance checks:** Turn subjective goals into observable checks across content, behavior, responsive layout, accessibility, and visual fidelity.

## Write the builder prompt

Use this structure and omit sections that genuinely do not apply:

```text
OBJECTIVE
- What to build, for whom, and the outcome it must support.

KNOWN INPUTS
- Supplied content, data, assets, brand rules, and reference roles.

USER FLOW
- Entry state, primary task, decisions, completion state, and recovery paths.

INFORMATION ARCHITECTURE
- Page or screen order and why each part exists.

LAYOUT AND RESPONSIVE BEHAVIOR
- Container/grid logic, hierarchy, density, reflow, overflow, and mobile priorities.

VISUAL SYSTEM
- Type roles, spacing rhythm, color roles, surfaces, imagery, and icons.

COMPONENTS AND STATES
- Components plus default, hover, focus, active, disabled, loading, empty, error, and success states as applicable.

MOTION
- Purpose, trigger, mechanism, timing, interruption, exit, and reduced-motion behavior.

CONTENT
- Final supplied copy or clearly marked draft copy. No unexplained lorem ipsum.

ACCESSIBILITY
- Semantics, keyboard path, focus, labels, contrast, targets, errors, alternatives, and motion controls.

TECHNICAL CONSTRAINTS
- Existing stack, reusable components, asset rules, data behavior, and prohibited dependencies.

ACCEPTANCE CHECKS
- Concrete desktop/mobile, interaction, content, and accessibility checks.

OUT OF SCOPE
- Explicit exclusions that prevent accidental expansion.
```

Make instructions internally consistent. A fixed card width cannot coexist with an incompatible narrow viewport; a hover-only affordance cannot be the only mobile path; an image-dependent message needs meaningful alternative text or adjacent copy.

## Control variation without losing coherence

When the user asks for alternatives, produce two or three genuinely different directions. Keep the user task and content constant, then vary a coherent decision family such as:

- editorial versus utilitarian density;
- image-led versus type-led hierarchy;
- quiet versus expressive motion;
- compact application shell versus spacious marketing composition.

Summarize the tradeoff of each direction. Do not create cosmetic color swaps and call them concepts.

For refinement, preserve accepted decisions and change only the requested decision family. Restate what stays fixed.

## Avoid common failures

- Do not invent requirements, brand facts, testimonials, data, integrations, or device capabilities.
- Do not specify fashionable decoration with no relationship to the domain or task.
- Do not default every page to a giant hero, nested cards, glassmorphism, purple gradients, decorative blobs, or excessive rounded containers.
- Do not use font names the project cannot license or load; describe a typographic role when the actual family is unknown.
- Do not use image generation for exact logos or production typography without verification.
- Do not prescribe exact pixel values everywhere when a token system and responsive constraints are more durable.
- Do not claim accessibility from a prompt alone; require implementation and testing.

## Output modes

- **Builder prompt:** one paste-ready prompt.
- **Design brief:** decisions, rationale, assumptions, and acceptance checks.
- **Direction set:** two or three alternatives with tradeoffs, then one recommended direction.
- **Implementation handoff:** brief followed by the requested implementation or file changes.

When explaining a recommendation, distinguish an evidence-backed standard from a design heuristic. Read [references/criteria-and-sources.md](references/criteria-and-sources.md) when the user asks for rationale or sources.

## Completion check

Confirm that the result names the user task, contains real or marked content, covers interactive states, defines responsive behavior, includes accessibility and reduced-motion expectations, preserves known constraints, and ends with observable acceptance checks.
