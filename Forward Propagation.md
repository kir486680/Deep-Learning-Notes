For the sake of simplicity, let's assume that the input example is $\mathbf{x}\in \mathbb{R}^d$
and that our hidden layer does not include a bias term.
Here the intermediate variable is:

$$\mathbf{z}= \mathbf{W}^{(1)} \mathbf{x},$$
where $\mathbf{W}^{(1)} \in \mathbb{R}^{h \times d}$ is the weight parameter of the hidden layer. After running the intermediate variable $\mathbf{z}\in \mathbb{R}^h$ through the activation function $\phi$ we obtain our hidden activation vector of length $h$,

$$\mathbf{h}= \phi (\mathbf{z}).$$



The hidden layer output $\mathbf{h}$ is also an intermediate variable. Assuming that the parameters of the output layer only possess a weight of $\mathbf{W}^{(2)} \in \mathbb{R}^{q \times h}$, we can obtain an output layer variable with a vector of length $q$:
$$\mathbf{o}= \mathbf{W}^{(2)} \mathbf{h}.$$


Assuming that the loss function is $l$ and the example label is $y$, we can then calculate the loss term for a single data example,
$$L = l(\mathbf{o}, y).$$

  
According to the definition of $\ell_2$ regularization that we will introduce later, given the hyperparameter $\lambda$, the regularization term is

$$s = \frac{\lambda}{2} \left(\|\mathbf{W}^{(1)}\|_F^2 + \|\mathbf{W}^{(2)}\|_F^2\right),$$

[[L2 Regularization]]

  

where the Frobenius norm of the matrix is simply the $\ell_2$ norm applied after flattening the matrix into a vector. Finally, the model's regularized loss on a given data example is:

$$J = L + s.$$

  
We refer to $J$ as the *objective function* in the following discussion.

After the Forward Propagation comes [[Back Propagation]]