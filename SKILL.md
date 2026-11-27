---
name: rewrite-course-notes
description: >-
  Restructure and compress previously studied course slides or notes into
  exam review notes while preserving lecture order, original slide wording,
  source emphasis, and synthesis. Make key tools easy to retrieve, select useful
  examples, and explain proof mechanisms. Use for review sheets and structural or visual
  revisions. Keep instances beside their concepts and show complete formula,
  substitution, and result chains. This is not general prose polishing or
  standalone homework solving.
metadata:
  short-description: Lecture-ordered review with slide wording, synthesis, and worked steps
  version: "1.6.0"
---

# Course notes: restructure and compress

Write for someone who has already studied the material. Preserve recognizable course wording and progression while improving retrieval, synthesis, and solution clarity. Compress repeated exposition and layout overhead, not source meaning or essential reasoning.

These preferences apply unless the current user explicitly overrides them. Maintain this skill and its supporting materials in English. Choose the language of a course artifact from the current task; an English skill does not require every course artifact to be English.

## Establish scope and source structure

Start from the current source files and requested revision. Recover exam coverage, lecture sequence, source versions, output format, page constraints, and examples to retain. Inspect actual contents and page counts rather than trusting historical replies. Disclose unavailable or mismatched versions without claiming a comparison that was not performed.

When slide decks exist in both PPTX and PDF, extract PPTX slide text, speaker notes, and hidden-slide flags (`show="0"`) alongside PDF text before drafting. Speaker notes frequently carry exam-scope cues, Quick Check answers, and derivation boundaries omitted from PDF exports, while cross-checking PPTX against PDF catches clipped columns and hidden slides. Automatically flag image-bearing slides that lack extracted equation text (for example, `imgs > 0` with no math XML or suspiciously sparse text) and inspect rendered contact sheets visually so image-embedded formulas are never dropped or reconstructed from memory.

For PDF-only decks (such as Beamer slides), extract span-level formatting (`PyMuPDF` `get_text("dict")`) to capture color-highlighted and bold lecturer keywords verbatim and preserve them with clean typographic `\textbf{}` rather than rainbow fonts. Verify canonical slide numbering (Beamer footer vs. raw PDF page), inspect consecutive PDF pages sharing a footer (quiz/answer reveal overlays) so revealed answers are never missed, and run a programmatic diff comparing Lecture 1 / overview preview decks against Lectures 2..N before pruning duplicates so zero unique definitions are dropped. Confirm upfront with the user which optional companion volumes (`quick-lookup`, `self-test`, `extensions`) are wanted before generating them.

When compression is requested, read [compression-and-release.md](references/compression-and-release.md). Before editing, measure the current main-body pages and words separately from navigation and supplements. Set a task-specific budget and explicit contraction acceptance criterion, then verify the rendered result against it. A smaller box/example count or renamed checks is not evidence of compression. Report before/after main body, main-file total, and complete delivery totals, with deleted versus relocated material distinguished. Never transfer a previous course's page target to a new task.

For an open-book or retrieval-focused revision, read [retrieval-and-scope.md](references/retrieval-and-scope.md). Establish which layers are requested: local repair, a lecture, or a full-course pack. Master lookup pages and one-page lecture sheets are optional designs for a sufficiently broad task, not additions to every edit. Do not impose example counts, formula counts, or total-page targets from another course.

For a full rewrite, make a lightweight inventory in lecture order: topics, source terminology, parent concepts and their instances, worked examples, and synthesis/summary/comparison slides. Include these integrative slides in the coverage check. Verify whether main material resumes after an appendix; exclusion applies only where the course or user specifies it.

For a local revision, apply the relevant checks to the affected blocks. Do not expand a wording or layout change into an unrelated course rewrite. Ask only about missing information that would materially change the result and is not available in the supplied context.

## Preserve the lecture sequence and hierarchy

Use the source lecture order as the outer structure: Lecture 1, then Lecture 2, and so on. Improve organization **within each lecture** while respecting its concept hierarchy and teaching progression. Do not interleave lectures to build a new thematic syllabus. Connect material in different lectures with brief, working cross-references to one canonical statement/proof. Remove obsolete previews when the full treatment is already included later. Preserve the local conditions and definitions needed to read the body independently; an optional integrative overview does not replace it.

Keep each instance, application, special case, or counterexample directly with its parent concept, ideally in the same block, table, or adjacent paragraph. If the same named technique has a standalone treatment elsewhere, retain a short local instance and point to that treatment. Do not detach the instance and leave only its name several pages away.

