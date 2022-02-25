# Classifying Credit Card Fraud
Mai Tran

# Abstract
According to Atlast VPN, credit card fraud occurences have increased 161% from 2015-2020. Therefore, it is imperative to prevent these occurences and to mitigate related costs. This classification project explored simulated credit card transaction dataset from Kaggle which contain legitimate and fraud transactions from duration of Jan 1 2019 - Dec 31 2020. The best classifier found was a Gradient Boost with Under Sampling method with AUC ROC score of .95. Cost benefit analysis was applied to the model in the event of it failing to catch a fraudulent transaction at 5%. 

# Design
1. Research appropriate metric - AUC ROC score was found most appropriate

2. Data Cleaning - EDA was performed to detect correlation. Correlation matrix was produced with Amount feature yielding the highest correlation. Numeric features were only used for the baseline model. 

3. Baseline model with imbalanced data was produced using Logistic Regression CV with 10,000 sampled data
with balanced class weights. However, average precision-recall score was 0.00, and average ROC_AUC score was 0.54.

4. Model with Imbalance Correction was produced: 1) training data were stratify sampled during Train/Test Split and Cross-Validation with StratifiedKFold. 2) During Cross-Validation, 3 classifiers were compared: Logistic Regression, Random Forest, and Gradient Boost. Gradient Boost was the best performer. 3) Different sampling methods were compared using Gradient Boost as the base model: 1) random oversampling, random undersampling, and SMOTE (Synthetic Minority Oversampling Technique). Undersampling yielded the best performance. 


5. Final Classifier: Gradient Boost with Random Under Sampling was chosen as the best classifier yielding highest AUC score of .95. Final classifier was optimized by tuning its hyperparameters. 


6. Feature with the highest prediction score was mapped for feature importance ranking. Amount was found to be the most important feature. 

# Data
This dataset was obtained from Kaggle on Feb 15th 2022. The dataset is a simulated credit card transaction dataset containing legitimate and fraud transactions from duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants. The dataset was simulated using Sparkov Data Generation | Github tool created by Brandon Harris. The dataset contains over 1 million rows and over 10 feature columns. For modeling, 100,000 rows and 23 features were extracted from original dataset. 

# Algorithms
1. Logistic Regression - Mean AUC score: 0.5
2. Random Forest - Mean AUC score: .91
3. Gradient Boost - Mean AUC score: .95

Sampling Performance:
1. Random Oversampling - Mean AUC score:  .92
2. Random Undersampling - Mean AUC score: .93
3. SMOTE - Mean AUC score: .87

Accordingly, the best classifier is Gradient Boost with Random Undersampling. 

# Tools
- Numpy and Pandas for data manipulation
- Scikit-learn for modeling
- Matplotlib, Seaborn, and SHAP for plotting and visualizations
- Hyperopt for hyperparameter tuning

# Communication
Performance of Logistic Regression, Random Forest, and Gradient Boost using AUC Score as a metric
![classifier_comparison](https://user-images.githubusercontent.com/67651332/155738713-11ae581e-34a9-46c8-9b8a-bf5569faee9a.png)

Performance of Over Sampling, Under Sampling, and SMOTE using AUC Score as a metric
![sampling_comparison2](https://user-images.githubusercontent.com/67651332/155738714-7defb67e-2cd4-4915-8807-bf0ab34a9a1e.png)

Feature Importance Ranking
![features_impt_1](https://user-images.githubusercontent.com/67651332/155738745-66cea4c2-62b6-4f89-8a4a-299045bab681.png)

Feature Importance Ranking (bar graph)
![features_impt_2_bar](https://user-images.githubusercontent.com/67651332/155738747-b0b9a14c-d709-406e-aee7-1e0322cfeda2.png)
