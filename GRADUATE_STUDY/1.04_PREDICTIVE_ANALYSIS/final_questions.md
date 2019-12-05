#### Questions 

1. What happens to the margin in terms of cost?
   1. If the cost is small, many penalties will happen so the margin is large. 
   2. If the cost is big, the model has to switch quickly given the new data, so the variance is high and the boundary is narrow. 
2. Quiz #10 question
   1. No need to scale
   2. But in reality when calculating RMSE, we have to re-scale back.

#### Overview 

1. Module 2 bias and variance:

   1. Nothing can be done and changed to irreducible error

   2. More complex model, decrease bias, higher variance, test use up and down

   3. f(x): true functions usually not known

   4. Average all the $\hat{f}(x_0)$ for all the datasets; Hope it would equal to f(x)

      1. We can't calculate the exact number of bias
      2. We dont know the real function
      3. We dont have the expectation of $\hat{f}(x_0)$ 

   5. Variance: how far every $\hat{f}(x_0)$ from the average $\hat{f}(x_0)$ 

      1. To get expectation (E) you will need <u>infinite</u> datasets
      2. You can only get one dataset in real world
      3. So we couldn't calculate the exact number of variance

   6. Plot of flexibility vs. test MSE, bias, variance

      1. In real world we only know the MSE

      2. How to decide model's flexibility:

         1. Number of parameters: more non-linear / flexible

         2. > Neural network: 
            >
            > no hidden layer, then linear regression
            >
            > More hidden layers, then more flexible

2. Module 3: logistic regression

   1. If data is clearly separated, then logistic regression is not stable, 
      1. It needs some overlap, some buy some dont.
   2. Formula 
      1. S shape
      2. It could go up dramatics regarding x 

3. Module 3: LDA

   1. One of the oldest model, not used much now
   2. Bayes rule: best rule of probabilities; but we dont know those probability 
   3. <u>Assume</u> the likelihood function goes into bayes rule is normal distribution

4. Module 4: QDA

   1. **LDA** assumed that every class has the **same variance/ covarianc**e
   2. QDA allows for different variances among classes, the resulting boundaries become <u>quadratic</u> 
   3. More flexible than LDA, may be less flexible than KNN
   4. Every solution of model will give you probability so usually we use p to calculate LDA

5. Module 5: bootstrap

   1. Allows you to make that 1 dataset you possess to many dataset
   2. Randomly sample with replacement 
   3. Each sample with the same number of the original dataset
   4. From each dataset, we calculate some <u>statistics</u> (average)
   5. Many average coming from different sub dataset, then calculate the average and then standard error and variance; easy to calculate the <u>variability of the statistics</u> (how much confidence)
   6. Calculate any variability

6. Module 6: ridge regression

   1. Ordinary least squares estimates by minimizing RSS (linear regression);
   2. Lambda is infinite then eliminate all betas; lambda is 0, then all betas still stay
   3. However, betas will go very small but not 0; then LASSO
   4. Feasible region plot; lasso easily to touch the corner where beta is 0 of the feasible region

7. Module 7: tree

   1. Simple to interpret and explain the model; very simple picture
   2. Where to cut, which variable: which minimize MSE (regression) / minimize GENIE or entropy (classification)
   3. Average all y-hats and get the predicted value

8. Module 8: bagging

   1. Create bootstrapped dataset; DO NOT PRUNE 
      1. Tree is highly non-linear, not accurate
      2. One bagging tree is worse than the tree model because of overfitting
      3. But building many and averaging will <u>reduce variance</u> 
   2. Random forest
      1. We dont use all variables, we only use subset of variables, decorrelatfe the trees; do not make several variables dominate
      2. Not better than bagging every time
   3. Boosted trees
      1. Error correction
      2. Build small tree and predict, then have errors; on second tree you predict the error of the previous one
      3. Tune the size of the tree, usually take very small number of split; learning rate; tuning shrinkage value very important