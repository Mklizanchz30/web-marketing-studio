# Criteria and sources

## Packaging sources

- [OpenAI: Build skills](https://learn.chatgpt.com/docs/build-skills) documents Skill structure, `SKILL.md`, optional resources, discovery, and validation expectations.
- [OpenAI: Package your plugin](https://developers.openai.com/plugins/build/plugins) documents plugin packaging and bundled Skills.

## Web-platform sources

- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) supplies accessibility requirements relevant to visual and interactive web techniques.
- [MDN: `requestAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame) documents frame callbacks and timestamps.
- [MDN: ResizeObserver](https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver) documents element-size observation.
- [MDN: `prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) documents the user preference query.

## Extraction heuristics

The mechanism sentence, mechanism/staging/incidental classification, one-mechanism-per-Skill rule, demo quality bar, and requirement to write failures before adjectives are authoring heuristics. They should improve reuse and testability but are not platform standards.

## Source lineage

This Skill is a substantial adaptation of `web-technique-to-skill` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. The adaptation removes repository-specific assumptions, prevents self-modification, aligns packaging with current OpenAI Skill guidance, and adds ChatGPT Work-compatible authorization and evidence levels.

