# Credit Card Transactions Fraud Detection

**Data Description**

We are working with actual credit card purchases from a US government organization, covering transactions throughout 2006, from January 1 to December 31st. It provides credit card number and merchant information (description, zip code, etc.), along with a label determining if that particular transaction is fraud or not (target variable). The data consists of 10 fields and 96,753 records. 

**Data Cleaning**

We did data cleaning by excluding an outlier and only keeping records with transaction type ‘P’(Payment). We then imputed missing values for the fields merchant number, merchant zip code and merchant state.

**Feature Engineering and Selection**

We created 10 entities by combining fields such as card number, merchant number and zip code. A total of 804 expert variables were created based on the 10 entities, which include velocity variables, relative velocity variables, amount variables, days since last seen variables, risk variables, and Benford's law variables. Among the 804 variables, the 30 most relevant features were selected using a filter and then a wrapper.

**Modeling**

The OOT (Out-Of-Time) validation dataset is the records of the last two months and the train/test split we used is 0.7/0.3 split on the remaining data. We built 9 types of machine learning models (Logistic Regression, Decision Tree, Random Forest, LightGBM, KNN, Neaural Network, Catboost, GBC and SVM) and tuned hyperparameters to optimze model performance. 

**Result**

Using our best performance LightBGM model, we are able to achieve a Fraud Detection Rate of 90.4% for the training set, 81.5% for the testing set, and 55.5% for the out-of-time validation set at 3% of the population. We choose to capture fraudulent transactions at 3% because the overall saving is relatively high, and if choosing a higher cutoff rate than 3%, the overall incremental savings are low. Under the assumption that \$2,000 gain for every fraud caught and $50 loss for every false positive, the model will help the company save \$ 1M+ annually by capturing potential frauds.
