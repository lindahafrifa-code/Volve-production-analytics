# Volve-production-analytics
# Volve Field — Production Data Analytics

**Production analysis of Equinor's Volve field (North Sea, 2008–2016), built as a staged analytics pipeline: Python for data cleaning and KPI engineering, Excel for the stakeholder dashboard. SQL extraction layer and Power BI in progress.**

![Dashboard Monthly -Excel.png](https://github.com/lindahafrifa-code/Volve-Field-Production-Analytics-Python-Jupyter/blob/main/excel/Dashboard%20Monthly%20-Excel.png)

---

## Vole field in brief

Volve was a small oil field in block 15/9, central North Sea, producing from sandstones of the Middle Jurassic **Hugin Formation** at ~2,700–3,100 m depth. Originally planned for 3–5 years, it produced for over 8 years (Feb 2008 – Sep 2016), recovering 63 million barrels at a 54% recovery rate. Pressure was maintained by water injection, with injection water drawn from the shallow Utsira.

## Why Volve repo?

Volve is a comprehensive open dataset released from the NCS: roughly 40,000 files disclosed by Equinor and its licence partners (ExxonMobil, Bayerngas) in 2018.
The repo used Volve dataset for 3 main reasons: 
1. **It is real.** Real allocated production data, with real problems: NULL text in numeric columns, wells that changed role mid-life, missing sensor readings. This means cleaning it requires applying my professional skills instead of formulas only.
2. **It is verifiable.** The Volve's field history is publicly documented with peak production of ~56,000 bbl/d (≈9,000 Sm³/d), 63 million barrels recovered, a 54% recovery rate. Hence results from the repo can be reconciled against the official NPD records.
3. **It is a known field.** NCS operators know this field. Meaning the analysis can be judged on its merits by people who know the right answers.

## What the analysis found

**Two wells carried the field** NO 15/9-F-12 H (F-12) and NO 15/9-F-14 H (F-14) produced ~8.5M of the field's ~10M Sm³ of oil (85%). 

**Calculated rates reconcile with the official record** Peak producing rates (F-12 ≈ 5,300 Sm³/d) are consistent with the reported field peak of ~9,000 Sm³/d across all producers.

**Classic waterflood breakthrough** The two main producers show S-curve water cut rising to ~97%, the injected water front sweeping through the reservoir and arriving at the wells.

**Late wells watered up fast** F-11, F-1 C, and F-15 D, drilled in the second campaign from 2013 broke through steeply on start-up, consistent with drilled into an already-swept reservoir.

**Stable GOR read alongside rising water cut** indicates the injection scheme held reservoir pressure even as water arrived — the waterflood did its job.

**Rising water cut ended the field.** Field-wide water cut climbing past 90% is why Volve was shut in come 2016, despite pressure being successfully maintained. The field died of water, not of pressure loss.


## What should be done next
This repo is a staged build. Remaining stages, in order:

1. **SQL extraction layer** *(in progress)* — the same aggregations (production by well, monthly summaries, well rankings) written as queries against the raw data, completing the extract → analyse → communicate pipeline.
2. **Diagnosis notebook 3** — the interpretation layer: approximate VRR (with formation-volume-factor assumptions stated), water cut vs downhole pressure, and oil rate vs choke size to separate reservoir-driven decline from operational choking. 
3. **Power BI dashboard** — interactive stakeholder view.
4. **Connectivity study** — NPD notes that communication across faults in the heavily faulted western part of the structure is uncertain. Injector–producer pressure response is a data-driven way to investigate that connectivity question.

## Repository contents

| Path | Contents |
|---|---|
| `data/` | Raw production data (daily + monthly) and cleaned CSV |
| `notebooks/01_data_cleaning.ipynb` | Load, rename, flag well roles, handle NULLs, build KPIs (oil rate, water cut, GOR) |
| `notebooks/02_field_production_analysis_charts.ipynb` | Six charts: total oil/gas by well, rate decline, water cut, GOR, gas production |
| `excel/` | Dashboard workbook — pivot analysis, well-health summary table with conditional-format flags, key findings |
| `images/` | Exported charts |

## Data licence & attribution

Equinor Volve open dataset, released under **CC BY-NC-SA 4.0**. Data © Equinor, ExxonMobil E&P Norway, Bayerngas Norge, and the Norwegian Petroleum Directorate. Used here for learning and portfolio purposes in the spirit of the release; not for resale.

---

*Linda Afrifa — MSc Petroleum Geosciences (NTNU) · [LinkedIn](https://www.linkedin.com/in/linda-afrifa)*





