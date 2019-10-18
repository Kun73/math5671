# Loan recommendation with Collaborative Filtering

- `costFun(param, Y, r, n_lenders, n_loans, n_features, lamba)`

  It is to compute the regularized cost. 

  `param` : includes flatten X and <a href="https://www.codecogs.com/eqnedit.php?latex=\theta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\theta" title="\theta" /></a>

  `Y` : the response

  `r` : the indicating matrix

  `n_lenders`, `n_loans`, `n_features` : the number of dimensions of <a href="https://www.codecogs.com/eqnedit.php?latex=X\in\mathbb{R}^{nloans\times&space;nfeatures}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?X\in\mathbb{R}^{nloans\times&space;nfeatures}" title="X\in\mathbb{R}^{nloans\times nfeatures}" /></a>
  and <a href="https://www.codecogs.com/eqnedit.php?latex=\theta\in\mathbb{R}^{nlenders\times&space;nfeatures}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\theta\in\mathbb{R}^{nlenders\times&space;nfeatures}" title="\theta\in\mathbb{R}^{nlenders\times nfeatures}" /></a>

  `lambda` : tuning parameters

- `cost_grad(param, Y, r, n_lenders, n_loans, n_features, lamba)`

  It is returns the flatten gradient of X and <a href="https://www.codecogs.com/eqnedit.php?latex=\theta" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\theta" title="\theta" /></a>. 

- `optimizeCost(param, Y, r, n_lenders, n_loans, n_features, lamba, step, maxrun, tol)`

  It uses the gradient descent to get the optimal `param`.

  It returns a tuple `(param, cost_range, convergence, iteration)`. 

  `cost_range` contains the cost at each iteration. 
  
  # Preview .ipynb
  You may see [here](https://nbviewer.jupyter.org/github/Kun73/math5671/blob/master/assignment7/Loan%20Recommendation%20Template.ipynb) if it cannot be loaded
