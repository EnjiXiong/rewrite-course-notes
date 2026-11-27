# Synthesis, emphasis, and compact layout

## Start with the slides' structure

Inspect the source's summary, synthesis, and comparison slides before turning its text into lists. Preserve the relationships those slides make visible. A sequence of independent bullets can retain every sentence and still lose the actual synthesis.

| Content relationship | Suitable form | What to preserve |
|---|---|---|
| A concept with several kinds of property | Framed table with labeled rows | Original labels and one visible position per distinct claim |
| Methods compared on shared dimensions | Boxed comparison matrix | The source's comparison axes and wording |
| A parent concept with named instances | Grouped rows, an adjacent instance box, or a small hierarchy | The attachment between the general concept and each instance |
| A synthesis or summary | The source's compact table, diagram, or equivalent reconstruction | Categories, contrasts, dependencies, and integration |
| A few independent statements | A short list | Separate named facts without hidden semicolon sublists |
| A procedure or derivation | Numbered steps or aligned equations | Order and the reason for each transition |
| A quantitative or spatial relation | Plot or annotated diagram | Data, scale, units, geometry, and relevant labels |

Choose structure from the material. Tables are particularly useful for related text, but do not turn a two-step procedure into a large matrix or put an entire paragraph into one cell.

## Framed tables that remain readable

A box should group related content; internal row and column boundaries should reveal its dimensions. Prefer the source's organization when it is useful. Use a compact heading such as the source's own Synthesis, Summary, or Comparison label.

- Keep definitions, advantages, limitations, and costs in separate labeled rows or fields when they are distinct claims.
- Preserve the actual slide phrases inside cells. A table is a restructuring device, not an invitation to paraphrase every entry.
- Use multiple rows when a source category has several independent points. Do not conceal them in one long cell joined by semicolons.
- **Line-by-line anti-crowding rule:** never pack multiple points, metrics, applications, or parallel `Input / Output` pairs onto one line separated by semicolons—during high-stress exam review, dense semicolon walls sharply degrade scanning speed. Start every distinct point on its own line using the reusable hanging-indent table cell macros in `review-style.sty` (`\tfirst`/`\ti` for bullets, `\tnumfirst`/`\tnum` for numbered entries, `\tsubfirst`/`\tsub` for bold sub-group headings, separated by `\addlinespace[2.5pt]`–`\addlinespace[3.5pt]` row breathing room), or stack compact parallel pairs (such as `Input` and `Output`) with a left curly brace `\begin{cases}...\end{cases}` inside full-width blocks. Never place wide `cases` blocks inside narrow half-width `minipage`s where they overflow horizontally.
- Keep related instances in the parent's group. A named method may also have a detailed treatment elsewhere, referenced from the local instance.
- Show an absent comparison value as unspecified when necessary rather than inventing a symmetric counterpart.
- Split an overlong matrix into coherent groups or continuation tables before reducing text to an unreadable size.

Original slide images may retain their internal layout if legible. Reconstruct a table when cropping or scaling the original would make it hard to read. Verify its wording and relationships against the source.

## Keep lecture order visible

Use lecture headings and navigation in source order. Group the lecture's concepts and synthesis inside that boundary. Do not move a later lecture's section into an earlier lecture merely because their topics are related. Cross-reference the connection instead.

A lecture's opening overview and ending synthesis serve different purposes; preserve their placement when it contributes to the progression. An additional cross-lecture overview can complement the body but cannot replace the lecture-ordered presentation.

## Match depth before adding visuals

Choose a topic's treatment from explicit exam guidance, the source's emphasis, its worked examples, and synthesis. Raw slide count is only a clue. Do not invent assessment weights or equate ease of explanation with importance.

A minor property or named instance should normally remain a compact local entry. A core assessed method may warrant a calculation or fuller diagram. A request to illustrate a topic is not a request to add new theory or dedicate a page to it.

The user found the earlier ROC treatment disproportionately detailed. This is an instance of poor emphasis calibration, not a rule to exclude ROC from future courses. If the source treats a topic briefly, a small diagram and its essential reading rule may be enough. If another course treats it deeply, follow that course's depth.

## Visual examples, not a topic checklist

Past instances illustrate how a representation can help:

- Quantile comparison can use a Q-Q plot to show its axes and reference relationship.
- Ranked predictions can use linked ROC/PR markers or an area cue when those concepts are in scope and deserve that treatment.
- Tree or search examples can label branches and counts to expose a split or pruning decision.
- Dependency networks can show the parent sets used by a factorization.
- Neighbor, sequence, and graph examples can visualize the distances, mappings, or counting units used in the solution.

Do not require these topics in other courses. An assumption table, proof dependency chain, classification summary, or timeline may be the appropriate representation instead.

## Data and proximity

Reuse adjacent example data and retain labels, values, order, conditions, and directions. If only distances or occurrence counts are given, explicitly label a constructed coordinate layout or topology as schematic. Do not turn that choice into an added problem condition.

