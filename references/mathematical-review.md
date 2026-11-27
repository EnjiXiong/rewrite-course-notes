# Mathematical review: statements, proofs, and calculations

Use this reference for courses in which reconstructing an argument is part of review, such as statistical learning theory, probability, optimization, and linear algebra. It supplements the source-wording, lecture-order, and example rules; it does not prescribe these topics or a fixed document template.

## Organize around the question and its mathematical objects

Open a lecture with its immediate mathematical objective and, when helpful, one short connection to the preceding lecture. Within the lecture, connect the problem, missing step, required tool, and resulting conclusion. Retain the source's progression and synthesis without repeating a roadmap before each result.

Define a symbol before using it. For matrices, vectors, random variables, and functions that are easy to confuse, give dimensions and roles. If two symbols represent the same object in different coordinates, state the translation once and use one consistent convention thereafter. Distinguish a trainable parameter from a quantity computed from it, and a function from its values on a sample.

For a statistical statement, make these reading questions answerable from the statement and its immediate context:

- What object is controlled, and under which loss or norm?
- What is held fixed, what is random, and what distribution supplies the probability or expectation?
- What assumptions license the claim, and which comparator or reference value is used?
- What is the conclusion, including constants, quantifiers, rate, and simultaneous scope?
- Which boundary or omitted condition would invalidate the application?

Use a concise setup or notation table shared by nearby results when this avoids repeated assumptions. Do not turn every theorem into a mandatory five-row form.

## Preserve proof priorities without inventing exam requirements

Read explicit source badges and assessment guidance. A full proof printed on a slide does not by itself make independent reconstruction required. A theorem can have an application requirement while selected proof steps have reconstruction requirements.

Where the source supports it, distinguish:

| Role | Appropriate treatment |
|---|---|
| Required reconstruction | Complete statement and reconstructible proof, with each essential inference |
| Supporting derivation | Preserve source status; label added derivations as editorial support. Use 1–3 lines for elementary identities, full essential reasoning for substantive arguments |
| Stated tool or application | Statement, hypotheses, and an actual application; do not silently elevate an external proof |
| Explicit source-optional extension or preview | Mark source status in a lecture-end section or authorized supplement; remove duplicate later-covered previews and keep assessed applications in the main path |

Required proof and assessed application are separate dimensions: an APPLY result is not optional merely because reconstruction of its proof is not required. Labels such as REBUILD / CORE, REBUILD / SUPPORT, and APPLY are conventions from one accepted project. Keep the current course's vocabulary when different. Record the source location and any editorial recommendation separately.

## Write proofs as actions with their reasons

Put the theorem or lemma in the existing result style, with its genuine assumptions, quantifiers, and guarantee type. For a substantive multi-step proof, write a concise **Core idea** that identifies its mechanism: the construction, symmetry, decomposition, or inequality that makes the argument work. It can precede the statement or follow it immediately before the proof. A topic label such as “use algebra” is insufficient.

For elementary identities, use a direct 1–3-line deduction with its conditions; omit compulsory Core idea and Steps scaffolding. This still applies when reconstruction is required: brevity must retain every inference. A SUPPORT label is not evidence of simplicity. Preserve substantive hard proofs, essential dependencies, and required reasoning regardless of badge; do not promote or demote source labels to fit a layout.

For substantive arguments, follow with named actions that explain what is done and why. Display substantive multi-step algebra, inequalities, and differentiation separately with alignment and key justifications. Do not use semicolon-chain proofs or bury multiple essential transformations in inline prose. Use as many steps as the argument needs; do not force every proof into three. Ordinary punctuation is allowed, but it cannot substitute for the inference structure.

After the argument, use a compact **Scope / Exam trap** only for an actual likely misapplication. It may take several lines or a small counterexample. Do not move a necessary hypothesis out of the statement into this box, and do not remove an assumption's justification from the proof. Provenance belongs in a short locator or maintenance record, not a repeated defensive sentence in each step.

Show the inference at which an assumption is used: invertibility before an inverse, independence before cancelling cross terms, a fixed comparator before taking its expectation, or a global bound before a population conclusion. Preserve equality cases, signs, singular cases, support restrictions, limit order, and normalization factors when they affect validity.

For example, a minimum-norm argument can remain short without dropping its logic:

**Statement and conditions:** Let \(J\in\mathbb R^{m\times p}\), \(q\in\mathbb R^m\), and \(K=JJ^\top\succ0\). The unique minimum-norm solution of \(Ju=q\) is \(u_*=J^\top K^{-1}q\).

**Core idea:** Split every feasible solution into the candidate in the row space of \(J\) and an orthogonal null-space residual; only the residual adds squared norm.

1. **Establish feasibility.** Substitute the candidate and use invertibility of \(K\):
   \[
   Ju_*=JJ^\top K^{-1}q=KK^{-1}q=q.
   \]
