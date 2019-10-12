# K-Means Clustering 

The function `km()` is to implement the K-Means clustering. 

`km(X, K, max_iters)`

- `X` : the design matrix
- `K` : the tuning parameter in K-Means clustering
- `max_iters` : the maximum iteration times



In this function, we first assign each observation to a centroid, then we update the centroid. If the centroids do not change, we consider it as convergence and return the results. 

