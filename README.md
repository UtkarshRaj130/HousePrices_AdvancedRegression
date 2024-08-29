# House Prices: Advanced Regression Techniques - Kaggle Competition

[This repository](https://github.com/UtkarshRaj130/HousePrices_AdvancedRegression) contains the solution to the Kaggle competition "House Prices: Advanced Regression Techniques." The goal of this competition is to predict the final sale price of homes based on various features.

## Solution Overview

The solution is implemented in the Jupyter Notebook `Final_Solution.ipynb`. The approach used includes data preprocessing, feature selection, and model training with a stacking ensemble of XGBoost, LightGBM, and CatBoost regressors. Ridge regression is used as the final estimator.

### Steps Followed:

1. **Data Import:**
   - The `train.csv` and `test.csv` files are imported.
   - The original test IDs are stored for reference.

2. **Data Concatenation:**
   - The training and test datasets are concatenated.
   - A new column `Source` is created to distinguish between train and test data.

3. **Handling Missing Values:**
   - Null values are checked and analyzed.
   - Numeric columns with missing values are filled using the median.
   - Categorical columns with missing values are filled using the mode.
   - Features with more than 500 null values are dropped.

4. **One-Hot Encoding:**
   - One-hot encoding is applied to categorical variables.

5. **Data Splitting:**
   - The combined data is split back into train and test sets.
   - The training data is further split into training and validation sets.

6. **Model Selection:**
   - Base models used:
     - XGBoost Regressor
     - LightGBM Regressor
     - CatBoost Regressor
   - Stacking Regressor is used as the final model with Ridge as the final estimator.

7. **Model Training and Evaluation:**
   - The stacking model is trained on the training data.
   - Predictions are made on the validation set.
   - Evaluation metrics:
     - **Logarithmic RMSE:** 0.1457
     - **R² Score:** 0.8862

8. **Test Set Prediction:**
   - The model is re-trained on the entire training dataset and used to predict the test set.
   - The predictions are saved in `test_predictions.csv`.

### Kaggle Competition

This solution was submitted to the Kaggle competition "House Prices: Advanced Regression Techniques." The submission resulted in a score of **0.13327** on the public leaderboard.

For more details on the competition, visit the [Kaggle competition page](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview).

### Repository Structure

- `Final_Solution.ipynb`: The main Jupyter Notebook containing the solution.
- `test_predictions.csv`: The file containing the predicted house prices for the test set
