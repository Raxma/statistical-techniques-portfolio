# Statistical Analysis Portfolio (R) — Time Series Tests + Predictive Modelling

This project is a portfolio of statistical techniques implemented in **R / R Markdown** (Sep 2023). It demonstrates hypothesis testing, assumption checking, and predictive modelling across two contexts:

1) **Financial time series** — Apple (AAPL) and Microsoft (MSFT) stock price analysis across COVID-era periods  
2) **Medical diagnostics** — logistic regression classification for breast cancer tumour prediction

The goal is decision-driven analysis: choose the appropriate statistical test, validate assumptions, confirm results with non-parametric alternatives, and communicate outcomes clearly.

---

## Results snapshot (high-signal)

### Stock price analysis (AAPL / MSFT)

**Pre vs during pandemic (paired comparison)**
- Shapiro–Wilk normality test: **W = 0.97661, p = 0.0003749** (non-normal)
- Paired t-test: **t = -42.612, df = 250, p < 2.2e-16**
- Wilcoxon signed-rank: **V = 0, p < 2.2e-16**

**Across three periods (pre / during / post)**
- ANOVA: **p < 2.2e-16**
- Kruskal–Wallis: **χ² ≈ 827.39, df = 2, p < 2.2e-16**
- Post-hoc testing performed (Tukey HSD / Dunn) to identify which periods differ

**AAPL vs MSFT (post-pandemic window)**
- Welch two-sample t-test: **t = -64.395, df ≈ 677.21, p < 2.2e-16**
- Wilcoxon rank-sum: **W = 0, p < 2.2e-16**

**Correlation (movement synchronisation)**
- Pearson correlation ≈ **0.937**
- Spearman correlation ≈ **0.9476658**

### Breast cancer classification (logistic regression)
- Logistic Regression classifier with train/test split + confusion matrix evaluation
- **Accuracy ≈ 0.9091 (90.91%)**

---

## What’s inside

### 1) High-confidence hypothesis testing (financial time series)
- paired t-test vs Wilcoxon signed-rank  
- ANOVA + Tukey HSD vs Kruskal–Wallis + Dunn  
- Welch t-test vs Mann–Whitney  
- Pearson vs Spearman correlation

### 2) Predictive analytics (classification)
- logistic regression classification workflow (breast cancer dataset)
- preprocessing + evaluation

---

## Repo structure

- notebooks/
- statistical_techniques_portfolio.Rmd
- statistical_techniques_portfolio.html
- renv.lock
- README.md
- .gitignore


---

## How to run (reproducible)

### Option A — View outputs (recommended)
Open the knitted HTML:
- `notebooks/statistical_techniques_portfolio.html`

### Option B — Run locally

1) Open the project folder in RStudio (or set your working directory to the project root).

2) Restore dependencies and render:

```r
renv::restore()
rmarkdown::render("notebooks/statistical_techniques_portfolio.Rmd")
```
- Output will be generated as: notebooks/statistical_techniques_portfolio.html
### Portfolio note (KTP-ready evidence)

This repo evidences:

- robust test selection based on assumptions and validation

- clear communication of statistical outcomes with visuals

- predictive modelling + evaluation

- reproducibility via renv.lock
