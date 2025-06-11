# Enfermedades_infecciosas
A project that makes an LSTM to predict the cases of infection  of certain sickness
# Communicable Diseases in Mexico: Analysis and Prediction

This project analyzes data on communicable diseases in Mexico, focusing on respiratory, febrile, and dengue cases. It explores trends, identifies high-risk factors and geographical areas, and implements an LSTM model for time series forecasting of respiratory cases.

## Project Overview

The main goals of this project are:

1.  **Exploratory Data Analysis (EDA):** Understand the distribution of cases by disease type, demographic factors (age, sex, comorbidities), and geographical location (Mexican states).
2.  **Identification of High-Risk Factors:** Analyze the correlation between specific comorbidities (like diabetes, asthma, hypertension, pregnancy) and mortality rates for different disease types.
3.  **Geographical Analysis:** Determine which states have the highest incidence rates for respiratory, febrile, and dengue diseases.
4.  **Seasonal Trend Analysis:** Identify peak and low periods for respiratory and dengue cases nationally.
5.  **Outbreak Characterization:** Analyze characteristics (duration, fatality rate, age distribution, top states) of identified respiratory and dengue outbreak periods.
6.  **Time Series Forecasting:** Build and evaluate an LSTM model to predict future respiratory case counts based on historical data and engineered features.
7.  **Seasonal Clustering:** Use K-Means clustering to identify different seasonal patterns in the respiratory case time series.

## Data

The project utilizes the "enfermedades-contagiosas-mexico-2025-normalizado" dataset from Kaggle Hub. This dataset contains normalized records of communicable disease cases in Mexico up to 2025.

## Key Findings and Analyses

*   **Demographic Distribution:** Boxplots show the distribution of age across different disease types. Count plots illustrate the distribution of demographic and comorbidity factors within respiratory, febrile, and dengue cases.
*   **Geographical Distribution:** Bar plots visualize the number of cases per state for each disease type, highlighting states with the highest burden.
*   **Risk Factor Analysis:** Bar plots compare the percentage of deaths for specific combinations of comorbidities within different disease types (e.g., pregnancy + diabetes, asthma + hypertension).
*   **Temporal Evolution:** Line plots show the monthly evolution of cases by state for respiratory and dengue diseases, revealing geographical and temporal trends.
*   **Seasonal Polarity:** Line plots with marked peaks and valleys identify months with high and low incidence nationally for respiratory and dengue cases, indicating seasonality.
*   **Outbreak Analysis:** A DataFrame summarizes key statistics (duration, total cases, lethality, average age, top states) for identified respiratory and dengue outbreak periods.
*   **Time Series Forecasting (LSTM):** An LSTM model is trained on daily respiratory case data, incorporating features like smoothed case counts and day-of-week indicators. The model's performance is evaluated using MAE and RMSE over multiple runs for robustness. Predictions for future days are generated and visualized alongside historical data.
*   **Seasonal Clustering (K-Means):** K-Means clustering is applied to monthly respiratory case data using month and case count as features to group months into distinct seasonality patterns (e.g., high, medium, low incidence).

## Technical Details

*   **Libraries:** pandas for data manipulation, seaborn and matplotlib for visualization, numpy for numerical operations, scipy.signal for peak finding, sklearn for preprocessing (MinMaxScaler, StandardScaler, KMeans), tensorflow and keras for building the LSTM model.
*   **Environment:** Google Colaboratory notebook for execution.
*   **Methodology:**
    *   Data loading and initial cleaning (datetime conversion, handling missing values).
    *   Descriptive statistics and visualization for EDA.
    *   Filtering and analysis of specific disease types.
    *   Identification of outbreaks using peak/valley detection on time series.
    *   Feature engineering for the time series model (lag features, seasonal components, smoothing).
    *   Data scaling for neural network input.
    *   LSTM model architecture design, training with Early Stopping, and prediction.
    *   Robust evaluation of the LSTM model through multiple runs.
    *   K-Means clustering for identifying seasonal patterns in monthly data.

## How to Run

1.  Open the notebook in Google Colaboratory or Jupyter Notebook.
2.  Ensure you have the necessary libraries installed (`!pip install kagglehub pandas seaborn matplotlib numpy scipy scikit-learn tensorflow`). Note: The notebook includes commands to install specific library versions if needed.
3.  The notebook automatically downloads the dataset using Kaggle Hub.
4.  Run the cells sequentially to perform the analysis, visualization, and model training/prediction.

## Future Work

*   Explore other time series forecasting models (e.g., ARIMA, Prophet) for comparison.
*   Incorporate external factors (weather data, mobility data, vaccination rates) as features for the forecasting model.
*   Perform state-level time series analysis and prediction.
*   Develop interactive dashboards for exploring the data and model results.
*   Further investigate the characteristics and potential drivers of identified outbreaks.
*   Refine feature engineering and model architecture for improved prediction accuracy.
