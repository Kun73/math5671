# SVM for Credit Card Application	

In this notebook, we write three functions, `kernel()`, `predit()` and `intercept()`.

- `kernel(XTest, XTrain, Type = 0, d = 1, sigma = 1)`

  `XTest` and `XTrain` are the input matrix 

  `Type` :  It indicates which kernel the function uses, `0` is polynomial kernel, `1` represents for linear kernel and `2` stands for Gaussian kernel.

  `d` : It is the power in polynomial kernel 

  `sigma` : It is the $\sigma$ in Gaussian kernel 

- `predict(XTest, XTrain, ytrain, alpha, Type = 0, d = 1, sigma = 1)`

  It outputs the label of predicted results <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
  $$
  y_{pred} = 
  \begin{cases}
  1, g(x)\geq 0\\
  -1, g(x)<0
  \end{cases}
  $$
  `alpha` is the trained parameter.

- `intercept(XTest, XTrain, yTrain, alpha, Type = 0, d = 1, sigma = 1)`

  It calculates the intercept $b=\frac{1}{N_{s}}\left(\sum_{i=1}^{N_{s}}\left(y_{i}-\sum_{j=1}^{N_{s}} \alpha_{i} y_{i} K\left(x^{(i)}, x^{(j)}\right)\right)\right)$. 

In the submitting the test results, the website requires the label to be $0$ or $1$, so we add 

`y_test_more_pred['label'] = (y_test_more_pred['label'] + 1) / 2` to transform the label. 
