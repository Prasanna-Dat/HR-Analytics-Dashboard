# HR Analytics – Employee Performance & Payroll Dashboard

A Power BI dashboard I built to study employee attrition, payroll, performance and engagement for **3,400 employees**.

> The dataset looks synthetic, so this is a portfolio project and not a real HR study.

## Dashboard Preview

**1. Executive Overview**
![Executive Overview](Screenshots/overview.png)

**2. Attrition Analysis**
![Attrition Analysis](Screenshots/attrition.png)

**3. Payroll Analysis**
![Payroll Analysis](Screenshots/payroll.png)

**4. Performance & Engagement**
![Performance & Engagement](Screenshots/performance.png)

**5. Employee Details**
![Employee Details](Screenshots/details.png)

## Key Numbers

| Metric | Value |
|---|---|
| Total employees | 3,400 |
| Employees who left | 1,724 (50.7%) |
| Monthly payroll | 17,426,235 |
| Annual payroll | 209,114,820 |
| Average / median monthly income | 5,125 / 4,326 |
| Overtime share | 48.2% |
| High performers (rating 4 or 5) | 41.0% |

The dataset does not state a currency.

## What I Found

- Attrition is about 50% in every department, role, age group and tenure band.
- Employees without overtime left slightly more (53.1%) than those with overtime (48.1%).
- Average monthly income by role: Manager 9,505, Team Lead 7,663, Executive 3,516, Analyst 3,468, Intern 1,243. Executives earn less than Managers, which is unusual.
- Performance rating, income and job satisfaction show almost no relationship.

## How I Built It

1. Downloaded the HR Employee dataset from Kaggle.
2. Cleaned the data in Power Query: set data types, trimmed text, checked for duplicates and blanks (none found).
3. Added columns for age group, income band, tenure band, annual income and a data-quality flag.
4. Built a star schema: one employee table linked to Department, Job Role and Education tables.
5. Created about 35 DAX measures such as Attrition Rate, Monthly Payroll and High Performer %.
6. Designed five report pages with Department and Job Role slicers. All visuals cross-filter.
7. Applied a custom colour theme and documented the project.

## Repository Structure

| Folder / file | What it contains |
|---|---|
| `PowerBI/HR_Analytics_Dashboard.pbix` | The Power BI report |
| `Dataset/` | `HR_Dataset_raw.csv` (original Kaggle file), `HR_Employee_Clean.csv` (cleaned table), and `Dim_Department.csv`, `Dim_JobRole.csv`, `Dim_Education.csv` (lookup tables) |
| `Screenshots/` | Screenshots of the five report pages |
| `Documentation/` | [Data dictionary](Documentation/DATA_DICTIONARY.md) and [Project report (PDF)](Documentation/Project%20Report.pdf) |
| `theme/HR_Theme.json` | Power BI colour theme used in the report |

## How to Open

1. Install **Power BI Desktop** (Windows).
2. Download `PowerBI/HR_Analytics_Dashboard.pbix` and open it.
3. If the refresh fails, go to **Home → Transform data → Data source settings → Change Source** and select the CSV files from the `Dataset` folder.
4. To use the theme, go to **View → Themes → Browse for themes** and choose `theme/HR_Theme.json`.

## Data Limitations

- There is no date column, so I could not analyse trends over time.
- The data looks synthetic: attrition is about 50% everywhere and the variables are almost unrelated.
- 957 rows have more years at the company than possible for their age, and 608 rows have more years in the current role than at the company. I kept these rows and flagged them instead of deleting them.

## Data Source

[HR Employee Dataset](https://www.kaggle.com/datasets/justinlimyin/hr-employee-dataset) on Kaggle. Please check the licence on that page before reusing the data.

## Author

**Prasanna U N** · [GitHub](https://github.com/Prasanna-Dat)
