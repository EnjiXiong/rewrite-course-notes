# Changelog

## 1.6.0 — 2026-11-27

- Add line-by-line anti-crowding guidance and hanging-indent table cell macros (`\tfirst`/`\ti`, `\tnumfirst`/`\tnum`, `\tsubfirst`/`\tsub`, plus `\addlinespace` breathing room and full-width `\begin{cases}...\end{cases}` stacking for compact parallel `Input / Output` pairs) so multi-point concepts never collapse into semicolon-packed walls.
- Add an optional closed-book conceptual and paper-showcase course profile: understated `\depthcore` / `\depthcontrast` / `\depthmethod` / `\depthsupp` tags, `inlineconcept` and `supplementbox` environments, `Method Map: I/O` compression for repetitive paper-showcase tours, and the end-of-lecture `[Supplement]` placement rule keeping dense figure-embedded technical minutiae out of mid-lecture conceptual flow.
- Add PDF-only / Beamer extraction rules: span-level `PyMuPDF` `get_text("dict")` extraction for color-highlighted and bold lecturer keywords (rendered cleanly as `\textbf{}`), canonical slide numbering with multi-page overlay verification (catching quiz/answer reveals), and programmatic Lecture 1 / overview deduplication audits before pruning.
- Document pure-`PyMuPDF` (`fitz`, zero `PIL`/`Pillow` dependency) curated memory-aid slide figure cropping (`300 DPI`, `alpha=False`, `0.5pt` inset, recurring-logo filtering, single contact-sheet visual verification) and add tight-border `\slidefig` + `\figcap` helpers to `assets/review-style.sty` (preset 1.6.0).
- Add upfront user confirmation for optional companions (`quick-lookup`, `self-test`, `extensions`), the 3-part Closed-Book Conceptual Quick-Lookup architecture (Master *vs.* Contrast Matrix, Master Taxonomy & List Cheat-Sheet, Acronym & Key Term Glossary), and mandatory post-compile programmatic `(p. #)` page-pointer audits against the compiled bound PDF.
- Expand LaTeX build and audit safety gates from four to eight: two-column bound TOC `\numberline` / `\rightskip` alignment and `\thispagestyle{empty}` frontmatter headers, standalone cross-chapter `\ref` safety, side-by-side `[t]` `minipage` paragraph breaks and `\vspace{0pt}` top alignment, and `\newline` (never `\\`) in last-column table macros plus whitespace/apostrophe-normalized Ctrl+F audits.

## 1.5.0 — 2026-11-27

- Add multi-modal slide extraction protocol: extract PPTX text, speaker notes, and hidden-slide flags (`show="0"`) alongside PDF text, and visually inspect contact sheets for image-bearing slides missing equation text (`imgs > 0, math == 0`).
- Add evidence-grounded mastery-depth calibration (`[Hand-calc]`, `[Formula: interpret]`, `[Conceptual]`, `[Research preview]`, and explicit-only `[Not in exam scope]`) plus a narrow boundary permitting one 2–4 line script-verified `Intuition check (constructed, not required for hand-calc)` on unworked `[Formula: interpret]` formulas.
- Expand the notation registry into a notation, convention, and errata registry covering cross-lecture convention flips (self-inclusion, score polarity, denominators), silent table mutations, and Python-verified slide errata disclosed in `Scope / trap` and `SOURCE_MAP.md`.
- Document modular single-source multi-lecture LaTeX architecture (`lectures/lecture_N.tex` + standalone/bound wrappers), compact single-page bound TOCs, calm monochrome/slate palette restraint, and four LaTeX/pre-compile safety gates (`inlineexample` for minipages, `[Clean Title]` + `\texorpdfstring` for tagged/math headings, automated lint for Markdown/ampersands/humanizer tells, and native `/tmp` builds on WSL).
- Add `inlineexample`, `intuitionbox`, and understated `\depth*` helpers to `assets/review-style.sty` (preset 1.5.0) and verify `starter.tex` and `proof-layout.tex` compile cleanly with zero warnings.

## 1.4.1 — 2026-11-19

- Set worked examples to `lines before break=6`, reserving a useful opening while retaining breakable long examples. The starter keeps Example 2’s complete Given and first action together.
- Use the neutral “Illustrative notes” header when short lectures share a page; retain natural lecture flow without forced lecture page breaks.
- Recompile and visually inspect both templates: starter 2 pages, proof layout 1 page, with no warnings or overfull/underfull boxes. Preserve font sizes, plugin identity, scope, audience, and invocation metadata.

## 1.4.0 — 2026-11-19

- Require measured main-body page/word baselines, a task-specific contraction gate, and before/after main, total, deleted, and relocated accounting. No universal course quota or box-count proxy.
- Delete redundant one-number checks, duplicate proofs, and obsolete later-covered previews; retain canonical arguments with working cross-references and independently readable body definitions.
- Scale elementary support to 1–3 readable lines without mandatory Core idea/Steps; preserve substantive hard or required proofs regardless of source badge.
- Preserve classroom problems, learning difficulties, distinct assessed branches, synthesis, and complete calculations while merging setup.
- Support authorized separate lookup, source-optional extensions, and self-test volumes without duplicating their inventories in the body; retain assessed APPLY and necessary support.
- Put experiment audit minutiae in the source map, keeping consequential mappings, attribution, and uncertainty with results.
- Require rendered page-count/whitespace review and repair orphan Needspace/forced-break failures without tiny fonts; revise all references and templates together.
- Preserve plugin scope, private audience, manifests except version, and agent invocation metadata. Local installation remains a separate staged operation.

## 1.3.0 — 2026-11-19

- Add scoped retrieval-first guidance, term-led headings, optional course/lecture lookup layers, notation registry, and verified navigation checks.
- Replace any per-result example expectation with ranked selection preserving classroom exercises, learning checks, difficult concepts, distinct methods, and consequential counterexamples; retain Given/actions/formula-substitution/Result.
- Introduced Core idea before required proofs and aligned transformations (the blanket scaffolding rule is superseded by 1.4.0 complexity-sensitive treatment); removed the semicolon-chain sample.
- Keep true assumptions with claims; separate compact traps and provenance without one-line truncation or repeated disclaimers.
- Introduced marked lecture-end source extensions/previews with local pointers (1.4.0 adds authorized separate volumes and deletes duplicate previews), preserving assessed APPLY and necessary support.
- Revise preference evidence, phrasing/layout references, and optional LaTeX helpers/examples together. No course-specific page, example, formula, or diagram quotas.
- Carry local 1.2.0 mathematical guidance into the previously 1.1.0 plugin while retaining plugin identity, scope, presentation, and default prompts.

## 1.2.0 — 2026-10-27 (local baseline)

- Add mathematical review guidance for proof priorities, notation, computed versus reported values, and useful concrete examples.

## 1.1.0 — 2026-10-25 (previous plugin baseline)

- Preserve slide wording, lecture order, source synthesis, local instances, and full formula chains.
