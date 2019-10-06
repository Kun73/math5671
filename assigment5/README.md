# SVM for Credit Card Application	

In this notebook, we write three functions, `kernel()`, `predit()` and `intercept()`.

- `kernel(XTest, XTrain, Type = 0, d = 1, sigma = 1)`

  `XTest` and `XTrain` are the input matrix 

  `Type` :  It indicates which kernel the function uses, `0` is polynomial kernel, `1` represents for linear kernel and `2` stands for Gaussian kernel.

  `d` : It is the power in polynomial kernel 

  `sigma` : It is the $\sigma$ in Gaussian kernel 

- `predict(XTest, XTrain, ytrain, alpha, Type = 0, d = 1, sigma = 1)`

  It outputs the label of predicted results <a href="https://www.codecogs.com/eqnedit.php?latex=y_{pred}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y_{pred}" title="y_{pred}" /></a>

  <a href="https://www.codecogs.com/eqnedit.php?latex=y_{pred}&space;=&space;\begin{cases}&space;1,&space;g(x)\geq&space;0\\&space;-1,&space;g(x)<0&space;\end{cases}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y_{pred}&space;=&space;\begin{cases}&space;1,&space;g(x)\geq&space;0\\&space;-1,&space;g(x)<0&space;\end{cases}" title="y_{pred} = \begin{cases} 1, g(x)\geq 0\\ -1, g(x)<0 \end{cases}" /></a>
  
  `alpha` is the trained parameter.

- `intercept(XTest, XTrain, yTrain, alpha, Type = 0, d = 1, sigma = 1)`

  It calculates the intercept <a href="https://www.codecogs.com/eqnedit.php?latex=b=\frac{1}{N_{s}}\left(\sum_{i=1}^{N_{s}}\left(y_{i}-\sum_{j=1}^{N_{s}}&space;\alpha_{i}&space;y_{i}&space;K\left(x^{(i)},&space;x^{(j)}\right)\right)\right)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?b=\frac{1}{N_{s}}\left(\sum_{i=1}^{N_{s}}\left(y_{i}-\sum_{j=1}^{N_{s}}&space;\alpha_{i}&space;y_{i}&space;K\left(x^{(i)},&space;x^{(j)}\right)\right)\right)" title="b=\frac{1}{N_{s}}\left(\sum_{i=1}^{N_{s}}\left(y_{i}-\sum_{j=1}^{N_{s}} \alpha_{i} y_{i} K\left(x^{(i)}, x^{(j)}\right)\right)\right)" /></a>. 

In the submitting the test results, the website requires the label to be 0 or 1, so we add 

`y_test_more_pred['label'] = (y_test_more_pred['label'] + 1) / 2` to transform the label. 
