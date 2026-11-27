# Retrieval-first revision with a bounded scope

Use this reference for an open-book pack, a findability critique, or a substantial retrieval-focused restructuring. Apply only the layers covered by the task. A local wording fix does not require rebuilding a course or adding frontmatter.

## Choose the delivery layers

| Task scope | Useful design | Boundary |
|---|---|---|
| Local block or example | A term-led heading, clearer conditions, action steps, or one useful trap | Leave unrelated lectures and navigation alone |
| One lecture | Optional quick-lookup sheet, local dependency chain, selected examples, marked extensions at its end | A one-page sheet is a target only when chosen; keep the complete body and legible type |
| Full-course open-book pack | Optional master task-to-tool lookup, notation registry, lecture sheets, and lecture-ordered body | Keep the lecture-ordered body; separate lookup, extensions, or self-test volumes when the current user authorizes them |
| Full-course closed-book conceptual pack | Optional 3-part quick-lookup (contrast matrix, taxonomy cheat-sheet, acronym glossary), curated slide figures, and lecture-ordered body | Confirm optional companions (`quick-lookup`, `self-test`, `extensions`) upfront before building; never force an open-book formula index or unwanted self-test |

For compression, establish a baseline and budget using [compression-and-release.md](compression-and-release.md). Choose where navigation lives once; a separate lookup does not justify retaining the same inventory in the main file. Body definitions must remain sufficient without the lookup. Confirm with the user upfront which optional companion volumes (`quick-lookup`, `self-test`, `extensions`) are actually wanted for the current revision stage before generating them.

A lecture sheet can show core formulas with their assumptions, a dependency/assembly chain, and consequential distinctions. Select the formulas and traps from actual emphasis. No fixed count is required. If the chosen one-page format cannot remain readable, reduce duplication or simplify the navigation rather than hiding assessed content or shrinking the body.

Two complementary master-lookup architectures fit different exam formats:
- **Open-book task-to-tool lookup:** map a question or goal to a named tool, its conditions, guarantee type, and a clickable destination/page. A comparison of bounds should distinguish expectation, high-probability, finite-sample, and asymptotic statements.
- **Closed-book conceptual 3-part quick-lookup:** when the exam prioritizes closed-book conceptual recall, comparisons, and MCQ discrimination, structure the companion into three focused sections: (1) **Master *vs.* Contrast Matrix** (targeting free-text "difference between X and Y" prompts), (2) **Master Taxonomy & List Cheat-Sheet** (an MCQ "which of the following is *not*..." distractor shield), and (3) **Acronym & Key Term Glossary**.

In both architectures, derive every `(p. #)` page pointer from the compiled bound document (never estimate from standalone lecture page counts) and run a post-compile programmatic audit verifying every listed destination page against the rendered bound PDF. Do not fabricate universal master-page counts, lecture quotas, or compression ratios from a prior critique.

## Retrieval follows source terminology

Put the searchable name first: for example, “Fisher information — local quadratic KL” rather than only “Measure local cost.” This is illustrative, not a mandatory course topic. Keep lecturer synonyms as aliases where they aid recognition. Headings should promise content actually present.

Prefer a small dependency chain when the problem is assembling results, a comparison matrix when choosing between tools, and a local geometric sketch when the reasoning depends on geometry. Label edges with operations or assumptions when useful. Avoid decorative diagrams and repeated theorem inventories. Preserve source synthesis even when the individual facts appear elsewhere.

## Inventory before pruning

Record source location, assessment role, parent concept, unique method/branch, and planned treatment for affected topics and examples. Distinguish a source designation from an editorial choice. Start example selection with classroom exercises/assessed cases, then learning checks, then difficult concepts and reusable calculations, then instructive counterexamples. Essential coverage overrides rank. Retain a lower-ranked example when it is the only explanation of a required branch or failure.

A standalone example earns its space through a method, conceptual obstacle, or meaningful test of assumptions. Delete redundant one-number substitutions and synonymous checks outright. Rebranding them as unnumbered sanity checks does not reduce content. Merge a genuinely useful warning into the relevant explanation. Do not attach an example mechanically to every theorem. Do not remove helpful concrete examples merely because the learner wants shorter notes. A running example can serve adjacent results if all necessary inputs remain locally available.

