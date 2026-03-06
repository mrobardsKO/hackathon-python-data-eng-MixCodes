# 7.1-7.3 Analysis Summary

## 7.1 Conclusions

This project analyzed country-level COVID-19 testing and positive case counts to answer:

**Which countries have reported the highest number of positive cases in relation to the number of tests conducted?**

Based on the notebook workflow, the analysis produced three key outputs:

1. Top countries by total positive cases.
2. Top countries by total tests conducted.
3. Top countries by positive-to-test ratio (`total_positive_cases / total_tests_conducted`).

Main observations:

1. Countries with the highest total positive cases are not always the same countries with the highest positivity ratio.
2. Countries with very large testing volumes can still have moderate ratios because of broader testing coverage.
3. The positivity ratio is useful for comparative screening but should not be interpreted alone as disease burden or policy effectiveness.

## 7.2 Limitations

1. Aggregation method:
   - Country-level totals are derived from cumulative series (using country maxima), which can hide sub-national variation.
2. Data quality:
   - Missing values, inconsistent reporting cadence, and methodology differences across countries can affect comparability.
3. Metric interpretation:
   - Positivity ratio is sensitive to testing strategy (targeted vs broad testing), so cross-country comparisons can be biased.
4. Temporal dynamics:
   - A single aggregated ranking can mask changes over time (waves, policy shifts, backlog updates).

## 7.3 Next Steps

1. Add time-series analysis:
   - Compute rolling positivity trends by country and detect turning points.
2. Normalize for fairer comparisons:
   - Add population-adjusted indicators (tests per capita, positives per capita).
3. Improve robustness:
   - Apply outlier checks and reporting anomaly flags.
4. Expand context:
   - Join vaccination, hospitalization, and mortality datasets for multi-metric interpretation.
5. Productionize outputs:
   - Export cleaned tables and visual artifacts into a reproducible reporting pipeline.
