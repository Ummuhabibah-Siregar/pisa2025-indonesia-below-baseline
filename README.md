# Reproducible analysis code for: Not All Students Below the Mathematics Baseline Are the Same: A Threshold-Specific Analysis of PISA 2025 Indonesia

Ummu Habibah Siregar, Dadan Dasari, Jarnawi Afgani Dahlan · Universitas Pendidikan Indonesia · Submitted to *Large-scale Assessments in Education*

This repository contains the Python code that reproduces all results reported in the article: Tables 1–3, Figures 2–4 and Additional file 1 (Tables A1–A7).

## Contents

| File | Description |
|---|---|
| `PISA2025_Indonesia_Below_Baseline_Analysis.ipynb` | Jupyter notebook with the complete analysis, organised in numbered sections that follow the manuscript |
| `requirements.txt` | Python packages used |
| `Results_PISA2025_Indonesia.xlsx` | All estimates produced by the notebook (one sheet per table) |
| `Figure2_levels_by_group.png` | Figure 2 |
| `Figure3_threshold_forest.png` | Figure 3 |
| `Figure4_predicted_probabilities.png` | Figure 4 |

## Data

The PISA 2025 data are **not** included in this repository. Download the public-use student and school questionnaire files from the OECD:
https://www.oecd.org/en/about/programmes/pisa/pisa-data.html

The notebook accepts the original SPSS (`.sav`) files or CSV extracts for Indonesia (CNT = "IDN"). Files are detected automatically by their content.

## How to run

**Google Colab (recommended).** Open the notebook in Colab, run all cells, and upload the student and school files when prompted in Section 0.3.

**Locally.**

```bash
pip install -r requirements.txt
jupyter notebook PISA2025_Indonesia_Below_Baseline_Analysis.ipynb
```

Place the data files in the same folder as the notebook, or set `DATA_DIR` in Section 0.2.

A full run (10 plausible values × 20 imputations × 80 BRR-Fay replicate weights) takes about 8 minutes on a standard Colab instance. Random seeds are fixed, so results are reproduced exactly.

## Analysis overview

- Final student weights (W_FSTUWT) and 80 BRR-Fay replicate weights (Fay factor 0.5)
- Proficiency levels assigned separately for each of the 10 mathematics plausible values
- Multiple imputation of missing predictors by chained equations with predictive mean matching (20 datasets)
- Proportional-odds logistic regression (RQ2), threshold-specific logistic regressions with formal tests of coefficient equality and Holm correction (RQ3), and logistic regression with ESCS interactions (RQ4)
- Estimates pooled with Rubin's rules for nested multiple imputation
- Supplementary analyses: average marginal effects (Table A5), reliability of the school mean ESCS, a two-level random-intercept sensitivity model (Table A6), and checks of multicollinearity, suppression, the proportional-odds assumption and a curiosity × ESCS interaction (Table A7)

## Citation

If you use this code, please cite the article:

> Siregar, U. H., Dasari, D., & Dahlan, J. A. (under review). Not all students below the mathematics baseline are the same: A threshold-specific analysis of PISA 2025 Indonesia. *Large-scale Assessments in Education*.

## License

Code: MIT License (see `LICENSE`).