After pruning, check that every distinct assessed action can still be practiced or reconstructed. An APPLY badge is assessed material when the source says so: keep its statement, conditions, and application in the main path even if its proof is omitted.

## Separate extensions without losing them

Place explicitly source-optional extensions at their lecture end or in an authorized separate extensions volume. Remove obsolete previews whose substantive treatment already appears elsewhere in the delivered body; use a verified canonical cross-reference only when useful. Do not create nearly empty preview appendices. Retain a brief local pointer next to the parent concept for extensions actually retained. State their source status; do not imply that an appendix is automatically outside the exam. If an extension includes an assessed application, keep the application in the main path and cross-reference the additional derivation. Keep necessary support available where the main argument uses it.

When source and assessment labels conflict or remain unclear, preserve the material in the main path pending resolution and record the uncertainty. Do not infer optionality from length, difficulty, position, or the absence of a required proof.

## PDF-only (Beamer) extraction, overlays, and overview deduplication

When slides exist only as PDF (commonly LaTeX Beamer exports), plain-text dumps lose visual emphasis and overlay structure. Run three checks during extraction:
- **Span-level emphasis recovery:** extract spans via `PyMuPDF` `get_text("dict")` to detect color-highlighted (blue, red, green) and bold lecturer keywords verbatim. Preserve those exact emphasis terms cleanly with typographic `\textbf{}` in the review notes rather than reproducing rainbow font colors.
- **Canonical slide numbering and multi-page overlays:** verify whether exam guidance or cross-references cite Beamer footer slide numbers or raw PDF page indices, declare the chosen convention at the start of each chapter and in `SOURCE_MAP.md`, and inspect every run of consecutive PDF pages sharing one Beamer footer (commonly 2-page quiz-prompt / answer-reveal overlays or progressive bullets) so revealed answers and final overlay items are never dropped.
- **Lecture 1 / overview deduplication audit:** before pruning an introductory overview deck whose slides preview later lectures, run a programmatic diff comparing its extracted definitions, terms, and scope cues against Lectures 2..N. Delete only genuinely duplicated previews and preserve every unique definition or course-scope statement in Lecture 1.

## Mastery-depth tags and incomplete-slide calibration

Concept-heavy or applied slide decks frequently present formulas without numeric examples alongside brief research previews, leaving learners uncertain what requires hand calculation versus conceptual recognition. Choose the understated right-aligned mastery-depth tag palette that matches the course's actual assessment format—never force one palette onto an unrelated exam style, and ground every tag strictly in slide evidence and speaker notes:

**Palette A — Math / applied decks (mixed hand calculations, formulas, and conceptual topics):**

| Tag | Source evidence required | Treatment |
|---|---|---|
| `[Hand-calc]` | Slides work through numeric steps, traces, or explicit calculations | Preserve full formula/substitution chain and trap checks |
| `[Formula: interpret]` | Formula appears without a worked hand calculation | Explain symbol roles, sign/direction, and trade-offs; allow one 2–4 line script-verified `Intuition check (constructed, not required for hand-calc)` when learners need concrete grounding |
| `[Conceptual]` | Definitions, taxonomies, workflows, leakage rules, or comparisons | Keep concise structured tables/distinctions without inventing equations |
| `[Research preview]` | Passing recent papers, future directions, or tool pointers | Condense to 2–3 lines unless the lecturer marks them assessed |
| `[Not in exam scope]` | Explicit course or user exclusion (such as excluded appendices) | Consolidate cleanly at lecture end; never apply by guesswork |

This calibration distinguishes *missing-example intuition checks* (one small, clearly labeled numeric check for an unworked `[Formula: interpret]` equation) from *redundant one-number substitutions* on already-worked formulas (which remain banned and must be deleted).

**Palette B — Closed-book conceptual & paper-showcase decks (definitions, contrasts, taxonomies, and method I/O without unexamined NN wiring):**