## Make retrieval and scope visible

Lead section headings with recognizable source or standard terms; follow with a short purpose phrase when useful. Preserve lecture order and source terminology. Match lookup architecture to the exam format: an open-book task-to-tool lookup can index questions, applicable methods, hypotheses, guarantee type, and verified destinations, whereas a closed-book conceptual companion can use a 3-part structure (Master *vs.* Contrast Matrix, Master Taxonomy & List Cheat-Sheet, and Acronym & Key Term Glossary) without replacing the body. Programmatically audit every `(p. #)` destination in a companion lookup against the compiled bound PDF rather than estimating from standalone lecture counts. Use dependency chains and comparison tables where they reduce search or explain assembly.

Maintain a notation, convention, and errata registry for multi-lecture work: symbol, meaning, lecture/context, dimensions, explicit aliases, cross-lecture convention flips (such as self-including versus self-excluding neighborhoods, inverted score polarity, or population versus sample denominators), and verified source slide errors. Preserve source conventions unless a justified local change improves clarity; check every affected definition and equation, and disclose source discrepancies transparently in a `Scope / trap` note and the source map. Do not apply blind global replacements to overloaded symbols.

Keep required reconstruction, assessed application (including APPLY), and necessary support in the main study path. Choose optional understated mastery-depth tags grounded strictly in slide evidence and speaker notes to match the course format—either the math/applied palette (`[Hand-calc]`, `[Formula: interpret]`, `[Conceptual]`, `[Research preview]` condensed to 2–3 lines, and explicit-only `[Not in exam scope]`) or the closed-book conceptual / paper-showcase palette (`[Core Concept]`, `[Contrast / Taxonomy]`, `[Method Map: I/O]`, `[Supplement]`); never invent assessment depth without evidence or force one palette onto every course. For paper-showcase decks, compress repetitive paper tours into a structured `Method Map: I/O` table (`Method category | Paradigms/Sub-methods | Exact Input -> Output | Slides`) without unexamined NN layer wiring, and keep figure-embedded technical details not expanded in slide text (pseudocode, dense pipelines, joint ID tables) out of mid-lecture conceptual flow by retaining a concise conceptual summary plus a one-line local pointer in the body and relocating the technical detail strictly to a lecture-end `[Supplement]` box after summary tables. Place genuinely optional, source-identified extensions in a marked lecture-end section or, when the current task authorizes it, a separate extensions volume with a short local pointer. Delete duplicate later-covered previews rather than relocating them. Separate lookup and self-test volumes are also valid when authorized; avoid copying their inventories back into the body, while retaining body definitions and substantive synthesis. Preserve their source label and any assessment qualification. Never demote assessed APPLY material merely because its proof is optional, nor classify unfamiliar or lengthy material as an extension without evidence.

## Preserve slide wording before polishing prose

For definitions, properties, advantages, disadvantages, costs, limitations, assumptions, and comparison labels, reuse the slides' wording wherever available. Preserve qualifiers and terminology even when a synonymous rewrite sounds smoother. Make compression mainly through selection, deduplication, grouping, and layout.

Separate independent source clauses into rows or cells without rewriting them. Apply a strict line-by-line anti-crowding rule: never pack multiple points, metrics, applications, or parallel `Input / Output` pairs onto one line joined by semicolons—start each distinct point on its own line (using hanging-indent table cell macros, bullets/numbered items, or full-width left-brace `\begin{cases}...\end{cases}` stacks for compact parallel pairs, avoiding wide `cases` inside narrow half-width `minipage`s). A name can lead a row or a labeled block; it does not have to lead an `itemize` entry.

Write new prose only for missing connections, solution actions, or necessary clarification. Keep added explanations distinguishable from slide text. Correct an identified source error transparently, and check the rendered slide when extraction is suspect. If the original wording is unavailable, do not present a reconstruction as a quotation. If translation is requested, retain key source terms and translate faithfully.

A humanizer pass, when requested, applies to assistant-authored transitions and explanations. It must not paraphrase preserved slide statements or rename the lecturer's concepts. Read [structure-and-phrasing.md](references/structure-and-phrasing.md) when editing text or worked solutions.

## Choose structure instead of defaulting to lists

Inspect the slides' own synthesis and summary arrangements before choosing a layout. Preserve their comparison axes, categories, and relationships. Related text often belongs in a compact framed table or grouped matrix, especially when that is how the slides summarize it.

