# Linear Regression

## Introduction

Linear regression can help answer questions such as "How can x be used to predict y". Where x is information and y is information we want to know. 
Simplest Example is finding the price of your house. No. of bedrooms 2 (this is x) and know how much the estate is worth on the market (this is y)

Linear regression is a supervised machine learning model which is the most simple and popular technique for predicting a continous variables.

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/1.png"> 
</p>

Let's consider X is the values corresponding to the living are of houses (input) amd y is the price of these houses respectively (output). The y values are predicted by h. h can be thought of as a function that maps X values to y.

The predicted values or y values are continuous in nature. So the goal is to learn a function h : X → y such that h can be a good predictor for values of y. 

X can be referred to as independent variable whereas y can be referred as dependent variable

In this case a pair (X(i),y(i)) will be a trainig example. A training set then can be defined as {X(i),y(i); i = 1 ...... m}

Linear regression was developed in the field of statistics and is studied as a model for understanding the relationship between input and output numerical variables, but with the course of time, it has become an integral part of modern machine learning toolbox.

## Types of Linear Regression

Based on the number of independent variables (i.e X) there are two types of regression

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/2.png"> 
</p>

1. Simple Linear Regression : A simple linear regression has a single independent variable and the form is : 

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/8.png"> 
</p>

Here,

- Y is a dependent variable.
- X is an independent variable.
- β0 and β1 are the regression coefficients.
- β0 is the intercept or the bias that fixes the offset to a line.
- β1 is the slope or weight that specifies the factor by which X has an impact on Y.

2. Multiple Linear Regression : A multiple linear regression has multiple independent variables and the form is : 

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/9.png"> 
</p>

- Y is a dependent variable.
- X1, X2, …., Xn are independent variables.
- β0, β1,…, βn are the regression coefficients.

## Working of Linear Regression

Consider dummy house dataset with 2 independent variables (Living area and number of bedrooms) and one dependent variable (price)

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/3.png"> 
</p>

To perform regression we need a way to represent h. Considering the initial choice to be such that we approximate y as a linear function of x:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/4.png"> 
</p>

The θi’s are parameters used to map X to y accurately. To make things simpler for understanding lets drop the θ from the hθ(x) and letting X0 = 1 (intercept) such that 

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/5.png"> 
</p>

The θi’s are parameters used to map X to y accurately. To make things simpler for understanding lets drop the θ from the hθ(x) and letting X0 = 1 (intercept) such that 

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/6.png"> 
</p>

Reason behind square value instead of absolute value can be found [here](https://www.quora.com/Why-do-we-use-square-error-instead-of-absolute-value-when-we-calculate-R-2-in-regression-analysis). 

This function defined above is the cost function. This function is sometimes used as a measure of how well different iterations of our model perform – the lower the cost / error, the better your model is. Due to how the cost functions designed, if you were to graph all possible combinations of weights and y-intercepts for a given set of explanatory and response variables, it would look like a convex curve.

## Training a Linear Regression

There are many methods to train a linear regression model Ordinary Least Squares (OLS) being the most popular among them. So, it is good to refer a linear regression model trained using OLS as Ordinary Least Squares Linear Regression or just Least Squares Regression.

### Least Squares Regression

Our aim is to select θ so as to minimize J(θ).  We could possibly use a search algorithm that starts with "Initial guess" for θ and that repititively would change θ to make J(θ) smaller until we find a value of θ such that it minimizes J(θ). 

This optimization can be done by an algorithm called gradient descent.

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/7.png"> 
</p>

Here, α is called the learning rate. This is a very natural algorithm that repeatedly takes a step in the direction of steepest decrease of J. This term α effectively controls how steep your algorithm would move to the decrease of J. It can be pictorially expressed as the following:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/gradient_Descent.jpg"> 
</p>

Following would be the results for different learning rates:

<p align="center" width="100%">
    <img src="https://github.com/absolutelyharsh/Linear_Regression/blob/main/Images/gradient_descent_2.png"> 
</p>

## Gradient Descent

There are commonly two variants of gradient descent:

- The method that looks at every example in the entire training set on every step and is called **batch gradient descent**.
- The method where you repeatedly run through the training set, and
each time you encounter a training example, you update the parameters
according to the gradient of the error with respect to that single
training example only. This algorithm is called **stochastic gradient descent** (also incremental gradient descent).
    

---- References ---- 

[https://blog.galvanize.com/introduction-to-linear-regression/as](https://blog.galvanize.com/introduction-to-linear-regression/as)

[https://www.datacamp.com/community/tutorials/essentials-linear-regression-python](https://www.datacamp.com/community/tutorials/essentials-linear-regression-python)

[https://www.hackerearth.com/practice/machine-learning/machine-learning-algorithms/beginners-guide-regression-analysis-plot-interpretations/tutorial/](https://www.hackerearth.com/practice/machine-learning/machine-learning-algorithms/beginners-guide-regression-analysis-plot-interpretations/tutorial/)
