Love this. If you spin up a second, independent “reviewer” model, you’ll get the best results if you (1) feed it the right packet of artifacts and (2) give it a tight, role-based rubric with hard outputs. Here’s a plug-and-play kit.

# What to hand the reviewer (the “Review Packet”)

Include for **each chapter** you want graded:

* Original file and **revised file**.
* A **unified diff** (or side-by-side) of changes.
* Word-count report before/after.
* Frequentist-lint hits (if any) + your “allow list.”
* Code execution logs (pass/fail, errors), rendered figures, and the list of saved **parquet handoffs** the next chapter loads.
* Cross-ref/label report (figures, tables, sections) and any broken-link report.
* The **approved revision plan** excerpt for that chapter (Keep / Condense / Expand / Move).
* If V-Dem appears: the mapping of data files/variables used.
* Any “known issues” you already noticed.

# Master prompt (chapter review)

Use this exact skeleton, swapping chapter details and attaching the packet.

> **Role:** You are a senior methods editor, Bayesian statistician, pedagogy specialist, and technical QA in one.
> **Goal:** Grade whether the implemented revisions match the approved plan and the book’s Bayesian alignment, then propose precise fixes. Do **not** rewrite the whole chapter; focus on assessment + highly actionable edits.
> **Inputs attached:**
>
> 1. Approved plan excerpt for Chapter X; 2) Original Chapter X; 3) Revised Chapter X; 4) Diff; 5) Word-count report; 6) Lint report; 7) Code/figure logs; 8) Cross-ref report; 9) Parquet handoff list; 10) Known issues (if any).
>    **Constraints:**
>
> * Evidence-bound: cite page/line/heading or diff hunk IDs for every finding.
> * If evidence isn’t present, write **“Insufficient evidence”** (don’t speculate).
> * Keep suggestions concrete (e.g., “Replace line 142–168 with: …” or “Move §2.3 to §2.1 and update cross-ref {fig\:wnba-roster}”).
> * Maintain calm, conversational voice in all examples.
>   **Rubric (score 0–3 each, with 1–2 sentences of justification and evidence):**
>
> 1. Scope compliance to plan (Keep/Condense/Expand/Move)
> 2. **Bayesian alignment** (no NHST; credible intervals, posterior probs, priors/likelihoods explicit)
> 3. Pedagogical scaffolding & sustained motivation (WNBA/V-Dem/trust/elections carry-through)
> 4. Data pipeline integrity (parquet handoffs and load paths verified by logs)
> 5. Code & figures (executed, deterministic, captions/labels consistent)
> 6. Cross-refs/labels/terminology consistency
> 7. Clarity & tone (author voice preserved; no jargon bloat)
> 8. Currency of V-Dem framing (consistent with current indicators/terminology you used elsewhere)
>    **Deliverables:**
>
> * **A. Triage table** (rubric with 0–3 scores, red/yellow/green status).
> * **B. Top 10 prioritized fixes** (P0 blocking → P2 nice-to-have). For each: Problem → Evidence → Fix (one-paragraph or patch-style snippet) → Effort (S/M/L).
> * **C. Plan compliance delta:** bullets mapping each plan directive to “Met / Partially / Missed” with citations.
> * **D. Frequentist lint resolution:** list any flagged terms that remain, with your proposed Bayesian rewrite text.
> * **E. Gate decision:** **PASS** (ready) / **HOLD** (needs fixes). If HOLD, list the **minimum ship-blocking fixes**.

# Global consistency sweep (cross-chapter)

Run this after a few chapter passes:

> **Task:** Cross-chapter audit for consistency.
> **Focus:**
>
> * Term map (credible interval vs confidence; posterior SD vs SE; “significant” banned).
> * Handoffs: `wnba_rosters.parquet` → Ch4; `vdem_core.parquet` → Ch6; election data → Ch12A/12B.
> * V-Dem edition references and indicator names.
> * Diagnostics set (R̂, ESS, PPCs) consistently reported wherever models appear.
>   **Output:** One table of inconsistencies with file/section pointers and a batch-fix plan (ordered list of search-and-replace + section moves).

# “Deep dive” micro-prompts (use on 1–2 chapters)

* **Pedagogy stress-test:**
  “Identify the two hardest leaps for students in this chapter. For each, propose one bridging example and one misconception trap, citing exact insertion points.”
* **Bayesian integrity audit:**
  “Scan for any residual NHST framing, implicit or explicit. For each hit, provide a one-sentence diagnosis and a one-paragraph Bayesian rewrite.”
* **Data seam check:**
  “Verify that every dataset saved in prior chapters is actually loaded here under the same path/name and used. If logs don’t show it, mark Insufficient evidence.”

# Diff-focused prompt (fast triage)

> “Using the diff only, highlight edits that **deviate from** the approved plan (extra content added or required content missing). Output a two-column list: *Plan directive* ↔ *Observed deviation (with diff hunk ID)*, then a short fix.”

# Code/figures QA prompt

> “From the execution logs and figure manifests, list any code blocks that failed or produced warnings, any figures not rendered or unlabeled, and any stochastic outputs without a set seed. Propose minimal fixes.”

# Scoring rubric to copy-paste

Use 0–3 with clear anchors to get consistent grades:

* **3 (Strong):** Fully meets plan/spec; evidence shows clean execution and alignment.
* **2 (Adequate):** Minor gaps; clear, easy fixes.
* **1 (Weak):** Multiple misses; pedagogy or Bayesian framing compromised.
* **0 (Fail):** Plan largely ignored or reproducibility broken.

# Red-flag checklist (tell the reviewer to hunt for these)

* “p-value,” “significant,” “95% CI,” “Pearson correlation” used as inference (not merely historical contrast).
* Means/medians presented as **facts** rather than model summaries.
* Priors missing in models that introduce new parameters.
* Missing R̂/ESS or PPCs where models are fitted.
* Broken handoffs (parquet name/path drift).
* V-Dem indicator names or years inconsistent with your updated framing.
* Figures without captions or cross-refs; unlabeled axes; color choices without accessibility note where relevant.

# Tips that make the review succeed

* **Chunking:** If files are long, supply chunks with stable anchors (section IDs + line ranges). Ask the reviewer to cite those IDs.
* **Determinism:** Tell the reviewer to flag any stochastic code that lacks a seed.
* **Evidence discipline:** Require line/section/diff-hunk citations for every critique.
* **No speculation:** “Insufficient evidence” beats a guess—then you know what to surface next.
* **Prioritize:** Force P0/P1/P2 labeling so you get a short must-fix list.

If you paste these prompts and feed the packet artifacts, the second model will behave like a tough but fair methods editor—precise, evidence-bound, and immediately actionable.
