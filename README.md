# Car Prices (Araba Ücretleri)

🎯 Bu egzersizde, yeni bir dataset üzerinde veri hazırlama ve feature selection tekniklerini uygulayacaksınız.

Egzersize başlamak için `jupyter notebook` içinde `Car-Prices.ipynb` dosyasını açın ve talimatları takip edin.

🚀 Sıra sizde!

# 🚗 Car Prices – Feature Selection & Classification
📌 Project Overview

This project focuses on building a machine learning pipeline for predicting car price categories (cheap vs expensive) using a structured dataset. The main goal is to perform data preprocessing, feature engineering, feature selection, and baseline classification modeling.

🎯 Objective
Clean and preprocess raw car dataset
Handle missing values and inconsistent data
Encode categorical variables appropriately
Scale numerical features based on distribution
Perform feature selection using permutation importance
Train a baseline Logistic Regression model
Evaluate model stability using cross-validation and different train-test splits
📂 Dataset
Source: Provided CSV dataset (Car Prices)
Features include:
Engine characteristics
Car dimensions
Engine type
Physical specifications
Target variable:
price → binary classification (cheap, expensive)
⚙️ Workflow
1. Data Cleaning
Removed duplicate rows
Handled missing values using:
Median imputation (numerical features)
Most frequent imputation (categorical features)
Converted inconsistent data types
2. Feature Engineering
Binary Encoding
aspiration → std / turbo → 0 / 1
enginelocation → front / rear → 0 / 1
Ordinal Encoding

cylindernumber mapped manually:

two → 2
three → 3
four → 4
five → 5
six → 6
eight → 8
twelve → 12
One-Hot Encoding
enginetype converted using pd.get_dummies(drop_first=True)
3. Feature Scaling

Different scaling strategies were used based on distribution:

RobustScaler
carwidth
stroke
peakrpm
StandardScaler
curbweight
cylindernumber
4. Target Encoding

price converted to binary:

cheap → 0
expensive → 1
5. Model Training
Model: Logistic Regression
Evaluation: Cross-validation (5-fold)
Metric: Accuracy

Baseline model performance was established using:

cross_val_score(model, X, y, cv=5).mean()
6. Feature Selection
Method: Permutation Importance
Features shuffled to measure impact on performance
Weak features removed iteratively
Final model trained using reduced feature set
📊 Key Findings
Most important features:
curbweight (strongest predictor)
carwidth
Engine-related features had moderate impact
Some features had negligible or zero contribution and were removed
🔁 Model Stability Analysis
Train-test split evaluated with different random_state values (1–10)
Observed variation in test scores
Stratified splitting ensured consistent class distribution
Confirmed importance of cross-validation for reliable evaluation
🧠 Key Learnings
Proper encoding strategy depends on feature type (binary, ordinal, nominal)
Feature scaling must consider distribution and outliers
Permutation importance is effective for feature selection
Single train-test split is not reliable → cross-validation is essential
Data leakage must be avoided by separating preprocessing and modeling correctly
🛠️ Technologies Used
Python
Pandas
NumPy
Scikit-learn
Matplotlib / Seaborn
🚀 Future Improvements
Try tree-based models (Random Forest, XGBoost)
Hyperparameter tuning (GridSearchCV)
Pipeline automation using sklearn Pipeline
Feature interaction engineering
📌 Author

Machine Learning Practice Project – Feature Engineering & Classification