Use matching markers across related figures when helpful, and provide meaningful labels, axes, units, and counting conventions. Standard plotting tools suit accurate quantitative graphics; TikZ or SVG can suit structural diagrams. Prefer vectors in PDF and retain the data or generating source.

Place each visual and instance with its parent concept. A caption should add only the necessary reading instruction. Added exposition must not bury the source statement or create a distant standalone chapter for an incidental example.

## Curated memory-aid slide figure cropping

For anatomy diagrams, conceptual wheels, pipelines, timelines, or visual intuition sketches that directly aid recall, prefer clean high-resolution crops from the original slides over redrawing complex artwork:

- **Pure-`PyMuPDF` (`fitz`) extraction:** crop directly with `PyMuPDF` (`page.get_pixmap(clip=rect, dpi=300, alpha=False)`) so the pipeline needs zero `PIL`/`Pillow` dependency. Filter out repeating slide template logos, headers, and footers automatically by recurring image `xref` and small edge bounding boxes, and skip purely decorative stock photos.
- **Tight crop & contact-sheet verification:** apply a tight `0.5pt` inset to clip hairline frame borders, render all cropped figures onto one visual contact sheet, and inspect every crop for clipped labels or stray margins before inserting it into `.tex`.
- **Tight-border framing in LaTeX:** insert cropped figures using `\slidefig` (which sets `\fboxsep=1.5pt`, `\fboxrule=0.4pt`, and deducts the `3.8pt` frame padding automatically) and `\figcap` from `review-style.sty`. Default `3pt` `\fcolorbox` padding silently adds `6pt+` to a figure's width and forces paired figures in side-by-side `minipage`s to wrap vertically.

## Compress through layout

Keep single-column body text. A local text/figure pair is useful when both remain readable. Given stays in its own paragraph above the solution. Put a long calculation chain full-width rather than narrowing it beside a diagram.

A useful compression order is:

1. Measure main-body pages/words and set the task budget; remove duplicated exposition, proofs, obsolete previews, and trivial checks while preserving source qualifications.
2. Consolidate related text using source-style synthesis and comparison tables.
3. Remove repeated setup around examples, retaining the formula and substitution stages.
4. Adjust table widths, local image placement, and unnecessary whitespace.
5. Repair orphan continuations, excessive Needspace reservations, and oversized unbreakable blocks without shrinking the type or hiding independent facts. Inspect actual pages for unused space; a few lines stranded on an otherwise empty page are a layout failure.

Do not enforce one topic per page. Preserve the hierarchy and complete reasoning, then choose page breaks. If a hard page limit conflicts with complete readable coverage, identify the concrete tradeoff; do not silently remove scope or source synthesis.

## Retrieval-focused presentation

Read [retrieval-and-scope.md](retrieval-and-scope.md) when retrieval is the task. Use standard/source terms at the start of headings, verified cross-references, and useful dependency chains or comparison matrices. A full-course master lookup and a one-page lecture sheet are optional scoped designs, not universal quotas. Preserve assessed APPLY material when placing source-optional extensions in a marked lecture-end section or authorized separate volume. Separate lookup and self-test files should not also be copied into the body. Keep body definitions, local conditions, and substantive synthesis.

For substantive proofs, separate assumptions, the Core idea, proof actions, and a consequential trap visually without boxing every sentence. Elementary support needs only 1–3 readable lines, with no compulsory Core idea or numbered Steps. A hard SUPPORT proof still needs its essential argument. Traps may wrap to multiple lines. A provenance label identifies where a number came from; it must not compete with the teaching explanation or imply that a reported measurement was computed.

## Optional template

The English assets demonstrate two **illustrative lecture sections**, framed concept/synthesis tables, selected nearby instances, separate Given paragraphs, complete formula chains, and an optional standalone proof-layout sample. Their statistics and neighbor content is demonstration material, not a required syllabus.

`review-style.sty` (preset 1.6.0) includes `reviewsynthesis`, `reviewlookup`, `reviewextension`, `inlineconcept`, and `supplementbox` boxes, understated mastery-depth tags (`\depthcalc`..`\depthnoexam` and optional closed-book conceptual tags `\depthcore`, `\depthcontrast`, `\depthmethod`, `\depthsupp`), tight-border `\slidefig` + `\figcap`, hanging-indent cell helpers (`\tfirst`/`\ti`, `\tnumfirst`/`\tnum`, `\tsubfirst`/`\tsub`), plus wrapping `\coreidea`, `\assumptions`, `\examtrap`, and `\provenance` helpers. Use only the helpers justified by the task; no macro enforces a page or example quota. The standalone `proof-layout.tex` contrasts an elementary deduction with a substantive proof and a canonical cross-reference without adding mandatory topics to the starter. `review-style.sty` includes a `reviewsynthesis` box. Inside it, use a table with clear row or column boundaries to expose the relationships. The starter also shows one topic's properties as rows instead of a list of semicolon-packed bullets.

