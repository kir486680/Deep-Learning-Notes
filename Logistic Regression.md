
Logistic regression is a classification algorithm used to assign observations to a discrete set of classes. Some of the examples of classification problems are Email spam or not spam, Online transactions Fraud or not Fraud, Tumor Malignant or Benign. Logistic regression transforms its output using the logistic sigmoid function to return a probability value.

## **What are the types of logistic regression**

1.  Binary (eg. Tumor Malignant or Benign)
2.  Multi-linear functions failsClass (eg. Cats, dogs or Sheep's)

We can call a Logistic Regression a Linear Regression model but the Logistic Regression uses a more complex cost function, this cost function can be defined as the  [[Sigmoid]] or also known as the ‘logistic function’ instead of a linear function.


When using [[Linear Regression]] we used a formula of the hypothesis i.e.

> hΘ(x) = β₀ + β₁X

For logistic regression we are going to modify it a little bit i.e.

> σ(Z) = σ(β₀ + β₁X)

We have expected that our hypothesis will give values between 0 and 1.

> Z = β₀ + β₁X
> 
> hΘ(x) = sigmoid(Z)
> 
> i.e. hΘ(x) = 1/(1 + e^-(β₀ + β₁X)

![](https://miro.medium.com/max/1046/1*l59BUnPwWHMf1H-GNxgZHQ.png)
