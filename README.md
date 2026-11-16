# Predictive Analytics for Supply Chain Demand Forecasting and Inventory Planning

**Author:** Criselvi Lindsey  
**University:** Bellevue University  
**Course:** DSC 680 – Applied Data Science Capstone

## Project Overview

This project evaluates machine learning approaches for forecasting short-term retail grocery sales. The objective is to determine whether predictive models can improve forecasting accuracy compared with a traditional weekly seasonal baseline.

The analysis uses historical Corporación Favorita grocery sales data from Ecuador. Improved demand forecasts can support inventory planning decisions, although this project does not directly optimize inventory quantities.

## Dataset

Source: Kaggle – Store Sales: Time Series Forecasting

https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data

The original training dataset contains approximately 3 million daily sales records across 54 stores and 33 product families.

This study focuses on:
- Product family: GROCERY I
- Stores: 44, 45, and 47
- Analysis dataset: 5,052 daily records
- Forecast horizon: 16 days

Required source files:
- `train.csv`
- `stores.csv`

Download these files from Kaggle and place them in the notebook's working directory before running the analysis.

## Methodology

The project compares three forecasting methods:

1. Seasonal naïve forecasting
2. Random forest regression
3. Histogram-based gradient boosting regression

The analysis includes data validation, store-data integration, calendar features, lagged sales, rolling averages, and time-series evaluation.

Historical sales features are calculated using information available at each forecast origin to prevent future-data leakage.

Three rolling-origin validation windows are used, followed by a separate final holdout period.

## Final Holdout Results

| Model | MAE | RMSLE | WAPE |
|---|---:|---:|---:|
| Seasonal Naïve | 1,500 | 0.1904 | 14.6% |
| Random Forest | 1,440 | 0.1830 | 14.0% |
| Histogram Gradient Boosting | 1,369 | 0.1755 | 13.3% |

Histogram-based gradient boosting achieved the lowest error on the final holdout, reducing MAE by approximately 8.8% compared with the seasonal naïve baseline.

## Business Relevance

More accurate demand forecasting can support decisions about replenishment and inventory planning.

However, the study does not measure actual inventory cost savings, stockout reductions, or optimal reorder quantities because the required operational data were unavailable.

## Technologies and Skills

- Python
- pandas
- NumPy
- scikit-learn
- Jupyter Notebook
- Data preparation and validation
- Feature engineering
- Time-series cross-validation
- Predictive modeling
- Data visualization
- Model performance evaluation

## Project Files

The repository includes:
- Final Jupyter notebook (`.ipynb`)
- Final white paper (`.pdf`)
- This README

## Project Presentation

[View Narrated PowerPoint Presentation](https://drive.google.com/file/d/1JxE0X5-d06Rep7xofJBirnDLlta9ijZB/view?usp=drive_link)

The presentation is hosted on Google Drive because its embedded narration makes the PowerPoint file too large for GitHub's browser uploader.

For the best playback experience, download the PowerPoint and open it in Microsoft PowerPoint.

## Running the Notebook

1. Download the notebook from this repository.
2. Download `train.csv` and `stores.csv` from the Kaggle dataset linked above.
3. Place both CSV files in the notebook's working directory.
4. Install the Python libraries used by the notebook.
5. Open the notebook in Jupyter Notebook or JupyterLab.
6. Run the cells in order.

## Limitations

- The analysis covers only three stores and one product family.
- Forecast accuracy does not establish inventory optimization benefits.
- Promotional comparisons are descriptive and do not establish causation.
- The selected stores have similar characteristics, limiting comparisons across store types.
- Model performance may differ for other stores, products, and time periods.

## Author

**Criselvi Lindsey**  
Master of Science in Data Science  
Bellevue University
