# Preference evidence and limits

Read this when maintaining the skill or checking the basis of a preference, not during every ordinary rewrite.

The evidence comes from iterative review-note reconstruction sessions and subsequent rewrite, compression, structure, and visualization feedback across multiple university courses. The user explicitly excluded the file-renaming, header/footer, and signature segment; that segment supplies no preference rules or identity settings here.

Clarifications made while creating this skill do apply: all skill materials should be in English, and the general rule is to represent structured content structurally. Individual charts and course topics are instances, not universal requirements.

## Revision precedence

Feedback after the user actually studied with the PDF, received on 2026-10-25, refines the earlier defaults. It takes precedence where they conflict: preserve slide wording instead of broadly rephrasing it, retain lecture order instead of interleaving themes, prefer source synthesis and framed tables for related text instead of defaulting to lists, and show full formula chains even for short worked calculations.

The 2026-11-19 post-rewrite compression feedback further refines proof scaffolding, deduplication, and volume placement as described below. Current explicit user instructions take precedence. The excluded naming and identity segment remains excluded; substantive study feedback is included because the user explicitly requested skill revisions.

## Feedback after using the notes

The feedback is translated into English below.

| Observed problem or preference | Operative rule |
|---|---|
| Definitions, advantages, disadvantages, costs, limitations, and other textual properties should use the slides' original wording wherever possible. Rephrasing disrupts review recognition. | Retain source phrasing and qualifiers; restructure through selection, grouping, and layout. Limit polishing to added prose. |
| A single item still joins several smaller points with semicolons and hides information. | Separate independent claims into rows, fields, or visible subentries. Do not pack them into a bullet or table cell. |
| Too much enumerate/itemize hides structural relationships. The slides' synthesis and summary sections are missing from the notes. | Inventory and preserve synthesis as content, using source-style framed tables, matrices, or diagrams where appropriate. |
| The L5/L6 sequence was confused. Present the review in lecture order. | Keep lectures in their source order. Improve structure within each lecture and use cross-references across lectures. |
| An instance such as S3VM was placed too far from its parent concept. | Keep instances, applications, and special cases directly with the concepts they illustrate. The named technique is an example, not a required topic. |
| Formula-based example solutions should show notation = formula = formula with substituted values = result, rather than notation = outcome. | Show the full symbolic-to-numeric chain for every essential formula-based calculation. Use approximate equality for rounded results. |
| Some list content would be clearer in the slides' framed summary tables. | Preserve original comparison axes and phrasing in framed structures; retain lists for genuinely independent facts or ordered steps. |
| Topics treated lightly in the slides were explained too extensively in the notes, including the ROC page. | Match space and detail to source and assessment emphasis. A visual request does not imply an expanded tutorial. |

## Mathematical-course refinement, 2026-10-27

While extending a Statistical Machine Learning course notes through Lecture 7, the user asked to integrate this project's review-note conventions with the existing skill, especially for courses centered on reasoning, proofs, and calculation. They also said the new topic remained unfamiliar after study and requested concrete worked examples, while keeping the surrounding prose oriented toward review.

The established mathematical-course requirements supply the following complementary guidance:

| Evidence from the course-note work | Reusable guidance and limits |
|---|---|
| Define notation before use and connect each tool to the problem it resolves. | Give object roles and dimensions where needed; keep the mathematical dependency visible within lecture order. |
| Distinguish proofs to reconstruct from results to apply. | Follow explicit source badges. Supporting derivations are editorial advice, not invented exam requirements. |
| Show short named proof steps and keep assumptions, quantifiers and boundary cases. | Compress repeated prose before essential reasoning; theorem statements and proofs may need a different layout from property comparisons. |
| Follow results with concrete or NN-related examples. | Select useful instances for identified difficulties and keep each beside its parent. A continuing example can cover connected results; this does not require an example after every result or neural networks in unrelated courses. |
| The learner could not reproduce actual forward-pass measurements from the exercise's summary values. | Distinguish computed values from source-reported measurements and specify missing inputs. |
| The learner confused score gradients, loss gradients, parameter coordinates, residuals and remainders. | Map aliases and roles explicitly; separate different error terms and types of guarantee. |
| Keep a lean main.tex, per-lecture files, shared styles, and source coverage. | Preserve suitable existing project structure and deliver synchronized editable sources. These filenames are a project convention, not a universal requirement. |

