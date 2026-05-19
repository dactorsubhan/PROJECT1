AI Class Project: Customer Churn Prediction
This is my code for the Introduction to Applied Artificial Intelligence course (8th Semester). The main goal of this project is to use machine learning to predict whether a telecom customer is going to ditch their service (churn) or stick around. 
Week 1: Data Exploration (EDA)
I loaded up the Telco dataset to see what we were working with and made a bunch of charts. A few interesting things I noticed about the customers who leave: 
•	People on month-to-month contracts are way more likely to leave compared to the yearly ones. 
•	If someone has been with the company for less than 6 months, they are a huge flight risk. 
•	Customers using Fiber optic internet actually churn more than the ones on regular DSL. 
Week 2: Baseline Models
This week was all about getting the data ready for the actual math. I cleaned up the missing values and turned all the text categories (like gender, yes/no columns, etc.) into numbers. 
I trained three basic models to see what would happen: Logistic Regression, Decision Tree, and Random Forest. Random Forest ended up doing the best overall. I also played around with creating a few custom features, like multiplying tenure by monthly charges to get TotalRevenue, to see if it would help the model learn better. 
Week 3: Tuning & XGBoost
Learned a hard lesson this week: regular "accuracy" is basically a trap. Since most customers in the dataset don't churn, a lazy model could just guess "stay" every single time and still get a decent accuracy score. 
Because of that, I switched to looking at the F1-score, which gives a way better picture of how well we are actually catching the churners in an imbalanced dataset. I used Grid Search to test out a ton of hyperparameter combinations , and finally swapped the model over to XGBoost since it runs faster and generally performs better for this kind of tabular data. 
How to run this stuff
If you want to pull this repo and run the notebooks yourself, make sure you have the dataset downloaded as customer_data.csv in the same folder. 
You'll also need to install these libraries if you don't have them:
Bash
pip install pandas numpy matplotlib seaborn jupyter scikit-learn xgboost

