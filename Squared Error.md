$l^{(i)}(\mathbf{w}, b) = \frac{1}{2} \left(\hat{y}^{(i)} - y^{(i)}\right)^2.$

where $\hat{y}^{(i)}$ us oreduction for example that corresponds to a true label $y^{(i)}$
The constat 1/2 has no real difference because it proves to be notationally conveniet since it cancels out when we take the derivative of the loss. 

To measure the loss for the whole dataset of n examples we simply average the loss: 

$L(\mathbf{w}, b) =\frac{1}{n}\sum_{i=1}^n l^{(i)}(\mathbf{w}, b) =\frac{1}{n} \sum_{i=1}^n \frac{1}{2}\left(\mathbf{w}^\top \mathbf{x}^{(i)} + b - y^{(i)}\right)^2.$
