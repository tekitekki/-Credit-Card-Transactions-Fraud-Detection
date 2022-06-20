# Credit-Card-Transactions-Fraud-Detection


## Exploratory Data Analysis and Data Cleaning
The data consists of 10 fields and 96753 records. We only retained the records with transaction type ‘P’(Payment) and imputed missing values for the fields merchant number, merchant zip code and merchant state.

## Feature Engineering and Feature Selection
We engineered features by combining fields such as card number and merchant number with the average/median amount spent in each transaction. We also created days since variables and velocity variables for the combination variables. Among the 343 variables that were engineered, the 30 most relevant features were selected using a random forest wrapper.

## Building Classification Models and Evaluating Performance

We divided the data into training, testing and out of time (OOT) sets, and built four classification models using Logistic Regression, Neural Networks, Boosted Trees and Random Forest. The performance of each model was evaluated using the Fraud Detection Rate in the top 3% of the OOT data.
Determine the optimal score cutoff to maximize savings: We assumed a $2000 savings for every fraudulent transaction that was caught and a $50 loss for every false positive. For our best performing model, we calculated the fraud savings, lost sales and overall savings at each score cutoff, above which the transaction will be flagged. The most profitable score cutoff was determined.
The result of the project was that the best classifier was built using a Random Forest Model, which had an average FDR of 59.7% in the top 3% of the OOT data. We recommend a score cutoff at the top 3% of the OOT population, which will result in yearly savings of over $2.2 million.