| Tag | Macro | Source evidence & treatment |
|---|---|---|
| `[Core Concept]` | `\depthcore` | Definitions, physical/biological mechanisms, principles, and explicit in-class checks explained in slide text |
| `[Contrast / Taxonomy]` | `\depthcontrast` | Named comparisons, classifications, dimensions, or pros/cons axes |
| `[Method Map: I/O]` | `\depthmethod` | Compress repetitive paper-showcase tours into one structured table (`Method category \| Paradigms/Sub-methods \| Exact Input -> Output \| Slides`) without unexamined neural-network layer wiring |
| `[Supplement]` | `\depthsupp` | Figure-embedded technical minutiae not expanded in slide text (pseudocode boxes, dense training/inference pipelines, joint ID tables) |

**End-of-lecture `[Supplement]` placement rule:** when a conceptual lecture contains figure-embedded technical details that are not expanded in slide prose, do not place a dense technical callout mid-lecture where it breaks conceptual review rhythm. Retain a concise conceptual summary plus a one-line local pointer in the main body, and relocate the dense technical or figure-embedded details strictly to a lecture-end `supplementbox` placed after summary tables and coding practice.

## Maintain a notation, convention, and errata registry

Use columns for symbol, meaning, context/lecture, object type or dimensions, and alias if any. The same glyph may legitimately have different roles in different lectures. Preserve the source symbol with an explicit context or local alias; do not globally replace every L, A, D, or K.

In multi-lecture decks, also track three high-risk cross-lecture discrepancies:
- **Convention flips:** such as self-including versus self-excluding neighborhoods (e.g., `p ∈ N(p)` in one lecture vs. `D \ {p}` and `n - 1` denominator in another), population (`N`) versus unbiased sample (`n - 1`) variance denominators, and inverted score polarity (where a smaller score indicates a stronger anomaly/signal).
- **Silent dataset or table mutations:** when later slides alter numbers or rows in a recurring example without announcing the change.
- **Verified slide errata:** arithmetic mistakes, truncated rounding, wrong citations, or mislabeled axes caught by running a Python verification script over every worked example and constructed check. Disclose each discrepancy briefly in a `Scope / trap` note and log it in `SOURCE_MAP.md` so learners are never confused when their exact hand calculation differs from a slide.

Before renaming, inspect definitions, formulas, diagrams, prose, and cross-references in the affected scope. Record the original-to-revised mapping, check dimensions and mathematical meaning, then verify the rendered equations. A registry is a disambiguation aid, not authority to overwrite the lecturer's conventions.

## Keep provenance separate from teaching

Use a concise source locator or “Constructed illustration” / “Source-reported measurement” label where the distinction matters. Put detailed source coverage, extraction issues, verification status, experiment seeds, sample/path counts, error-bar conventions, and reproduction settings in the source map or maintenance record. Keep such details in study text only when assessed or needed to interpret the result. A value that cannot be calculated from the displayed inputs must remain visibly attributed or symbolic; moving provenance must not make it look computed.

Teaching text explains what a result does, why a step works, and how to interpret an answer. Repeated statements such as “no experiment was rerun” usually belong in the provenance record, not every proof. Mathematical assumptions belong with the claim. Consequential misuse belongs in a separate compact trap, with sufficient explanation rather than a rigid one-line limit.

## Verify retrieval and preservation

Keep one canonical proof per result, with real label-based references at later uses rather than reboxed statements or repeated proofs. For an independently delivered lecture, resolve references to a supplied companion or include the minimum necessary local statement; do not leave a broken destination.

For the affected scope, check term-led headings, source recognition, required proof/action coverage, retained essential examples, extension pointers, notation mappings, and navigation destinations. For companion lookup PDFs, run a post-compile programmatic audit verifying that every `(p. #)` destination matches the actual page in the compiled bound PDF rather than an estimate from standalone lecture counts. On PDFs, test representative Ctrl+F terms or extracted text, including multiword headings—normalizing wrapped whitespace and curly apostrophes (`’` -> `'`) in automated audits—and inspect the actual display size. Check bookmarks as well as page references. Record failures honestly; successful compilation alone does not prove findability.
