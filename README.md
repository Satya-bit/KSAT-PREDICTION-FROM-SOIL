# KSAT-PREDICTION-FROM-SOIL(The project is still in progress.)

![image](https://github.com/user-attachments/assets/0113f145-a0cd-434e-a62d-0f793868039f)

This project aims on predicting KSAT (Saturated Hydraulic conductivity) from USKSAT soil data which is responsible for how fast the water moves in the depth of soil. 

The model achieved RMSE score of 6.74 cm/hr on 10 fold cross validation

# Steps

1) Cleaned and preprocessed the data.

2) Removed outliers using IQR andfilled the misisng values using Iterative imputer from sklearn library.

![image](https://github.com/user-attachments/assets/97e5249b-2857-4893-81e0-3a9ad4d1dc6a)

3) Stacking ensemble (LIGHTGBM, CATBOOST AND XGBOOST) as base estimator and ElasticNet as final estimator. Used Optuna for hyperparameter training.

 ![image](https://github.com/user-attachments/assets/d07b08ca-5cce-45bd-9dda-52554b861d33)

 ![image](https://github.com/user-attachments/assets/6a5eaeac-7d34-4313-b43f-eeda6175ec7a)

4) Future plans- Modularise the entire code in pipelines from data ingestion to validation, Streamlit for frontend, Grafana for monitoring shift and GCP for deployment 

![image](https://github.com/user-attachments/assets/b62fac5f-1da8-4aa6-988e-66decdc2441f)

![image](https://github.com/user-attachments/assets/59461acb-0eb4-4047-8a22-0556b53874f8)

![image](https://github.com/user-attachments/assets/7d8ccc8c-865e-4478-83e1-d534d497e682)
