# Project Report

## Turbofan Engine Remaining Useful Life (RUL) Prediction

**Machine Learning Internship Project**  
**Company:** UCT (Upskill)  
**Intern:** Jnanesh M  
**Project Duration:** August 2026

---

## 1. Background of the Project

In modern industries, especially aviation and manufacturing, equipment health monitoring plays a critical role in reducing unexpected failures and maintenance costs. Turbofan engines are complex systems that operate under high stress and varying conditions. Predicting the remaining useful life of such engines before failure can significantly improve safety, reduce downtime, and optimize maintenance schedules.

Predictive maintenance uses sensor data and machine learning models to estimate how long a machine can continue to operate before it fails. The NASA C-MAPSS (Commercial Modular Aero-Propulsion System Simulation) dataset is a widely used benchmark for developing and evaluating Remaining Useful Life (RUL) prediction models.

This project was undertaken as part of the Machine Learning Internship at **UCT (Upskill)** to build a data-driven model that predicts the Remaining Useful Life of turbofan engines using multivariate sensor data.

---

## 2. Problem Statement and Relevance

### Problem Statement
Develop a machine learning model that can accurately predict the Remaining Useful Life (RUL) of a turbofan engine based on its operational settings and sensor measurements.

### Relevance
- Helps in scheduling maintenance before actual failure occurs
- Reduces unexpected downtime and repair costs
- Improves operational safety in aviation and industrial systems
- Supports the growing field of Predictive Maintenance and Industry 4.0
- Highly relevant to real-world industrial applications

The ability to predict RUL is a core requirement in modern predictive maintenance systems used by airlines, manufacturing plants, and energy companies.

---

## 3. Dataset Description

- **Dataset Name:** NASA C-MAPSS Turbofan Engine Degradation Dataset
- **Subset Used:** FD001
- **Description:** The dataset contains multivariate time series data from a fleet of engines of the same type. Each engine starts with different degrees of initial wear and manufacturing variation.
- **Features:**
  - Unit number
  - Time (in cycles)
  - 3 Operational settings
  - 21 Sensor measurements
- **Target:** Remaining Useful Life (RUL)
- **Files Used:**
  - `train_FD001.txt`
  - `test_FD001.txt`
  - `RUL_FD001.txt`

In FD001, the engines operate under a single operating condition and experience a single fault mode (HPC degradation).

---

## 4. Design / Approach

The project followed a standard predictive maintenance pipeline:

1. **Data Loading and Understanding**
   - Loaded training, testing, and true RUL files
   - Explored the structure of the multivariate time series data

2. **RUL Calculation**
   - Calculated Remaining Useful Life for each cycle in the training data
   - Applied RUL clipping at 125 cycles (common practice to focus on the degradation phase)

3. **Feature Engineering & Selection**
   - Removed constant and low-variance sensors that do not contribute useful information
   - Selected the most relevant operational settings and sensor features

4. **Preprocessing**
   - Applied MinMax scaling to normalize the feature values

5. **Model Training**
   - Trained multiple regression models:
     - Random Forest Regressor
     - Gradient Boosting Regressor
     - XGBoost Regressor
   - Compared model performance

6. **Evaluation**
   - Evaluated models using RMSE, MAE, and R² Score
   - Visualized True RUL vs Predicted RUL

---

## 5. Implementation Details

### Tools and Technologies Used
- Programming Language: Python
- Libraries: Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib, Seaborn, Joblib
- Platform: Google Colab

### Key Steps Implemented
- Calculated RUL for the training set
- Dropped uninformative sensors (`op3`, `s1`, `s5`, `s10`, `s16`, `s18`, `s19`)
- Scaled features using `MinMaxScaler`
- Prepared the test set by taking the last recorded cycle of each engine
- Trained and compared three regression models
- Saved the best performing model

### Model Evaluation Metrics
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **R² Score**

---

## 6. Results

Multiple models were trained and evaluated on the FD001 test set. The models were able to learn the degradation patterns from the sensor data and provide reasonable RUL predictions.

### Key Observations
- Tree-based ensemble models performed well on this dataset
- The best model was selected based on the lowest RMSE
- The prediction plot shows a clear correlation between true RUL and predicted RUL
- Performance can be further improved with advanced time-series models (LSTM, Transformer, etc.)

The final model and the True vs Predicted RUL plot are saved in the project repository under the `models/` and `results/` folders respectively.

---

## 7. Learnings

During this project, the following important learnings were gained:

- Understanding of Remaining Useful Life (RUL) prediction in predictive maintenance
- Working with multivariate time series sensor data
- Importance of feature selection and removal of constant sensors
- Practical experience in training and comparing multiple regression models
- Evaluation of regression models using RMSE, MAE, and R²
- Best practices for organizing a professional machine learning project
- Writing a structured technical report for internship submission

This project strengthened practical knowledge of predictive maintenance and industrial machine learning applications.

---

## 8. Conclusion

The Turbofan Engine RUL Prediction project successfully demonstrates the application of machine learning for predictive maintenance. Using the NASA C-MAPSS FD001 dataset, a regression model was developed that can estimate the remaining useful life of turbofan engines based on sensor data.

This project fulfills the requirements of the Machine Learning Internship at **UCT** and provides valuable hands-on experience in building real-world predictive maintenance solutions.

---

## 9. Future Scope

- Implement deep learning models such as LSTM or CNN-LSTM for better sequence modeling
- Experiment with other C-MAPSS subsets (FD002, FD003, FD004)
- Perform hyperparameter tuning for improved performance
- Deploy the model as a real-time prediction API
- Integrate the solution with a dashboard for maintenance planning

---

**Submitted as part of Machine Learning Internship**  
**Company: UCT (Upskill)**  
**Intern: Jnanesh M**