| Relationship | Preferred presentation |
|---|---|
| One concept with properties, strengths, costs, and limits | Labeled rows in a framed concept table |
| Several methods compared on shared dimensions | Boxed comparison matrix using source labels |
| Parent concept with named instances or special cases | Grouped block, parent/instance rows, or a small hierarchy |
| Source synthesis or summary | A compact synthesis table or diagram preserving its integrative role |
| A few genuinely independent facts | Separate named items; a short list is appropriate |
| Ordered procedure, calculation, or proof | Numbered actions and aligned reasoning |
| Spatial, temporal, or quantitative relationships | An appropriate local diagram, timeline, or plot |

Do not replace every bullet with a table. Choose the smallest structure that reveals the relationship. Within a cell or item, give distinct claims separate visible positions. Group two or three short formulas on one row only when their relationship is clear and each retains its name.

Retain substantive synthesis from the source in the appropriate lecture position. It may replace repeated prose, but it must not disappear as supposedly redundant. If relationships are only implicit, a concise synthesis built from the covered material can help; do not invent relationships or attribute a new summary to the lecturer. Original screenshots can retain useful internal layouts when legible.

## Worked examples: conditions, formula chain, decision

Select examples by their teaching or assessment role, then place them next to the concepts they exercise. Rank candidates by: (1) classroom worked exercises and explicitly assessed cases, (2) learning checks, (3) difficult concepts or reusable multi-step solution patterns, and (4) counterexamples that expose a consequential failure. These priorities guide selection, not automatic deletion: preserve every distinct required method, branch, and essential counterexample, including a lower-ranked case needed for understanding.

Do not use a one-result-one-example rule. Combine repeated setup into a running example when helpful. Delete a redundant one-number substitution or synonymous restatement with no additional method or conceptual value; do not relabel it as a check, note, or unnumbered paragraph. If a fragment exposes a genuine trap, merge only that fragment into the existing explanation. Preserve useful constructed examples for unfamiliar concepts; specifically, when an in-scope `[Formula: interpret]` equation has no worked numeric example in the slides and leaves learners unsure how its symbols or sign behave, a single 2–4 line neutral block explicitly labeled `Intuition check (constructed, not required for hand-calc)` is permitted once numerically verified by script. Keep a compact selection/coverage record when substantially pruning; no universal per-lecture quota applies.

- **Given / Situation:** a separate paragraph containing inputs, conditions, and the target. Input tables or figures may follow; calculations begin separately.
- **Solution:** use numbered actions where order matters. For each essential formula-based quantity, show **notation = symbolic formula = formula with the given values substituted = result**. A nearby formula elsewhere does not justify skipping the formula stage in the worked solution.
- **Reasoning:** explain the condition that licenses a method, branch, normalization, or pruning step. Commas and semicolons alone must not carry those transitions.
- **Result / Conclusion:** state the answer, units where relevant, rounding direction for integer budgets, and necessary interpretation. Use a short Check only for a real trap, not as a compulsory final paragraph.

Keep the four-stage calculation on one readable line when possible, or align it across lines. Use `\approx` for rounding instead of a false equality. Intermediate values may be reused once visibly computed. For symbolic questions, show the corresponding symbolic substitution or derivation; do not invent numeric inputs. Do not create a redundant formula chain for a purely qualitative decision.

Omit repetitive arithmetic expansions, not the formula or substitution. If Given lacks a required parameter, retain a symbolic result or identify the missing quantity. The examples in [structure-and-phrasing.md](references/structure-and-phrasing.md) demonstrate the required chain.

## Match depth to the course

Allocate space according to explicit assessment guidance, the slides' emphasis, worked examples, and synthesis. Use slide count as context, not a mechanical weighting rule. Cover assessed material, but keep briefly mentioned properties or instances brief. Do not turn a passing topic into a full tutorial because it is familiar or easy to visualize.

A request for a figure changes representation; it does not automatically authorize additional theory, methods, or a full-page treatment. Prefer a small adjacent figure or source-style summary when that matches the source depth. Expand a topic only when the user, assessment, or source treatment warrants it. Specific charts and course topics in the references are examples, never required content.

