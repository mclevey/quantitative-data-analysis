Here’s a **12-week teaching lens** that mirrors your revision plan, keeps everything Bayesian-only, and scaffolds skills from WNBA scraping → V-Dem EDA → measurement/IRT → generative/regression → multilevels.

---

# 12-Week Course Schedule (Teaching Lens)

## Assessment & Rhythm (at a glance)

* **Weekly labs (30%)**: small, autogradable-ish notebooks (run-all must pass).
* **Project A (15%)**: WNBA scraping + tidy dataset (wk 3 due).
* **Project B (25%)**: V-Dem EDA + visualization + validation brief (wk 6 due).
* **Project C (30%)**: Bayesian modelling mini-capstone (wk 12 due): generative model + regression (+ optional multilevel).

**Policy**: no p-values/NHST; use posterior summaries, credible intervals, PPCs, and LOO/WAIC only.

---

## Week 1 — Computing with Python & Colab (Ch.1)

**Lecture**: Colab basics; Python expressions; objects & methods; tracebacks; try/except.
**Mini-theory**: *Measurement scales (lightweight)*: nominal/ordinal/interval/ratio as data representations, framed as uncertainty about the world.
**Lab 01**: Run-all Colab sanity checks; short exercises with strings, numbers, Booleans; read/interpret tracebacks.
**Deliverable**: 1-page “tools, not ends” reflection linking code snippets to social questions.
**Scaffolding link**: Sets up JIT concepts needed for WNBA data structures in Week 2.

---

## Week 2 — Data Structures & Control Flow (Ch.2)

**Lecture**: lists/tuples/dicts; slicing; iteration; list comprehensions; `in`/`not in`; *functions/classes/methods as helpers for scraping*.
**Motivation**: **WNBA roster** objects: players, positions, links.
**Lab 02**: Build a tiny `Player` class; write helper functions to clean names/positions; parse small static HTML snippet (provided) into Python containers.
**Milestone**: **Project A spec** released (WNBA scraper).
**Scaffolding link**: Data containers become inputs to scrapers next week.

---

## Week 3 — Scraping & Parsing Pipeline (Ch.3)

**Lecture**: requests → BeautifulSoup → select/clean → DataFrame; ethics/robots; focused BS4 cheat-sheet.
**Motivation**: **WNBA Wikipedia rosters** (primary) + one related page (e.g., team stats).
**Lab 03**: Build a resilient fetch-parse-clean-save pipeline; save to `wnba_rosters.parquet`. Add minimal validation asserts (non-empty, expected cols, unique keys).
**Due**: **Project A** (end of week).
**Scaffolding link**: Produces real, tidy data that Pandas will exploit in Week 4.

---

## Week 4 — Series & DataFrames (Ch.4)

**Lecture**: Pandas mental model (Series, Index, DataFrame); select/filter/group; joins (light); datetime (light).
**Motivation**: **V-Dem**: “How has liberal democracy changed in 20 years?” + reuse WNBA file for secondary examples.
**Lab 04**: Load V-Dem subset; tidy/select; `groupby` comparisons across regions/years; write clean subsets; document decisions.
**Scaffolding link**: Mechanics first; stats concepts next week through visualization.

---

## Week 5 — Description, Visualization, Validation (Ch.5)

**Lecture**: EDA + **Box’s Loop**; distributions, location, dispersion; Seaborn essentials; perception rules (Cleveland & McGill); validation mindset.
**Lab 05**: Two clear plots per question (effective vs. problematic); compute medians/quantiles; articulate why axes/encodings are chosen; save `vdem_core.parquet`.
**Due**: **Project B** assigned (due Week 6): EDA+viz brief on V-Dem.
**Scaffolding link**: Moves from mechanical Pandas to reasoning with evidence.

---

## Week 6 — Measurement: Sentiment & Emotion (Ch.6)

**Lecture**: Latent constructs via text; dictionary vs. VADER vs. transformers; measurement uncertainty; validation ideas.
**Lab 06**: Small text dataset; run two methods; compare distributions; discuss disagreements as uncertainty.
**Due**: **Project B** (V-Dem EDA brief).
**Scaffolding link**: Sets the intuition for formal validation and latent variables.

