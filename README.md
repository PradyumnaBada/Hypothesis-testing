# University Towns & Housing Prices During Recessions

## Project Goal
This analysis determines if university towns' mean housing prices were less negatively impacted by the 2008-2009 recession compared to non-university towns.

## Data Used
* `university_towns.txt`: List of US university towns.
* `gdplev.xls`: Quarterly US Gross Domestic Product (GDP) data.
* `City_Zhvi_AllHomes.csv`: Zillow Home Value Index (ZHVI) data.

## Core Analysis
1.  **Identify University Towns**: A list of university towns is parsed from `university_towns.txt`.
2.  **Determine Recession Timeline**:
    * The start ('2008q3'), bottom ('2009q2'), and end ('2009q4') of the recession are identified using GDP data from `gdplev.xls`.
3.  **Process Housing Data**:
    * Monthly housing price data from Zillow (`City_Zhvi_AllHomes.csv`) is converted into quarterly averages.
4.  **Hypothesis Testing**:
    * A **price ratio** is calculated for each town: (Mean housing price in the quarter before recession start, i.e., '2008q2') / (Mean housing price at recession bottom, i.e., '2009q2').
    * An independent two-sample t-test is performed to compare the mean price ratios of university towns versus non-university towns.
    * **Null Hypothesis (H₀):** The mean price ratio is the same for university and non-university towns.
    * **Alternative Hypothesis (H₁):** University towns have a lower mean price ratio (indicating prices were less affected).

## Findings
* **P-value:** `0.002724`
* **Outcome:** The null hypothesis is rejected (p < 0.01).
* **Conclusion:** University towns, on average, had a significantly lower price ratio, suggesting their housing prices were less negatively affected by the recession compared to non-university towns.

## Technical Stack
* `pandas`
* `numpy`
* `scipy.stats` (for `ttest_ind`)

---
