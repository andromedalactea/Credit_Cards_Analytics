# Credit Card Dataset Analysis

This repository contains the analysis of a credit card dataset available on [Kaggle](https://www.kaggle.com/datasets/arjunbhasin2013/ccdata). The analysis focuses on customer segmentation based on two key factors: purchases and payments, credit limit and account balance, as well as cash advances. The relevant project information and findings are detailed below.

## About the Dataset

This case requires the development of a customer segmentation to define a marketing strategy. The sample dataset summarizes the behavior of approximately 9000 active credit card holders over the last 6 months. The file contains client-level data with 18 behavioral variables.

Below is the data dictionary of the credit card dataset:

- CUST_ID: Credit card holder identification (Categorical)
- BALANCE: Remaining account balance for purchases
- BALANCE_FREQUENCY: Frequency of balance updates, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated)
- PURCHASES: Amount of purchases made from the account
- ONEOFF_PURCHASES: Maximum purchase amount made in a single transaction
- INSTALLMENTS_PURCHASES: Amount of purchase made in installments
- CASH_ADVANCE: Cash advanced by the user
- PURCHASES_FREQUENCY: Frequency of making purchases, score between 0 and 1 (1 = frequent purchases, 0 = infrequent purchases)
- ONEOFF_PURCHASES_FREQUENCY: Frequency of one-off purchases (1 = frequent, 0 = infrequent)
- PURCHASES_INSTALLMENTS_FREQUENCY: Frequency of installment purchases (1 = frequent, 0 = infrequent)
- CASH_ADVANCE_FREQUENCY: Frequency of cash advances
- CASH_ADVANCE_TRX: Number of transactions made with "cash advance"
- PURCHASES_TRX: Number of purchase transactions made
- CREDIT_LIMIT: Credit card limit for the user
- PAYMENTS: Amount of payment made by the user
- MINIMUM_PAYMENTS: Minimum amount of payments made by the user
- PRCFULL_PAYMENT: Percentage of total payment made by the user
- TENURE: Duration of credit card service for the user

## Analysis Methodology

The analysis began with a minor data cleanup and evaluated the correlation between each of the variables. Two segmentations were carried out using the K-means method:

1. Segmentation based on purchases, payments, credit limit, and account balance.
2. Segmentation based on cash advances, balance, credit limit, and payments.

The effectiveness of the segmentation was then verified through variable reduction. Finally, a dashboard was created to present the graphs and key conclusions.

# Highlighted Results

## Correlation Conclusions

![Dataframe Correlations](docs_for_dasboard/Correlation.png)

1. The 'PURCHASES' variable shows a high correlation with 'ONEOFF_PURCHASES' (0.917), 'INSTALLMENTS_PURCHASES' (0.680), 'PURCHASES_TRX' (0.690), and 'PAYMENTS' (0.603). This suggests that customers who make larger purchases (ONEOFF_PURCHASES) tend to make more purchases in general (PURCHASES) and in installments (INSTALLMENTS_PURCHASES). There is also a positive relationship with payments made (PAYMENTS), indicating that customers who make more purchases also tend to make larger payments.

2. The 'CASH_ADVANCE' variable shows a significant correlation with 'CASH_ADVANCE_FREQUENCY' (0.629) and 'CASH_ADVANCE_TRX' (0.656). This suggests that customers who take more cash advances (CASH_ADVANCE) also tend to do so more frequently (CASH_ADVANCE_FREQUENCY) and in a greater number of transactions (CASH_ADVANCE_TRX).

## Segmentation Conclusions

The insights gained from the analysis are as follows:

![Customer Segmentation by Purchases and Balance](docs_for_dasboard/Segmentation_for_clients_according_to_balance_purchases_and_maximum_credit.png)

- Focus on high-value customers: Prioritize customers with higher balances, purchases, and credit limits. These customers are key to retention and loyalty strategies. Additionally, segmentation number 2 stands out for its high purchases and payments, although they are not numerous and do not have the highest balances, they also require special attention.

- Capturing potential new customers (Growth Opportunities): Segmentation number 0 represents the largest number of customers in the dataset, indicating a great potential for attracting new customers. Improving their balance is key to classifying them into higher segmentations. It is important to monitor and analyze their behavior as they may change their purchase patterns and loyalty.

![Segmentation by Cash Advances](docs_for_dasboard/Segmentation_by_cash_advances.png)

- Reducing cash payments: Segmentations 0 and 3 present a high percentage of cash payments, indicating the need to implement strategies to reduce cash usage and promote credit card payments. Attractive incentive programs and exclusive programs that encourage the adoption of this payment modality are suggested.

## References

- AI Model: OpenAI's GPT-3.5

This AI model, developed by OpenAI, provides advanced support for various applications, including data analysis, text generation, and natural language processing.

Reference: https://openai.com/

- HAINES CITY Credit Card - PCA - KElbow - KMeans

This Kaggle project uses PCA (Principal Component Analysis), KElbow, and KMeans techniques for credit card data analysis in Haines City. It provides valuable insights into customer segmentation and behavior patterns in credit card data.

Reference: https://www.kaggle.com/code/hainescity/credit-card-pca-kelbow-kmeans
