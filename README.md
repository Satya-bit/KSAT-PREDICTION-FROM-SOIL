**KSAT-PREDICTION-FROM-SOIL**

![image](https://github.com/user-attachments/assets/0113f145-a0cd-434e-a62d-0f793868039f)

This project aims on predicting KSAT (Saturated Hydraulic conductivity) from USKSAT soil data which is responsible for how fast the water moves in the depth of soil. 

The model achieved RMSE score of 6.74 cm/hr on 10 fold cross validation

**Steps**
1) Data Preprocessing

Cleaned and prepared the dataset for modeling.
Scaled/normalized features where necessary to ensure smooth optimization.
Selected features
Handled missing values and ensured categorical/numerical features were properly encoded.

2) Removed outliers using IQR andfilled the misisng values using Iterative imputer from sklearn library.

![image](https://github.com/user-attachments/assets/97e5249b-2857-4893-81e0-3a9ad4d1dc6a)

3) Stacking ensemble (LIGHTGBM, CATBOOST AND XGBOOST) as base estimator and ElasticNet as final estimator. Used Optuna for hyperparameter training.

 ![image](https://github.com/user-attachments/assets/d07b08ca-5cce-45bd-9dda-52554b861d33)

 ![image](https://github.com/user-attachments/assets/6a5eaeac-7d34-4313-b43f-eeda6175ec7a)

4. Model Training & Evaluation

Performed cross-validation (10-fold) to estimate generalization performance.

Evaluated the model using RMSE (Root Mean Squared Error) as the main metric.

Compared ensemble results against individual base models and baselines.

5. Residual Analysis

Plotted residuals vs fitted values to check heteroscedasticity.

Analyzed distribution of residuals to assess normality and detect outliers.

Plotted actual vs predicted values to visualize fit quality.

6. Insights

The ensemble model significantly reduced error compared to individual learners.

Most predictions were close to actual values, though variance increased for higher target values.

Residual analysis revealed a strong peak around zero but with some heavy tails (outliers).

**📊 Results**

Cross-Validation RMSE: 6.7347 cm/hr

Test RMSE: (Add final test RMSE here)

Plots show good alignment between predicted and actual values, with most residuals clustered around zero.

**🛠️ Tech Stack**

Python

scikit-learn (StackingRegressor, ElasticNet, pipelines)

XGBoost

LightGBM

CatBoost

Optuna (hyperparameter tuning)

Matplotlib/Seaborn (visualizations)

NumPy/Pandas (data processing)

**🚀 Future Improvements**

Apply log-transform on target variable to stabilize variance.

Try alternative meta-learners (Ridge, Gradient Boosting) for stacking.

Explore robust losses (Huber, MAE, Tweedie) to handle outliers.
