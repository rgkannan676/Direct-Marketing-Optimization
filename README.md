# Direct-Marketing-Optimization

## Objective
Maximize revenue from direct marketing campaigns using the provided dummy data.  
**Business Context**: This case study simulates a real-world marketing scenario to optimise resource allocation to maximize revenue.

## Data Description
- Social-Demographic Information: Age, gender, and bank tenure.
- Product Holdings and Volumes: Details on current accounts, savings accounts, mutual funds, overdrafts, credit cards, and consumer loans.
- Financial Transactions: Aggregated inflow/outflow on current accounts and average monthly card turnover over the past three months.
- Sales and Revenue Data: Available for 60% of clients, serving as a training set.

## Constraints
- Contact Limitation: The bank can reach only 15% of clients (approximately 100 individuals).
- Single Offer Per Client: Each client can receive only one marketing offer. For example, a  client might receive an offer for a consumer loan, a new credit card, or an investment in mutual funds based on their profile and financial behaviour.

## Task Breakdown
- Create Analytical Datasets: Prepare train and test datasets using the provided data. 
- Develop Propensity Models: Build three models to estimate the likelihood of purchase for: a. Consumer Loan b. Credit Card and c. Mutual Fund
- Optimize Targeting Strategy: Select clients to target with marketing offers to maximize revenue, adhering to the constraints.

## Approach Summary
The process is comprised of three key steps: 1) Data Processing, 2) Model Training, and 3) Production Inference.
- Data Processing : The data is merged from multiple Excel sheets into a single Pandas DataFrame using the client ID. Missing values in "count" and "revenue" are filled with zeros, and missing values in "Sex" are imputed with the mode and converted to binary. Clients with no transaction data are excluded. High correlation between "Current Account (XX_CA)" features leads to their removal. The "Sales_Revenues" sheet is merged, with 10% reserved for testing. Data is split for classification and regression tasks. StandardScaler() is used for feature standardization, RFE for feature selection, and PCA reduces dimensionality. The processed data is saved for further use.
- Model Training : For this task, I will train six models—three classification models and three regression models. The classification models will determine whether a client should be selected for the campaign for a specific product, while the regression models will predict the potential revenue generated from each client.
- Production Inference : For production inference, all necessary metadata, including PCA components, scalers, selected features, and trained models, will be used. The entire dataset is loaded from an Excel file, and a data processing pipeline handles standardization, feature selection, and PCA. Processed data is passed through prediction pipelines for both classification (to identify campaign targets) and regression (to predict revenue). Only revenue for selected clients is considered, with product categories (CL, CC, MF) added. The top 100 clients by revenue per product are selected for the campaign, and final revenue predictions are made. 

## File Details
- Data Processing: DataProcessing.ipynb  
- Model Training: ModelsTraining.ipynb  
- Production Inference: ProductionInference.ipynb  
- Final Result: 'prediction_result' folder.
- Report: TechnicalReport.pdf
  
