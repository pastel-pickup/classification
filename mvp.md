# Credit Card Fraud Classifier

# Minimum Viable Product (MVP)
1. During EDA, it was discovered the dataset was highly imbalanced with fraud rate of 0.4%
2. ![class_distribution](https://user-images.githubusercontent.com/67651332/155042757-7f502506-b054-4019-952b-1fa40c9f9d69.png)
3. With 22 features, for baseline model, and using domain knowledge of credit card fraud, the following features were used: 1) amt, 2) category, 3) trans_year, 4) trans_month, 5) trans_day with "is_fraud" as the target feature with binary classes of 1 and 0. 
4. "Category" was examined. There were 14 categories with top 3 fraudulent classes with highest amounts were: "misc_net", "shopping_net", and "shopping_post" with amounts larger than $600 each transaction. "Category" feature was then one-hot encoded to only categorize the top 12 categories as 1 and others as 0. The hot-one encoded 12 features were then added to the baseline model dateframe of 5 features, for a total of 17 features. 
5. F1 Score was chosen as a metric since it is the balance between recall and precision, both of which are important in adjusting depending on the needs of the bank. If the bank had limited human capacity to review false positive cases, then maybe precision might need to be weighted more. 
6. F1 Score went from 0.0 to 0.07 (with class balancing) in Logistic Regression
7. This is Confusion Matrix with Imbalanced Data in Logistic Regression:
8. ![confusion_matrix_imbalanced](https://user-images.githubusercontent.com/67651332/158099528-5c87ac85-144a-4d6f-81c8-ca960861cd1c.png)
9. This is Confusion Matrix with Data Re-balanced using class weights in Logistc Regression:
10. ![confusion_matrix_balanced](https://user-images.githubusercontent.com/67651332/158099625-56364dfa-ffc3-44a2-b81f-5c4c432f53dc.png)
11. GridSearchCV was used to find optimal class weights for maximum F1 score with the following graph of F1 score vs class weights: 
12. ![f1_weights](https://user-images.githubusercontent.com/67651332/158099711-b9295ffe-a101-48e3-9da2-2c58efb5f926.png)

# Next Steps
1. Fine tune GridSearch CV to find optimal class weights for maximum F1 score
2. Adjust the model based on if 1) recall weighs more or 2) precision weighs more or other realisic banking/credit card scenarios
3. Map out precision-recall curves
4. Try other class imbalance correction methods: oversampling, undersampling, and SMOTE
