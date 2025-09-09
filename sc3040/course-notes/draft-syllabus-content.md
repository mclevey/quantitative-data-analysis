
# Syllabus: Bayesian Quantitative Methods for Social Sciences

## Course Overview

This course introduces students to quantitative data analysis and modelling in the social sciences from a **Bayesian and generative perspective**. Python is our tool, not our end: each programming skill is learned in service of **data analysis, measurement, and inference**. Students will progress from scraping real-world data (WNBA rosters) to exploratory data analysis (V-Dem democracy indices), then on to measurement models, generative inference, regression, and multilevel models.

The course is structured as a **12-week progression**, aligned with the textbook’s revised chapter plan. Each week combines lecture, lab, and project work.

## Learning Outcomes

By the end of the course, students will be able to:

* Operate confidently in **Google Colab** and use Python for social science data tasks.
* Acquire and clean real-world data through **scraping and parsing workflows**.
* Use **Pandas** for data manipulation, description, and visualization.
* Apply **Box’s Loop** to exploratory data analysis and validation.
* Understand and evaluate **measurement strategies** for latent constructs.
* Implement **Bayesian IRT models** for democracy measurement.
* Develop intuition for **probability, uncertainty, and belief updating**.
* Specify and fit **generative Bayesian models** with prior/posterior predictive checks.
* Conduct **Bayesian regression analyses** with diagnostics and causal reasoning.
* Fit and interpret **multilevel models**, understanding pooling and shrinkage.
* Communicate uncertainty clearly through **credible intervals, posterior summaries, and model checks**.

## Assessment

* **Weekly Labs (30%)**
  Short applied notebooks (must run top-to-bottom). Focus on code, clarity, and correct use of concepts.

* **Project A: Scraping & Tidying (15%)**
  Due Week 3. Build a WNBA roster scraper, clean the data, and save a tidy dataset.

* **Project B: EDA & Visualization (25%)**
  Due Week 6. Conduct exploratory analysis of V-Dem democracy data. Submit visualizations with a short narrative.

* **Project C: Bayesian Modelling Mini-Capstone (30%)**
  Due Week 12. Fit and interpret a Bayesian generative model (regression required; multilevel optional). Include priors, posterior summaries, and model checks.

## Weekly Schedule

### Week 1 — Computing with Python & Colab (Ch.1)

* *Topics*: Colab basics, Python expressions, data types, measurement scales (nominal/ordinal/interval/ratio).
* *Lab*: Run simple Python code; interpret tracebacks; try/except debugging.
* *Outcome*: Understand Python as a tool for representing data.

### Week 2 — Data Structures & Control Flow (Ch.2)

* *Topics*: Lists, tuples, dicts, iteration, slicing, functions, classes, methods.
* *Motivation*: WNBA roster data.
* *Lab*: Build simple functions and a `Player` class; parse static roster HTML snippet.
* *Outcome*: Organize information with Python structures.

### Week 3 — Scraping & Parsing Data (Ch.3)

* *Topics*: Requests, BeautifulSoup, scraping ethics, cleaning pipelines.
* *Motivation*: Live WNBA rosters.
* *Lab*: Fetch–parse–clean–save pipeline; write parquet file.
* *Deliverable*: **Project A due**.
* *Outcome*: Acquire real data and prepare it for analysis.

### Week 4 — Series & DataFrames (Ch.4)

* *Topics*: Pandas Series/DataFrames, selection, filtering, grouping, joins.
* *Motivation*: V-Dem democracy data.
* *Lab*: Tidy and explore V-Dem subset.
* *Outcome*: Manipulate structured data with Pandas.

### Week 5 — Description, Visualization, Validation (Ch.5)

* *Topics*: Distributions, central tendency, dispersion, Box’s Loop, visualization design.
* *Motivation*: Democratic backsliding trends.
* *Lab*: Produce interpretable histograms, scatterplots, and comparisons.
* *Deliverable*: **Project B assigned**.
* *Outcome*: Describe and visualize data to build intuition.

### Week 6 — Measuring Sentiment & Emotion (Ch.6)

* *Topics*: Dictionary vs. VADER vs. transformer approaches; measurement error and uncertainty.
* *Motivation*: Sentiment in text (e.g., YouTube comments).
* *Lab*: Compare methods; discuss disagreements as uncertainty.
* *Deliverable*: **Project B due**.
* *Outcome*: Recognize measurement as probabilistic evidence.

### Week 7 — Measurement Validation & Reliability (Ch.7)

* *Topics*: Construct/convergent/discriminant validity; Bayesian correlations; belief networks.
* *Motivation*: Political trust.
* *Lab*: Simulate measurement error; estimate Bayesian correlations.
* *Outcome*: Validate measures and interpret uncertainty in validation.

### Week 8 — Latent Factors & IRT (Ch.8)

* *Topics*: Bayesian IRT; difficulty, discrimination; posterior interpretation; PPCs.
* *Motivation*: V-Dem democracy indices.
* *Lab*: Fit a small IRT model; interpret parameters; run PPCs.
* *Outcome*: Model latent constructs with uncertainty.

### Week 9 — Probability, Uncertainty, Bayesian Thinking (Ch.9)

* *Topics*: Probability as uncertainty; priors, likelihoods, posteriors; distributions (Normal, Beta, Gamma).
* *Intuition*: McElreath’s “forking paths”; Kruschke’s “reallocating credibility.”
* *Lab*: Visualize priors and posteriors; update beliefs with new evidence.
* *Outcome*: Build intuition for belief updating.

### Week 10 — Generative Models & Statistical Inference (Ch.10)

* *Topics*: Generative thinking; prior/posterior predictive checks; model checking; LOO/WAIC.
* *Motivation*: V-Dem (e.g., media freedom and democracy).
* *Lab*: Fit and critique a simple generative model.
* *Deliverable*: **Project C assigned**.
* *Outcome*: Frame inference as testing theories of data generation.

### Week 11 — Bayesian Regression (Ch.11)

* *Topics*: Linear regression as generative; priors, diagnostics, PPCs, residuals.
* *Motivation*: Campaign spending and electoral outcomes.
* *Lab*: Fit and diagnose regression; interpret coefficients with uncertainty.
* *Outcome*: Use regression for causal reasoning under uncertainty.

### Week 12 — Multilevel Models (Ch.12A/B)

* *Topics*: Partial pooling logic; hierarchical intercepts/slopes; shrinkage; advanced diagnostics.
* *Motivation*: Election forecasting and group effects.
* *Lab*: Fit a basic hierarchical model; interpret pooling.
* *Deliverable*: **Project C due**.
* *Outcome*: Share information across groups with hierarchical models.

## Guiding Principles

* **Calm, confident, conversational tone**: every technical term defined clearly when first used.
* **Bayesian only**: credible intervals, posteriors, PPCs, LOO/WAIC; no p-values or NHST.
* **Scaffolded learning**: every week builds directly on the last, with prior datasets feeding into later analyses.
* **Reproducibility**: all code runs top-to-bottom; cached datasets provided; no hidden dependencies.
* **Problem-driven**: WNBA rosters → V-Dem democracy → text sentiment → elections.
