# rewrite-course-notes

> **Version 1.6.0** · Agent Skill for students reviewing previously studied courses before exams  
> Restructure and compress course slides (PPTX / Beamer PDF) in original lecture order while preserving lecturer wording, complete formula chains, and slide synthesis—producing clean, searchable LaTeX / PDF review notes without visual clutter.

---

## 1. Introduction: What It Is, Why Use It, and Style

### What It Is

`rewrite-course-notes` is an **Agent Skill** ([SKILL.md](SKILL.md), version history in [CHANGELOG.md](CHANGELOG.md)) built for learners who have already attended class and need compact, exam-ready review sheets rather than another introductory textbook. Given course slides and exam scope, the agent extracts text, speaker notes, and figures in lecture order, verifies worked calculations and errata with scripts, and outputs structured LaTeX / PDF review notes and optional lookup companions.

### Why Use It: Eliminating "AI Slop" Course Notes

Too many lecture decks and AI-generated study summaries suffer from **AI slop**: pages look busy yet actively get in the way of exam prep. Each rule in this skill targets one concrete failure mode:

| Common slide / AI summary failure | How it disrupts exam review | How `rewrite-course-notes` fixes it |
|---|---|---|
| **Indiscriminate content stuffing** | Definitions, motivational filler, research outlooks, and trivial numeric plugs crowd the same page, hiding what is actually tested | • Separates core exam material from lecture-end `[Supplement]` / extension blocks<br>• Deletes redundant one-number checks and obsolete later-covered previews<br>• Keeps classroom exercises, difficult concepts, and consequential counterexamples |
| **Cluttered layout** | Semicolon-packed sentences and deeply nested bullet walls hide boundaries between distinct claims | • Picks the smallest structure that fits the relation (property table, comparison matrix, numbered steps)<br>• Enforces line-by-line anti-crowding so every independent claim starts on its own line |
| **Excessive colors** | Rainbow text highlights and loud callout boxes across every page cause rapid visual fatigue | • Uses a restrained slate-blue, soft-green, and neutral-gray palette ([review-style.sty](assets/review-style.sty))<br>• Normalizes colored Beamer / PPTX highlights into clean typographic `\textbf{}` |
| **Diluted emphasis** | Hand calculations, formula interpretation, concept contrasts, and paper tours look identical, leaving you guessing what to memorize vs. compute | • Places understated, evidence-backed mastery-depth tags in headings<br>• Selects either the math/applied palette or the closed-book conceptual palette per course, never invented weights |
| **Broken main thread** | Cross-lecture reshuffling and detached examples separate an instance from its parent concept by pages | • Preserves the outer lecture sequence (`Lecture 1` through `Lecture N`), reorganizing only within each lecture<br>• Keeps every instance adjacent to its parent concept and links repeated proofs to one canonical source |
| **Unclear page purpose** | Flipping a page gives no immediate cue whether you are reading a definition, contrast, worked derivation, or optional aside | • Assigns explicit visual roles: `reviewmethod` (tools/statements), `reviewsynthesis` (summaries), `workedexample` (problems), `Exam trap`, and lecture-end `supplementbox`<br>• Supports clickable tables of contents and script-audited `(p. #)` lookup sheets |

### Style and Core Mechanisms

| Dimension | Operative Rule | Built-in Implementation |
|---|---|---|
| **Source wording first** | Reuse slide phrasing and qualifiers for definitions, properties, costs, limitations, and comparison axes; compress by selection, deduplication, and layout | • Restricts prose polishing to added transitions and action verbs<br>• Discloses verified slide typos or convention flips openly in `Scope / trap` and `SOURCE_MAP.md` instead of silently altering source terms |
| **Line-by-line anti-crowding** | Never pack multiple metrics, applications, or parallel `Input / Output` pairs onto one semicolon-separated line | • Uses hanging-indent table cell macros (`\tfirst`/`\ti`, `\tnumfirst`/`\tnum`, `\tsubfirst`/`\tsub`) in [review-style.sty](assets/review-style.sty)<br>• Stacks compact parallel pairs in full-width `\begin{cases}...\end{cases}` blocks |
| **Four-stage calculation chains** | Worked formula examples must expose inputs, symbolic formula, substitution, and result instead of jumping straight to a number | • Separates `Given` above numbered solution steps<br>• Shows `notation = symbolic formula = substituted values = result` (`\approx` when rounded)<br>• Verifies every numerical example and constructed check with Python before delivery |
| **Complexity-aware proofs** | Explain the trick behind hard derivations without burying elementary identities under boilerplate | • Substantive multi-step proofs: `Assumptions`, one-sentence `Core idea`, named steps, aligned displays, and optional `Exam trap`<br>• Elementary identities: 1–3 readable lines without forced headings |
| **Course-matched depth tags** | Match assessment labels to the actual exam format rather than forcing one template onto every course | • **Math / applied courses (Palette A):** `[Hand-calc]`, `[Formula: interpret]`, `[Conceptual]`, `[Research preview]`, `[Not in exam scope]`<br>• **Closed-book conceptual / paper-showcase courses (Palette B):** `[Core Concept]`, `[Contrast / Taxonomy]`, `[Method Map: I/O]`, `[Supplement]` |
| **Multimodal extraction & figure cropping** | Capture clues that plain PDF text dumps drop, and retain clean visual memory aids | • PPTX + PDF: extracts speaker notes, hidden slides (`show="0"`), and flags `imgs > 0` pages lacking math XML for visual contact-sheet review<br>• Beamer PDF: runs span-level `PyMuPDF` inspection for color/bold keywords and shared-footer quiz/answer overlays<br>• Pure-`PyMuPDF` (`fitz`, no `PIL` dependency) `300 DPI` figure cropping with recurring-logo filtering and tight-border `\slidefig` |
| **Single-source builds & 8 safety gates** | Build standalone lecture PDFs and a full bound book from one canonical source without broken formatting | • Canonical `lectures/lecture_N.tex` files included by thin standalone and bound wrappers<br>• Enforces 8 LaTeX gates: non-breakable `inlineexample`/`inlineconcept` in `minipage`s, `[Clean Title]` + `\texorpdfstring`, two-column bound TOC spacing, cross-chapter `\ref` safety, `[t]` `minipage` top alignment, `\newline` in last-column table macros, pre-compile lint, and Ctrl+F / `(p. #)` audits |

