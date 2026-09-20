# Criteria and sources

Use these sources to explain the basis for a recommendation. Recheck current product behavior when a task depends on a particular model or ChatGPT surface.

## Evidence-backed criteria

### Domain-specific, task-complete UI instructions

**Criterion:** Define the audience, domain, real workflow, complete controls and states, responsive stability, and verification expectations instead of requesting a generic attractive interface.

**Source:** [OpenAI: Frontend prompt instructions](https://developers.openai.com/api/docs/guides/frontend-prompt).

This supports task-specific prompts, real content and assets, complete states, stable layouts, and verification. Individual visual prohibitions in that guide are model-steering defaults, not universal laws of design; override them when the existing system or user brief requires a different result.

### Accessibility requirements

**Criterion:** Include semantic structure, keyboard access, visible focus, sufficient contrast, labels and instructions, error identification, target sizing, text alternatives, and motion accommodations.

**Source:** [W3C: Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/).

A prompt can require these outcomes but cannot prove conformance. The implementation still needs keyboard, screen-reader, zoom, contrast, and responsive testing.

### Plain, audience-centered content

**Criterion:** Use familiar words, organize around the reader's task, and make instructions actionable.

**Source:** [Digital.gov: Plain language guide](https://digital.gov/guides/plain-language).

## Design heuristics that require judgment

The following are useful defaults, not standards:

- one dominant task per screen;
- a small number of coherent visual roles;
- changing one decision family at a time during iteration;
- avoiding decorative components that do not support hierarchy or interaction;
- using semantic tokens instead of prescribing every pixel;
- limiting concept sets to two or three meaningfully different directions.

Explain the tradeoff and validate the chosen direction with representative content, target viewports, and user tasks.

## Source lineage

This skill is a substantial adaptation of `design-first-ui-prompting` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. It adds web-app states, responsive behavior, accessibility, reference boundaries, acceptance checks, and ChatGPT Work/Sites compatibility.
