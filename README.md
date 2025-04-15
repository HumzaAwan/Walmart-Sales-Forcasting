Introduction
The Walmart Sales Forecasting project aims to predict weekly sales for Walmart stores using historical data on store attributes, departments, and temporal factors. Conducted in a Jupyter Notebook (Walmart_Sales_Forecasting.ipynb), this project leverages machine learning techniques to build and evaluate regression models, providing insights into sales patterns and enabling accurate forecasting. The analysis is designed to support retail decision-making by identifying key predictors of sales and optimizing model performance through rigorous evaluation.

What I Have Done in This Project
In the Walmart_Sales_Forecasting.ipynb project, I performed a comprehensive analysis to predict weekly sales for Walmart stores, focusing on model development and evaluation. The key tasks accomplished include:

Data Preparation:
Loaded a dataset containing sales records for multiple Walmart stores, with features including:
Store: Store identifier (integer).
Dept: Department identifier (integer).
IsHoliday: Binary indicator of holiday weeks (boolean).
Size: Store size (integer).
Week: Week number (integer).
Year: Year of sales (integer).
Split the dataset into features (X) and target (y, weekly sales), then divided it into training (70%, 295,099 records) and test (30%) sets using a random seed of 42 for reproducibility.
Model Building and Hyperparameter Tuning:
Developed and evaluated four regression models to predict weekly sales, using cross-validation and hyperparameter tuning to optimize performance:
Ridge Regression:
Applied GridSearchCV with 7-fold cross-validation, testing alpha values [0.0001, 0.001, 0.01, 0.1, 1, 10, 100, 1000, 10000, 100000].
Scoring used negative mean absolute error to minimize prediction errors.
Lasso Regression:
Used GridSearchCV with 15-fold cross-validation, testing the same alpha range as Ridge.
Focused on feature selection and error minimization.
Decision Tree Regression:
Employed GridSearchCV with 10-fold cross-validation, tuning max_depth from 3 to 29.
Aimed to capture non-linear relationships in the data.
Random Forest Regression:
Applied RandomizedSearchCV with 3-fold cross-validation and 3 iterations, tuning:
n_estimators: [100, 200]
min_samples_split: [2, 5, 10]
min_samples_leaf: [1, 2, 4]
Leveraged ensemble learning for robust predictions.
Model Evaluation:
Predicted sales for both training and test sets using each model’s best parameters.
Evaluated model performance with two metrics:
Root Mean Squared Error (RMSE): Measured prediction error magnitude.
R-Squared (R²): Assessed the proportion of variance explained.
Results for each model:
Ridge Regression:
Train: RMSE = 21,696.19, R² = 0.0844
Test: RMSE = 21,812.00, R² = 0.0845
Lasso Regression:
Train: RMSE = 21,975.47, R² = 0.0607
Test: RMSE = 22,092.15, R² = 0.0609
Decision Tree Regression:
Train: RMSE = 1,998.50, R² = 0.9922
Test: RMSE = 4,889.26, R² = 0.9540
Random Forest Regression:
Train: RMSE = 2,736.12, R² = 0.9854
Test: RMSE = 3,881.37, R² = 0.9710
Identified Random Forest as the best-performing model due to its low test RMSE (3,881.37) and high test R² (0.9710), indicating strong predictive accuracy and generalization.
Conclusion:
Successfully forecasted Walmart weekly sales using the Random Forest model, which outperformed Ridge, Lasso, and Decision Tree models.
Demonstrated the effectiveness of ensemble methods in capturing complex patterns in retail sales data, suitable for practical forecasting applications.
