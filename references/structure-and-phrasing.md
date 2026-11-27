# Source wording, synthesis, and worked solutions

The user values recognition of the slides during review. Restructure the presentation while retaining the lecturer's terminology and phrasing. The examples below illustrate the rules, not required course topics.

## Preserve source statements

Use original wording for concepts, definitions, properties, advantages, disadvantages, costs, limitations, and assumptions. Do not substitute a stylistically polished synonym, compress several qualifications into a generic claim, or humanize a lecturer's recognizable statement.

| Material | Editing approach |
|---|---|
| A definition or property from a slide | Retain its wording and conditions; change placement or formatting as needed |
| Several independent clauses in one source bullet | Split into labeled rows or cells while preserving the individual phrases |
| A repeated statement elsewhere in the same lecture | Keep one occurrence and retain any additional qualification |
| An assistant-written transition or calculation instruction | Write a short, direct action or logical connection |
| A source statement that appears incorrect | Check the slide and explain the correction; do not silently rewrite it |
| Text available only through uncertain extraction or an older note | Verify against the rendered source or disclose the limitation; do not claim exact wording |

If translation is requested, use a faithful translation and preserve key source labels. Unrelated grammar polishing is secondary to source recognition. Humanizer may refine added prose, not the source statements.

## Replace hidden subpoints with visible structure

Consider these **invented source phrases**, used only to demonstrate layout:

- Method A: “Fast training.” “High prediction cost.” “Sensitive to irrelevant attributes.”
- Method B: “Training cost depends on model complexity.” “Low prediction cost.”

A bullet such as “Method A: fast to train; prediction is expensive; irrelevant attributes can hurt” both paraphrases the source and hides three properties.

A framed matrix can preserve each phrase:

| Source dimension | Method A | Method B |
|---|---|---|
| Training | Fast training. | Training cost depends on model complexity. |
| Prediction | High prediction cost. | Low prediction cost. |
| Limitation | Sensitive to irrelevant attributes. | Not specified in this example. |

The last cell explicitly reports missing information rather than inventing a matching limitation. In real notes, use the slides' dimension labels and wording. The table is not a license to force every topic into these particular columns.

Lists remain useful for a few independent facts. Use numbered lists for ordered actions. Inside a list item or table cell, do not join independent advantages, costs, and limitations with semicolons. Give each claim its own row, field, or short subentry. Semicolons used as ordinary punctuation are not categorically forbidden. They must not carry multi-step proof logic: give essential transformations named actions and separate aligned displays, as in [mathematical-review.md](mathematical-review.md).

## Preserve synthesis and lecture order

Use the lecture sequence as the main hierarchy. Reorganize related material only inside its source lecture unless the user explicitly requests a thematic order.

Before drafting a lecture, identify its synthesis, summary, comparison, and overview slides. Record what each one connects. Preserve that connection in the notes, even if its sentences have already appeared individually. A summary matrix is not redundant merely because all its cells contain familiar terms.

Keep the summary in the lecture where it belongs and respect its role in the teaching progression. An introductory synthesis may orient a section; an ending comparison may consolidate it. Do not automatically move every summary to the end of the entire document.

When an important relationship is implicit, a short constructed synthesis can group already covered material. Keep it source-grounded and do not present it as a verbatim lecturer summary. Cross-lecture connections use references or a clearly additional overview; they do not interleave the main lecture blocks. Choose one canonical statement/proof and replace later restatements with working references. Delete obsolete previews when the complete treatment is already supplied. A separate lookup should index this body, not trigger a duplicate inventory inside it; preserve definitions needed for standalone reading.

## Keep instances attached

A named technique, application, special case, or counterexample belongs directly under the concept it illustrates. A useful shape is:

| Parent concept | Source condition or property | Instance from these slides |
|---|---|---|
| The source concept's name | Its original wording | The named instance, followed by one necessary explanation |

Do not relocate a named instance to a distant general-method chapter solely because the same term appears there. Keep a compact local mention and use a cross-reference for the longer treatment. The earlier S3VM feedback illustrates this locality failure; it does not make S3VM a mandatory topic or establish its parent for unrelated courses.

