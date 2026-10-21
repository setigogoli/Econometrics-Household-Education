# Results

These aggregate outputs accompany the analysis notebook. Descriptive population statistics use household survey weights; the figures, model comparisons, and decomposition generally use unweighted observations. The report distinguishes the two.

## Figures

| File | Contents |
|---|---|
| [f01_zeros.png](figures/f01_zeros.png) | Positive-spending distribution and zeros by expenditure decile |
| [f02_engel.png](figures/f02_engel.png) | Education budget share by within-year expenditure rank |
| [f03_who_spends.png](figures/f03_who_spends.png) | Budget shares by head's education and employment group |
| [f04_diagnostics.png](figures/f04_diagnostics.png) | Residual distribution, Q–Q plot, and residuals against fitted values |
| [f05_quantity_quality.png](figures/f05_quantity_quality.png) | Spending per student and conditional estimates by expenditure tercile |
| [f06_reconciliation.png](figures/f06_reconciliation.png) | Resource elasticity estimates across models |
| [f07_oaxaca.png](figures/f07_oaxaca.png) | Oaxaca–Blinder decomposition of the budget-share change |

## Tables

| File prefix in `tables/` | Contents |
|---|---|
| `t00`, `t01`, `t02` | Wave compatibility, schooling-field checks, sample filters |
| `t03`, `t04` | Weighted descriptives and unweighted head-education composition |
| `t05`, `t06`, `t06b` | Zero-spending rates and budget-share patterns |
| `t07` | Five baseline OLS specifications |
| `t08`, `t09` | Standard-error comparison and VIF diagnostics |
| `t10`, `t11` | Participation models and 300 province-bootstrap replicates |
| `t12`, `t13` | Student-count estimates, pooled and by expenditure tercile |
| `t14` | Nine elasticity estimates by model and resource measure |
| `t15`, `t16` | Year interactions and Oaxaca–Blinder decomposition |
| `t17` | Sensitivity checks, with specification notes |

In `t07`, parentheses contain province-clustered standard errors; stars indicate p < 0.01 (***), p < 0.05 (**), and p < 0.10 (*). The `t14` classifications describe point estimates relative to one, without testing that threshold. The `t17` partial weighting check holds the extensive margin fixed. Its deviations compare several different estimands with the income two-part baseline and should not all be interpreted as changes to the same model.

Figures 6 and 7 plot the rounded values in `t14` and `t16`. The raw workbooks are required to regenerate the full set of results.
