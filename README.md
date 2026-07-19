# 🏠 California Housing Price Prediction

[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/jupyter-notebook-orange.svg)](https://jupyter.org/)
[![XGBoost](https://img.shields.io/badge/xgboost-1.5%2B-green.svg)](https://xgboost.readthedocs.io/)

## 📌 Project Overview

This project focuses on predicting median house values for census block groups in California using supervised machine learning. The analysis includes comprehensive **Exploratory Data Analysis (EDA)**, **outlier treatment**, **feature engineering**, and **model evaluation**.

The goal is to build a reliable regression model that can estimate housing prices based on demographic and geographic features, and compare the performance of traditional linear models with gradient-boosting techniques.

---

## 📊 Dataset

The **California Housing Dataset** is a classic machine learning dataset containing aggregated housing data from the 1990 U.S. Census. It includes **20,640 samples** and **9 variables**, one of which is the target.

### Feature Description

| Feature       | Type      | Description |
| :------------ | :-------- | :---------- |
| `MedInc`      | Continuous | Median household income (in tens of thousands of USD) |
| `HouseAge`    | Continuous | Median age of houses in the block group |
| `AveRooms`    | Continuous | Average number of rooms per household |
| `AveBedrms`   | Continuous | Average number of bedrooms per household |
| `Population`  | Integer    | Total population in the block group |
| `AveOccup`    | Continuous | Average number of occupants per household |
| `Latitude`    | Continuous | Geographic latitude |
| `Longitude`   | Continuous | Geographic longitude |
| **`Price`**   | Continuous | **Target:** Median house value (in hundreds of thousands of USD) |

---

## 🧠 Methodology

### 1. Exploratory Data Analysis (EDA)
- Visualized feature distributions using histograms and boxplots.
- Identified skewed features and extreme outliers.
- Analyzed geographic price distribution using spatial scatter plots.

### 2. Data Preprocessing
- **Outlier Clipping**: Applied 99th percentile clipping to `AveRooms`, `AveBedrms`, `AveOccup`, and `Population` to reduce the influence of extreme values.
- **Standardization**: Scaled `Population` using `StandardScaler` to bring it to a comparable range.
- **Geographic Features**: Latitude and longitude were left unscaled to preserve their spatial meaning.

### 3. Modeling
Two models were implemented and evaluated:

- **Linear Regression**: Served as the baseline model.
- **XGBoost**: A powerful gradient-boosting algorithm known for handling non-linear relationships and interactions.

---

## 📈 Results

| Metric       | Linear Regression | XGBoost   | Improvement |
| :----------- | :---------------: | :-------: | :---------: |
| **R²**       | 0.657             | **0.835** | **+27.1%**  |
| **RMSE**     | 0.671             | **0.465** | **-30.7%**  |
| **MAE**      | 0.493             | **0.313** | **-36.5%**  |
| **MAPE**     | 30.11%            | **18.13%**| **-39.8%**  |

### Interpretation
- XGBoost explains **83.5%** of the variance in median house prices, a significant improvement over linear regression.
- The model’s average prediction error is approximately **$31,300**, which is reasonable given the target range.
- The lower MAPE (18.13%) indicates more reliable predictions across the price spectrum.

---

## 🛠️ Technologies Used

- **Python 3.8+**
- **Pandas**, **NumPy** – Data manipulation
- **Matplotlib**, **Seaborn** – Data visualization
- **Scikit-learn** – Preprocessing and Linear Regression
- **XGBoost** – Gradient boosting model
- **Jupyter Notebook** – Interactive development environment

---

## 📁 Project Structure
