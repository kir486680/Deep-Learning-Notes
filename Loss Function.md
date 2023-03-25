Fitting the model to the data requires that we agree on some measure of fitness. Loss quantifies the distance between the real and predicted values of the target. The loss will usually be a non-negative number where smaller values are better and perfect prediction is loss 0. 

<h6>For Regression</h6>
[[Linear Regression]]
Most common loss is [[Squared Error]] 

$l^{(i)}(\mathbf{w}, b) = \frac{1}{2} \left(\hat{y}^{(i)} - y^{(i)}\right)^2.$

where $\hat{y}^{(i)}$ us oreduction for example that corresponds to a true label $y^{(i)}$
The constat 1/2 has no real difference because it proves to be notationally conveniet since it cancels out when we take the derivative of the loss. 

To measure the loss for the whole dataset: 

$L(\mathbf{w}, b) =\frac{1}{n}\sum_{i=1}^n l^{(i)}(\mathbf{w}, b) =\frac{1}{n} \sum_{i=1}^n \frac{1}{2}\left(\mathbf{w}^\top \mathbf{x}^{(i)} + b - y^{(i)}\right)^2.$

[[Logistic Regression]]
For logistic regression, the Cost function is defined as:

> −log(_hθ_(_x_)) if y = 1
> 
> −log(1−_hθ_(_x_)) if y = 0

![[Pasted image 20230226133322.png]]

The above two functions can be compressed into a single function i.e.

![](https://miro.medium.com/max/1400/1*_52kKSp8zWgVTNtnE2eYrg.png)


Also, there are options such as 
- [[Mean Absolute Error (MAE)]]
- [[Mean Absolute Percentage Error (MAPE)]]
- [[Root Mean Squared Error (RMSE)]]


