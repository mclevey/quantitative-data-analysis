# Editor-Reviewer

Totally. Here’s the idea in plain terms, and why it works.

# What we’re doing

You’ve already told one model to **rewrite the book** following a detailed plan. Now you want a **different model** to act as a *reviewer/QA editor* that checks whether those revisions actually match the plan, keep the Bayesian framing, preserve your tone, and don’t break code or the data pipeline.

Think of it like peer review: the first model is the author; the second is the methods editor.

# Why use a second model at all?

* **Fresh eyes & less bias:** A separate model won’t “defend” the choices it made earlier.
* **Evidence-bound review:** We make it cite *exact lines* in the revised text (or in the diff) so feedback is concrete, not hand-wavy.
* **Actionable outputs:** We force it to propose *minimal* fixes—small wording tweaks or specific code edits—so you can patch quickly.

# Two simple ways to feed context to the reviewer

## Option A — Simplest: Plan + New Text

You paste:

1. The chapter’s **plan excerpt** (Keep/Condense/Expand/Move),
2. The **revised chapter** (or just changed sections),
3. (Optional) the **old text**.

The reviewer judges whether the new text implements the plan, flags Bayesian drift, checks tone, code, and handoffs—then gives small, targeted fixes.

**Pros:** Zero tooling.
**Tradeoff:** It sees the full chapter but doesn’t “know” exactly what changed unless you also include the old text.

## Option B — Precise: Use the Git diff

You already committed everything *before* kicking off revisions. That commit is your **BASE**. The working tree after revisions is **HEAD**.

You give the reviewer:

* The **plan excerpt** and
* The **patch** (the output of `git diff BASE..HEAD`).

Now it reviews *only the changed lines*, cites hunk headers (e.g., `@@ -210,7 +240,12 @@`) and tells you exactly where a fix belongs. If it needs more context, it can ask for just that file/section.

**Pros:** Laser-focused, fast to act on.
**Tradeoff:** It won’t see unchanged parts unless requested.

# What the reviewer produces (and why)

We structure the prompt to force high-quality, actionable output:

1. **Rubric table (0–3 scores)** across seven things that matter:

   * Plan compliance
   * Bayesian alignment (no NHST/p-values language; use priors/likelihoods/credible intervals)
   * Pedagogical scaffolding (motivation, sequencing, bridges)
   * Data pipeline handoffs (parquet saves/loads; consistent paths)
   * Code viability (runs, seeds, figure labels)
   * Terminology & cross-refs (consistent names, updated refs)
   * V-Dem currency (indices, framing)

   *Why:* A rubric gives you a quick “where are the risks?” snapshot.

2. **Top 5 fixes**: Problem → offending quote (or diff hunk) → **smallest possible edit** (one sentence or one code tweak).

   *Why:* Keeps the cost of action low and avoids scope creep.

3. **Missed plan directives**: Quote the plan line that wasn’t implemented → say exactly where to add it.

   *Why:* Ensures the revision plan, not the model’s taste, drives edits.

4. **Two sample rewrites** (≤120 words) in *your* tone to demonstrate how to fix trickier spots.

   *Why:* Concrete examples make it easy to copy/paste the fix.

5. **PASS or HOLD** with at most two blocking issues if HOLD.

   *Why:* Clear decision rule so you know whether to ship or patch.

# Why this structure works for LLMs

* **Evidence binding:** Requiring quotes (or diff hunk IDs) keeps the model grounded and reduces hallucinations.
* **Minimal fixes:** LLMs tend to over-rewrite; forcing “smallest edit that works” keeps voice and scope intact.
* **Scope control:** One chapter per run limits cognitive load and makes feedback specific.
* **Guardrails:** Explicit “no frequentist language” plus checks for parquet handoffs and seeds keeps the review on-mission.

# How a run typically looks (at a glance)

1. You choose a chapter.
2. You paste the plan excerpt and either (A) the revised text or (B) the patch.
3. The reviewer returns: rubric → five fixes → missed directives → sample rewrites → PASS/HOLD.
4. You apply the minimal fixes (or send a tiny follow-up prompt for a micro-rewrite).

# Common pitfalls & how this setup avoids them

* **Vague critique →** We demand quotes/hunk IDs.
* **Massive rewrites →** We enforce “minimal fix” guidance.
* **Losing your tone →** We state “preserve calm, confident, conversational voice” explicitly.
* **Bayesian drift →** We include a strict Bayesian checklist and a “frequentist lint” mindset (flag words like “significant,” “p-value,” etc.).
* **Broken pipelines →** The rubric requires checking parquet saves/loads and consistent paths/filenames.
* **Overlong inputs →** Review per-chapter, and in diff mode when possible.

# Which option should you start with?

* If you don’t want to touch git right now: **Option A** (Plan + New Text).
* If you can run two git commands: **Option B** (diff) is cleaner, faster, and easier to act on.

Either way, the goal is the same: a second model *grades* the implementation against your plan, flags concrete issues, and hands you tiny, precise edits to make it airtight.
