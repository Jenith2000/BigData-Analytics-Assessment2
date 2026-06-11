# Big Data Analytics — Assessment 2

Course: GDDA709 / BBIM709 : Big Data Analytics  
Institution: New Zealand Skills and Education College (NZSE)

What is this project about?

This is my Assessment 2 portfolio for the Big Data Analytics course. 
For this project I used a banking transactions dataset from India 
that has 550,000 rows of real transaction data. I used Databricks 
to store, analyse, and build machine learning models on this data.

The main things I tried to find out were:
- Which states in India have the most fraud?
- Which payment channels do people use the most?
- Can a machine learning model detect if a transaction is fraud?
- visualizing the dataset by state, channel, monthly transaction and by monthly fraud

About the Dataset

The dataset I used is called the Indian Banking Transactions dataset. 
It has 550,000 transactions and 20 columns. 
Some of the important columns are the transaction amount, the state 
where it happened, the channel used (like Mobile App or ATM), 
the customer credit score, and whether the transaction was fraud or not.

The file is uploaded here as a zip file. Just extract it to get 
the original CSV file.

Files in this repository

- Assessment2_BigData.ipynb : This is my main Databricks notebook. 
  It has all my code and the output results. You can click on it 
  and see everything directly in GitHub without needing any software.

- indian_banking_transactions.zip : This is the dataset I used. 
  Extract it to get the CSV file.

- README.md : This file that you are reading right now.

What I did in each task

Task 1 : Setting up the data pipeline

First I uploaded the CSV file to Databricks. Then I cleaned the 
data by fixing the column types because some number columns were 
stored as text. After cleaning I saved everything into Delta Lake 
which is a faster storage format. This whole process is called 
an ETL pipeline — Extract, Transform, and Load.

Task 2 : MapReduce Analysis

I ran three MapReduce jobs using PySpark to analyse the data. 
The first one looked at fraud by state and I found that Maharashtra 
had the most fraud cases (885 cases). The second one looked at which 
channel people use most and Mobile App was the highest with over 
200,000 transactions. The third one was a time series analysis 
showing monthly transaction trends from 2019 to 2020.

Task 3 : Machine Learning

I built two models. The first one was a Random Forest model to 
classify whether a transaction is fraud or not. It got 99.11% 
accuracy. The second one was a Linear Regression model to predict 
the transaction amount, which got an R2 score of 1.0. I also 
made charts to show the feature importance and how close the 
predictions were to the actual values.

Task 4 : Discussion and Conclusion

In this task I wrote about what I found from all the analysis. 
The most interesting thing I found was that transaction amount 
is the strongest signal for detecting fraud. I also discussed 
why the AUC-ROC score was low even though accuracy was high - 
this is because fraud cases are very rare in the dataset (less 
than 1%) which causes class imbalance.

Results Summary

For fraud detection the Random Forest model got 99.11% accuracy 
and an F1 score of 0.9860. For transaction amount prediction 
the Linear Regression model got an RMSE of 0.29 and R2 of 1.0.

The top feature for detecting fraud was transaction_amount 
with an importance score of 0.49, which means the amount of 
money involved in a transaction is the biggest clue for 
whether it is fraud or not.

How to view the notebook

Just click on Assessment2_BigData.ipynb at the top of this page. 
GitHub will show you all the code and outputs including the charts. 
You do not need to install anything.

If you want to run the code yourself you will need a free Databricks 
account from https://community.cloud.databricks.com. Upload the 
dataset, import the notebook, and run the cells from top to bottom.

References

- Databricks Docs: https://docs.databricks.com  
- Apache Spark MLlib: https://spark.apache.org/docs/latest/ml-guide.html  
- Delta Lake: https://delta.io
