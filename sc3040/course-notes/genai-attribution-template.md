
## Minimal attribution template (required)

```markdown
### Attribution & Reproducibility Log

**Student:** ______________________   **Course:** SOCI/CRIM 3040   **Assignment:** __________  
**Notebook:** (link if shared) ____________________    **Date:** __________

**Data sources:**  
- [ ] Own data   [ ] Course-provided   [ ] Public URL(s): __________________________  
- License/ToS acknowledged? [ ] Yes  [ ] N/A   Personal data? [ ] No  [ ] Yes (explain): ________

**GenAI use (what/how/verification):**  
- **Tool(s) & model(s):** __________________ (e.g., ChatGPT, Claude; model name if known)  
- **Purpose:** (e.g., debug a loop / explain regression output / draft plot code)  
- **Prompt(s) or summary:** ______________________________________________  
- **What I used verbatim vs. adapted:** __________________________________  
- **Verification steps:** (tests/prints, compare to docs/textbook, unit checks) __________________  
- **I can explain this code/results:** [ ] Yes

**Other help/resources:** (classmates, office hours, docs/links) _______________________________

**Environment & randomness:** Python ___; key pkgs: pandas ___, numpy ___, bambi ___, pymc ___.  
Random seed(s): ________  Re-run expected to match within randomness? [ ] Yes
```

---

## Extended template (recommended)

```markdown
### Attribution & Reproducibility (Extended)

**Student / Section / Date:** _____________________________________________  
**Assignment/Module:** __________________________________  **Notebook link:** __________________

#### Data & Ethics
- Source(s) & URLs: ______________________________________________________________  
- Robots.txt/ToS respected for scraping? [ ] Yes  N/A [ ]  
- Contains personal/sensitive data? [ ] No  [ ] Yes → Mitigation: _____________________

#### GenAI Usage
- Tool(s)/Model(s): ___________________________________  Access method: (web/app/APIs)  
- Purpose(s): ☐ debugging ☐ syntax help ☐ concept explanation ☐ code sketch ☐ writing aid  
- Prompt(s) or concise summary:  
  > _____________________________________________________________________________
- Output used (lines/cells/ideas): _______________________________________________  
- Edits I made: _________________________________________________________________  
- Verification: ☐ ran tests/prints ☐ compared to textbook/notes ☐ checked against small hand
  examples ☐ reviewed diagnostics ☐ prof/TA feedback  
- Understanding statement: *I can explain each line/result I kept.* ☐ Yes

#### Collaboration & Resources
- People (names/roles): _________________________________  
- Docs/links (APA/URL): _________________________________________________

#### Reproducibility
- Python: ___  Packages: pandas ___, numpy ___, matplotlib ___, bambi ___, pymc ___  
- Random seed(s): ________  Data snapshot/version: ______________________  
- Expected variability on re-run: _______________________________________
```

---

## Tiny filled example (for students to see what “good” looks like)

```markdown
### Attribution & Reproducibility Log

**Student:** A. Student   **Course:** SOCI/CRIM 3040   **Assignment:** Module 2 Portfolio  
**Notebook:** https://colab.research.google.com/…   **Date:** 2025-10-28

**Data sources:** Public URL (V-DEM demo subset, course repo). License acknowledged. Personal data: No.

**GenAI use (what/how/verification):**  
- **Tool & model:** ChatGPT (model unknown).  
- **Purpose:** Explain why my correlation heatmap had duplicated axes; suggest seaborn-free Matplotlib code.  
- **Prompt summary:** “Why does my correlation plot duplicate labels? Using pandas .corr(), Matplotlib only.”  
- **Used/adapted:** Adopted tick rotation snippet; rewrote plotting loop myself.  
- **Verification:** Ran on a 5×5 toy DataFrame; labels correct; values match `df.corr()`.  
- **I can explain this code/results:** ☑ Yes

**Other help/resources:** Office hours (TA), pandas docs (https://pandas.pydata.org/pandas-docs/).

**Environment & randomness:** Python 3.12; pandas 2.2.2, numpy 2.0.1, bambi 0.13, pymc 5.15.0.  
Seed: 1234. Re-run should match aside from randomized jitter in one plot (disabled now).
```

If you want, I can drop the minimal template into your syllabus under the **GenAI** section and also add it to the top of the starter notebooks.
