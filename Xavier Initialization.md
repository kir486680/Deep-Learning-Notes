


Xavier initialization is a weight initialization technique used to initialize the weights of a neural network. The intuition behind this technique is to keep the variance of the activations and gradients of the weights fixed during the forward and backward propagation steps.

In a forward propagation step, the activation $o_i$ for a neuron is given by the weighted sum of its inputs $x_j$:

$o_i = \sum_{j=1}^{n_{in}} w_{ij} x_j$

The goal of the Xavier initialization is to keep the variance of the activations fixed. To do this, we would like to have $E[o_i]=0$ and $\mathrm{Var}[o_i]=1$. One way to keep the variance fixed is to set $n_\mathrm{in} \sigma^2 = 1$.

<small>"n_in" refers to the number of inputs to a layer in a neural network. This means the number of neurons in the previous layer.

"n_out" refers to the number of outputs from a layer in a neural network. This means the number of neurons in the current layer.

For example, if a layer has 100 neurons in the previous layer, then n_in=100. If a layer has 50 neurons in the current layer, then n_out=50.<small>

However, during backpropagation, gradients are propagated from the layers closer to the output, and there is a similar problem with the gradients' variance potentially exploding. To prevent this, we would like to have $n_\mathrm{out} \sigma^2 = 1$, where $n_\mathrm{out}$ is the number of outputs of this layer.

The problem with these two conditions is that we cannot possibly satisfy both of them simultaneously. Instead, we simply try to satisfy the condition $\frac{1}{2} (n_\mathrm{in} + n_\mathrm{out}) \sigma^2 = 1$, which is equivalent to $\sigma = \sqrt{\frac{2}{n_\mathrm{in} + n_\mathrm{out}}}$.

In practice, this initialization method works well for deep neural networks and has been found to improve training performance compared to other weight initialization methods. Helps against [[Overfitting]]


<h5>Deep Explanation</h5>
Let's look at the scale distribution of an output $o_{i}$ for some fully connected layer *without nonlinearities*. With $n_\mathrm{in}$ inputs $x_j$ and their associated weights $w_{ij}$ for this layer, an output is given by

  

$$o_{i} = \sum_{j=1}^{n_\mathrm{in}} w_{ij} x_j.$$

  

The weights $w_{ij}$ are all drawn independently from the same distribution. Furthermore, let's assume that this distribution has zero mean and variance $\sigma^2$. Note that this does not mean that the distribution has to be Gaussian, just that the mean and variance need to exist. For now, let's assume that the inputs to the layer $x_j$ also have zero mean and variance $\gamma^2$ and that they are independent of $w_{ij}$ and independent of each other. In this case, we can compute the mean and variance of $o_i$ as follows:
$$

\begin{aligned}

E[o_i] & = \sum_{j=1}^{n_\mathrm{in}} E[w_{ij} x_j] \\&= \sum_{j=1}^{n_\mathrm{in}} E[w_{ij}] E[x_j] \\&= 0, \\

\mathrm{Var}[o_i] & = E[o_i^2] - (E[o_i])^2 \\

& = \sum_{j=1}^{n_\mathrm{in}} E[w^2_{ij} x^2_j] - 0 \\

& = \sum_{j=1}^{n_\mathrm{in}} E[w^2_{ij}] E[x^2_j] \\

& = n_\mathrm{in} \sigma^2 \gamma^2.

\end{aligned}

$$
Xavier initialization is a weight initialization method for neural networks that is designed to ensure that the output of each activation has a mean of 0 and a variance that is equal to the number of inputs. The intuition behind this method is to provide a starting point for the weights that will not lead to either very large or very small activations in the network. This can help prevent issues like vanishing or exploding gradients, which can impede the training process.

The formulas represent the expectation and variance of the output of a single activation unit in the network, with $n_{in}$ being the number of inputs, $w_{ij}$ being the weight from the $j$-th input to the $i$-th output, $x_j$ being the $j$-th input, and $\sigma^2 \gamma^2$ being a constant that depends on the activation function and its input distribution.

The first formula, $E[o_i] = \sum_{j=1}^{n_\mathrm{in}} E[w_{ij} x_j]$, calculates the expected value of the activation output. The expected value of a product of two random variables is equal to the product of the expected values of the variables, so the formula simplifies to $E[o_i]=0$.

The second formula, $\mathrm{Var}[o_i] = \sum_{j=1}^{n_\mathrm{in}} E[w^2_{ij} x^2_j]$, calculates the [[Variance]] of the activation output. The variance of a product of two random variables is equal to the product of the variances of the variables, so the formula simplifies to $\mathrm{Var}[o_i] = n_\mathrm{in} \sigma^2 \gamma^2$.
The line $\mathrm{Var}[o_i] = E[o_i^2] - (E[o_i])^2$ expresses the definition of variance. Variance is a measure of the spread or dispersion of a set of values around their mean. In this case, the set of values is the output $o_i$ of a neuron. The expected value of $o_i^2$, denoted $E[o_i^2]$, represents the average value of $o_i^2$ over multiple realizations of the input. This can be thought of as the average squared value of the output of the neuron. The expected value of $o_i$, denoted $E[o_i]$, represents the average value of $o_i$ over multiple realizations of the input. This can be thought of as the average value of the output of the neuron. The variance of $o_i$, denoted $\mathrm{Var}[o_i]$, is then defined as the difference between the expected value of the square of the output and the square of the expected value of the output:

$$\mathrm{Var}[o_i] = E[o_i^2] - (E[o_i])^2$$

In other words, the variance measures how much the output of the neuron varies around its mean value. 

In a forward propagation step, the activation $o_i$ for a neuron is given by the weighted sum of its inputs $x_j$:

$o_i = \sum_{j=1}^{n_{in}} w_{ij} x_j$

The goal of the Xavier initialization is to keep the variance of the activations fixed. To do this, we would like to have $E[o_i]=0$ and $\mathrm{Var}[o_i]=1$. One way to keep the variance fixed is to set $n_\mathrm{in} \sigma^2 = 1$.

However, during backpropagation, gradients are propagated from the layers closer to the output, and there is a similar problem with the gradients' variance potentially exploding. To prevent this, we would like to have $n_\mathrm{out} \sigma^2 = 1$, where $n_\mathrm{out}$ is the number of outputs of this layer.

The problem with these two conditions is that we cannot possibly satisfy both of them simultaneously. Instead, we simply try to satisfy the condition $\frac{1}{2} (n_\mathrm{in} + n_\mathrm{out}) \sigma^2 = 1$, which is equivalent to $\sigma = \sqrt{\frac{2}{n_\mathrm{in} + n_\mathrm{out}}}$.