These additions are routed through [mathematical-review.md](mathematical-review.md). They preserve the 2026-10-25 source-wording, synthesis, and lecture-order preferences. They do not turn all review tasks into proof tutorials or impose that course's colors, labels, example counts, or page lengths on other courses.

## Retrieval-focused refinement, 2026-11-19

The user supplied a Gemini critique of Statistical Machine Learning review notes and explicitly requested reusable skill and plugin revisions. Its descriptions of a 189-page PDF, example totals, and particular theorem defects are external review claims, not measurements independently verified in this skill-maintenance task. They motivate checks, not fixed targets or new syllabus requirements. The user's explicit preservation requirements govern interpretation of that critique.

| Critique and user clarification | Reusable rule and boundary |
|---|---|
| Important exercises were buried by mechanical micro-examples. | Rank classroom/assessed exercises, learning checks, difficult concepts/reusable calculations, and meaningful counterexamples. Keep essential cases regardless of rank; no one-result-one-example rule or universal example quota. |
| Required proofs started with symbols before their mechanism was clear. | For substantive proofs, add a concise Core idea, then actions, reasons, and aligned displays; the later compression refinement exempts elementary identities from compulsory scaffolding. Do not compress essential reasoning into semicolon chains. |
| Assumptions, warnings, and provenance interrupted the argument. | Keep real assumptions with the statement and their use in the proof. Put likely misapplications in compact separate traps, without a hard one-line limit. Use concise provenance labels and maintenance records; preserve attribution of reported values. |
| Worked examples had become prose paragraphs. | Restore separate Given, ordered actions, complete formula/substitution chains, and Result. Include units and rounding direction where relevant. |
| A long course pack was hard to search. | Use term-led headings and useful diagrams/matrices. Offer a master lookup and one-page lecture sheets for broad retrieval tasks; they are optional, not mandatory frontmatter for local edits. |
| Overloaded symbols caused cross-lecture confusion. | Maintain a context-aware notation registry and verified aliases. Preserve source conventions; do not apply blind global replacements. |
| Extensions/previews competed with core material. | Mark explicit source-optional extensions at each lecture's end or in an authorized separate volume, with local pointers; delete duplicate later-covered previews. Preserve assessed APPLY and necessary support in the main study path; appendix position does not establish exam exclusion. |

This refinement supersedes any interpretation of the 2026-10-27 example guidance as a per-result obligation. It preserves the need for concrete examples and complete calculations. Suggested page ranges, formula counts, fixed example ceilings, mandatory one-line traps, specific SML diagrams, and blanket notation locks are not adopted as all-course rules. See [retrieval-and-scope.md](retrieval-and-scope.md) for scope decisions and verification.

## Post-rewrite compression refinement, 2026-11-19

The new critique reported a 193+ page release with 183+ main-body pages and said that micro-examples had merely been renamed checks. These are reviewer-reported figures, not measurements performed during skill maintenance. The current task authorized a roughly 95–110-page main body and separate lookup, extensions, and self-test volumes. That range belongs to this edition only: no per-course, per-lecture, or fixed contraction quota is reusable.

