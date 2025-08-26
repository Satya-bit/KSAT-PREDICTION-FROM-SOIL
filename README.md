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

2) Removed outliers using IQR andfilled the misisng values using Iterative imputer from sklearn library. Used standard scaler.

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

Cross-Validation RMSE: 6.8680 cm/hr

Test RMSE: 6.2903 cm/hr

Mean R² for stacked model (10-fold CV): 0.9050

Plots show good alignment between predicted and actual values, with most residuals clustered around zero.

<img width="850" height="547" alt="image" src="https://github.com/user-attachments/assets/e755e03d-7b00-4091-b866-b0a4ba1e8c41" />

1. **Regression Line: Actual vs Predicted**

    - **Positive**: The scatter plot with the regression line demonstrates a strong alignment between the actual and predicted values, indicating that the model captures the underlying patterns in the data effectively.

   - **Negative**: Some points deviate significantly from the regression line, suggesting that the model may struggle with certain data points or outliers.

<img width="853" height="547" alt="image" src="https://github.com/user-attachments/assets/44e7cdeb-571b-4ad9-a6a4-dff3eb0e6e69" />

2. **Residual Plot**

   - **Positive**: The residual plot shows a random scatter of residuals around the zero line, which is a good indication of no systematic errors in the model. This highlights the robustness of the model in handling the data.

   - **Negative**: There may be slight clustering or patterns in certain areas, which could indicate potential issues like heteroscedasticity or areas where the model's predictions could be improved.

<img width="859" height="547" alt="image" src="https://github.com/user-attachments/assets/9a28b21e-4bf6-442a-bcb8-43c0253e71ab" />

3. **Distribution of Residuals**

    - **Positive**: The histogram of residuals reveals a distribution centered around zero, indicating that the model's errors are unbiased. The roughly normal distribution suggests that the model's assumptions about the data are valid.

   - **Negative**: There may be slight skewness or heavy tails in the distribution, which could indicate that the model is not fully capturing certain aspects of the data or that there are outliers affecting the results.

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

Applying log-transform on target variable to stabilize variance.

Trying alternative meta-learners (Ridge, Gradient Boosting) for stacking.

Explore robust losses (Huber, MAE, Tweedie) to handle outliers.

Adding modular approach and converting to a full stack application 
