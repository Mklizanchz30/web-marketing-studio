---
name: reference-originality-web
description: Compare a website, page, interface, or motion experience with supplied references and produce an evidence-backed originality-risk audit. Use for copy, brands, numbers, images, assets, layout, interaction, video, or source residue; do not use as a substitute for legal advice or when no current work and no reference evidence are available.
---

# Reference Originality Audit for Web

Audit observable overlap, provenance, and release risk. Do not turn visual intuition into a legal conclusion.

## Preserve the task boundary

- If the user asks for an audit, inspect and report; do not edit the site unless asked.
- Use `overlap`, `originality risk`, `source residue`, or `red flag`. Do not declare plagiarism, infringement, fair use, or legal clearance.
- Pair every material finding with current-work evidence and reference evidence.
- Separate facts, inferences, and unavailable evidence.
- State the jurisdiction and ownership assumptions only when supplied.

If either the current work or the promised reference set is missing, request it or return `Blocked by missing evidence`. A homepage screenshot cannot clear an entire site or motion system.

## Build the evidence registry

Accept sources available in ChatGPT Work, including:

- current URLs, Sites, HTML/code archives, screenshots, exports, videos, and asset folders;
- reference URLs, screenshots, moodboards, videos, prompt packs, brand guides, and named creators;
- ownership, license, credit, or provenance records;
- version history or repository evidence when connected and authorized.

For every item record its label, location or URL, date or version when known, role, access status, and categories it can support. Prefer preserved task-time evidence over a live reference that may have changed.

Do not infer license or authorship from a filename.

## Inventory the current experience

Cover the checked scope across:

1. **Text:** headings, paragraphs, labels, CTAs, captions, metadata, alt text, and legal copy.
2. **Brands:** names, logos, wordmarks, proprietary icons, product names, people, companies, URLs, and partner claims.
3. **Numbers and data:** prices, percentages, dates, counts, metrics, plan structures, table values, and sample records.
4. **Images and media:** exact files, crops, generated derivatives, screenshots, people, poses, objects, audio, posters, and videos.
5. **Assets and code:** fonts, icon sets, textures, 3D models, downloads, library licenses, code bundles, and embedded source URLs.
6. **Structure:** section order, unusual composition, information hierarchy, navigation, and combinations of layout devices.
7. **Motion and interaction:** timing, shot order, transitions, pinned sequences, scroll effects, cursor behavior, shaders, and state changes.
8. **History:** renamed, recolored, cropped, hidden, deleted, or replaced material when history is available and within scope.

Inspect rendered output and source files when both exist. Hidden test fixtures or explicit forbidden-string tests are not automatically shipped violations; explain their context.

## Use deterministic checks as leads

When the runtime and files allow it, use:

- SHA-256 for exact file identity;
- dimensions, metadata, and byte size for asset triage;
- normalized text comparison for exact or near-exact phrasing;
- OCR for text embedded in images;
- perceptual hashes or image-difference methods for candidate visual matches;
- timestamped frame comparison for motion;
- DOM/component and asset-reference searches for source residue.

These methods produce leads, not automatic findings. Compression, resizing, common phrases, stock assets, and shared libraries can create misleading matches. Visually inspect every escalated candidate.

## Compare category by category

For each candidate overlap:

1. identify the current artifact and exact location;
2. identify the reference artifact and exact location;
3. describe what is observably the same;
4. describe material differences;
5. state provenance or permission evidence, or say it is unknown;
6. assign a release-oriented severity;
7. propose the smallest meaningful fix.

Use this severity rubric:

- **Block:** exact or near-exact third-party logo, asset, substantial copy, data, or media is shipped without confirmed authorization; or source-brand residue creates a clear identity problem.
- **High:** a distinctive combination of composition, subject, copy, identity, and motion remains strongly reference-specific even without an exact file match.
- **Medium:** localized or partial overlaps should be replaced or redesigned before a high-visibility release.
- **Low:** common conventions, generic patterns, or isolated weak similarities; document but do not overstate.
- **Not assessed:** evidence or access was insufficient.

Severity is a product-release heuristic, not a legal test.

Common elements such as dark backgrounds, large sans-serif headings, ordinary card grids, standard fade-ins, conventional footers, or familiar interface controls are not material findings by themselves. Escalate exact evidence or distinctive combinations.

## Recommend real fixes

- Rewrite source-like copy from the new audience, offer, and brand vocabulary.
- Replace names, URLs, logos, people, metrics, dates, plans, and legal text.
- License or create new imagery with a different subject, composition, staging, and motif system.
- Replace copied assets and document provenance.
- Re-cut video with new footage, shot order, timing, overlays, and audio.
- Redesign a distinctive sequence rather than merely recoloring it.
- Remove source residue from the current build and, only when explicitly requested, address history or published artifacts.

Do not recommend concealment, renaming, cropping, recoloring, or minor edits as a sufficient fix for an exact or distinctive copied element.

## Report the result

Lead with one scope-bound verdict:

- `Clear within checked scope`
- `Clear within checked scope with low-risk similarities`
- `Changes recommended`
- `Block release in checked scope`
- `Blocked by missing evidence`

Then provide:

1. scope and evidence registry;
2. red-flag table ordered by severity;
3. category pass table, including `Not assessed` rows;
4. provenance and history findings;
5. access gaps and remaining uncertainty;
6. prioritized fix plan;
7. explicit statement that the audit is not legal clearance.

Use side-by-side crops, exact excerpts within quotation limits, hashes, timestamps, or paths when they materially help verification. Do not overwhelm the report with screenshots of ordinary patterns.

## Completion check

- Every supplied reference form was inspected or marked inaccessible.
- The current rendered result and available source were checked.
- Text, brands, numbers, images/media, assets/code, structure, motion, and history were covered or marked `Not assessed`.
- Every material finding cites both sides of the comparison.
- Exact matches are distinguished from stylistic similarity.
- Permission and provenance are distinguished from visual difference.
- The verdict is limited to the checked scope.

Read [references/criteria-and-sources.md](references/criteria-and-sources.md) before explaining copyright or trademark rationale, and recheck the applicable jurisdiction for a high-stakes release.