| Failure or clarification | Reusable correction |
|---|---|
| Navigation improved while the study body grew. | Establish actual main-body page/word baselines, distinguish navigation and supplements, set a task-specific contraction gate, and report main versus total versus relocated content. Box counts do not establish compression. |
| One-number micro-examples survived under new names. | Delete redundant arithmetic and synonymous checks; merge only useful trap fragments. Preserve classroom problems, identified learning difficulties, required branches, and consequential counterexamples. |
| Repeated proofs and later-covered previews remained. | Keep one canonical argument, replace later copies with working references, and delete obsolete previews and empty appendix stubs. |
| Elementary support acquired bulky proof scaffolding. | Use 1–3 readable lines for elementary identities; retain substantial hard/required proofs regardless of badge. Core idea plus named steps is a complexity-sensitive tool. |
| The critique called symmetrization CORE, whereas the source labels it SUPPORT. | Preserve the source label. Its substantive proof can still deserve full essential reasoning; a badge neither proves complexity nor permits deletion. This is an example of source verification, not a required topic. |
| Lookup, self-test lists, and optional extensions swelled the main file. | Use authorized separate volumes without duplicating their inventories in the body. Keep the body independently readable, and retain assessed APPLY plus necessary support. Source optionality, not appendix position or length, determines removal. |
| Seeds, simulation counts, and experiment audit notes distracted from study. | Keep reproducibility detail in the source map unless assessed or needed for interpretation; retain meaningful results, parameter mappings, attribution, and uncertainty. |
| Tiny appendix stubs and page reservations created blank space. | Check rendered page counts and all-page whitespace, repair orphan Needspace/forced-break failures, and retain readable type. |

These rules replace the earlier permission to rebrand redundant examples and the blanket requirement for Core idea before every proof. Earlier source wording, lecture order, full calculation chains for retained examples, and assessment-preservation requirements still apply. See [compression-and-release.md](compression-and-release.md).

## Slide-heavy conceptual & multi-lecture refinement, 2026-11-27

While rewriting and consolidating all 11 lectures of an Introduction to Data Mining course (including standalone lecture PDFs, L1–L6 / L7–L9 bundles, and a 53-page complete L1–L11 bound book), five recurring practical failure modes emerged and were validated across 900+ slides. The user explicitly approved incorporating these lessons into the skill.

| Observed failure or learner need | Reusable guidance and boundary |
|---|---|
| Slides contained embedded PNG formulas (e.g., L8 FCM/GMM/CHAMELEON/Spectral), hidden slides, PDF-clipped columns, and speaker-note exam cues invisible to PDF-only extraction. | Extract PPTX text + speaker notes + `show="0"` flags alongside PDF text; flag `imgs > 0, math == 0` slides and visually inspect rendered contact sheets before drafting. |
| Incomplete slides presented formulas without worked examples alongside research previews, causing exam-scope anxiety. | Use evidence-based mastery-depth tags (`[Hand-calc]`, `[Formula: interpret]`, `[Conceptual]`, `[Research preview]`, `[Not in exam scope]` when explicitly excluded) grounded in worked examples and speaker notes; allow one 2–4 line script-verified `Intuition check (constructed, not required for hand-calc)` on unworked `[Formula: interpret]` formulas without relaxing the ban on redundant checks for already-worked formulas. |
| Cross-lecture convention flips (self-including vs. self-excluding neighborhoods, inverted score direction, denominator mismatches) and slide arithmetic typos misled review. | Expand the notation registry to cover conventions and errata; verify every calculation and constructed check via Python before compiling, and disclose discrepancies transparently in `Scope / trap` and the source map. |
| Multi-lecture LaTeX builds suffered from `breakable` `tcolorbox` clipping inside `minipage`, heading tags polluting TOCs, stray Markdown/unescaped `&`/humanizer dashes, and duplicated lecture sources. | Maintain single-source `lectures/lecture_N.tex` + thin wrappers for standalone and bound PDFs; provide non-breakable `inlineexample`, require `[Clean Title]` + `\texorpdfstring` on tagged/math headings, and run pre-compile lint + zero-warning checks. |
| Flashy multi-color boxes added cognitive fatigue on concept-dense courses. | Document a calm monochrome/slate palette option (light tint frames, muted slate tags, neutral gray for intuition/appendix blocks) as a recommended restraint preset rather than a mandatory theme. |

Generalization limits remain unchanged: do not assume appendices are excluded unless explicitly stated for that course, do not hardcode per-lecture page counts, and do not insert constructed intuition checks where slides already provide clear worked numbers.

## Closed-book conceptual & paper-showcase refinement, 2026-11-27

