Awesome—here’s a quick, surgical gap-analysis and crosswalk.

# What the old course actually teaches (from the syllabus)

* **Platform & tools:** SPSS is required; two lab blocks are “Getting Started with SPSS.”&#x20;
* **Textbook:** *Statistics: A Tool for Social Research and Data Analysis* (Healey, Donoghue, Prus), 4th (5th ok).&#x20;
* **Sequence of topics (by assigned chapters):**

  * Research foundations (Ch.1) → descriptive stats (Ch.2) → central tendency/dispersion (Ch.3) → **normal curve & probability** (Ch.4) → **sampling & sampling distributions** (Ch.5) → **chi-square for nominal/ordinal** (Ch.7) → **measures of association for nominal variables** (Ch.8; lab cites Ch.9) → **one- and two-sample tests** (Ch.10–11) → **partial correlation & multiple regression** (Ch.10–11).&#x20;
* **Assessments emphasize data collection + classic inference:** a **Survey Design project (30%)**, midterm, and four in-class labs.&#x20;

*(For textbook context: Healey’s series is a standard, intro social-stats text organized around the classical frequentist toolkit with step-by-step software support—Cengage positions it that way, with MindTap/SPSS resources.)*

# Where your new Bayesian course already covers/extends this

* **Descriptives & visualization:** Ch.4–5 (pandas + perception, Box’s Loop). (Covers old Ch.2–3 and strengthens EDA ethics/validation.)
* **Probability:** Ch.9 gives a full Bayesian treatment (distributions, uncertainty, updating) that replaces the old normal-curve-then-sampling-distribution arc.
* **Inference:** Ch.10–11 move students into **generative modeling and Bayesian regression** (posterior predictive checks, priors, diagnostics), which subsumes the old t-tests/correlations/regression workflow.
* **Categorical analysis:** Your plan replaces “chi-square + nominal measures” with **Bayesian correlation/covariance** (Ch.7) and network-style thinking; contingency-table questions can be handled via **Dirichlet–multinomial/Beta–binomial** models and posterior predictive checks.
* **Measurement (huge upgrade):** Ch.6–8 add the theory the old course doesn’t—construct validity, reliability, and **Bayesian IRT with V-Dem**.
* **Data pipeline & computing:** Ch.1–3 and 4–5 add **Python/Colab, scraping, wrangling, parquet handoffs**—none of which appear in the old syllabus.
* **Multilevel models:** Ch.12A/12B push beyond the old course entirely.

# Foundations the old course foregrounds that you might be **light** on (and easy fixes)

1. **Survey design & data collection basics**

   * Old course spends four meetings on “Collecting Quantitative Data / Surveys” and grades a **Survey Design** project. &#x20;
   * **Add (recommended):** a compact, applied “**Design → Sample → Measure**” mini-module: questionnaire pitfalls, modes, coverage/nonresponse error, and the link to **measurement error** you model later. Place a 800–1200-word section either at the end of Ch.5 (as a “Before we model…” box) or at the start of Ch.6. Include one lab using a small survey you provide; analyze one proportion with a **Beta–binomial** prior/posterior to show how design meets Bayes.

2. **Sampling distributions & the CLT (as *concepts*)**

   * Old course explicitly teaches “Sampling and the Sampling Distribution.”&#x20;
   * **Your course covers this implicitly** via generative models/posteriors.
   * **Add (nice-to-have):** a one-page **“Why the Normal Shows Up”** sidebar in Ch.9 that explains CLT as a property of data-generating processes, then contrasts **sampling distributions** with **posterior distributions** (so students can “translate” when they meet frequentist language elsewhere).

3. **Classical tests as named procedures** (chi-square, one/two-sample tests)

   * Students will still hear these names in internships/other classes.
   * **Add (recommended):** a short appendix or inline “**Translate the Test**” callouts:

     * t-test → **Bayesian difference of means** (posterior for μ₁–μ₂; ROPE or posterior probability of direction).
     * Chi-square → **Dirichlet–multinomial contingency analysis** with posterior cell probs + PPCs; report **posterior Cramér’s V** (derived from posterior cell counts).
     * Correlation “significance” → **posterior for ρ** with a credible interval (you already do this in Ch.7).

4. **Nominal measures of association (λ, φ, Cramér’s V)**

   * Old course singles these out.&#x20;
   * **Add (optional):** a brief technical note (Ch.7 or appendix) showing how to compute **Cramér’s V from posterior draws** and why you prefer posterior predictive checks + effect sizes over null-hypothesis tests.

5. **Software expectations**

   * Old = SPSS menus; New = Python/notebooks.&#x20;
   * **Add (optional):** a one-page “**SPSS → pandas/PyMC Rosetta Stone**” mapping (select/filter, crosstabs, compute variable, regression) to help SPSS-trained TAs/students orient quickly.

# Quick crosswalk (old → new)

* Descriptives (Ch.2–3) → **Ch.4–5** (plus better viz & validation)
* Normal curve/probability (Ch.4) → **Ch.9** (Bayesian probability + updating)
* Sampling distributions (Ch.5) → **Ch.9–10** (generative view; optional CLT sidebar)
* Chi-square & nominal measures (Ch.7–8) → **Ch.7** (Bayesian correlation/evidence) + **appendix** (Dirichlet–multinomial, posterior V)
* One/two-sample tests (Ch.10–11) → **Ch.10–11** (Bayesian estimation & model checks)
* Partial correlation & multiple regression (Ch.10–11) → **Ch.11** (Bayesian regression; partial effects via posteriors)
* Survey design project → **Add mini-module + lab** (ties into Ch.6–7 measurement)

# Bottom line

* Your course **covers (and elevates)** every analytical competency in the old syllabus—from descriptives to regression—while replacing “button-click inference” with **generative, Bayesian modeling**, stronger **measurement theory**, and a **modern data pipeline**.
* The only foundations the old course explicitly **teaches that you might gloss over** are (a) **hands-on survey design/data collection** and (b) **named classical tests / nominal effect sizes**. Both are easy to fold in without derailing your Bayesian spine: one short survey/design module + a “translate the test” appendix (or callouts) will make your students bilingual and future-proof.

If you’d like, I can draft the mini-module outline (learning goals, 60–90-minute lab, and a tiny Beta–binomial demo) and the “Translate the Test” callouts next.
