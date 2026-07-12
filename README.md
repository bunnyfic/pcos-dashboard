# PCOS Dataset Analysis — Interactive Dashboard

An interactive, single-file HTML dashboard exploring how BMI, age, testosterone levels, and menstrual cycle regularity relate to PCOS (Polycystic Ovary Syndrome) diagnosis across a 1,000-patient dataset.

**[Live demo →](#)** *https://bunnyfic.github.io/pcos-dashboard/*

![Dashboard preview](preview.png)
*<img width="1325" height="601" alt="image" src="https://github.com/user-attachments/assets/349898c5-eea4-46df-861e-a686b8c5def1" />
<img width="1333" height="599" alt="image" src="https://github.com/user-attachments/assets/3e80c1e7-1829-4a38-bd9e-03ed39d094ac" />
*

## What it does

- **Filters**: BMI category, age group, and PCOS status — all combinable, with a live count of how many records match the current selection
- **KPI cards**: total women in selection, PCOS prevalence, and average antral follicle count split by diagnosis, all recalculated on every filter change
- **Auto-generated insights**: plain-language takeaways (prevalence rate, follicle-count gap between groups, highest-risk age bracket) that update with the filters, including a small-sample-size warning so thin subgroups aren't over-read
- **8 charts**: PCOS rate by age (bar + radar), menstrual irregularity by BMI, testosterone by BMI, follicle count by diagnosis, BMI sample-size distribution, a testosterone-vs-follicle-count scatter colored by diagnosis, and an age distribution stacked by diagnosis

## Tech stack

- Vanilla HTML / CSS / JavaScript — no build step, no dependencies to install
- [Chart.js](https://www.chartjs.org/) for all charts
- Data is parsed from the source spreadsheet with `pandas` and embedded directly in the page as JSON, so the dashboard runs entirely client-side with no backend or database

## Dataset

`pcos_dataset.xlsx` — 1,000 records, 6 fields: `Age`, `BMI`, `Menstrual_Irregularity`, `Testosterone_Level (ng/dL)`, `Antral_Follicle_Count`, `PCOS_Diagnosis`.

BMI is bucketed using standard clinical cutoffs:

| Category | BMI range |
|---|---|
| Underweight | < 18.5 |
| Normal weight | 18.5 – 24.9 |
| Overweight | 25 – 29.9 |
| Obese | ≥ 30 |

## Running locally

No build tools required — it's a single HTML file.

```bash
git clone https://github.com/<your-username>/pcos-dashboard.git
cd pcos-dashboard
open index.html   # or double-click the file / use a Live Server extension
```

## Project structure

```
.
├── index.html          # the dashboard (data embedded inline)
├── pcos_dataset.xlsx    # source data
└── README.md
```

## Notes

This is a portfolio / data-visualization project built to practice translating a BI-style dashboard (originally prototyped in Tableau) into a fully interactive, dependency-light web page.
