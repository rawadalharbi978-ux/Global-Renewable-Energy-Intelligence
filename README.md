Global Renewable Energy Intelligence & Predictive Modeling

Project Overview

An applied Data Science project investigating renewable electricity patterns across countries through advanced exploratory data analysis, unsupervised learning, and predictive machine learning.

The project combines statistical analysis, K-Means clustering, and one-year-ahead forecasting to examine renewable energy transitions and evaluate whether machine learning improves on simple forecasting benchmarks.

Dataset

•⁠  ⁠Source: Our World in Data — Global Energy Dataset
•⁠  ⁠Coverage: 2015–2025 (analysis subset)
•⁠  ⁠Original dataset: 23,377 records and 130 features
•⁠  ⁠Cleaned dataset: 2,191 country-year records
•⁠  ⁠Data source: https://github.com/owid/energy-data

Methodology

1.⁠ ⁠Data acquisition and preprocessing using Python and Pandas.
2.⁠ ⁠Exploratory analysis of renewable electricity trends.
3.⁠ ⁠Country profiling using K-Means clustering and silhouette-based model selection.
4.⁠ ⁠One-year-ahead forecasting using Random Forest and Gradient Boosting.
5.⁠ ⁠Time-based evaluation against a persistence baseline using MAE and R².

Key Results

| Forecasting Model | MAE |
|---|---:|
| Persistence Baseline | 1.965 |
| Random Forest | 2.144 |
| Gradient Boosting | 2.159 |


Both machine learning models achieved approximately 0.989 R² on the test data. However, the persistence baseline produced the lowest MAE, highlighting the importance of benchmarking complex models against simple alternatives.

Technologies

Python, Pandas, NumPy, Matplotlib, Scikit-learn, Google Colab.

Limitations

•⁠  ⁠Some indicators contain missing observations.
•⁠  ⁠Country coverage and data availability vary across years.
•⁠  ⁠The global country-average trend is not weighted by electricity generation.
•⁠  ⁠Predictive performance is evaluated on historical data and does not guarantee future forecasting accuracy.

Project Files

•⁠  ⁠Global_Renewable_Energy_Intelligence.ipynb — analysis and machine learning notebook.
•⁠  ⁠Global_Renewable_Energy_Report.pdf — academic project report.

Author

Rawad Alharbi
Data Science Undergraduate
