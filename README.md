# AnalyticsVidyaHackathon

## DataSet Description
Credit Card Lead Prediction
Happy Customer Bank is a mid-sized private bank that deals in all kinds of banking products, like Savings accounts, Current accounts, investment products, credit products, among other offerings.
The bank also cross-sells products to its existing customers and to do so they use different kinds of communication like telecasting, e-mails, recommendations on net banking, mobile banking, etc.
In this case, the Happy Customer Bank wants to cross sell its credit cards to its existing customers. The bank has identified a set of customers that are eligible for taking these credit cards.
Now, the bank is looking for your help in identifying customers that could show higher intent towards a recommended credit card,in short in machine learning lingo
this is a supervised problem and we have to predict the `Is_Lead` column,based on the other features,our target column is `Is_Lead`,here is the description of the dataset

| Feature        | TYPE   |
| :------------- | :----------: | 
|  ID | Categorical   | 
| Gender   | Categorical |
|  Age | Numeric   | 
| REGION   | Categorical |
|  Occupation | Categorical   | 
| Channel   | Categorical |
|  Vintage | Numeric   | 
| Credit_Product   | Categorical |
|  Active_Account | Numeric   | 
| Is_Active   | Categorical |
| Is_Lead   | Categorical |



This dataset aims to solve the problem of finding the customer who would like to take
interest in taking the credit. The data contains the details of customers who all are eligible
for taking credit cards.

## INITIAL ATTEMPT 

<p align = "center">
   <img src="https://github.com/mv1249/AnalyticsVidyaHackathon/blob/main/images/1.PNG">
</p>

This was my first Approach in Solving the Problem, after visualising the dataset using EDA
and other transformations, the first approach which clicked in my head is to use Ensemble
Techniques and then If that did not work the use Neural Network and if that did not give
me the Required solution then use a combination of both, This Approach after all the Preprocessing and EDA gave me a result of 85.4% ROCAUC on Submission, viz I had used
AUTO VML and Randomized Search CV for getting the best parameters for LIGHT GBM and
Neural Network, Here is the final Approach which Worked for me.

## FINAL ATTEMPT

<p align = "center">
   <img src="https://github.com/mv1249/AnalyticsVidyaHackathon/blob/main/images/2.PNG">
</p>

In the previous Attempt i.e. where my model was a combination of Neural Network and
LightGBM, I got a descent score, but then I started exploring LightGBM more ,I used
different kinds of hyperparameter techniques to get the best Parameters like Randomized
Search CV, Bayesian Optimization and all, after finding the best parameters I used
Stratified KFOLD CROSS VALIDATION on my model and tested on the testing dataset, it
gave me a descent score of 87.1% which was more than the previous one.

## Approach For the Problem

My initial approach for the problem was simple, First I build the baseline model with
logistic regression and submitted it. After then I started exploring the ensemble
techniques like LightGBM, Random Forest and many more, After that I started exploring
models and checked my score for the validation set. After giving a dry run for these
models, I checked out for possible transformations which I can make in my data, like can I
make a transformation such that I get the Data in Gaussian Distribution and then try out
Neural Network and other techniques, so I explored on EDA part more and I found that
the Avg_balance column was left skewed and then I applied box-cox transformation to
make it centrally-skewed, then after came the categorical features, first I used get
dummies method, which did not give a good score ,then I moved on with mean encoding
which gave a descent score not that great as well, then I used Label Encoder on all
columns except for the Region Column ,on Region Col I used mean encoding, After all
Encodings I decided to check out for Outliers, I also did the outlier removal also but that
did not work and model performance decreased then I realized sometimes in the finance
sector domain outliers helps us to capture the underlying patterns in the data which rarely
occurs. I applied 10 Fold Cross validation to train all my models and reached to final
model.


## Feature Engineering Ideas

I tried many variants here, first I started of with categorical features, I noticed that there
is one feature which had Null values, I fixed it by filling in with some Random Value, like
‘DK’, then I used the Dummies method first and checked with all my ensemble and Neural
Nets, It did not give that good score, then I switched on to Label Encoding except for the
Region Col where I applied Mean Encoding as it’s count for more, after then I had a look at
the distributions, I noticed few transformations may help us, so I made few Quantile and
Log, Box-Cox Transformations on the data, and noticed that there are few outliers, I
removed the outliers and noticed that this dropped my performance, outliers may help
sometimes, so I filled those outliers with the most frequent value of that col, then after I
moved on for Scaling and Transforming the Data


## Results

FINAL ROC AUC : 87.1%

PUBLIC RANK :  540



### Tools Used
 
 <code><img height="30" src="https://raw.githubusercontent.com/numpy/numpy/7e7f4adab814b223f7f917369a72757cd28b10cb/branding/icons/numpylogo.svg"></code>
<code><img height="30" src="https://raw.githubusercontent.com/pandas-dev/pandas/761bceb77d44aa63b71dda43ca46e8fd4b9d7422/web/pandas/static/img/pandas.svg"></code>
<code><img height="30" src="https://matplotlib.org/_static/logo2.svg"></code>
<code><img height="30" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Scikit_learn_logo_small.svg/1280px-Scikit_learn_logo_small.svg.png"></code>
<code><img height="30" src="https://statisfaction.files.wordpress.com/2016/06/plotly_logo_for_digital_final_6.png?w=359&resize=359%2C400#038;h=400"></code>