The preset uses single-column A4, 10.8pt serif body text, blue headings and summary/method frames, and green example frames. These are adjustable defaults. For concept-dense courses where multi-color callouts create visual fatigue, maintain a calm monochrome/slate palette (deep slate ink, muted slate headings/tags, light tint boxes, and neutral gray for constructed intuition checks, lecture-end supplements, and non-exam appendices) rather than loud accents. Prefer suitable existing sources or the user's chosen template. For Chinese body text, choose a suitable CJK font and compiler configuration instead of inserting it directly into this English pdfLaTeX starter.

## Modular multi-lecture sources and LaTeX safety gates

When a course requires both standalone lecture PDFs and combined or full-course bound editions, keep each lecture in one canonical body file (`lectures/lecture_N.tex`) and compile standalone wrappers (setting `\setcounter{chapter}{N-1}`), phase bundles, and a full-course bound edition from that single source so edits never drift across outputs. For bound editions with long tables of contents, tune `\l@chapter` vertical spacing and compact frontmatter sizing so the cover, depth-tag legend, and clickable TOC fit cleanly on one page without an orphan trailing TOC page.

Guard against eight recurring LaTeX build, layout, and audit traps before delivery:

1. **Never put a `breakable` `tcolorbox` inside a `minipage`:** `tcolorbox` computes remaining height against the outer page and silently crushes or clips the box with `The upper box part has become overfull` warnings. Always use a non-breakable variant (`inlineexample` or `inlineconcept`, with `breakable=false` placed *after* the base style) beside figures in a `minipage`.
2. **Keep badges and math out of raw TOC/bookmark strings:** when using right-aligned depth tags (`\depth...`) or math in `\section` / `\subsection`, pass a clean short TOC title and wrap tags/math in `\texorpdfstring` (for example, `\section[Clean title]{Clean title \texorpdfstring{\depthconcept}{}}`), and avoid `\hfill`-based tags inside inline prose or `itemize` bullets (use plain italic parentheticals instead).
3. **Run pre-compile numerical verification and source lint:** verify every worked example and constructed check with a Python script, and lint `.tex` files before `pdflatex` for stray Markdown syntax (`*...*`, single backticks), unescaped `&` outside tabular/align separators, and—when a humanizer pass is active—prose em/en dashes (`—`, `–`, `---`) or stock AI filler words.
4. **Build fast on native storage in WSL/mounted drives:** when source files reside on a slow mounted filesystem (such as `/mnt/d/`), copy sources to a native `/tmp` build directory, run two `pdflatex` passes there, verify zero warnings, and copy the resulting PDFs and logs back.
5. **Two-column bound TOC spacing and clean frontmatter headers:** when placing a single-page clickable TOC inside `multicols`, explicitly redefine `\numberline` with a fixed-width `\makebox` inside `\l@chapter` and `\l@section` and reserve a right-aligned page-number channel via `\rightskip=2.0em \parfillskip=-2.0em` so long titles wrap cleanly without colliding with page numbers. Set `\thispagestyle{empty}` on cover and TOC pages so `Lecture 0` never appears in the running header.
6. **Cross-chapter `\ref` safety in single-source standalone wrappers:** never put bare cross-chapter `\ref{chap:lM}` inside canonical `lectures/lecture_N.tex` files (standalone builds cannot resolve another lecture's chapter label and emit undefined-reference warnings); use plain lecture labels (`Lecture M`) or a wrapper-aware conditional macro instead.
7. **Side-by-side `[t]` `minipage` paragraph breaks and top alignment:** precede side-by-side `minipage` pairs with `\par\vspace{1pt}\noindent` (never place them directly after an inline bold lead-in) and start each `[t]` `minipage` with `\vspace{0pt}` so adjacent frame top borders align cleanly.
8. **`\newline` inside last-column table macros and normalized Ctrl+F audits:** use `\par` or `\newline` (never `\\`) inside custom cell-formatting macros that may appear in the last column of `longtable` / `tabularx` (otherwise LaTeX interprets `\\` as a table row terminator and fails with `Missing } inserted`). In automated PDF Ctrl+F audits, normalize wrapped whitespace and curly apostrophes (`’` -> `'`) before checking extracted text so line breaks and smart quotes do not produce false misses.

Copy the two assets into the task's output directory and compile:

```bash
pdflatex -interaction=nonstopmode -halt-on-error starter.tex
pdflatex -interaction=nonstopmode -halt-on-error starter.tex
```

Split long examples at complete step boundaries and retain their identity on continuation. Do not separate a parent concept from its instance or a formula from its substitution merely to fill a page.

## Review the result

Check lecture progression, original wording, synthesis coverage, instance locality, formula chains, topic emphasis, and numerical correctness. Then inspect the rendered document at actual reading size for cell overflow, text size, diagram labels, clipped equations, orphan pages, and navigation. For compression, compare the actual before/after counts by main body, main-file total, and entire delivery, reporting relocated supplements separately. Inspect every page in an overview, then near-empty pages and page breaks at full size; find whether Needspace, forced breaks, or nonbreaking containers caused gaps. See [compression-and-release.md](compression-and-release.md) for acceptance gates.

A full reconstruction needs all-page and source-coverage review. A local edit needs affected-block checks. Deliver synchronized sources and required assets, and distinguish those checks from untested future behavior.
