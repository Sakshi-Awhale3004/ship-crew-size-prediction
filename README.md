# Ship Crew Size Prediction

A regression project that estimates a cruise ship’s reported crew size from vessel characteristics.

## Project overview

The goal is to estimate crew size using a ship’s age, tonnage, passenger capacity, length, cabin count, passenger density, and cruise line.

## Dataset

The project uses a dataset of 158 cruise ships. The `crew` target is recorded in hundreds, so a value of `7.8` represents about 780 crew members.

- [CSV dataset](https://raw.githubusercontent.com/niclasko/niclasko.github.io/master/data/cruise_ship_info.csv)
- [Dataset notes, including units](https://www.scribd.com/document/978267329/ITITIU21024-Lab9-Ipynb-Colab)

## Method

- Checked the data and missing values.
- Split the data into training and test sets.
- Used a scikit-learn pipeline to scale numeric features and one-hot encode cruise line.
- Compared Linear Regression with Random Forest.
- Used 5-fold `GroupKFold` cross-validation, keeping cruise lines separate between training and validation folds.

## Results

Linear Regression performed better than Random Forest in grouped cross-validation.

| Model | Grouped CV MAE |
|---|---:|
| Linear Regression | 0.705 ± 0.190 dataset units |
| Random Forest | 0.855 ± 0.401 dataset units |

Since crew is recorded in hundreds, the Linear Regression MAE is about 71 crew members. On the 20% holdout split, Linear Regression had MAE 0.499 units, RMSE 0.771 units, and R² 0.954.

The notebook’s example ship received an estimated crew size of about 1,850.

## Limitations

This is a learning project based on a small cruise ship dataset. It estimates patterns in reported crew counts; it does not calculate legally required staffing or provide a safety-approved crew recommendation.

## Notebook

[Open the Colab notebook](https://colab.research.google.com/github/Sakshi-Awhale3004/ship-crew-size-prediction/blob/main/Ship_Crew_Size_Prediction.ipynb)
