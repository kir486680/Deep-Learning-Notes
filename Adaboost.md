https://sefiks.com/2018/11/02/a-step-by-step-adaboost-example/


![[Pasted image 20230208211832.png]]


In this case,

-   _n_ is the dimension of real numbers, or the number of attributes in our dataset
-   _x_ is the set of data points
-   _y_ is the target variable which is either -1 or 1 as it is a binary classification problem, denoting the first or the second class (e.g. Fit vs Not Fit)

We calculate the weighted samples for each data point. AdaBoost assigns weight to each training example to determine its significance in the training dataset. When the assigned weights are high, that set of training data points are likely to have a larger say in the training set. Similarly, when the assigned weights are low, they have a minimal influence in the training dataset.

Initially, all the data points will have the same weighted sample _w_:

![](https://blog.paperspace.com/content/images/2019/11/image-51.png)

where N is the total number of data points.

The weighted samples always sum to 1, so the value of each individual weight will always lie between 0 and 1. After this, we calculate the actual influence for this classifier in classifying the data points using the formula:

![](https://blog.paperspace.com/content/images/2019/11/image-52.png)

_Alpha_ is how much influence this stump will have in the final classification. _Total Error_ is nothing but the total number of misclassifications for that training set divided by the training set size. We can plot a graph for _Alpha_ by plugging in various values of _Total Error_ ranging from 0 to 1.

![](https://www.notion.so/image/http%3A%2F%2Fchrisjmccormick.files.wordpress.com%2F2013%2F12%2Fadaboost_alphacurve.png?table=block&id=9c43a3a4-8318-4035-852a-52628778c4e3&width=2560&cache=v2)
Notice that when a Decision Stump does well, or has no misclassifications (a perfect stump!) this results in an error rate of 0 and a relatively large, positive alpha value.

If the stump just classifies half correctly and half incorrectly (an error rate of 0.5, no better than random guessing!) then the alpha value will be 0. Finally, when the stump ceaselessly gives misclassified results (just do the opposite of what the stump says!) then the alpha would be a large negative value.

After plugging in the actual values of _Total Error_ for each stump, it's time for us to update the sample weights which we had initially taken as _1/N_ for every data point. We'll do this using the following formula:

![](https://blog.paperspace.com/content/images/2019/11/image-53.png)

In other words, the new sample weight will be equal to the old sample weight multiplied by Euler's number, raised to plus or minus alpha (which we just calculated in the previous step).

The two cases for alpha (positive or negative) indicate:

-   Alpha is positive when the predicted and the actual output agree (the sample was classified correctly). In this case we decrease the sample weight from what it was before, since we're already performing well.
-   Alpha is negative when the predicted output does not agree with the actual class (i.e. the sample is misclassified). In this case we need to increase the sample weight so that the same misclassification does not repeat in the next stump. This is how the stumps are dependent on their predecessors.
- 
## Advantages and Disadvantages of AdaBoost

AdaBoost has a lot of advantages, mainly it is easier to use with less need for tweaking parameters unlike algorithms like SVM. As a bonus, you can also use AdaBoost with SVM. Theoretically, AdaBoost is not prone to overfitting though there is no concrete proof for this. It could be because of the reason that parameters are not jointly optimized — stage-wise estimation slows down the learning process. To understand the math behind it in depth, you can follow this [link](https://jeremykun.com/2015/09/21/the-boosting-margin-or-why-boosting-doesnt-overfit).

AdaBoost can be used to improve the accuracy of your weak classifiers hence making it flexible. It has now being extended beyond binary classification and has found use cases in text and image classification as well.

A few Disadvantages of AdaBoost are :

Boosting technique learns progressively, it is important to ensure that you have quality data. AdaBoost is also extremely sensitive to Noisy data and outliers so if you do plan to use AdaBoost then it is highly recommended to eliminate them.

AdaBoost has also been proven to be slower than XGBoost.