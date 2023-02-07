$$s = \frac{\lambda}{2} \left(\|\mathbf{W}^{(1)}\|_F^2 + \|\mathbf{W}^{(2)}\|_F^2\right),$$
The L2 regularization term in the formula,can be understood as follows:

1.  $$\frac{\lambda}{2}$$: This term is a scalar that controls the strength of the regularization. A larger value of λ means a stronger regularization, and a smaller value of λ means a weaker regularization.
    
2.  $$|\mathbf{W}^{(1)}|_F^2$$: This term calculates the sum of squares of all elements in matrix W^(1) and is known as the Frobenius norm of the matrix. It measures the magnitude of W^(1) and provides a measure of how large the weights are.
    
3.  $$\mathbf{W}^{(2)}|_F^2$$: This term is similar to the previous one and calculates the Frobenius norm of matrix W^(2). It measures the magnitude of W^(2) and provides a measure of how large the weights are.
    
4. $$ \left(|\mathbf{W}^{(1)}|_F^2 + |\mathbf{W}^{(2)}|_F^2\right)$$: This term adds up the magnitudes of both matrices W^(1) and W^(2). The combined term provides a measure of the total magnitude of all weights in the network.
    

In summary, the L2 regularization term adds a penalty to the loss function that is proportional to the magnitude of the weights in the network. The term helps to prevent [[Overfitting]] by discouraging the model from having large weights.

Pytorch decays weight and biases simoultaneously 