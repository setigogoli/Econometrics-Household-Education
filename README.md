# Household Education Expenditure in Iran

How do household resources and family composition relate to education spending? We study this question using Iran's Household Expenditure and Income Survey for **1394 and 1403** in the Solar Hijri calendar (approximately 2015–16 and 2024–25).

This project was completed for the Econometrics course at the School of Industrial Engineering, Sharif University of Technology.

**Authors:** Setayesh Heydari and Bardia Soltani Moakhar  
**Instructor:** Dr. Fatemeh Asghari

## Main findings

- The survey-weighted mean education budget share fell from **2.27% to 1.36%** among households with at least one enrolled student.
- **28.3% of the analysis sample reported zero education spending.** Including these households in a two-part model gives an income elasticity of **0.915**, compared with **0.753** from log-OLS on positive spenders. The two-part estimate's province-bootstrap 95% interval is **[0.825, 1.024]**.
- The estimates depend on the resource measure and model. Expenditure-based estimates are generally higher than income-based estimates. The pooled relationship between student numbers and spending per student is negative but statistically inconclusive when total expenditure is controlled for.

These are conditional associations. The data do not identify the causal effect of income, family size, or a policy change.

![Mean education budget share by within-year expenditure rank](results/figures/f02_engel.png)

The figure uses unweighted sample means; the 2.27% and 1.36% figures above use survey weights. The horizontal axis compares relative expenditure positions within each year.

## Explore the project

| File or folder | Contents |
|---|---|
| [Analysis notebook](notebooks/education_expenditure.ipynb) | Data preparation, estimation, diagnostics, and saved outputs |
| [English report](docs/report.md) | Research question, methods, results, and limitations |
| [Data notes](data/README.md) | Required workbooks, source information, and variable definitions |
| [Results](results/README.md) | Index of the seven figures and nineteen CSV tables |

The analysis starts with 75,757 household records. The main sample contains 36,382 households with an enrolled student, including 26,082 with positive education spending. We compare log-OLS, a probit/log-OLS two-part model, PPML, Tobit, and Working–Leser OLS and 2SLS specifications. Most regression standard errors are clustered across 31 provinces; exceptions are explained in the notebook.

## Run the analysis

Use Python 3.11 or 3.12. From the repository folder:

```bash
python -m venv .venv
```

Activate the environment with `source .venv/bin/activate` on macOS/Linux, or `.venv\Scripts\Activate.ps1` in Windows PowerShell. Then run:

```bash
python -m pip install -r requirements.txt
python -m jupyterlab notebooks/education_expenditure.ipynb
```

Place the two workbooks listed in [data/README.md](data/README.md) in `data/raw/`, then run the notebook from top to bottom. Tables and figures are written to `results/`. The notebook also supports workbooks attached under `/kaggle/input` when run on Kaggle.

The raw workbooks are **not included**. Saved notebook outputs and exported results can be read without them. A complete rerun requires those inputs. Dependency ranges in `requirements.txt` are not an exact lock of the original execution environment.
