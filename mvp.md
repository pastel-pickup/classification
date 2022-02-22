# Credit Card Fraud Classifier

# Minimum Viable Product (MVP)
1. During EDA, it was discovered the dataset was highly imbalanced with fraud rate of 0.4%
2. ![class_distribution](https://user-images.githubusercontent.com/67651332/155042757-7f502506-b054-4019-952b-1fa40c9f9d69.png)
3. Numeric features were extracted and split into train and test sets
4. Features were scaled using StandardScaler
5. Logistic Regression CV with 10 folds was performed and classiciation report was produced
6. Average precision-recall score: 0.00
7. Average ROC_AUC score: 0.54
8. Confusion matrix was produced for the classes
9. ![confusion_matrix](https://user-images.githubusercontent.com/67651332/155043410-dc31c111-4dcb-48e1-a44a-af910bc3167f.png)


<img width="377" alt="logistic_regression_cv" src="https://user-images.githubusercontent.com/67651332/155042815-0e4790c4-cf3c-4096-be5c-b0f10a2eb81c.PNG">


# Next Steps
1. Upsample the data using either Stratified Sampling or SMOTE to get more amplification of minority class signal
2. Rerun the dataset with Logistic Regression CV
