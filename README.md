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