For courses centered on mathematical reasoning, proofs, and calculations, read [mathematical-review.md](references/mathematical-review.md). Preserve the source's proof requirements, state theorem conditions and randomness, and keep the steps needed to reconstruct the argument. For a substantive multi-step proof, give a concise **Core idea** explaining the mechanism or proof trick, then named actions, reasons, and aligned displays. Keep elementary supporting identities to 1–3 readable lines without compulsory Core idea or Steps headings. Required elementary proofs still show every inference. Proof complexity and dependency role govern space as well as assessment status: retain substantive hard or required proofs regardless of a SUPPORT badge, and do not relabel source badges to justify the layout. Do not compress a proof into a semicolon chain. A theorem may deserve a boxed statement and named proof steps rather than a property table.

Keep genuine assumptions, quantifiers, and the type of guarantee with the statement, and identify their use in the proof. Put consequential misapplications in a compact, separate **Scope / Exam trap** after the argument or example; use enough lines to preserve the distinction. Do not make traps compulsory or impose a one-line truncation. Separate provenance (source locator, constructed inputs, reported measurement, verification status) from teaching (mechanism, actions, interpretation). Keep seeds, path/sample counts, Monte Carlo error-bar conventions, API defaults, and reproduction details in the source map or maintenance record unless they are assessed or necessary to interpret the result. Retain the study conclusion, consequential parameter mapping, and any attribution or uncertainty needed to interpret a value immediately.

When the user has studied a topic but still finds it unfamiliar, strengthen the worked examples locally. Reuse a fully specified example across connected results when that makes the deductions easier to follow. Keep review-level prose concise; do not remove conditions or intermediate calculations to meet an arbitrary page target.

## Layout and delivery

Default to single-column body text. Use local text-and-figure arrangements when helpful. Reuse example data and label constructed layouts schematic when coordinates or topology are unspecified. Check that counts, directions, and labels agree with the source and solution.

Reduce repetition and improve tables and local layout while keeping readable type; tiny fonts are not compression. For anatomy diagrams, conceptual wheels, pipelines, and visual memory aids, prefer pure-`PyMuPDF` (`300 DPI, alpha=False, 0.5pt inset`, recurring-logo filtered, contact-sheet verified) cropped slide figures framed with tight-border `\slidefig`. For multi-lecture deliverables that require both standalone lecture PDFs and combined or full-course bound editions, maintain one canonical per-lecture source file (`lectures/lecture_N.tex`) included by thin wrapper files rather than duplicating content. Review actual page counts and whitespace. Repair orphan headings/continuations and excessive Needspace reservations or unbreakable boxes rather than accepting almost-empty pages; follow the eight LaTeX safety gates in [figures-and-layout.md](references/figures-and-layout.md) (including non-breakable `inlineexample`/`inlineconcept` in `minipage`s, `[Clean Title]` + `\texorpdfstring` on tagged/math headings, 2-column bound TOC spacing and `\thispagestyle{empty}` frontmatter headers, standalone cross-chapter label safety, `[t]` `minipage` paragraph breaks + `\vspace{0pt}`, and `\par`/`\newline` rather than `\\` in last-column table macros). The optional [style](assets/review-style.sty) and [starter](assets/starter.tex) demonstrate framed synthesis, lecture order, instance locality, and complete calculations. Prefer suitable existing sources or a user-specified template.

Before delivery, review the affected material for: preserved source wording, lecture order, synthesis coverage, instance-to-parent proximity, complete formula chains, source-appropriate depth, example selection, proof mechanisms, assumptions versus traps, explicit extension/supplement placement, notation/convention/errata mappings, and script-verified numerical correctness (run a Python or equivalent check over every worked calculation and constructed intuition check, plus a pre-compile lint pass for stray Markdown tokens, unescaped `&`, and requested humanizer constraints). For PDF output, compile and inspect affected pages; a full reconstruction also needs an all-page overview and a topic/example/synthesis coverage check. For retrieval-focused PDFs, test representative term searches (normalizing wrapped whitespace and curly apostrophes in automated audits), heading text extraction, bookmarks, and programmatically audited `(p. #)` lookup destinations; do not infer searchable text from visual appearance alone. Syntax validation alone does not establish these semantic properties.

Deliver the artifact and usable editable sources with required figures and styles. For compression tasks, the page/word contraction, preserved coverage, working canonical references, and whitespace checks are delivery gates; disclose unmet targets or unavailable rendering rather than declaring success. Report only checks actually completed. Preference provenance and revision precedence are documented in [preference-evidence.md](references/preference-evidence.md); read it when maintaining the skill or resolving conflicting defaults.
