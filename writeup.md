# Classifying Credit Card Fraudulent Transactions
Mai Tran

# Abstract
According to Atlas VPN, credit card fraud occurences have increased 161% from 2015-2020. Therefore, it is imperative to prevent these occurences and to mitigate costs. This classification project explored simulated credit card transaction dataset from Kaggle which contains legitimate and fraud transactions from duration of Jan 1 2019 - Dec 31 2020. The best classifier found was a Logistic Regression with F1 Score of .48 with class weight adjustment and hyperparameter tuning. F1 Score was chosen as an evaluation metric to account for both high recall and high precision.

# Design
1. Collect data - said dataset from Kaggle was downloaded with over 1 million transaction rows, 21 features, and binary target class "is_fraud" being 1 (fraud) or 0 (valid). The features included: "trans_date_trans_time", "cc_num", "merchant", "category", "amt", "first", "last", "gender", "street", "city", "state", "zip", "lat", "long", "city_pop", "job", "dob", "trans_num", "unix_time", "merch_lat", "merch_long". 

2. Research appropriate evaluation metric - since F1 score = (2) * [(precision * recall)/(precision + recall)], which is a harmonic mean of both precision and recall, therefore, it would be desirable to select a F1 score to be an appropriate metric for this particular problem because it is critical to not compromise either recall or precision for the other. Since this problem pertains to vital financial assets, we cannot risk either having too many non-fraud transactions that were fraud (false negatives) or too many legitimate transactions that were falsely flagged as fraud (false positives). In the first case, both of the financial institution and the cardmember would lose money. In the second case, it would also cost the financial insitution money to audit these falsely flagged fraud charges since the audit would require more manpower and staffing. For the best interests of the financial institution, we would like to mitigate the occurences of both cases as much as possible with both high recall and high precision, consequently, a high F1 score. 

2. Data Cleaning - EDA was performed to detect correlation. Correlation matrix was produced with "amt" feature yielding the highest correlation. "Amt" feature was explored for different spending categories since there were only 14 spending categories. These categories were further 1-hot encoded or engineered as additional features to the model. The top 5 common fraud categories were: "shopping_net", "shopping_pos", "grocery_pos", "misc_net", and "gas_transport". The top 3 common fraud categories that were higher than $550 per transaction were: "shopping_net", "shopping_pos", and "misc_net". The two graphs below show these common fraud categories and their occurences. 

![top_5_fraud_cats_2](https://user-images.githubusercontent.com/67651332/159604094-0b62b991-2621-4649-970e-a070e4c0d57e.png)

![top_3_fraud_cats_highest_2](https://user-images.githubusercontent.com/67651332/159604172-2fc947d2-a4ee-4c48-9468-9664522a3701.png)

3. Baseline Model - Logistic Regression. Logistic regression was used as a baseline model with incremental tuning of class weights and hyperparameters to mitigate inherent class imbalance of the dataset. Stratified sampling with cross-validation Kfolds was used to maintain data consistency during sampling from original dataset to sample dataset. F1 score increased from 0.0 to 0.48, with 0.48 being the best F1 score of all. 

4. Logistic Regresison was compared with 4 other models such as KNN, Gaussian Naive Bayes, Random Forest, and XGBoost with Logistic Regression being the best performer. See graph below. 

5. Logistic Regression was further explored with different resampling techniques such as over-sampling, under-sampling, and SMOTE (Synthetic Minority Oversampling Technique). SMOTE yielded the highest F1 score of 0.0921. 

# Data
This dataset was obtained from Kaggle on Feb 15th 2022. The dataset is a simulated credit card transaction dataset containing legitimate and fraud transactions from duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants. The dataset was simulated using Sparkov Data Generation | Github tool created by Brandon Harris. The dataset contains over 1 million rows and over 10 feature columns. For modeling, 10,000 rows and 21 features were extracted from original dataset. 

# Algorithms
1. Logistic Regression - tuned with stratified sampling, class weight balancing, and hyperparameters. For optimal class weights and hyperparameters, both RandomizedGridSearchCV and GridSearchCV were used to search for optimal parameters. Probability decision threshold was experimented and observed. Features were scaled using StandardScaler(). Consequently, the best F1 score yielded by the model was 0.48. 

<img width="528" alt="log_reg_tuning" src="https://user-images.githubusercontent.com/67651332/159618392-fa4d1677-77e5-4811-921c-000a35f4c26b.PNG">



2. K-Nearest Neighbors (KNN) - the best K neighbor was searched by GridSearchCV and it was found to be only 1. This was the only paramater that was experimented with in KNN. The model yielded 0.07. 


3. Gaussian Naive Bayes - this model was the second best performer compared to Logistic Regression with not hyperparameter tuning and straight-out-of-the-box. The model yielded 0.42. 

4. Random Forest - this model was performing also straight-out-of-the-box, yielding F1 score of .12. 

5. XGBoost - this model was performing also straight-out-of-the-box, yielding F1 score of .24. 

# Tools
- Numpy and Pandas for data manipulation
- Scikit-learn for modeling
- Matplotlib and Seaborn for plotting and visualizations

# Communication
<img width="1500" alt="model_performance_edited" src="https://user-images.githubusercontent.com/67651332/159605374-41781578-d4ba-46aa-b896-be1953d57d6b.png">
