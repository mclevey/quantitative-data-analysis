# Quantitative Data Analysis

John McLevey<br>
Professor and Head of Sociology<br>
Memorial University, St. John's, NL, Canada<br>
mclevey@mun.ca | johnmclevey.com<br>

> This repository contains **course materials** for Sociology/Criminology 3040: Quantitative Data Analysis, including a **draft manuscript** for the required course readings (McLevey, *Quantitative Social Science: Core Concepts, Skills, and Stories*), companion **Python package** (`clark`), syllabus, lab notebooks, quizzes and assignments, automation scripts, and so on...

## 1. Book Manuscript

> John McLevey. 2025. *Quantitative Social Science: Core Concepts, Skills, and Stories*. Draft manuscript.

```bibtex
@book{mclevey2025qss,
    title={Quantitative Social Science: Core Concepts, Skills, and Stories},
    author={John McLevey},
    year={2025},
    publisher={Draft manuscript}
}
```

## 2. Course Materials for SOCI/CRIM 3040, Quantitative Data Analysis

> Sociology/Criminology 3040, Quantitative Data Analysis, is an introduction to quantitative data analysis for undergraduate students in the social sciences. Topics include data processing, description, and visualization; exploratory data analysis; inference and modelling; measurement and latent variables; association, regression; networks and multilevel models; quantitative text analysis.

### 2.1. Syllabus

### 2.2. Lectures and Labs

### 2.3. Course Notes

### 2.4. Assignments


## 3. Clark (Python Package)

### 3.1 Quick Publish

See [workflow/publish-to-pypi.md](workflow/publish-to-pypi.md) for details.

```bash
cd clark

## Bump patch version and publish to TestPyPI
bash publish.sh --test-pypi --patch

## Test install in clean venv
bash publish.sh --test-install

## Bump patch version and publish to PyPI
bash publish.sh --pypi --patch
```

### 3.2 Quick Installation

```bash
## name conflict on PyPI, so use clark-qss to install
pip install clark-qss
```

And then you can use `clark` as expected.

```python
import clark
print(clark.__version__)
```

### 3.3 Editable Installation for Development

Pip will install `clark` in editable mode when the pixi environment is activated (e.g., `pixi shell` or `pixi run python test.py`, etc).
