# Data

The analysis uses household summary workbooks for the Statistical Centre of Iran's Household Expenditure and Income Survey, waves 1394 and 1403. Monetary variables are annual nominal Iranian rials.

## Required inputs

Place these exact files in `data/raw/`. Each workbook must contain a worksheet named `data`.

| Workbook | Rows in the saved analysis | Columns |
|---|---:|---:|
| `Iran_HBS_Summary_1394_V.0.3.xlsx` | 38,252 | 149 |
| `Iran_HBS_Summary_1403_V.0.3.xlsx` | 37,505 | 149 |

The original analysis cites the [Iran Open Data HBSIR project](https://github.com/Iran-Open-Data/HBSIR) as its data-processing source. Its [documentation](https://iran-open-data.github.io/HBSIR/) describes the survey tools. These links are background references; they are not verified download links for the exact v0.3 Excel release used here. A newly generated HBSIR table may have a different schema.

The raw workbooks are not distributed with this repository. The notebook retains saved outputs, and `results/` contains aggregate tables and figures. Reproducing the estimates requires the workbooks above. Raw inputs, cached data, and the generated household-level analysis sample are excluded from version control.

## Main variables

| Workbook column | Analysis variable | Use |
|---|---|---|
| `Education Services` | `edu` | Education-services expenditure |
| `Income` | `income` | Reported household income |
| `Gross_Expenditure` | `totexp` | Total household expenditure |
| `Number_of_Students` | `students` | Number of enrolled household members |
| `Number_of_Childs` | `kids` | Child count used in the original analysis as children under 18 |
| `Family_Size` | `fsize` | Household size |
| `Head_Education_Level` | `edulev` | Head's education category |
| `Weight` | `weight` | Household survey weight |
| `Province`, `Season`, `Urban_Rural` | Location and season controls | Regression controls and province clustering |

The notebook also uses the head's age, sex, marital and employment characteristics, spouse information, housing tenure, and asset indicators. Its loader checks all required columns before estimation. The workbook's codebook should be consulted when interpreting the underlying survey fields.

## Sample and derived measures

The main sample requires at least one enrolled student, positive income and total expenditure, education spending no greater than total expenditure, and a head aged 15–99. Zero education spending remains in this sample. Log-spending regressions use only positive spenders.

The education budget share is `edu / totexp`; spending per student is `edu / students`. The latter is a household average and does not measure how spending is divided between individual children. The two waves are treated as repeated cross-sections, without household-level matching.