### Repository Contents

| Path | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Main skill specification (v1.6.0): scope discovery, lecture order, source wording, worked chains, layout, and release gates |
| [CHANGELOG.md](CHANGELOG.md) | Complete release notes from v1.1.0 through v1.6.0 |
| [assets/review-style.sty](assets/review-style.sty) | Single-column A4 LaTeX preset (10.8pt serif body, slate/green/gray palette, boxes, depth tags, `\slidefig`, hanging-indent cell macros) |
| [assets/starter.tex](assets/starter.tex) | Compilable lecture demo (concept matrix, full calculation chain, text-plus-TikZ `minipage`, lecture synthesis) |
| [assets/proof-layout.tex](assets/proof-layout.tex) | Compilable proof demo contrasting a 1–3 line identity with a `Core idea` + named-steps proof and `Exam trap` |
| [references/structure-and-phrasing.md](references/structure-and-phrasing.md) | Source-wording preservation, anti-crowding tables, instance locality, and four-stage calculation rules |
| [references/figures-and-layout.md](references/figures-and-layout.md) | Structure selection, pure-`PyMuPDF` 300 DPI cropping, single-source builds, and the 8 LaTeX safety gates |
| [references/retrieval-and-scope.md](references/retrieval-and-scope.md) | Open-book vs. closed-book 3-part quick-lookup designs, Beamer extraction, depth palettes, and notation/errata registry |
| [references/mathematical-review.md](references/mathematical-review.md) | Theorem conditions, randomness/quantifier hygiene, proof prioritization, and computed vs. reported measurements |
| [references/compression-and-release.md](references/compression-and-release.md) | Main-body baseline accounting, deduplication criteria, companion-volume boundaries, and page/whitespace gates |
| [references/preference-evidence.md](references/preference-evidence.md) | Provenance and generalization boundaries for maintaining the skill |
| [agents/openai.yaml](agents/openai.yaml) | Agent UI discovery metadata and default prompt |

---

## 2. Configure on an Agent

### Option A: Install via Skills CLI (Recommended)

