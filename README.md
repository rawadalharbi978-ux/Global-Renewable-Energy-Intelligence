# Global Renewable Energy Intelligence & Predictive Modeling

 ## Research Overview

This project investigates cross-country patterns in renewable electricity generation and evaluates the effectiveness of machine learning for one-year-ahead forecasting.

Using historical energy data from Our World in Data, the analysis integrates exploratory data analysis, country-level energy profiling, unsupervised learning, and supervised predictive modeling.

The central research question is:

Can machine learning models improve one-year-ahead renewable electricity share forecasts compared with a simple persistence baseline?

Rather than assuming that more complex models provide better predictions, the project evaluates their performance against an interpretable benchmark using chronologically separated data.

 ## Data and Analytical Scope

| Component | Description |
|---|---|
| Data source | Our World in Data — Global Energy Dataset |
| Analysis period | 2015–2025 |
| Original dataset | 23,377 records, 130 features |
| Cleaned dataset | 2,191 country-year observations |
| Forecast target | Next-year renewable electricity share |
| Training target years | 2017–2023 |
| Testing target years | 2024–2025 |
| Primary evaluation metric | Mean Absolute Error (MAE) |


Dataset: https://github.com/owid/energy-data
### Dataset Coverage Clarification

The dataset covers a broader set of countries and territories, while the country-level forecasting evaluation includes 191 countries with eligible test observations. These figures represent different analytical subsets and should not be interpreted as contradictory.

 ## Analytical Methodology

 ### 1.⁠ ⁠Data Acquisition and Preprocessing

The workflow begins with the acquisition of historical energy data, followed by variable selection, missing-value assessment, data cleaning, and the construction of country-year observations.

Temporal consistency checks are performed to verify the continuity of observations used in the forecasting workflow.

 ### 2.⁠ ⁠Exploratory Data Analysis

Exploratory analysis examines renewable electricity shares and the relative contributions of solar, wind, and hydropower.

Descriptive statistics and visualizations are used to investigate differences in renewable electricity patterns across countries.

 ### 3.⁠ ⁠Renewable Energy Profiling

K-Means clustering is applied to characterize countries according to their renewable electricity profiles.

Silhouette-based model selection supports the clustering process, while cluster-level summaries describe differences in solar, wind, and hydropower composition.

 ### 4.⁠ ⁠Predictive Modeling

Two supervised machine learning approaches are evaluated:

•⁠  ⁠Random Forest Regressor
•⁠  ⁠Histogram-Based Gradient Boosting Regressor

Both models are compared with a persistence baseline that uses the current renewable electricity share as the following year’s prediction.

 ### 5.⁠ ⁠Temporal Evaluation and Validation

A chronological evaluation strategy separates earlier target years from later test years.

Validation checks confirm that:

•⁠  ⁠Training and testing target years do not overlap.
•⁠  ⁠The prediction target is excluded from the model input features.
•⁠  ⁠Training and testing features contain no missing values.
•⁠  ⁠Modeled observations satisfy the temporal continuity checks.

 ### 6.⁠ ⁠Model Interpretation and Error Analysis

Random Forest feature importance is examined to identify the variables most strongly associated with its predictions.

Country-level MAE is also calculated to investigate differences in forecasting performance and identify cases with relatively large prediction errors.

Results

Overall Forecasting Performance

Forecasting approach	Test MAE
Persistence Baseline	1.965
Random Forest	2.144
Gradient Boosting	2.159

Principal finding: The persistence baseline achieved the lowest overall MAE, outperforming both machine learning models.

This demonstrates that strong predictive fit does not necessarily translate into improved forecasting performance over a simple benchmark.

Country-Level Forecasting Performance

The evaluation included 191 countries.

Better-performing approach	Number of countries
Random Forest	84
Persistence Baseline	107

Although Random Forest outperformed the baseline in some countries, the baseline performed better in the majority of evaluated countries.

Country-level comparisons should be interpreted cautiously because some countries contribute only one or two test observations.

Feature Importance

Random Forest feature importance was strongly concentrated in the current renewable electricity share.

This suggests that renewable electricity shares exhibit substantial persistence over time, consistent with the strong performance of the baseline model.

Feature importance describes the fitted model’s behavior and should not be interpreted as evidence of causality.

Renewable Energy Profiles

The clustering analysis identified five renewable electricity profiles with different combinations of solar, wind, and hydropower contributions.

These profiles support descriptive comparisons of national renewable electricity structures. They do not establish causal relationships or imply that countries will follow the same energy transition pathways.

Discussion

Three findings emerge from the analysis.

First, benchmarking is essential. Despite the flexibility of ensemble machine learning methods, neither model improved upon the persistence baseline in overall MAE.

Second, forecasting performance varies across countries. Aggregate evaluation alone does not capture the differences observed in country-level errors.

Third, renewable electricity systems are heterogeneous. Clustering highlights differences in the composition of renewable electricity generation, providing a complementary perspective to the forecasting analysis.

Together, these findings illustrate the importance of combining predictive performance evaluation with descriptive analysis and model interpretation.

Limitations

•⁠  ⁠The analysis relies on historical observational data and does not establish causal relationships.
•⁠  ⁠Some countries have limited test observations, reducing the stability of country-level error estimates.
•⁠  ⁠Clustering observations are unevenly distributed across the most recent years.
•⁠  ⁠Model feature importance does not provide a causal explanation of renewable energy development.
•⁠  ⁠Performance on the historical test period does not guarantee equivalent results in future years.

Technical Stack

Language: Python

Libraries: Pandas, NumPy, Matplotlib, Scikit-learn

Environment: Google Colab

Methods: Exploratory Data Analysis, K-Means Clustering, Random Forest Regression, Histogram-Based Gradient Boosting, Temporal Validation, Forecast Benchmarking, Feature Importance, and Country-Level Error Analysis

Repository Contents

•⁠  ⁠Global_Renewable_Energy_Intelligence.ipynb — Complete analytical workflow, visualizations, machine learning models, and evaluation.
•⁠  ⁠Report.pdf. — Detailed academic report presenting the methodology, results, figures, and interpretation.

Conclusion

This project presents an integrated Data Science investigation of renewable electricity patterns and forecasting performance across countries.

The findings show that a simple persistence benchmark can outperform more complex machine learning models, even when those models achieve strong predictive fit.

By combining exploratory analysis, clustering, chronological validation, model comparison, and country-level error assessment, the project emphasizes methodological rigor, transparent evaluation, and evidence-based interpretation.
