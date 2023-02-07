
This model has an assumption of linearity that means that expected value of the target can be expressed as a weighted sum of the features

Ex. 
$\mathrm{price} = w_{\mathrm{area}} \cdot \mathrm{area} + w_{\mathrm{age}} \cdot \mathrm{age} + b.$

The weights determine the influence of each feature on our prediction. The bias term determines the value of the esrimate when all features are zero. 

$\hat{y} = w_1  x_1 + ... + w_d  x_d + b.$

Collecting all features into a vector $\mathbf{x} \in \mathbb{R}^d$ and akk weights into a wector $\mathbf{w} \in \mathbb{R}^d$, we can express the model compactly via the dot product between w and x

$\hat{y} = \mathbf{w}^\top \mathbf{x} + b.$

We will often find it convenient to refer to features of our entire dataset of $n$ examples via the _design matrix_ $\mathbf{X} \in \mathbb{R}^{n \times d}$ . Here X contains one row for every example and one column for every feature. The prediction $\hat{\mathbf{y}} \in \mathbb{R}^n$  can be expressed as matrix-vector product: 

${\hat{\mathbf{y}}} = \mathbf{X} \mathbf{w} + b,$

The goal of the regression model is to predict with lowest error. To measure the error we need a [[Loss Function]]

After the loss is measured, we need to minimize the loss and optimize the model using [[Optimization Algorithm]]

