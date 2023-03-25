MAPE is defined as:

$$MAPE = \frac{1}{n}\sum_{i=1}^{n}\frac{|y_i - \hat{y_i}|}{|y_i|}$$

where the difference is divided by the actual value to get a percentage error. MAPE is useful when you want to measure the relative error rather than the absolute error, which is particularly relevant when dealing with data of different scales.


Mean Absolute Percentage Error (MAPE) is a useful metric to use when you want to measure the relative error between predicted and actual values. It is particularly relevant when dealing with data of different scales or when you want to compare the performance of models that make predictions on different types of data.

MAPE expresses the error as a percentage of the actual value, which makes it more interpretable than other metrics that are not in the same units as the original data. This means that it can be used to compare the performance of models on different types of data, such as sales figures, temperatures, or stock prices.

MAPE is also useful when you want to assess the accuracy of a forecasting model over multiple periods or time periods. For example, if you are trying to forecast sales for the next quarter, MAPE can give you a sense of how well your model is performing across multiple time periods.

However, MAPE has some limitations. It can produce infinite or undefined values when the actual value is zero or close to zero, and it can be sensitive to outliers or extreme values. Additionally, MAPE can give misleading results when the actual values are negative or when the forecast values are zero or negative.

In summary, MAPE is appropriate when you want to measure the relative error between predicted and actual values, particularly when dealing with data of different scales or when comparing the performance of models that make predictions on different types of data. However, it is important to be aware of its limitations and to use it in conjunction with other metrics when evaluating the performance of a model.


For example, consider a machine learning model that is used to predict the sentiment of customer reviews on a scale of 1 to 5. The model is trained on a dataset of customer reviews and their corresponding sentiment scores. When evaluating the performance of the model, it may be more meaningful to express the error in terms of the percentage of incorrect predictions rather than the absolute difference in sentiment scores. This is because the sentiment scores themselves may not have a clear or meaningful interpretation in this context, and it may be more relevant to focus on the overall accuracy of the model in predicting the correct sentiment.

Similarly, in some cases, the units of the original data may be difficult to interpret or compare, such as when dealing with data from different domains or with different measurement scales. In these cases, expressing the error in a common unit or scale may be more useful for comparing the performance of different models or analyzing the overall accuracy of the predictions.

In summary, expressing the error in units that are different from the original data may be appropriate when the original units are not meaningful or relevant to the analysis, or when comparing the performance of models with different types of data.