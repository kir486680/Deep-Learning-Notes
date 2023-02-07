
The log-likelihood formula represents the probability of observing a set of outcomes Y given a set of inputs X. The formula is expressed as:

$P(\mathbf{Y} \mid \mathbf{X}) = \prod_{i=1}^n P(\mathbf{y}^{(i)} \mid \mathbf{x}^{(i)}).$

The product of n terms is the result of multiplying n numbers together. In this case, the formula represents the product of the probabilities of observing each individual outcome y^(i) given its corresponding input x^(i), for all i from 1 to n.

For example, if n=3, then the product would be:

P(Y | X) = P(y^(1) | x^(1)) * P(y^(2) | x^(2)) * P(y^(3) | x^(3))

In this formula, the "prod" notation is used to represent the product of all terms, which are the probabilities of observing the individual outcomes given their corresponding inputs, for all i from 1 to n.

However, numrical issue occurs when the product of many small probabilities results in a very small number that cannot be represented accurately by the computer's floating-point representation. In other words, the computer may not be able to store the result of the calculation without losing some precision.

To overcome this issue, log-likelihood is used instead of likelihood in many machine learning algorithms. The log-likelihood is defined as the logarithm of the likelihood:

$$-\log P(\mathbf{Y} \mid \mathbf{X}) = \sum_{i=1}^n -\log P(\mathbf{y}^{(i)} \mid \mathbf{x}^{(i)})
= \sum_{i=1}^n l(\mathbf{y}^{(i)}, \hat{\mathbf{y}}^{(i)})$$


The logarithm of a number is the exponent to which a fixed base must be raised to produce that number. In this case, the logarithm of the likelihood is taken to prevent numerical underflow. The logarithm is a monotonically increasing function, meaning that if x > y then log(x) > log(y). This means that maximizing the likelihood is equivalent to maximizing the log-likelihood.

The intuition behind this definition is that the log-likelihood provides a way to estimate the quality of the model's predictions in a more robust way, by penalizing models that make predictions with low probabilities. In other words, if a model predicts an outcome with a low probability, the corresponding log-likelihood will be high, indicating that the model is not confident in its prediction. Conversely, if a model predicts an outcome with a high probability, the corresponding log-likelihood will be low, indicating that the model is confident in its prediction.

The log-likelihood is negative because it is the logarithm of the likelihood, which is a probability, and probabilities are always between 0 and 1, inclusive. The logarithm of a number between 0 and 1 is negative, since the logarithm function is monotonically decreasing on this interval.

In other words, the log-likelihood is negative because the logarithm of a probability less than 1 is negative. In practice, this negative sign is ignored and the log-likelihood is treated as a positive quantity. The reason for this is that the goal is often to maximize the log-likelihood, which is equivalent to minimizing the negative log-likelihood. The negative sign cancels out when taking the derivative of the log-likelihood, making it easier to perform optimization.

Therefore, when working with log-likelihood, the focus is usually on its magnitude rather than its sign. The magnitude of the log-likelihood measures how well the model fits the data, with larger magnitudes indicating better fit. In this sense, maximizing the log-likelihood is equivalent to finding the best-fitting model to the data.

We can also define a loss function which is called [[Cross-Entropy]]