# AP-Moller_AIML


# Sourcing Cost Prediction Model

## Overview
This project develops a predictive model to forecast sourcing costs based on various product and regional characteristics. The model leverages historical data to understand cost drivers and predict future expenses, enhancing budgeting and strategic planning.

## Dataset Description
The dataset consists of historical sourcing data which includes multiple features such as product type, manufacturer, area code, sourcing channel, and the cost associated with sourcing. Each entry corresponds to a unique sourcing operation, with detailed annotations for month and year of sourcing, allowing for time-series analysis.

## Problem Statement
The objective is to accurately predict the sourcing costs for new product sourcing operations. Predictive accuracy is crucial as it directly supports financial planning and operational strategies. The challenge lies in accounting for the complex relationships and varying influences of the features on the sourcing cost.

## Approach
The project is divided into two main phases: Exploratory Data Analysis (EDA) and Model Development for forecasting.

### Exploratory Data Analysis (EDA)
1. **Import Datasets**: Initial data ingestion and preliminary assessment.
2. **Feature Engineering**: Splitting month and year for detailed time-series analysis and future forecasting purposes.
3. **Data Transformation and Encoding**:
   - **One-Hot Encoding**: Applied to categorical variables to fit them into the model.
   - **Area Codes Transformation**: Converted into numerical values to unify and simplify their representation.
4. **Visual Analysis**:
   - **Scatter Plots**: Generated for each feature against the Sourcing Cost to visualize relationships and trends.
   - **Correlation Matrix**: Created to identify and quantify dependencies between features and the target variable.
5. **Outlier Detection**:
   - Initially attempted using quartiles to identify and remove outliers. However, this method excessively reduced the sample size.
   - Adopted a more tailored approach by setting a cutoff threshold at 250 for Sourcing Cost based on detailed range analysis, balancing data integrity and model accuracy.

### Forecasting Models
1. **Model Selection**: Chose the Random Forest Regressor based on its ability to handle the complexity and non-linear relationships within the data. ARIMA was considered but deemed unsuitable due to limited variability in the temporal data available for training.
2. **Model Optimization**:
   - **Initial Random Forest Model**: Used as a baseline for performance.
   - **Hyperparameter Tuning via RandomizedSearchCV**:
     - Conducted with a focus on refining the model parameters using a complete dataset and limited parameter distributions over 20 iterations to validate the approach.
     - Extended to explore more diverse parameter distributions but with a smaller subset of the data (30% sampled) over 30 iterations to enhance performance while managing computational efficiency.
3. **Final Model Evaluation**:
   - Evaluated using RMSE, MAE, and other relevant metrics to confirm the model's predictive accuracy and generalizability.

## Results
The final model achieved significant improvements in predictive accuracy, with a lower RMSE in subsequent iterations of parameter tuning and model refinement. The professional and methodical approach to model tuning and validation ensured robust performance and highlighted the model's applicability to real-world forecasting tasks.

## Conclusion
The project successfully demonstrates the capability to build a predictive model that effectively forecasts sourcing costs based on historical data. The iterative approach to model enhancement and validation provided deep insights into the feature influences and model dynamics, which are critical for deploying the model in a production environment.

---