Works across Codex, Claude Code, Antigravity, Cursor, OpenCode, and other tools compatible with [Agent Skills](https://skills.sh/):

```bash
npx skills add EnjiXiong/rewrite-course-notes
```

Install globally without interactive prompts:

```bash
npx skills add EnjiXiong/rewrite-course-notes -g -y
```

### Option B: Clone Directly into Your Agent's Skills Directory

The repository root is a self-contained skill folder (`SKILL.md`, `assets/`, `references/`). Clone it into the target directory and run `git pull` later to update:

| Agent / Scope | Install command | Invoke in chat |
|---|---|---|
| **Codex** (global) | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git ~/.codex/skills/rewrite-course-notes` | `$rewrite-course-notes` |
| **Antigravity** (global) | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git ~/.gemini/config/skills/rewrite-course-notes` | `/rewrite-course-notes` |
| **Claude Code** (global) | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git ~/.claude/skills/rewrite-course-notes` | `/rewrite-course-notes` |
| **Project-local** (Cursor, OpenCode, Antigravity, etc.) | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git .agents/skills/rewrite-course-notes` | Reference the skill name in chat |

### Optional Local Dependencies (For PDF Compilation & Slide Extraction)

Markdown-only review sheets need no extra packages. To compile the LaTeX templates into PDF and extract PPTX speaker notes, hidden slides, and slide figures:

1. **LaTeX distribution**: TeX Live (`pdflatex` for English notes; `xelatex` + `ctex` for Chinese notes). Verify the bundled preset works:
   ```bash
   cp assets/review-style.sty assets/starter.tex /tmp/ && cd /tmp && pdflatex starter.tex && pdflatex starter.tex
   ```
2. **Python extraction libraries** (install as needed for your source decks):
   ```bash
   pip install pymupdf python-pptx
   ```

---

## 3. Recommended Prompt

Copy the Markdown block below, replace the `[...]` placeholders with your course details, and paste it to your agent (switch `/rewrite-course-notes` to `$rewrite-course-notes` if using Codex):

```markdown
Use /rewrite-course-notes to build exam review notes for **[Course Code & Title]**.

## 1. Source Files & Lecture Order
- **Source directory:** `[path/to/slides/]`
- **Files included (in lecture order):** `[Lecture 01 .. Lecture N; specify whether PPTX, PDF, or both exist]`
- **Slide numbering convention:** `[Beamer footer slide number / PPTX slide index / raw PDF page]`
- **Extra source materials (optional):** `[homework solutions, midterm review sheet, syllabus, or "None"]`

## 2. Exam Coverage & Scope Boundaries
- **In-scope lectures / topics:** `[e.g., Lectures 1-10 in full, plus Lecture 11 Sections 1-2]`
- **Explicitly excluded from exam:** `[e.g., Lecture 4 Appendix and Lecture 9 research outlook, or "None - confirm before dropping anything"]`
- **Emphasis / exam weights (if known):** `[e.g., Lectures 5-8 account for ~60% of the final, with heavy weight on derivations in L6]`
- **Must-keep examples / exercises:** `[e.g., all in-class Quick Checks and Tutorial 3-5 worked problems]`

## 3. Exam Format & Preferred Assessment Style
- **Exam format:** `[Closed-book / Open-book / One-sheet cheat-sheet allowed]`
- **Question types & focus:** `[e.g., 40% hand calculation, 30% concept comparison and MCQ discrimination, 30% proof reconstruction]`
- **Mastery-depth tag palette:** `[Palette A: Hand-calc / Formula: interpret / Conceptual / Research preview  OR  Palette B: Core Concept / Contrast / Taxonomy / Method Map: I/O / Supplement]`
- **Proof & derivation depth:** `[e.g., full reconstructible proofs for starred theorems, 1-3 lines for elementary identities, statement + conditions + application for APPLY results]`
- **Paper-showcase / conceptual slides (if any):** `[e.g., compress paper tours into Method Map: I/O tables and relocate dense figure-embedded details to lecture-end Supplement boxes]`

## 4. Deliverables, Language & Companion Volumes
- **Output directory:** `[path/to/output/]`
- **Output format & language:** `[LaTeX + compiled PDF using assets/review-style.sty; notes in English (or Chinese with original English canonical terms)]`
- **Build layout:** `[Single-source modular lectures/lecture_N.tex -> standalone per-lecture PDFs + one full bound PDF  OR  single combined PDF]`
- **Page / compression target:** `[e.g., prioritize completeness with clean density  OR  compress an existing draft to ~40-50 main-body pages without shrinking font]`
- **Optional companion volumes (confirm upfront):**
  - `quick-lookup`: `[Yes (open-book task-to-tool index) / Yes (closed-book 3-part contrast + taxonomy + glossary) / No]`
  - `self-test`: `[Yes / No]`
  - `extensions`: `[Yes (separate file) / Keep marked at lecture end / No]`

## 5. Personal Weak Spots & Verification Gates
- **Topics I still find unfamiliar (strengthen worked examples):** `[e.g., Lecture 6 spectral clustering, Lecture 8 EM updates]`
- **Visuals & slide figures:** `[Crop high-value diagrams, conceptual wheels, and pipelines from slides at 300 DPI via PyMuPDF with contact-sheet check; skip decorative clutter]`
- **Mandatory checks before delivery:**
  1. Preserve original slide wording for definitions, properties, assumptions, and trade-offs.
  2. Enforce line-by-line anti-crowding (no semicolon-packed walls in bullets or table cells).
  3. Show complete `notation = symbolic formula = substituted values = result` chains and verify all numerical examples with a Python script.
  4. Maintain a notation, convention-flip, and slide-errata registry (`SOURCE_MAP.md`), and verify zero LaTeX warnings, clean page breaks, searchable text, and audited `(p. #)` pointers.
```

### Quick Guide to Key Prompt Fields

| Field | What to specify | Effect on the output |
|---|---|---|
| **In-scope / Excluded** | List covered lectures and explicitly excluded parts; write `None` if unsure | Prevents accidental removal of tested appendices and keeps excluded topics out of core space |
| **Exam format** | State `Closed-book` or `Open-book` | Selects the companion architecture (contrast matrix + taxonomy + glossary vs. task-to-tool index) |
| **Mastery-depth tag palette** | Pick **Palette A** for math/applied exams or **Palette B** for closed-book conceptual/paper courses | Applies one consistent set of depth badges across the whole pack |
| **Optional companion volumes** | Answer `Yes` or `No` upfront for `quick-lookup`, `self-test`, and `extensions` | Generates only the volumes you will actually study before the exam |
| **Topics I still find unfamiliar** | Name 2–4 topics where you keep getting stuck | Strengthens worked examples and intuition checks locally without bloating other lectures |