---

## Week 7 — Validation & Reliability; Belief Networks (Ch.7)

**Lecture**: Construct validity; convergent/discriminant validity; reliability (internal/test-retest/rater); **Bayesian correlation** (with intervals); belief networks/cultural schemas (conceptual).
**Lab 07**: Bayesian correlation(s) between text-based measures and survey items; small simulation of measurement error propagation.
**Scaffolding link**: Bridges informal measurement to formal latent modelling.

---

## Week 8 — Latent Factors & IRT with V-Dem (Ch.8)

**Lecture**: IRT as Bayesian measurement; difficulty/discrimination; posterior interpretation; PPCs; invariance checks; reproducing aspects of V-Dem pipeline (conceptual).
**Lab 08**: Fit a small IRT model on a toy subset (PyMC/Bambi if feasible); interpret item parameters; PPC sanity checks.
**Scaffolding link**: Completes the measurement arc; prepares for probability foundations.

---

## Week 9 — Probability, Uncertainty, Bayesian Thinking (Ch.9)

**Lecture**: Bayesian probability; priors/likelihood/posterior; Normal/Beta/Gamma (core); **McElreath’s “forking paths”** intuition; **Kruschke’s “reallocating credibility.”**
**Lab 09**: Prior/posterior visualizations; simple updating demos; link back to IRT posteriors (interpretation only).
**Scaffolding link**: Conceptual bridge to generative models.

---

## Week 10 — Statistical Inference with Generative Models (Ch.10)

**Lecture**: Generative stories; prior predictive → fit → posterior predictive; model checking; LOO/WAIC; theory ↔ model alignment.
**Case**: V-Dem (e.g., media freedom ↔ democracy).
**Lab 10**: Prior predictive checks; fit a simple generative model; posterior predictive checks; compare two plausible model specs.
**Project C** released: choose a question + dataset (V-Dem/WNBA/approved).
**Scaffolding link**: From probability to fitted models with checks.

---

## Week 11 — Bayesian Regression (Ch.11)

**Lecture**: Linear regression as a generative model; priors that regularize; diagnostics (R̂, ESS), PPCs, residuals; causal thinking; brief Bambi vs. PyMC.
**Lab 11**: Fit, diagnose, and iterate one regression; conduct LOO model comparison; write 5-bullet interpretation with uncertainty.
**Scaffolding link**: Sets up partial pooling logic.

---

## Week 12 — Multilevels Foundations → Advanced (Ch.12A/12B)

**Lecture**: **12A**: partial pooling, hierarchical intercepts/slopes, shrinkage intuition; **12B (glimpse)**: divergences, reparameterization, informative group-level priors.
**Lab 12**: Fit a basic hierarchical model (random intercepts by region/team); inspect shrinkage; one PPC + one calibration plot.
**Due**: **Project C** (mini-capstone): generative model + regression (+ optional multilevel), with priors, PPCs, and a short uncertainty narrative.

---

## Alignment Map (Chapters → Weeks)

* **Ch1** → W1
* **Ch2–3** → W2–3 (WNBA pipeline)
* **Ch4–5** → W4–5 (Pandas → EDA/Viz/Validation, V-Dem)
* **Ch6–8** → W6–8 (Measurement → Validation → IRT)
* **Ch9–10** → W9–10 (Probability → Generative inference)
* **Ch11–12A/B** → W11–12 (Regression → Multilevels)

---

## Teaching Notes & Guardrails

* **Tone**: calm, confident, conversational; define terms crisply right where they appear.
* **Bayesian-only**: credible intervals, posterior summaries, PPCs, LOO/WAIC; no NHST/p-values.
* **Code safety**: every lab/project must **run top-to-bottom**; include 2–3 lightweight `assert`s for schema sanity.
* **Scaffolding**: each week references a prior artifact (e.g., `wnba_rosters.parquet`, `vdem_core.parquet`).
* **Accessibility**: default to Colab; include cached data snippets; avoid GPU dependence except where clearly noted.