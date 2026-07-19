California Housing Price Prediction

Project Overview

This project focuses on predicting median house values for census block groups in California using supervised machine learning. The analysis includes comprehensive Exploratory Data Analysis (EDA), outlier treatment, feature engineering, and model evaluation.

The goal is to build a reliable regression model that can estimate housing prices based on demographic and geographic features, and compare the performance of traditional linear models with gradient-boosting techniques.

Dataset

The California Housing Dataset is a classic machine learning dataset containing aggregated housing data from the 1990 U.S. Census. It includes 20,640 samples and 9 variables, one of which is the target.

Feature Description

MedInc: Median household income (in tens of thousands of USD)
HouseAge: Median age of houses in the block group
AveRooms: Average number of rooms per household
AveBedrms: Average number of bedrooms per household
Population: Total population in the block group
AveOccup: Average number of occupants per household
Latitude: Geographic latitude
Longitude: Geographic longitude
Price: Target: Median house value (in hundreds of thousands of USD)

Methodology

1. Exploratory Data Analysis (EDA)
   - Visualized feature distributions using histograms and boxplots.
   - Identified skewed features and extreme outliers.
   - Analyzed geographic price distribution using spatial scatter plots.

2. Data Preprocessing
   - Outlier Clipping: Applied 99th percentile clipping to AveRooms, AveBedrms, AveOccup, and Population to reduce the influence of extreme values.
   - Standardization: Scaled Population using StandardScaler to bring it to a comparable range.
   - Geographic Features: Latitude and longitude were left unscaled to preserve their spatial meaning.

3. Modeling
   Two models were implemented and evaluated:
   - Linear Regression: Served as the baseline model.
   - XGBoost: A powerful gradient-boosting algorithm known for handling non-linear relationships and interactions.

Results

Metric           | Linear Regression | XGBoost | Improvement
R²               | 0.657             | 0.835   | +27.1%
RMSE             | 0.671             | 0.465   | -30.7%
MAE              | 0.493             | 0.313   | -36.5%
MAPE             | 30.11%            | 18.13%  | -39.8%

Interpretation:
- XGBoost explains 83.5% of the variance in median house prices, a significant improvement over linear regression.
- The model's average prediction error is approximately $31,300, which is reasonable given the target range.
- The lower MAPE (18.13%) indicates more reliable predictions across the price spectrum.

Technologies Used

- Python 3.8+
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

Project Structure

california-housing-prediction/
│
├── California-housing.ipynb       # Complete analysis pipeline
├── README.md                      # Project documentation
├── requirements.txt               # Dependencies
├── .gitignore                     # Ignored files
│
└── images/
    ├── histograms.png             # Feature distributions
    ├── price_map.png              # Geographic price visualization
    └── correlation_heatmap.png    # Feature correlation matrix

Getting Started

Prerequisites:
- Python 3.8 or higher

Installation:

1. Clone the repository:
   git clone https://github.com/MehdiAlizadehDev/california-housing-prediction.git
   cd california-housing-prediction

2. Install the required packages:
   pip install -r requirements.txt

3. Launch Jupyter Notebook:
   jupyter notebook California-housing.ipynb

Future Improvements

- Hyperparameter Tuning: Use GridSearchCV or Optuna to optimize XGBoost parameters.
- Feature Engineering: Create distance-based features (e.g., distance to coast, distance to Los Angeles).
- Model Comparison: Test Random Forest and Gradient Boosting for benchmarking.
- Deployment: Build a REST API using Flask or FastAPI for real-time predictions.

License

This project is intended for educational and portfolio purposes. Feel free to use and modify it.

Contact

Your Name
GitHub: https://github.com/MehdiAlizadehDev
If you have any questions or feedback, feel free to reach out.
