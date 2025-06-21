# House Price Prediction - Machine Learning Final Project

## Overview

This project aims to predict **house prices** using machine learning techniques. The dataset contains real estate features such as area, number of bedrooms/bathrooms, and additional amenities. The goal is to develop a model that accurately estimates house prices based on these attributes.

## Dataset Description

- **Source:** Housing Price Dataset (Kaggle / UCI ML Repository) [[Dataset Link](https://www.kaggle.com/datasets/saurabhbadole/housing-price-data?resource=download)]
- **Rows:** 545
- **Columns:** 13 (including categorical & numerical features)
- **Target Variable:** `price` (House Price)

### **Key Features:**

| Feature            | Description                                      |
| ------------------ | ------------------------------------------------ |
| `area`             | Total square footage                             |
| `bedrooms`         | Number of bedrooms                               |
| `bathrooms`        | Number of bathrooms                              |
| `stories`          | Number of floors                                 |
| `parking`          | Available parking spots                          |
| `mainroad`         | Whether the house is near the main road (yes/no) |
| `airconditioning`  | Presence of AC (yes/no)                          |
| `furnishingstatus` | Furnished, semi-furnished, or unfurnished        |

---

## Exploratory Data Analysis (EDA)

### **Findings:**

- No missing values were found in the dataset.
- `price` follows a **right-skewed distribution** (high-priced houses are fewer).
- Features like `area`, `bedrooms`, and `bathrooms` showed the **strongest correlation** with `price`.
- Some categorical features (`mainroad`, `airconditioning`) had a clear impact on price.

### **Visualizations:**

- **Histogram of House Prices**: Showed an uneven distribution with some high-price outliers.
- **Correlation Heatmap**: Highlighted relationships between features and price.
- **Scatter Plot (Actual vs. Predicted Prices)**: Used for model evaluation.

---

## Preprocessing Steps

### **Steps Taken:**

 Converted categorical variables to numerical using **One-Hot Encoding**.
 Scaled numerical features using **MinMax Scaling** to standardize data.
 Created **new features** such as:

- `area_per_bedroom = area / bedrooms`
- `bathrooms_per_bedroom = bathrooms / bedrooms`
- `parking_per_story = parking / stories`
   Removed low-correlation and redundant features to enhance model performance.

---

## Model Implementation

### **Models Used:**

1. **Linear Regression** (Baseline Model)
2. **Random Forest Regressor** (For comparison)

### **Results:**

| Model                 | R² Score |
| --------------------- | -------- |
| **Linear Regression** | **0.64** |
| Random Forest         | 0.57     |

- **Linear Regression performed best**, explaining **64% of the variance** in house prices.
- Feature engineering helped but did not significantly improve performance.
- Random Forest slightly underperformed due to overfitting on a small dataset.

---

## Model Evaluation

### **Metrics Used:**

 **R² Score**: Measures how well the model explains variance (**0.64 for Linear Regression**).
 **RMSE (Root Mean Squared Error)**: Shows average error magnitude.
 **Actual vs. Predicted Scatter Plot**: To visualize prediction accuracy.

---

## Challenges & Lessons Learned

### **Challenges:**

- Some categorical features had weak correlation with price.
- Feature engineering had **limited impact** due to the dataset’s structure.
- Random Forest didn’t outperform Linear Regression, which was unexpected.

### **Lessons Learned:**

 **Simple models (Linear Regression) can sometimes outperform complex ones.**
 **Feature selection is key**—removing unnecessary features helped improve performance.
 **Scaling and encoding significantly impact results.**

---

## Repository Structure

```
 MachineLearning-Final-Project
 ├── Kayden_Rumsey_Machine_Learning_Final.ipynb  # Full Jupyter Notebook
 ├── README.md  # Project Summary & Report
```

---

## Future Improvements

- **Try XGBoost or Gradient Boosting** for better accuracy.
- **Hyperparameter tuning** to optimize Random Forest performance.
- **Experiment with polynomial regression** to capture non-linear relationships.

 Final Conclusion:

This project highlighted the significance of data preprocessing, feature selection, and model evaluation in machine learning. While multiple models were tested, Linear Regression emerged as the best performer, explaining 64% of the variance in house prices. Feature engineering contributed marginally, reinforcing the need for careful selection of meaningful predictors. Despite Random Forest not surpassing Linear Regression, this experiment provided valuable insights into overfitting and model complexity. Future work will focus on hyperparameter tuning and advanced boosting techniques to improve predictive accuracy. 🚀