While rewriting all 12 lectures of a Human-Centered Artificial Intelligence course (782 PDF-only Beamer slides, 50 cropped 300-DPI figures, 12 standalone lecture PDFs, a 57-page complete bound book, and a 6-page 3-part Quick-Lookup companion; the user declined a self-test volume before starting review), six cross-course patterns emerged and were approved by the user for inclusion in the skill.

| Observed failure or learner need | Reusable guidance and boundary |
|---|---|
| Multi-point definitions, metrics, applications, and parallel `Input / Output` pairs packed onto one semicolon-separated line felt cramped and triggered exam-review fatigue. | Start every distinct point on its own line (using hanging-indent table cell macros `\tfirst`/`\ti`, `\tnumfirst`/`\tnum`, `\tsubfirst`/`\tsub` and `\addlinespace`, or compact full-width left-brace `\begin{cases}...\end{cases}` stacks for parallel pairs; never put wide `cases` blocks inside narrow half-width `minipage`s). |
| Paper-showcase courses tested concept definitions, contrasts, taxonomies, and method I/O rather than NN layer wiring, and mid-lecture figure-embedded technical boxes broke study rhythm. | Offer an optional conceptual depth-tag palette (`[Core Concept]`, `[Contrast / Taxonomy]`, `[Method Map: I/O]`, `[Supplement]`) alongside `[Hand-calc]`, compress repetitive paper tours into a `Method Map: I/O` table, and relocate unexpanded figure-embedded technical minutiae strictly to a lecture-end `[Supplement]` box with a conceptual summary and 1-line local pointer in the body. |
| PDF-only Beamer decks hid emphasis in text colors, split quiz questions and answers across consecutive PDF pages with one footer number, and repeated Lecture 1 preview items in later lectures. | Extract span-level color/bold emphasis with `PyMuPDF` `get_text("dict")` (rendering emphasis cleanly as `\textbf{}`, not rainbow fonts), declare canonical slide numbering and inspect shared-footer overlays, and run a programmatic Lecture 1 / overview deduplication diff before pruning. |
| Anatomy diagrams, conceptual wheels, and timelines from slides acted as high-value memory aids, while repeating slide logos and default `\fcolorbox` padding caused clutter or vertical wrapping in paired `minipage`s. | Use a pure-`PyMuPDF` (`fitz`, zero `PIL`) cropping workflow filtering recurring logos by dimensions/`xref`, cropping curated memory-aid figures at `300 DPI, alpha=False, 0.5pt inset`, verifying all crops on a contact sheet, and framing with tight-border `\slidefig` (`\fboxsep=1.5pt, \fboxrule=0.4pt`). |
| Closed-book conceptual exams needed contrast recall, MCQ distractor screening, and acronym lookup rather than an open-book task-to-tool formula index, and companion volumes should match user readiness. | Confirm optional companions (`quick-lookup`, `self-test`, `extensions`) upfront; support a 3-part Closed-Book Conceptual Quick-Lookup (Master *vs.* Contrast Matrix, Master Taxonomy & List Cheat-Sheet, Acronym & Key Term Glossary) alongside open-book lookups, and programmatically audit every `(p. #)` pointer against the compiled bound PDF. |
| Multi-lecture bound and standalone builds hit four new LaTeX/audit traps: 2-column TOC crowding and `Lecture 0` headers, undefined cross-chapter `\ref`s in standalone wrappers, misaligned `[t]` `minipage`s, and `\\` breaking last-column table macros plus curly-apostrophe Ctrl+F false misses. | Codify Gates 5–8 in [figures-and-layout.md](figures-and-layout.md) covering 2-column TOC spacing + `\thispagestyle{empty}`, standalone cross-chapter label safety, `[t]` `minipage` `\par\vspace{1pt}\noindent` + `\vspace{0pt}`, and `\newline` in last-column table macros plus whitespace/apostrophe-normalized Ctrl+F checks. |

