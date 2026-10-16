# Data Dictionary

Source: Kaggle "HR Employee Dataset" (justinlimyin). 3,400 rows, 20 raw columns, no missing values, no duplicate Employee_ID.
The dataset has no date column and no currency label.

| Column | Type | Role in model | How it is used |
|---|---|---|---|
| Employee_ID | Integer | Key | Distinct count only (headcount). Never put on an axis. |
| Department | Text | Dimension (Dim_Department) | Slicer, axis, drill-through |
| Gender | Text | Dimension | Diversity visuals / legend |
| Age | Integer | Attribute | Avg Age; source of Age_Group |
| Education_Level | Text | Dimension (Dim_Education) | Axis (sorted by Education_Order) |
| Job_Role | Text | Dimension (Dim_JobRole) | Axis (sorted by Role_Order) |
| Monthly_Income | Decimal | Measure source | Payroll, averages; source of Annual_Income, Income_Band |
| Years_At_Company | Integer | Attribute | Avg Tenure; source of Tenure_Band |
| Years_In_Current_Role | Integer | Attribute | Data-quality check |
| Job_Satisfaction | 1-5 | Measure source | Avg Job Satisfaction |
| Performance_Rating | 1-5 | Measure source | Avg Performance; High (>=4) / Low (<=2) performer |
| Work_Life_Balance | 1-5 | Measure source | Avg Work Life Balance |
| Training_Hours_Last_Year | Integer | Measure source | Avg Training Hours |
| Last_Promotion_Years_Ago | Integer | Measure source | Avg Years Since Promotion |
| Distance_From_Home | Integer | Attribute | Avg Commute Distance |
| Overtime | Yes/No | Dimension | Attrition split |
| Attrition | Yes/No | Dimension | Attrition Rate |
| Marital_Status | Text | Dimension | Demographic split |
| Number_Of_Companies_Worked | Integer | Attribute | Detail/drill-through |
| Stock_Option_Level | 0-3 | Attribute | Detail/drill-through |

## Derived columns
Age_Group (+Age_Group_Sort), Income_Band (+Income_Band_Sort), Tenure_Band (+Tenure_Band_Sort), Annual_Income (= Monthly_Income x 12), Data_Quality_Flag.

## Known data-quality issues (kept, flagged, not deleted)
- 957 rows: Years_At_Company > Age - 18 (tenure longer than possible working life)
- 608 rows: Years_In_Current_Role > Years_At_Company
- 32 rows: both
- Only 1,803 rows pass both checks. The data looks synthetic (near-zero correlation between rating, pay and satisfaction), so treat insights as practice, not real HR conclusions.