## Select examples before formatting them

Use the main skill's ranked selection: classroom/assessed exercises, learning checks, difficult concepts or reusable solution patterns, and consequential counterexamples. Essential coverage overrides this ordering. Preserve distinct methods and useful concrete explanation, not a fixed example count. A theorem does not automatically need its own example. Merge repeated setup and delete redundant one-number substitutions or synonymous checks. Do not rename them to retain the same text. Preserve classroom problems, stated learning difficulties, distinct methods, and consequential counterexamples; a useful fragment may be merged into the existing explanation.

A retained example separates **Given**, numbered **actions** when order matters, and **Result**. Preserve the formula/substitution chain below. Use a separate compact **Check / Exam trap** only where it helps; do not force the example back into a single prose paragraph. Keep source/constructed labels short and distinguish them from the mathematical explanation.

## Formula-based solutions must show the calculation chain

The minimum chain is:

\[
\text{notation}
=\text{symbolic formula}
=\text{formula with values substituted}
=\text{result}.
\]

A numeric result alone is insufficient, even if the formula appears elsewhere on the page. The formula shows what is being calculated; substitution connects it to Given. Use an approximate-equality sign when rounding.

Illustrative variance example:

> **Given:** Values \(1,2,3\). Compare population and sample variance. Use \(N=n=3\).
>
> 1. **Mean:**
>    \[
>    \bar x=\frac1n\sum_{i=1}^n x_i=\frac{1+2+3}{3}=2.
>    \]
>    For these same three values treated as the entire population, \(\mu=\bar x\).
> 2. **Population variance:**
>    \[
>    \sigma^2=\frac1N\sum_{i=1}^N(x_i-\mu)^2
>    =\frac{(1-2)^2+(2-2)^2+(3-2)^2}{3}
>    =\frac23\approx0.6667.
>    \]
> 3. **Sample variance:**
>    \[
>    s^2=\frac1{n-1}\sum_{i=1}^n(x_i-\bar x)^2
>    =\frac{(1-2)^2+(2-2)^2+(3-2)^2}{3-1}=1.
>    \]
>
> **Result:** The denominator changes from \(N\) to \(n-1\). Choose it from the question's population/sample interpretation.

Keep Given above the solution, not inside the first equation. Align long chains across lines rather than making them tiny. Reuse computed intermediate values when their meaning and earlier calculation are visible.

For the original neighbor instance, the formulas must also be visible:

\[
\begin{aligned}
W_A&=\sum_{i:y_i=A}\frac1{d_i^2}
=\frac1{1^2}=1,\\
W_B&=\sum_{i:y_i=B}\frac1{d_i^2}
=\frac1{2^2}+\frac1{3^2}=\frac{13}{36}.
\end{aligned}
\]

Do not replace the first line with just \(W_A=1\). An ordinary vote count or qualitative decision does not require an artificial formula merely to fit the pattern.

For symbolic questions, show the equivalent chain without inventing numbers. Proofs need their assumptions and deduction structure, not a fabricated numerical substitution. Elementary identities can use 1–3 readable lines without Core idea or Steps headings; substantive proofs retain mechanism and essential steps regardless of source badge. Preserve a short justification when a branch, bound, or normalization is the actual reasoning step.

## Compression and added phrasing

Compress repeated exposition, not the essential formula stages of selected examples or independent in-scope source claims. Measure contraction using [compression-and-release.md](compression-and-release.md); deleting a box environment or changing its title does not count as deletion. Move reproduction minutiae to the source map, and use separate lookup, extensions, or self-test volumes only within the authorized task scope. Use specific verbs for newly written solution instructions: Compute, Substitute, Compare, Normalize, Prune. Remove generic introductions from assistant-authored prose.

Depth follows the course: a passing instance normally needs its local role, not a separate tutorial. A heavily assessed method may need a fuller worked solution. Preserve useful distinctions and source qualifiers while allocating space to what the slides and assessment actually emphasize.
