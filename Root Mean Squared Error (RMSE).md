RMSE is defined as:

$$RMSE = \sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y_i})^2}$$

RMSE is a popular metric because it penalizes large errors more than small errors, making it more sensitive to outliers than MAE. It is also differentiable, which makes it suitable for optimization algorithms such as gradient descent. 

RMSE is particularly useful in scenarios where it is important to reduce the impact of large errors or outliers in the data. For example, in financial modeling, it is important to accurately predict stock prices, and large errors in the predictions can have significant financial consequences. In this case, using RMSE as the evaluation metric can help to identify and penalize large errors, which can improve the overall accuracy of the model.

Another scenario where RMSE can be useful is when the predicted values are continuous and follow a normal distribution. In this case, RMSE can provide a measure of the spread of the errors around the mean prediction. This can help to identify cases where the model consistently under or overestimates the values, which can be useful for improving the accuracy of the model.

However, RMSE has some limitations. It is not as interpretable as MAE because it is not in the same units as the original data. Additionally, RMSE can be sensitive to outliers or extreme values, which can affect its usefulness in certain scenarios.

In summary, RMSE is appropriate when it is important to reduce the impact of large errors or outliers in the data, and when the predicted values are continuous and follow a normal distribution. However, it is important to be aware of its limitations and to use it in conjunction with other metrics when evaluating the performance of a model.