# Turbofan Engine Remaining Useful Life (RUL) Prediction

**Machine Learning Internship Project – UCT / Upskill**

---

## Project Overview

This project focuses on **Predictive Maintenance** by estimating the Remaining Useful Life (RUL) of turbofan engines. The goal is to predict how many more operational cycles an engine can run before failure using sensor data.

We used the NASA C-MAPSS Turbofan Engine Degradation Dataset (FD001 subset) and trained multiple regression models to predict RUL.

---

## Problem Statement

In the aviation and manufacturing industries, unexpected engine failures can lead to high maintenance costs, downtime, and safety risks. 

**Goal:** Build a machine learning model that can accurately predict the Remaining Useful Life (RUL) of a turbofan engine based on sensor readings and operational settings.

---

## Dataset

- **Name:** NASA C-MAPSS Turbofan Engine Degradation Dataset
- **Subset Used:** FD001
- **Description:** Multivariate time series data from a fleet of engines of the same type
- **Features:** Operational settings + 21 sensor measurements
- **Target:** Remaining Useful Life (RUL)

**Files used:**
- `train_FD001.txt`
- `test_FD001.txt`
- `RUL_FD001.txt`

---

## Approach

1. Data Loading and Cleaning
2. RUL calculation for training data
3. Feature selection (removed constant/low-variance sensors)
4. Feature scaling (MinMaxScaler)
5. Model Training using:
   - Random Forest Regressor
   - Gradient Boosting Regressor
   - XGBoost Regressor
6. Evaluation using RMSE, MAE, and R² Score

---

## Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib & Seaborn
- Google Colab

---

## Results

Multiple models were trained and evaluated. The best performing model was selected based on the lowest RMSE.

**Evaluation Metrics:**
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- R² Score

The prediction plot (True RUL vs Predicted RUL) is available in the `results/` folder.

---

## Project Structure

02-Turbofan-RUL-Prediction/  
├── data/  
│   ├── train_FD001.txt  
│   ├── test_FD001.txt  
│   └── RUL_FD001.txt  
├── notebooks/  
│   └── Turbofan_RUL_Prediction.ipynb  
├── models/  
│   └── best_rul_model.pkl  
├── results/  
│   └── rul_prediction_plot.png  
├── report/  
│   └── Project_Report_Turbofan_RUL.md  
└── src/  
│   ├── placeholder.txt  
└── README.md  

---

## How to Run

1. Clone this repository
2. Install required libraries:
   ```bash
   pip install pandas numpy scikit-learn xgboost matplotlib seaborn joblib
3. Open the notebook in notebooks/ folder and run all cells
4. Make sure the data files are present in the data/ folder

---

## Learnings

- Understanding of Remaining Useful Life (RUL) prediction
- Working with multivariate time series sensor data
- Feature engineering and selection for predictive maintenance
- Training and comparing multiple regression models
- Model evaluation using RMSE, MAE, and R²
- Organizing a professional machine learning project for internship submission

---

## Author  
Jnanesh M  
Machine Learning Intern – UCT / Upskill  

---

## License  
This project was developed as part of the Machine Learning Internship at UCT.
