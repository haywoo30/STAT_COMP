
Family wise error rate with correlated tests:

Modify the three-predictor [example discussed in class today](https://github.com/gdlc/STAT_COMP/blob/master/LARGE_SCALE_TESTING.md) by making the three predictors correlated accoridng to 
the following correlation matrix (do not use `mvrnorm()`):

| | | |
|----|----|----|
| 1.0  | 0.5 | 0.5 |
| 0.5  | 1.0 | 0.5 |
|0.5.  | 0.5 | 1.0 |


Hint: 

   - Compute the lower-triangular cholesky of the above matrix (`L=t(chol(S))`)
   - Check that `S==L%*%t(L)`
   - Initialize a matrix X (n rows, q columns)
   - In a loop from 1 to n:
        - Generate `q` iid iid N(0,1) `z=rnorm(3)`
        - set `X[i,]=L%*%z`
   - Use this incidence matrix in the example discussed in class today.

Estimate and report the type-I error rate when you reject using `alpha=0.05`, `alpha=0.05/3`.