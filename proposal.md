# Classifying Fraudulent Credit Card Transactions

# Question/Need:
# What is the framing question of your analysis, or the purpose of the model/system you plan to build?
- How to identify and classify whether a credit card transaction is fraudulent or not?

# Who benefits from exploring this question or building this model/system?
- Consumers including credit card users
- Credit card companies
- Cybersecurity professionals

# Data Description:
# What dataset(s) do you plan to use, and how will you obtain the data?
- This dataset was obtained from Kaggle on Feb 15th 2022. The dataset is a simulated credit card transaction dataset containing legitimate and fraud transactions from duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants. The dataset was simulated using Sparkov Data Generation | Github tool created by Brandon Harris. The dataset contains over 1 million rows and over 10 feature columns. 

# What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?
- An individual unit of analysis is a transaction with features such as date-time, credit card number, category of purchase, purchase amount, location of user, location of merchant, first name of user, last name of user, trasaction ID, and whether the transaction is fraudulent or not. 

# If modeling, what will you predict as your target?
- My target will be a class labeled as fraudulent transactions to classify whether a transaction is predicted and classified to be a fraudulent transaction or not.

# Tools:
# How do you intend to meet the tools requirement of the project?
- Use Pandas in Python for data manipulation and EDA
- Matplotlib and Seaborn for data visualization

# Are you planning in advance to need or use additional tools beyond those required?
- might integrate AWS to experiment with cloud computing and cloud storage

# MVP Goal:
# What would a minimum viable product (MVP) look like for this project?
- Finished analyses of KNN, Logistic Regression, and Classification
- Have "fraud" class successfully implemented with with Logistic Regression
