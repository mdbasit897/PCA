## Principle Component Analysis
Linear dimensionality reduction using Singular Value Decomposition of the data to project it to a lower dimensional space. The input data is centered but not scaled for each feature before applying the SVD.

It uses the LAPACK implementation of the full SVD or a randomized truncated SVD by the method of Halko et al. 2009, depending on the shape of the input data and the number of components to extract.

It can also use the scipy.sparse.linalg ARPACK implementation of the truncated SVD.

Notice that this class does not support sparse input. See TruncatedSVD for an alternative with sparse data.

Read more in the [User Guide.](https://scikit-learn.org/stable/modules/decomposition.html#pca)

## Methods

|  |  |
| ------------- | ------------- |
| fit(X[, y])  | Fit the model with X.  |
| fit_transform(X[, y])  | Fit the model with X and apply the dimensionality reduction on X.  |
| get_covariance() | Compute data covariance with the generative model. |
| get_params([deep]) | Get parameters for this estimator. |
| get_precision() | Compute data precision matrix with the generative model. |
| inverse_transform(X) | Transform data back to its original space. |
| score(X[, y]) | Return the average log-likelihood of all samples. |
| score_samples(X) | Return the log-likelihood of each sample. |
| set_params(**params) | Set the parameters of this estimator. |
| transform(X) | Apply dimensionality reduction to X. |







































## References
For n_components == ‘mle’, this class uses the method from: [Minka, T. P.. “Automatic choice of dimensionality for PCA”. In NIPS, pp. 598-604](https://tminka.github.io/papers/pca/minka-pca.pdf)

Implements the probabilistic PCA model from: [Tipping, M. E., and Bishop, C. M. (1999). “Probabilistic principal component analysis”. Journal of the Royal Statistical Society: Series B (Statistical Methodology), 61(3), 611-622.](http://www.miketipping.com/papers/met-mppca.pdf) via the score and score_samples methods.

For svd_solver == ‘arpack’, refer to > scipy.sparse.linalg.svds.

For svd_solver == ‘randomized’, see: [Halko, N., Martinsson, P. G., and Tropp, J. A. (2011). “Finding structure with randomness: Probabilistic algorithms for constructing approximate matrix decompositions”. SIAM review, 53(2), 217-288.](https://doi.org/10.1137/090771806) and also [Martinsson, P. G., Rokhlin, V., and Tygert, M. (2011). “A randomized algorithm for the decomposition of matrices”. Applied and Computational Harmonic Analysis, 30(1), 47-68.](https://linkinghub.elsevier.com/retrieve/pii/S1063520310000242)
