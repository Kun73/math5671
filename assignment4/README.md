# Assignment 4

We summarize the process of neural network as the following:

From layer `l` to layer `l+1`,  we compute the state at the layer `l+1` based on the state of layer `l` , a sigmoid function `g`, and a matrix $\theta^{l}$.  The matrix $\theta^l$ helps us to transform the number of nodes at different layers.



In shorts, we decompose the model training into 4 parts. 

- `normalize()` is to scale input matrix `X`.
- `sigmoid()` and `gradient()` are about the logistic sigmoid and its gradient respectively.
- `thetaL()`,`computeCost()`, `computeGrad()`, `forward_propagation()` are about neural network training.  Additionally, `thetaL()` is to transform the flatten $\theta$ into matrix between two layers in the network. 
- `optimizeCost()` is to minimize the cost function by gradient descent. 

Besides, `predict()` is to output the results based on input $\theta$. 



Now we describe each functions for details. 

- `normalize(X)`

  It takes in design matrix `X` and returns the normalized matrix `Xnorm`.

- `sigmoid(z)`

  it returns the logistic sigmoid of `z`.

- `gradient(z)`

  It is relevant to `sigmoid(z)`, and returns its gradient. 

- `thetaL(theta, L, input_num, hidden_num, label_num)`

  `theta` is the flatten $\theta$  

   `L`: the number of total layers
   `input_num`: the number of input features
   `hidden_num`: the number of nodes in hidden layers 
   `label_num`: the number of output labels 

  it returns $\theta^{l}$ as matrix and stores in a list

- `computeCost(X, y, theta, L, input_num, hidden_num, label_num, lambd)`

  It returns the regularized cost. 

- `compute(X, y, theta, lambd, L, input_num, hidden_num, label_num)`

  It returns a list store $\Delta^{l}$, which has the same shape of $\theta^{l}$.

- `optimizeCost(theta, X, y, L, input_num, hidden_num, label_num, maxiter, lambd)`

  It optimizes the cost by gradient descent and returns a tuple storing bool variable `convergence`,  `theta` flatten $\theta$ after iteration, `cost` a list storing cost at each iteration step, and iteration times `i`. 

