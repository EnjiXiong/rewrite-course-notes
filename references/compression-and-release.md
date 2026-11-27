# Measured compression and delivery

Use this workflow when the task asks to shorten existing review notes. Retrieval improvements alone do not satisfy compression. Apply checks to the requested scope; do not expand a local repair into a full-course rewrite.

## Baseline and acceptance before editing

Inspect the actual current PDF and editable sources. Record filenames/versions, rendered page ranges, and word counts with the extraction/counting method. If the baseline is unavailable, say which comparison is unverified; do not reuse a reviewer's estimate as a measurement.

Separate these categories consistently before and after:

| Category | What to record |
|---|---|
| Main study body | Pages and words of the lecture-ordered study content, including required/assessed material and necessary support |
| Navigation | Cover, contents, master lookup, lecture sheets, notation index, or other navigation, whether embedded or separate |
| Supplementary study material | Source-optional extensions and self-test questions, whether embedded or separate |
| Main PDF total | All physical pages in the main file, including frontmatter, supplements, and blank pages |
| Entire delivery | Physical pages/words across all delivered volumes; distinguish repeated content and content relocated between files |

Use source boundaries or final labels to identify mixed-content pages; state how such pages are counted rather than subtracting guessed frontmatter lengths. Word counts must use the same method before and after. Math-heavy PDF extraction may undercount formulas, so pair words with rendered pages and source coverage; do not treat words alone as a coverage metric.

Set a task-specific main-body page budget and an explicit contraction criterion from the user's request. If the user gives no number, state a reasonable target based on measured removable repetition and the material that must remain. Allocate provisional lecture budgets according to assessment weight and complexity; do not distribute pages mechanically. Record the readable font/layout baseline. A previous course's range, lecture quota, example ceiling, or percentage is never a universal default.

Acceptance requires the agreed main-body contraction and coverage/readability gates below. If the target appears incompatible with required content, exhaust safe deduplication and authorized relocation first, then report the concrete remaining tradeoff. Do not silently declare success, remove required content, or make the type tiny to force the count.

## Prune content rather than rename containers

Maintain a compact source map: source location, assessment role, essential method/branch, original destination, decision, and final destination. Distinguish retained, merged, deleted as redundant, and relocated. It is a maintenance artifact, not another study-body chapter.

1. Keep one canonical statement and proof of each result. Replace later copies, including large Recall boxes, with actual label-based references and only the local assumptions or changed step required for use. Resolve references within the delivered set; independent lecture files must not contain broken references to absent files.
2. Delete obsolete previews when their substantive treatment already appears later in the delivered body. Do not move duplicates to extensions or create a mostly empty appendix for a transition sentence.
3. Delete one-number substitutions and synonymous checks that teach no new method, condition, or failure. Renaming an Example as a check, note, or unboxed paragraph is not compression. Merge a genuinely useful warning fragment into the existing explanation once.
4. Protect classroom problems, explicitly assessed exercises, stated learning difficulties, distinct solution branches, and consequential counterexamples. Merge shared givens into a running example when appropriate, retaining locally recoverable inputs and complete essential formula/substitution/result chains.
5. Match proof layout to complexity and role. Elementary supporting identities usually fit 1–3 readable lines without Core idea or Steps headings. Required elementary deductions still show all inferences. Substantive hard proofs and necessary dependencies keep their mechanism and essential steps even under SUPPORT or another lower-priority badge. Source labels remain unchanged.
6. Omit or relocate explicitly optional technical proofs only when no required reconstruction depends on them. Keep the statement, conditions, and assessed application. A proof's length, difficulty, or optional reconstruction status does not by itself make the result optional.

Preserve source synthesis when it adds relationships; familiar individual cells do not make a comparison redundant. Preserve lecture order, original terminology and qualifiers, guarantee types, and substantive worked reasoning.

## Split volumes within the authorized scope

When the user authorizes separate lookup, extensions, and self-test volumes, proceed without another approval gate. Keep their identities and links clear. Without that scope, use a compact in-file arrangement appropriate to the task; do not silently introduce an external dependency.

- **Lookup:** index tasks, tools, conditions, and verified body destinations. Do not also insert the full lookup and repeated notation inventories in the main body. The body must still define symbols and state conditions before use; an external notation table is not a substitute for standalone readability.
- **Extensions:** include material with evidence of source optionality. Preserve source status and useful local pointers. Assessed APPLY, required reconstruction, and necessary support remain in the main path. Delete later-covered preview duplicates rather than moving them here.
- **Self-test:** relocate requested recall-question lists once, with clear destinations for answers or relevant study material. Do not convert important worked classroom exercises into detached self-test questions to meet a page budget.
- **Source map:** retain audit detail such as experiment seeds, path/sample counts, Monte Carlo error-bar conventions, software defaults, and verification status. Study text keeps the meaningful conclusion and necessary parameter mappings, attribution, and uncertainty. Details that are assessed or change the interpretation stay with the result.

Recompute destinations after final pagination. Test links in the main file and every independently delivered companion; a prose “see later” or manually guessed page number is not a verified cross-reference.

## Render and inspect before claiming completion

For PDF delivery, compile the actual deliverables and inspect an all-page overview plus suspect pages at reading size. Check the affected equations, references, bookmarks, and searchable terms. Perform the applicable source-package reproducibility check. For source-only skill maintenance, static validation is valid but must be reported as such; it does not establish page counts or visual quality of future notes.

Audit near-empty pages, isolated headings, stranded proof endings, and large gaps before/after boxes. Excessive `Needspace` reservations, forced `clearpage` commands, and nonbreaking containers can turn a few lines into a whole extra page. Reduce reservations to the heading plus a few following lines, permit appropriate breaks, or split at complete inference boundaries. Do not fix gaps by shrinking text or separating a formula from its substitution. Record unavoidable breaks and why they remain.

The delivery gates are:

- The measured main-body page and word comparison meets the task-specific contraction criterion; any exception is explicitly reported.
- Every in-scope assessed result/action, necessary definition, essential proof inference, protected example, and substantive source synthesis is still present or correctly referenced.
- Deleted low-value checks and duplicate proofs have actually disappeared; they were not relabeled, unboxed, or hidden in another body section.
- Authorized relocation is separately accounted for, and the main body remains independently readable.
- Canonical references and cross-volume destinations resolve after final pagination.
- Rendered whitespace, orphan headings/continuations, font size, and equation/table legibility pass inspection.

## Honest before/after report

Report at least main-body pages/words, main PDF total pages, navigation and supplementary pages, and entire-delivery totals. Name the counting method and unresolved limitations. State which reduction is actual deletion/merging and which is relocation. Do not add per-category estimates as if they were independently measured page savings when pagination interactions prevent that attribution.

A drop in example boxes, theorem environments, headings, or filename size is only a structural observation. It is not evidence that the study body contracted or that total reading volume fell. A separate lookup can improve retrieval while increasing total pages; report both facts accurately.
