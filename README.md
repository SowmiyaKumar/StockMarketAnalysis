# Financial Market Forecasting

### Impact of U.S. Economic Indicators on the Australian ASX 200

**Unit:** Case Studies in Data Science
**Type:** Individual Project
**Domain:** Financial Analytics · Time Series · Machine Learning · Model Evaluation & Fairness

---

## 📌 Project Overview

This project investigates how **U.S. macroeconomic indicators** influence the **Australian ASX 200 index** and evaluates the effectiveness, robustness, and fairness of machine learning models used for forecasting.

The work is structured as an **end-to-end data science case study**, covering:

* Data integration and feature engineering
* Predictive modelling (regression & classification)
* Cross-validation and learning curve analysis
* Bias detection and mitigation using **IBM AI Fairness 360**

The project demonstrates not only **model accuracy**, but also **methodological rigor**, **generalisation reliability**, and **ethical evaluation**—all critical for real-world deployment.

---

## 🎯 Problem Statement

The study aims to answer the following questions:

* Do U.S. economic indicators such as **GDP, CPI, unemployment, housing index, industrial production, and recession periods** significantly influence ASX 200 prices?
* Which machine learning models are most effective for:

  * Predicting **price magnitude** (regression)?
  * Predicting **directional movement** (classification)?
* How reliable are model evaluations under **cross-validation and varying data sizes**?
* Do the models exhibit **systematic bias**, and can it be mitigated?

---

## 🧠 Machine Learning Approach

### Models Used

* **Linear Regression**
* **Random Forest Regressor**
* **Logistic Regression**
* **Random Forest Classifier**

> Random Forest was intentionally selected to differ from models used in earlier coursework, satisfying the assignment constraint.

---

## 📊 Key Insights

### Regression (Price Forecasting)

* **Random Forest Regressor** significantly outperformed Linear Regression

  * **RMSE ≈ 159**
  * **R² ≈ 0.98**
* Most influential predictors:

  * U.S. **Housing Index**
  * **GDP**
  * **Industrial Production (INDPRO)**
  <img width="508" height="369" alt="image" src="https://github.com/user-attachments/assets/39358e72-cb1c-4b74-803c-2ffface05c01" />


### Classification (Direction Prediction)

* Logistic Regression achieved **high recall** but poor precision
* Overall AUC ≈ 0.5 across classifiers
* Indicates that **directional market movement is inherently complex** and may require advanced models (e.g., XGBoost, LSTM)

### Economic Insight

* ASX 200 stagnation and decline aligned closely with **U.S. recession periods**
* Confirms **global economic spillover effects**
<img width="582" height="342" alt="image" src="https://github.com/user-attachments/assets/fff77a88-7e6b-4724-bc5e-18673d7f25a6" />
<img width="455" height="301" alt="image" src="https://github.com/user-attachments/assets/8f0f1e7f-f15f-4659-ba55-466fe16ec417" />



---

## 📈 Model Evaluation & Generalisation

### Cross-Validation

* K-Fold cross-validation (k = 5 → 100) used to reduce evaluation bias
* Random Forest showed:

  * Slightly higher RMSE under CV (expected)
  * More **realistic generalisation estimates**
* Linear Regression benefited from CV, indicating sensitivity to train-test splits

### Learning Curve Analysis

* Linear Regression showed persistent underfitting and instability
* Random Forest demonstrated:

  * Smooth convergence
  * Reduced train–validation gap
  * Better handling of increasing data volume

---

## ⚖️ Bias & Fairness Evaluation

Bias analysis was conducted using **IBM AI Fairness 360 (AIF360)**.

### Findings

* **Disparate Impact:** 0.3947 (significant bias)
* **Statistical Parity Difference:** −0.4306
* Model disadvantaged individuals from **high unemployment groups**

### Mitigation

* Applied **reweighing technique**
* Post-mitigation:

  * Disparate Impact improved to ~1.0
  * Model outcomes became statistically fair

This highlights the importance of **ethical model assessment beyond accuracy metrics**.

---

## 📂 Repository Structure

```text
.
├── data/
│   ├── raw/                      # Original ASX & US economic datasets
│   └── processed/                # Cleaned and merged datasets
│
├── notebooks/
│   ├── StockMarketAnalysis.ipynb        # Core modelling & insights
│   ├── Model_Performance_Analysis.ipynb # Cross-validation & learning curves
│   └── Bias_Evaluation.ipynb            # Fairness analysis (AIF360)
│
├── reports/
│   └── StockMarketAnalysisReport.pdf    # Full report with plots
│
└── README.md
```

---

## 🛠️ Tools & Technologies

* **Python**
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn
* **IBM AI Fairness 360**
* Jupyter Notebook

---

## 📜 License & Academic Use

This project was completed as part of coursework at **RMIT University**.

* Datasets and specifications are provided for **educational purposes only**
* Code and analysis are shared **for learning, demonstration, and portfolio use**
* Not intended for commercial or production deployment