Generalization limits: the conceptual depth-tag palette (`[Core Concept]` / `[Contrast / Taxonomy]` / `[Method Map: I/O]` / `[Supplement]`) and 3-part closed-book Quick-Lookup are course-fit options alongside `[Hand-calc]` and open-book task-to-tool lookups; never force one tag set or lookup layout onto a course with a different exam format, and always confirm optional companions before generating them.

## Earlier explicit preferences, interpreted with these refinements

The quoted feedback below is translated from Chinese into English; it is not a verbatim English transcript.

| User feedback, translated | Reusable rule |
|---|---|
| “The original slides are too verbose and fragmented; they need restructuring.” | Reorganize related content within each lecture while preserving lecture order and source wording. |
| “Include all exam content from these six lectures.” | Confirm each task's actual scope and preserve it; do not fix the scope at six lectures. |
| “Do not write at length. This is review, so no conceptual introductions; go directly to the core and examples.” | Write for someone who has studied the material; remove introductory teaching and repetition. |
| “Attach examples near the corresponding concepts.” | Keep examples next to the knowledge they exercise. |
| “Use a single column, not two. Refer to the formatting of the reference course.” | Default to single-column notes and respect a specified reference template. Local text-and-figure arrangements are compatible with this preference. |
| “The relationships in the derivation are hard to understand. Everything uses commas as transitions.” | Show actions, ordered steps, and necessary justifications instead of implicit comma transitions. |
| “My goal is midterm revision, not learning from scratch.” | Compression must not turn into another beginner's course. |
| “Each concept, or two or three related concepts, should occupy a row, with their names in front.” | Name first; separate unrelated concepts; group related short formulas when readable. |
| “Do not put unrelated textual definitions in one paragraph. Use enumerate or itemize.” | Keep independent concepts distinct, using rows or blocks for related text and lists for independent facts or ordered steps. Original screenshots can retain their internal format. |
| “Given conditions should be on a separate row, not mixed with calculation and formulas.” | Give conditions their own paragraph before calculation. |
| “For plotting methods and data points, put a figure or diagram beside the explanation.” | Use an appropriate representation for content whose meaning depends on visual structure. |
| “Use the corresponding example's data where possible; preserve concept items and separate Given; minimize added pages.” | Reuse inputs, place representations locally, and control length without undoing the accepted structure. |
| “The skills and supporting content should be fully in English.” | Maintain the skill, references, metadata, and template instructions in English. |
| “Not every course has AUC or Q-Q plots. The core is to present structured data, content, and knowledge structurally. This conversation can provide examples or instances, not fixed required content.” | Choose lists, tables, steps, trees, diagrams, or plots from the actual relationships in each course. Keep specific topics in optional examples. |

## Useful defaults and limits on generalization

- **Optional visual style:** the accepted artifact used serif body text, dark blue headings, blue method boxes, green example boxes, and local text/figure arrangements. Provide an optional preset rather than making its font size, colors, or boxes mandatory.
- **Phrasing:** the user allowed humanizer, then clarified that original slide wording must be preserved. Apply prose refinement only to added transitions and explanations, not to source definitions, properties, or labels.
- **Assessment emphasis:** the source course emphasized algorithms, concept discrimination, application, and calculation. Reassess the role of proofs, experiments, cases, and arguments for each new course.
- **Scope:** the source course excluded appendix material from the exam. Do not exclude every appendix in future courses, and check for main material resuming after an appendix.
- **Language:** English notes were accepted in the source task. The English-only requirement for this skill does not override a future request for course notes in another language.
- **Counts and compression ratios:** the process mentioned 18-, 31-, and 53-page versions; the resulting available artifact had 27 pages and retained 40 examples. These are case facts, not future page targets, example quotas, or compression ratios.
- **Version provenance:** the historical attachment available during the work differed from the latest page count described in that conversation. Inspect actual files before claiming a comparison or compression result.
- **Task boundary:** this skill concerns course review notes. It does not automatically add question generation, full-course tutoring, paper writing, or publication to external services.

Update the relevant rule, reference, and template together when new feedback arrives. Remove superseded instructions rather than appending a contradictory rule. Do not accumulate every local adjustment into a mandatory set of headings, tools, or checks for all courses.
