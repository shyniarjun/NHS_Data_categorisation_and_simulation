## Methodology

This project addresses the need for consistent KPI categorisation and “what-if” scenario modelling within the NHS Exemplar Accreditation programme.

### 1. Data Loading and Validation

* Imported two structured CSV files: `KPI_Data_2024.csv` and `KPI_Threshold_Lookup_Table.csv`
* Checked data types and identified non-numeric KPI entries
* Ensured consistency of `KPI_Name` fields across both sources

### 2. Merging Thresholds

* Performed a left join on `KPI_Name` to enrich KPI entries with their categorisation logic (Gold/Silver/Bronze thresholds and direction)
* Flagged any rows missing threshold definitions for further review

### 3. Categorisation Logic

* Built a reusable function `assign_category()` that:

  * Compared `KPI_Value` against thresholds
  * Considered `Direction` of metric (whether higher/lower is better)
  * Returned "Manual" if the KPI required comparator-based interpretation
* Created a new column `Assigned_Category` across the dataset

### 4. Aggregation by Ward and Month

* Grouped categorised data to count how many KPIs were Gold, Silver, Bronze, etc., by ward and by month
* Calculated category proportions and derived `Gold_Percentage` to evaluate performance consistency

### 5. Overall Rating Logic

* Translated `Gold_Percentage` into human-readable performance labels:

  * ≥90% → Excellent
  * 70–89% → Good
  * 50–69% → Needs Improvement
  * <50% → Needs Attention

### 6. Simulation 1: Tightened Gold Threshold

* Adjusted the Gold_Threshold from 95% to 97% to test the effect of stricter performance expectations.
* Re-applied categorisation to observe sensitivity to stricter targets
* Compared `Assigned_Category` vs `Simulated_Category` and calculated impact

### 7. Simulation 2: 3-Point Value Drop

* Simulated a dip in service performance by applying a ±3 adjustment to KPI scores

* Subtracted 3 from KPIs where higher values indicate better performance, and added 3 where lower values are better

* Re-ran the categorisation logic to assess impact

* Compared the original Assigned_Category with the new Simulated_Category

* Tracked which KPIs and wards experienced downgrades in category

### 8. Visualisation of Simulation Impact

* Created horizontal bar plots to show KPI category changes
* Used pie charts to summarise overall shifts (e.g. 42% of KPIs changed due to 3-point drop)

### 9. Design Considerations

* Manual KPIs were excluded from automation to preserve accuracy
* Simulations only applied to KPIs with numeric, directional thresholds
* Visual outputs support strategic decision-making around thresholds and quality assurance
