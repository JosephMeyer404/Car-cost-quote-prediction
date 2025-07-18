# Rusty Bargain: Used Car Price Prediction

This project involves building and evaluating machine learning models to predict the market value of used cars for Rusty Bargain, a car sales service developing a customer-facing app. Users should be able to quickly estimate their car's value based on historical listings.

## Project Objective

Rusty Bargain is focused on:
- High prediction accuracy (low RMSE)
- Fast prediction speed
- Efficient training time

---

## Dataset

The dataset includes over 300,000 used car listings with features like brand, model, power, mileage, fuel type, gearbox, and registration dates.

**Target Variable:**  
`price` (in euros)

**Features:**
- `vehicle_type`
- `registration_year`
- `gearbox`
- `power`
- `model`
- `mileage`
- `registration_month`
- `fuel_type`
- `brand`
- `not_repaired`

---

## Data Preprocessing

- Removed duplicates and invalid values (e.g., price ≤ 0, absurd power or year entries).
- Filled missing values in categorical features with `"unknown"`.
- Dropped unused or redundant columns (`date_created`, `postal_code`, etc.).
- Applied one-hot encoding to categorical features.

---

## Models Trained

| Model                  | RMSE (€)     |
|-------------------------|--------------|
| Linear Regression      | ~3,332       |
| Decision Tree          | ~2,790       |
| Random Forest          | ~2,294       |
| LightGBM               | ~2,308       |
| CatBoost               | ~2,376       |

**Evaluation Metric:**  
Root Mean Squared Error (RMSE)

---

## ⏱️ Model Efficiency

| Model             | Training Time (sec) | Prediction Time (sec) |
|------------------|----------------------|------------------------|
| Linear Regression| 1.61                 | 0.07                   |
| Random Forest     | 26.88                | 0.10                   |
| LightGBM          | 2.41                 | 0.27                   |
| CatBoost          | 2.65                 | 0.02                   |

---

## Key Findings

- **Random Forest** provided the best RMSE out of the box.
- **Tuned LightGBM** achieved nearly identical performance with faster training.
- **CatBoost** had the fastest prediction speed but slightly higher RMSE.
- **Linear Regression** served as a solid baseline and sanity check.

---

## Conclusion

Both **Random Forest** and **LightGBM** are excellent candidates for deployment:
- **LightGBM** offers a great balance of speed and accuracy.
- **Random Forest** is robust, interpretable, and performs slightly better on this dataset.

Further improvements could include:
- Hyperparameter tuning via grid/randomized search
- Cross-validation for stability checks
- Feature importance analysis to interpret drivers of car price

---

## Tools & Libraries
- Python 3.13
- pandas, numpy
- scikit-learn
- lightgbm
- catboost

---

## 📁 Repository Structure

