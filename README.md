# Udacity-project

## OverView
This project is part of the Udacity Azure ML Nanodegree. In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model. This model is then compared to an Azure AutoML run



## Summary ##
The dataset, I have worked on is Bank Marketing dataset. I have used Hyperdrive and automl for prediction of whether a customer has deposited or not. Here "Y" is my target variable.
With __Accuracy__ as primary metric, I have trained my dataset on _HyperDrive_ for tuning hyperparameters of Logistic Regression and got a accuracy score of **0.9042** and __automl__ with best algorithm it suggested as _VotingEnsemble_ and with a accuracy of **0.9175**. So when we compare Hyperdrive and AutoML , AutoML got better accuracy score than HyperDrive 

## Scikit-learn Pipeline ## 
Scikit- learn pipeline is trained with estimator as _SKLEARN Class_ and with _train.py_ script. The data is first fed into _Clean_data_ where the null values an removed. Then the data is split into training data as **80%** and test data as **20%**. The parameters for logistic Regession are *C* and *max_iter* and parameter sampling as Random.I used Bandit Policy  as early temination policy. The policy states that it terminates runs less than slack factor. 
After training the model, I got an accuracy score of **0.9042** and then dumped the best model through joblib
![hyperdrive result](https://user-images.githubusercontent.com/51949018/107182263-6a402680-6a02-11eb-9797-3a3cedd836cf.png)

## AutoML pipeline ##
My AutoML ran for 27 iterations in 30 mintutes. The best model is _votingEnsemble_ . The primary metric I used is __Acuraccy__ and Number of cross_validations as 6 for my AutoML configuation and I got an accuracy score of **0.9171** 
![automl result](https://user-images.githubusercontent.com/51949018/107182934-bb044f00-6a03-11eb-83ad-c19292e77977.png)
![auto_graph](https://user-images.githubusercontent.com/51949018/107183068-03237180-6a04-11eb-91c5-9fd0fec0755b.png)

## Comparision of the both pipelies ##
In HyperDrive, I was able to tune the hyperparameters of logistic regression with different parameters whereas in the AutoML, I was able to apply different algorithm model on my dataset and thus I was able derive better accuracy of **0.9171**

## Future Work ##
 1.Instead of bandit policy, I can apply median sxtopping policy or Truncation selection policy 
 2.Applying Parameter sampling methods like Baysian Sampling and grid Sampling
 3.Applying and testing data with different cross_validations
 4.Choosing different primary metric instead of accuracy
