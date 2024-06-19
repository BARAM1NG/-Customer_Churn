# Customer_Churn
2024-1학기 머신러닝 프로젝트

## Table of Contents
* [Problem Definition](#problem_definition)
* [Data Preprocessing](#data_preprocessing)
* [Modeling](#Modeling)
* [Model Performance Comparison and Interpretation](#Model_Performance_Comparison_and_Interpretation)

## Problem Definition
South Korea's telecommunications industry, known for its advanced technology, faces several challenges, including relatively high costs and complex plans that confuse consumers. The market is dominated by three major companies (SKT, KT, LG U+), making new customer acquisition costly, especially with the rise of budget phone services that attract both new and existing customers. Similarly, the U.S. telecom industry, dominated by AT&T, Verizon, and T-Mobile, is highly saturated with decreasing customer loyalty, necessitating effective marketing strategies to prevent customer churn. This report aims to predict and analyze customer churn using Telco Customer Churn data to propose efficient marketing and customer management strategies.

## Data Preprocessing
The dataset used in this report aims to predict customer behavior and develop targeted retention programs. It contains 7043 customers and 21 features, with no missing values. Initial preprocessing involved converting object-type numerical data and creating a new target variable for churn prediction. Visualization showed even distribution in both numerical and categorical data, highlighting the need for marketing strategies to convert month-to-month contract customers into long-term contracts. Correlation analysis identified `tenure`, `Contract`, `InternetService`, and `OnlineSecurity` as key features influencing churn.

## Modeling
We used various models for churn prediction, including Decision Tree, KNN, Random Forest, SVM, XGBoost, LightGBM, and Neural Network. Each model was tuned using GridSearchCV and 5-fold cross-validation to find the best hyperparameters. The results showed that while all models performed well, XGBoost and LightGBM had the highest performance in terms of F1 Score.
| Model        | F1-Score | Precision | Recall |
|--------------|-----------|--------|----------|
| Decision Tree| 0.56      | 0.6   | 0.52     |
| KNN          | 0.55      | 0.6   | 0.51     |
| Random Forest| 0.56      | 0.62   | 0.51     |
| SVM          | 0.56      | 0.64   | 0.5     |
| **XGBoost**  | **0.61**  | **0.67**| **0.56** |
| **LightGBM** | **0.60**  | **0.66**| **0.56** |
| Neural Net   | 0.57      | 0.65   | 0.53     |

## Model Performance Comparison and Interpretation
To interpret the models, we extracted Feature Importance for Decision Tree, Random Forest, XGBoost, and LightGBM. Decision Tree and Random Forest showed that tenure and Contract_Month-to-month were the most influential features. XGBoost and LightGBM also highlighted Contract_Month-to-month and tenure as critical features.

<img src="https://github.com/BARAM1NG/Customer_Churn/assets/122276734/59b8beb7-ed95-4d69-ab1b-3a1bc6ebf522" alt="feature_importance" width="450"/>
<img src="https://github.com/BARAM1NG/Customer_Churn/assets/122276734/211c3a41-628c-4368-aefd-67a0e0318593" alt="SHAP" width="450"/>

Using SHAP for XGBoost and LightGBM, we found that tenure and Contract_Month-to-month significantly increased churn predictions, while InternetService_Fiber Optic decreased churn predictions, indicating the importance of service duration and bundled services in preventing customer churn.

## Conclusion
The analysis shows that XGBoost and LightGBM models perform better than others, providing two key insights from the Telco Customer Churn data and corresponding marketing strategies.

First, tenure and Contract features significantly impact customer churn. Tenure refers to service duration, and Contract_Month-to-month refers to monthly contracts. To prevent churn among short-term customers, continuous promotions are needed, and contract renewal should be encouraged with additional benefits before expiration. Promoting long-term contracts with added benefits can also reduce churn rates.

Second, InternetService positively affects churn prevention, linked to bundled services like Phone, TV, Wifi, and Internet from the same provider. Enhancing the variety and benefits of bundled services can encourage customers to choose them, reducing churn and increasing satisfaction.

This analysis helps identify high-risk customers early, allowing focused management programs that reduce marketing costs and increase loyal customers, ultimately boosting revenue. Ongoing data analysis and customer management can further enhance service competitiveness and customer satisfaction.
