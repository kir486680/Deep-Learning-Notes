When we remove some neurons from the layers, the calculatoins of out.


Dropout is a regularization technique used in neural networks to prevent [[Overfitting]]. Overfitting occurs when a model becomes too complex and learns the noise in the training data rather than the underlying patterns. This results in poor generalization performance on unseen data.

Dropout works by randomly dropping out (i.e., setting to zero) a certain percentage of neurons during each training iteration. This forces the network to learn multiple independent representations of the data, rather than relying on a small number of neurons. During testing, all neurons are used and their activations are scaled by a factor equal to the dropout rate, to compensate for the reduced number of active neurons during training.

The intuition behind dropout is that it encourages the network to learn redundant representations of the data, since a dropped-out neuron cannot rely on other neurons to compensate for its absence. This redundancy improves the generalization ability of the model, as it can make correct predictions even if some neurons are missing or have incorrect values.

In summary, dropout is a simple and effective way to regularize deep neural networks by adding some noise to the activations, forcing the network to learn robust representations that are not dependent on a small number of neurons. The dropout rate is typically set between 0.2 and 0.5, and can be tuned as part of the model's hyperparameter optimization process.


<h5>Deep Explanation</h5>

The key challenge in using dropout regularization is to inject the noise in a manner that does not significantly change the expected value of the activations. The goal is to inject the noise in an unbiased way, so that the expected value of each layer, while fixing the others, equals the value it would have taken absent the noise.

Dropout, zeros out a fraction of the nodes in each layer. To ensure that the expected value of the activations remains unchanged, each layer is debiased by normalizing by the fraction of nodes that were retained (not dropped out). With dropout probability $p$, each intermediate activation $h$ is replaced by a random variable $h'$ as follows:
$$

\begin{aligned}

h' =

\begin{cases}

0 & \text{ with probability } p \\

\frac{h}{1-p} & \text{ otherwise}

\end{cases}

\end{aligned}

$$
By design, the expectation of $h'$ remains equal to $h$, i.e., $E[h'] = h$.

Why do the results stay the same? 

The expectation of $h$ remains the same after dropout because of the debiasing step. Let $p$ be the dropout probability and let $h$ be an intermediate activation in the network. Then, with probability $p$, the dropout operation sets the activation to zero, i.e., $h'=0$. With probability $1-p$, the activation is retained and is scaled by the factor $\frac{1}{1-p}$, i.e., $h'=\frac{h}{1-p}$.

The expected value of the perturbed activation $h'$ can be computed as follows:

$E[\mathbf{h}'] = \mathbf{p}*0 + (1-\mathbf{p}) * \frac{\mathbf{h}}{1-\mathbf{p}} =h$

So, the expectation of $h'$ remains equal to the expectation of $h$, i.e., $E[h'] = E[h]$. This is what is meant by the debiasing step, which ensures that the expected value of the activations remains unchanged after the dropout operation. By maintaining the expected value of the activations, the dropout operation retains the underlying patterns in the data, while making the network more robust to the failure of individual neurons.


```python
import torch
from torch import nn
from d2l import torch as d2l

def dropout_layer(X, dropout):
    assert 0 <= dropout <= 1
    if dropout == 1: return torch.zeros_like(X)
    mask = (torch.rand(X.shape) > dropout).float()
    return mask * X / (1.0 - dropout)
```