2. **Identify the residual.** For any feasible \(u\), set \(z=u-u_*\). Feasibility puts it in the null space:
   \[
   \begin{aligned}
   Jz&=Ju-Ju_*=q-q=0,\\
   u_*^\top z&=q^\top K^{-1}Jz=0.
   \end{aligned}
   \]
3. **Apply orthogonality.** Expand the norm to compare all feasible solutions:
   \[
   \|u\|^2=\|u_*\|^2+\|z\|^2\ge\|u_*\|^2.
   \]
   Equality holds exactly when \(z=0\), proving uniqueness.

**Exam trap:** If \(K\) is singular, the displayed inverse formula is unavailable. A pseudoinverse treatment needs its own feasibility conditions.

This is illustrative content, not a required topic in other courses. A proof needs symbolic deductions; it does not need invented numerical substitutions. Maintain one canonical proof with a stable label and actual working cross-references at later uses. When only one step changes, show that changed step and cite the canonical argument; do not repeat its full statement and proof in a Recall box. Remove obsolete later-covered previews. Optional technical proofs may leave the body only when source scope permits and they are not needed to reconstruct an assessed argument.

## Use examples that can actually be worked from their givens

Follow the Given / formula / substitution / result structure in the main skill. For an unfamiliar abstract topic, a small reusable example can carry several adjacent results: define its data and parameters once, then refer back while restating the quantities needed for each local calculation. Avoid forcing the reader to reconstruct an unstated assumption.

A useful example exercises the result's conditions and output, rather than merely mentioning a neural network or a real-world application. Show the required computation, including dimensions where helpful, and state what the result permits the reader to conclude. Use a counterexample when it exposes a condition that a numerical success case would hide.

Distinguish three kinds of numbers:

- **Computed:** all necessary inputs are given, and the solution shows how the number follows.
- **Source-reported measurement:** the source used data, weights, or experiment records that the local example does not supply. Attribute the number; do not present it as recoverable from a summary statistic.
- **Constructed illustration:** chosen to make a calculation transparent. Identify it as constructed and verify it independently.

For example, a current Jacobian or Gram matrix can determine a linearized prediction change without determining a nonlinear forward pass after the update. If the full model state is missing, keep the actual forward result symbolic or label the supplied measurement. A rounded calculation need not reproduce the final digit of a full-precision measurement; use approximate equality and explain a material rounding discrepancy.

Select examples by the ranked classroom / learning-check / difficult-concept / counterexample guidance in the main skill; do not require one example per result. One running example is a useful response to an identified difficulty, not a quota for every lecture. Keep distinct source methods, branches, exercises, and counterexamples even when they do not fit that example.

## Preserve the type and scope of every guarantee

Keep deterministic identities, conditional implications, finite-sample probability bounds, expectation bounds, asymptotic claims, and empirical observations distinct. An expectation of a signed gap, an expected absolute gap, and a high-probability bound are different statements.

If a theorem covers a fixed class, check that the algorithm's output belongs to it before substitution. Do not silently choose the class, radius, kernel, or comparator after observing data when the theorem assumes it is fixed independently. A uniform event can cover a data-selected member without changing its probability into a conditional probability given membership.

Separate the objective used for optimization from the loss used for evaluation. Separate approximation of a model from optimization within that model and statistical evaluation of the selected output. Similar notation does not make these the same error term.

A bound larger than a known trivial upper bound is uninformative; it is not evidence of large actual error. A measured agreement on finite inputs is not a population theorem. State the additional condition or error term needed for a transfer, without adding an unrelated theory chapter.

## Compress, maintain, and verify

Remove repeated introductions, duplicate theorem registers, repeated answer summaries, and redundant setup before removing reasoning. Preserve assumptions and calculation stages. Use the existing readable type size; adjust long displays, local tables, and page breaks instead of making mathematical text tiny.

For a maintained LaTeX course project, keep a small root file, shared style, and separate lecture files when that structure already exists. Keep detailed source coverage and proof-status provenance in a maintenance file, with brief locators in the study document. Recall questions may close a lecture when requested, or go to an authorized separate self-test volume. Do not repeat the question list in both. Keep definitions and necessary conditions in the body even when the notation registry is in a separate lookup.

For compression, follow [compression-and-release.md](compression-and-release.md): accept only measured task-specific main-body contraction with preserved assessment coverage, and disclose relocation separately. Keep experiment audit minutiae in the source map unless they are themselves assessed or affect interpretation.

Verification should cover what changed: recompute substantive numerical examples; check symbolic steps and theorem conditions; compare against the full in-scope source, including synthesis; compile; and inspect the rendered pages. If delivering a source ZIP, compile its extracted contents in a clean directory and check that the PDF and editable sources agree. Preserve unrelated earlier lectures and user annotations.
