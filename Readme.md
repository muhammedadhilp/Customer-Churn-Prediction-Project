# Customer Churn Prediction Project
## Overview
This project focuses on analyzing customer churn for a bank using a dataset containing various customer information. We explore the relationship between customer demographics, account information, and whether they exited the bank or not. We then apply a machine learning model, specifically a Decision Tree Classifier, to predict customer churn.

## Dataset
The dataset used in this project is Churn_Modelling.csv, which contains the following columns:

- RowNumber:Index of the record.
- CustomerId: Unique ID for each customer.
- Surname: Customer's surname.
- CreditScore: Customer's credit score.
- Geography: Country of the customer.
- Gender: Customer's gender.
- Age: Customer's age.
- Tenure: Number of years the customer has been with the bank.
- Balance: Customer's bank balance.
- NumOfProducts: Number of products held by the customer.
- HasCrCard: Whether the customer has a credit card (1 = Yes, 0 = No).
- IsActiveMember: Whether the customer is an active member of the bank (1 = Yes, 0 = No).
- EstimatedSalary: Estimated annual salary of the customer.
- Exited: Whether the customer has exited the bank (1 = Yes, 0 = No).
## Key Statistics
### Customer Demographics:
- Age: 
The average customer age is 38.92 years, with a wide range from 18 to 92.
- Credit Scores:
Customers have credit scores ranging from 350 to 850, with an average score of 650.
- Balance:
Bank balances range from $0 to $250,898, with an average of about $76,485.
- Churn Rate:
Around 20.37% of the customers have exited the bank.
- Product and Service Usage:
Most customers hold between 1 and 2 products with the bank, with few having more than 2 products.
Around 70% of the customers have a credit card.
About 51% of the customers are active members.
## Data Preprocessing
- Irrelevant Columns:
We drop the columns RowNumber, CustomerId, and Surname since they do not contribute to predicting customer churn.
- Handling Categorical Data:
We encode categorical variables, such as Geography and Gender, using LabelEncoder for modeling purposes.
- Data Splitting:
The dataset is split into training (80%) and testing (20%) sets using the train_test_split function from scikit-learn.
- Feature Scaling:
We apply StandardScaler to standardize the feature variables to improve model performance.
## Exploratory Data Analysis (EDA)
### Countplots:
We used Seaborn's countplot to visualize the distribution of customers across features like Geography, NumOfProducts, HasCrCard, and IsActiveMember in relation to churn.

Customers in France are less likely to leave compared to those in Germany and Spain.
Customers with 1 product are more likely to leave compared to those with 2 or more products.
Customers who hold credit cards are more likely to stay with the bank.
### Swarmplots:
Swarmplots provided insights into the relationships between variables and churn. For example, customers aged 40-70 tend to churn more often, regardless of whether they have a credit card.

### Distribution Analysis:
We observed that customer churn increases for those with balances between $100,000 and $150,000. Additionally, customers with credit scores below 400 have a higher likelihood of churning.

### Correlation Matrix:
We visualized the correlation between different variables using a heatmap. Age, Balance, and NumOfProducts showed moderate correlations with churn.

## Outlier Detection
We used boxplots and z-scores to identify outliers, especially in the Age, CreditScore, and NumOfProducts columns. Outliers might indicate significant deviations in customer behavior.
## Model Training
We used a Decision Tree Classifier to predict customer churn. The key steps were:

- Feature Selection:
All features except Exited were used as input variables (X), while Exited was the target variable (y).
- Training:
The model was trained on the training dataset using the scikit-learn DecisionTreeClassifier.
- Testing:
We tested the model on the test dataset and obtained the following results:
- Accuracy:
79.75%
- Classification Report:
Precision, recall, and F1-scores were calculated to evaluate model performance.
- Confusion Matrix:
We plotted the confusion matrix to visualize true positives, false positives, true negatives, and false negatives.
## Visualizations
Countplots: Showed customer distribution and churn patterns across different features.
Swarmplots and Scatterplots: Helped us understand the relationships between age, balance, credit score, and churn.
Heatmaps: Displayed the correlation between features and churn.
Boxplots: Identified outliers in the dataset.
## Conclusion
Age, Balance, and CreditScore play a significant role in predicting customer churn.
Customers with high balances and those aged 40-70 are more likely to exit the bank.
The Decision Tree Classifier provides a reasonably accurate prediction of churn, but further model tuning (e.g., hyperparameter optimization) could improve results.
- Instructions for Running the Code
- Install the necessary Python libraries:

```
pip install pandas numpy matplotlib seaborn scikit-learn.
```
Load the dataset and follow the exploratory data analysis steps to understand the patterns in customer churn.

Preprocess the data by encoding categorical features and scaling the feature variables.

Train and evaluate the Decision Tree model using the provided code.

Visualize the results to gain insights into customer behavior and churn patterns.
