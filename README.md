# ds
Introduction to DS

## Likely to show up on the exam:

### Train-test splits & metrics to assess performance

Performance metrics: 
MAE
Precision: True Positive / (True Positive + False Positive) or True Positive / Actual Results
Accuracy: True Positive / (True Positive + False Negatives) or True Positive / Predicted results
Recall: 

### Markov Chains
#### Important MC definitions
* Absorbing MC: In your case, if any state is absorbing (meaning the probability of staying in that state is 1), one cannot leave that state when one has entered.  check if it's possible to reach any other state from the absorbing state. If so, the chain is still irreducible.
* Irreducible MC: To determine if a Markov chain is irreducible, we need to verify whether it is possible to reach any state from any other state, directly or indirectly, through a sequence of transitions. A Markov chain is irreducible if it forms a single communicating class. If any state is absorbing (meaning the probability of staying in that state is 1), check if it's possible to reach any other state from the absorbing state. If so, the chain is still irreducible.
* Reversible MC:When the combinations of all x and y are reversible. See this image:

![alt text](https://github.com/elisehammarstrom/ds/blob/main/images/reversible_markovchain.png?raw=true) 
and this link (page 2): [Reversible MC](https://inst.eecs.berkeley.edu/~ee126/sp18/reversibility.pdf)
Here the file ExamTLab is good to look at. 
* Stationary distribution: Long term frequency. Calculate through raising the transition matrix to a high power, say with math.linalg.matrix_power(transition_matrix, 100)[0]. It is important to take the first row as the stationary distribution. One can also calculate this by using eigenvalues and eigenvectors. See ExamJanuary_2022_problem.ipynb problem 5 part 3


### Subgaussian and subexponential

### Risk

### LCG and Accept-Reject

### Regression
In various fields, the term "residual" can have different meanings, but in the context of statistics and regression analysis, a residual refers to the difference between the observed value of the dependent variable and the value predicted by the regression model. It represents the part of the dependent variable's variation that is not explained by the independent variables included in the model.
1) Observed Value (Actual Value): This is the actual value of the dependent variable that you have observed or measured.
2) Predicted Value: This is the value of the dependent variable predicted by the regression model based on the values of the independent variables.
3) Residual: The residual is the difference between the observed value and the predicted value. Mathematically, the residual (e_{i}) of the i-th observation is calculated as follows:
   e_{i} = Observed value_{i} - Predicted value_{i}
In a regression analysis, the goal is to build a model that minimizes the sum of the squared residuals. This method is known as least squares regression.

### General probability questions
Inversion sampling: We want samples. In normal cases we give the function an X, and it returns a probability. Now we want to get an X from a probability. See problem solving session 03. Istället för att ha F(x) = P(X<=x), som är vår sannolikhetsfunktion (=CDF) där vi då tar in ett värde på x, spottar ut sannolikheten så får vi med inversion sampling ut x baserade på en sannolikhet som input. 
Distribution function: sv: Fördelningsfunktion
Density function: sv: Hur mycket sannolikhet man har på olika intervall. 

## More unlikely to show:

### Dimensionality reduction

### Perceptron

### SVD

### Kernelization

## Other
### Covariance  
Covariance is the degree of say two variables, go together. If one is really positive where the other is really positive, and one is really negative where the other also is really negeative, then they have a high degree of covariance. If one has a really high positive value, and the other really low negative value, then they have a negative covariance. 
Covariance and correlation are very very similar, even up to their mathematical formulations. Correlation is bounded between -1 and 1 whereas covariance is not necessarily bounded between -1 and 1. The covariance matrix has all variables as rows and all variables as columns. 

![alt text](https://github.com/elisehammarstrom/ds/blob/main/images/covariance.png?raw=true)
As such, we see that the covariance of the variable with itself, is the variance of the variable. 
So Cov(A, A) = Var(A) = E(A*A) - E(A)*E(A) where E(A*A) is the mean of the squared A vector and E(A) just is the mean of the A vector. 
Cov(A,B) = Cov(B, A) as the order doesnt matter. The covariance matrix is symmetric, so the transpose of it is the same as the original matrix. 

This is all based from this YT: [Data Science Covariance](https://www.youtube.com/watch?v=152tSYtiQbw)

How to calculate covariance by hand: 
Get the mean of each column (eg mean of Apple, mean of Banana). This gives mean(A) = E(A) and mean(B) = E(B)
Covariance(A, B) = E(A*B) - E(A)*E(B). 
We find E(A*B) by going pairwise and multiply each value of A with each value of B. AS such, E(A*B) = mean(A@B) where @ is dotproduct. 


Coefficient matrix: 

