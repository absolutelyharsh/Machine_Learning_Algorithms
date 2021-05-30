# Logistic Regression

## Introduction

Logistic regression is an extremely popular machine learning algorithm choice that is used for classification tasks. It is widely used in real-life machine learning production settings. 

Logistic regression is a machine learning algorithm that can be used to predict the probability that an observation belongs to one of the two possible classes. 
Exammples: Email classifier for spam or not spam. Classifying if tumor is benign or malignant.

Data provided as input to the mode contains inputs and binary class to which the data belongs. For example : Input could be the email subject line ("A nigerian prince needs your help") into the model with class("spam"). 

Logistic regression is a supervised machine learning classification algorithm.

Imagine that you’re tasked to predict whether or not a client of your bank will default on their loan repayments. The first thing to do is construct a dataset of historic client defaults. The data would contain client demographic information (e.g. age, gender, location, etc.), their financial information (loan size, times that payment was overdue, etc.), and whether they ended up defaulting on a loan or repaying it.

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/Untitled.png"> 
</p>

The “Yes” and “No” categories can be recorded into 1 and 0 for the target variable (computers deal better with numbers than words):

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/2.png"> 
</p>

After this, we would train a logistic regression model, which would learn a mapping between the input variables (age, gender, loan size) and the expected output (defaulted). We could use the logistic regression model to predict the default probability on three new customers:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/3.png"> 
</p>

So, what does the new column Predicted default tell us? It states the probability of each of the new customers belonging to class 1 (defaulted on loan). We could come up with a threshold value (let’s say 0.5) and anything above that decision threshold would be default behavior (i.e. Customer 5 would be predicted to default on their loan payments, while Customers 4 and 6 would be predicted to repay them).

## Advantages

1. Easy To use : Training the model and using it for predictions is very simple, and it does not require a lot of overhead for maintenance.

2. Interpretability : Unlike deep learning models (neural networks), logistic regression is straightforward to interpret. Although it is not as interpretable as    linear regression, logistic regression can help us to assess which input variable is responsible for the greatest change in predicted value.

3. Scalability : The algorithm is extremely efficient. Fast training times combined with low computational requirements make logistic regression easy to scale, even when the data volume and speed increase.

4. Real-Time Predictions : Because of the ease of computation, logistic regression can be used in online settings, meaning that the model can be retrained with each new example and generate predictions in near real-time.

## Model Representation

Once trained, the model takes the form of a logistic regression equation:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/4.png"> 
</p>

In the above equation: 

- y is the predicted probability of belonging to the default class. In binary classification, we mark the default class with 1 and the other class with 0. y states the probability of an example belonging to the default class on a scale from 0 to 1 (exclusive). So y=0.99 would mean that the model predicts the example belonging to class 1. During training, y is also called the target variable in machine learning, or the dependent variable in statistical modeling. It represents the categorical value that we are trying to predict.

- 1/(1+e^-z) is the sigmoid function.

- wo + w1x is the linear model within logistic regression.

Let’s break down the entire model into the linear model and the accompanying sigmoid function in order to understand how logistic regression predicts probabilities of an example belonging to the default class.

Why wouldn’t we just use the linear model to make predictions about class membership, as we did with linear regression? Let’s look at an example.

Imagine that we have the following table for the number of late payments made by a customer (x) and whether the customer later defaulted on their loan (y).

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/5.png"> 
</p>

We could model the data with a linear regression in the following way:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/6.png"> 
</p>

There are a couple of problems here:

1. Linear regression predicts probabilities outside of the 0-1 range (so someone can have a -140% probability of default, which does not make sense).

2. For a certain number of late payments (two in this example), it is unclear whether we should categorize them under non-defaulting or defaulting behavior.

A better approach would be to model the probability of default using a sigmoid function.

## Sigmoid Function

The sigmoid function is a function that produces an s-shaped curve. It takes any real value as an argument and maps it to a range between 0 and 1 (exclusive). For the problem above, the sigmoid curve would look like this:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Logistic_Regression/blob/main/Images/7.png"> 
</p>

In machine learning, it is used to map the linear model in logistic regression to map the linear predictions to outcome probabilities (bounded between 0 and 1), which are easier to interpret for class membership.

We still have a problem, though. How do we map class membership probability to predicted class? We need a decision boundary to disambiguate between different probabilities.

## Decision Boundary

We still have a problem, though. How do we map class membership probability to predicted class? We need a decision boundary to disambiguate between different probabilities.

y = 0 if predicted probability < 0.5
y = 0 if predicted probability < 0.5

## Types Of Logistic Regression

Above, we presented the classical logistic regression, which predicts one of two classes. But based on the number and data type of the classes, there are different forms of logistic regression:

1. Binary logistic regression. The target variable takes one of two possible categorical values. For example, spam vs. not spam, 0 vs. 1, dog vs. not dog, etc.

2. Multinomial logistic regression. The target variable takes one of three or more possible categorical values. For example, vote Republican vs. vote Democratic vs. No vote, or “buy product A” vs. “try product A” vs. “not buy or try product A”. We can train this type of logistic regression in the same way that we would train the binary classification problem, but we would use a method called ‘one vs. all’ instead. We choose a target class (let’s say A) and calculate the probability of A versus all of the other classes (B and C and…). We repeat the method for each class.

3. Ordinal logistic regression. This is similar to multiple logistic regression,except the target categorical variables are ordered (for example, “medal on the Olympics”).

Irrespective of the type of logistic regression that we choose, training the logistic regression model follows a similar process in all cases.

## Model Evaluation

There are two main metrics for evaluating how well our model functions after we’ve trained it:

1. <b>Accuracy</b>. Represents the percentage of correctly classified samples. An accuracy score of 90% would tell us that our logistic regression model correctly classified 90% of all examples.

2. <b>ROC AUC</b>. Area Under the Receiver Operating Characteristic Curve (ROC AUC) describes
the relationship between the true positive rate (TRP) - that is, the ratio of samples that we correctly predicted belonging to the correct class - versus the false positive rate (FPR) - that is, the ratio of samples for which we incorrectly predicted their class membership. ROC AUC is preferable to accuracy, especially in multiclass prediction settings or when we have a class imbalance problem.
