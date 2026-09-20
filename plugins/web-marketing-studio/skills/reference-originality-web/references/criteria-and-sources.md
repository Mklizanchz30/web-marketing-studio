# Criteria and sources

This audit framework is not legal advice. It identifies evidence and release risk so the user can make design decisions or seek qualified counsel.

## Evidence-backed distinctions

### Unprotected categories do not make a whole work free to copy

**Criterion:** Treat ideas, methods, names, short phrases, familiar symbols, and common design conventions differently from a source's particular text, imagery, media, and selection or arrangement.

**Source:** [U.S. Copyright Office: Circular 33, Works Not Protected by Copyright](https://www.copyright.gov/circs/circ33.pdf).

This supports filtering out generic similarities. It does not establish that a particular implementation is lawful.

### Websites contain separately analyzable content

**Criterion:** Audit website text, artwork, photographs, audiovisual material, and code or other authorship as specific artifacts instead of treating "the website" as one indivisible visual style.

**Source:** [U.S. Copyright Office: Circular 66, Copyright Registration of Websites and Website Content](https://www.copyright.gov/circs/circ66.pdf).

### Minor changes may not create a meaningfully new work

**Criterion:** Recoloring, cropping, renaming, or making small editorial changes is not a reliable originality remedy for copied material.

**Source:** [U.S. Copyright Office: Circular 14, Copyright in Derivative Works and Compilations](https://www.copyright.gov/circs/circ14.pdf).

### Trademark is a separate identity question

**Criterion:** Review source names, logos, wordmarks, and other source identifiers separately from copyright-oriented similarity.

**Source:** [USPTO: Trademark basics](https://www.uspto.gov/sites/default/files/documents/tm-basics-learn-fundamentals.pdf).

### Legal determinations require qualified analysis

**Criterion:** Report evidence and uncertainty; do not present an automated or visual audit as an infringement decision or legal clearance.

**Source:** [U.S. Copyright Office: Circular 17, Limitations on Information and Services Provided by the Office](https://www.copyright.gov/circs/circ17.pdf).

The Copyright Office itself notes limits on giving legal advice and comparing works. A product audit should be even more explicit about its limits.

## Audit heuristics

The severity rubric, category list, exact-evidence pairing, perceptual-match triage, and scope-bound verdicts are operational heuristics. Hash equality can prove identical bytes, but neither a perceptual score nor a percentage of visual similarity proves or disproves infringement.

For work outside the United States, verify the applicable country's copyright, trademark, design-right, advertising, and contractual rules.

## Source lineage

This skill is a substantial adaptation of `audit-reference-originality` from [MengTo/Skills](https://github.com/MengTo/Skills), used under the MIT License. It removes local-repository dependence, adds ChatGPT Work evidence modes, separates provenance from similarity, and makes every verdict scope-bound and non-legal.
