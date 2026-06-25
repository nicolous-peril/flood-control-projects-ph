# DPWH Flood Control Projects in the Philippines

## Project Overview

This project analyzes publicly available data on Department of Public Works and Highways (DPWH) flood control projects in the Philippines from 2018 to 2025.

Flood control infrastructure is a major public investment area in the Philippines, where flooding regularly affects communities, mobility, livelihoods, and public safety. This project turns a large project-level dataset into a structured analytics story that helps viewers understand where funds are allocated, which regions and provinces receive the largest investments, what types of work are most common, and how project volume compares with funding levels.

The project has evolved from a single Tableau dashboard into a multi-dashboard Tableau workbook with a five-part Tableau Story designed for presentation and portfolio use.

> This is a descriptive data analysis project. It does not determine wrongdoing, evaluate political decisions, or assess the engineering effectiveness of individual projects. The goal is to make project spending patterns easier to explore and discuss using data visualization.

## Tableau Public Dashboard

View the interactive dashboard on Tableau Public:

[DPWH Flood Control Projects in the Philippines](https://public.tableau.com/app/profile/nicanor.jr.peril/viz/flood_control_project/Dashboard6?publish=yes)

![Tableau Public dashboard preview](images/Dashboard%206.png)

## Project Objectives

- Clean and prepare raw DPWH flood control project data for analysis.
- Summarize national, regional, provincial, and contractor-level spending patterns.
- Build visual dashboards that make infrastructure allocation easier to understand.
- Create a Tableau Story that guides viewers through the analysis in a clear narrative sequence.
- Present insights in a format suitable for recruiters, hiring managers, and data analytics reviewers.

## Key Questions

- How much funding has been allocated to flood control projects nationwide?
- Which regions and provinces receive the largest approved budgets?
- Where are flood control projects most concentrated?
- What types of flood control work dominate the project portfolio?
- How does project count compare with total funding and average project cost?
- Which patterns stand out for funding concentration and regional differences?

## Dataset

Source: [DPWH Flood Control Projects on Kaggle](https://www.kaggle.com/datasets/bwandowando/dpwh-flood-control-projects)

The repository includes both the raw dataset and the cleaned dataset used for Tableau visualization.

| File | Description |
| --- | --- |
| `data/dpwh_flood_control_projects_raw.csv` | Original raw project dataset |
| `data/dpwh_flood_control_projects_clean.csv` | Cleaned dataset exported from the Jupyter notebook |

### Dataset Summary

| Metric | Value |
| --- | ---: |
| Records | 9,855 |
| Columns | 22 |
| Funding years | 2018-2025 |
| Regions covered | 16 |
| Provinces covered | 84 |
| Unique contractors | 2,409 |
| Total approved budget | ₱549.98B |
| Total contract cost | ₱545.64B |
| Average contract cost | ₱55.52M |

### Key Fields

- `Region`, `Province`, `Municipality`, and `MainIsland`
- `ProjectName`, `TypeOfWork`, `ProjectId`, and `ContractId`
- `FundingYear`, `StartDate`, and `ActualCompletionDate`
- `ApprovedBudgetForContract` and `ContractCost`
- `Contractor` and `ContractorCount`
- Project and provincial capital latitude/longitude fields

## Data Cleaning

Data preparation was completed in Python using the notebook:

`notebooks/data_cleaning.ipynb`

Main cleaning steps:

- Loaded and inspected the raw CSV dataset.
- Reviewed column types, missing values, descriptive statistics, and duplicate records.
- Converted `ApprovedBudgetForContract` and `ContractCost` from text/object fields into numeric values.
- Converted `StartDate` and `ActualCompletionDate` into datetime fields.
- Preserved missing municipality values instead of imputing location-specific information.
- Exported the cleaned dataset to `data/dpwh_flood_control_projects_clean.csv`.

Data quality notes:

- The cleaned dataset contains 9,855 records and 22 columns.
- No duplicate rows were found during the notebook review.
- `Municipality` contains missing values for 666 records.
- Some budget/cost values could not be converted cleanly because of non-standard entries, including MYCA-related records; these were retained as missing values rather than forced into inaccurate numbers.

## Tableau Workbook and Story

The Tableau work is stored as a packaged workbook:

`tableau/flood_control_project.twbx`

The project is also published on Tableau Public:

[https://public.tableau.com/app/profile/nicanor.jr.peril/viz/flood_control_project/Dashboard6?publish=yes](https://public.tableau.com/app/profile/nicanor.jr.peril/viz/flood_control_project/Dashboard6?publish=yes)

The workbook includes multiple worksheets, dashboards, and a five-part Tableau Story:

1. **Why should we care?**

   Introduces the public relevance of flood control spending and shows national-level KPI context.

2. **Following the money**

   Explores regional funding share, average project cost by region, and project cost distribution.

3. **Where are projects being built?**

   Compares project counts by region and breaks down projects by type of work.

4. **Funding efficiency: volume vs. investment**

   Uses a bubble/scatter view to compare number of projects, total funding, and average project cost by region.

5. **Key takeaways**

   Summarizes the major patterns from the analysis in a presentation-ready closing page.

## Exported Story Pages

| Story page | Preview |
| --- | --- |
| Why should we care? | ![Why should we care](images/Story%201.png) |
| Following the money | ![Following the money](images/Story%201-2.png) |
| Where are projects being built? | ![Where are projects being built](images/Story%201-3.png) |
| Funding efficiency | ![Funding efficiency](images/Story%201-4.png) |
| Key takeaways | ![Key takeaways](images/Story%201-5.png) |

## Analysis Highlights

- Flood control projects in the dataset represent approximately **₱550B in approved budget** and **₱545.64B in contract cost**.
- **Region III** has the largest total approved budget and the highest project count, making it the clearest investment hotspot in the analysis.
- Funding is concentrated in a small set of high-investment provinces, led by **Metro Manila**, **Bulacan**, and **Cebu**.
- **Flood mitigation structures** are the dominant project type, accounting for the majority of records in the dataset.
- Average project cost varies meaningfully by region, with some regions receiving fewer projects but showing higher average investment per project.
- The Tableau Story frames these findings as a guided narrative instead of a standalone dashboard, making the project easier to present and review.

## Tools Used

- **Python**: data cleaning and validation
- **Jupyter Notebook**: documented data preparation workflow
- **Tableau**: dashboard development and Tableau Story creation
- **CSV**: raw and cleaned dataset storage
- **Git / GitHub**: version control and project publishing

## Repository Structure

```text
flood-control-projects-ph/
├── data/
│   ├── dpwh_flood_control_projects_raw.csv
│   └── dpwh_flood_control_projects_clean.csv
├── images/
│   ├── Dashboard 6.png
│   ├── Story 1.png
│   ├── Story 1-2.png
│   ├── Story 1-3.png
│   ├── Story 1-4.png
│   └── Story 1-5.png
├── notebooks/
│   └── data_cleaning.ipynb
├── tableau/
│   └── flood_control_project.twbx
└── README.md
```

## How to Explore the Project

1. Review the cleaned dataset in `data/dpwh_flood_control_projects_clean.csv`.
2. Open `notebooks/data_cleaning.ipynb` to see the data preparation process.
3. Open `tableau/flood_control_project.twbx` in Tableau to explore the workbook, dashboards, and Story.
4. View the published version on [Tableau Public](https://public.tableau.com/app/profile/nicanor.jr.peril/viz/flood_control_project/Dashboard6?publish=yes).
5. View `images/Dashboard 6.png` and the exported Story screenshots in the `images/` folder for a quick presentation-style walkthrough.

## Notes and Limitations

- The analysis depends on the completeness and accuracy of the source dataset.
- Missing municipality values were not filled because doing so could introduce incorrect location assumptions.
- The project analyzes allocation and project-record patterns only; it does not measure real-world flood reduction outcomes.
- Findings should be interpreted as exploratory and descriptive, not as proof of causation or project performance.
