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
      1. We don‘t use all variables, we only use subset of variables, decor-relate the trees; do not make several variables dominate
      2. Not better than bagging every time
   3. Boosted trees
      1. Error correction
      2. Build small tree and predict, then have errors; on second tree you predict the error of the previous one
      3. Tune the size of the tree, usually take very small number of split; learning rate; tuning shrinkage value very important

9. Module 9: SVM

   1. Maximize the distance, the margin (objective)
   2. Allow the budget and measure the violation, violation < budget (constraints)
   3. Decision: orientation of the plane
   4. Calculate dot products of x as a **kernel function**  (some form of dot products of x variables)
   5. Kernel function:
      1. linear
      2. polynomial
      3. Radial basis

10. Module 10: neural network

    1. Input layer:
       1. Doesn't behave well if you have a lot of number of variables; not a problem in tree models; 
          1. It's already highly non-linear; especially if there are a lot of variables
       2. Not good for classifications; have to have nodes for each class
    2. Update the weights

11. Module 11: k-means clustering

    1. Minimize sum of within-distance of each cluster

12. Module 11: hierarchical clustering 

    1. Dendrogram 
    2. How to decide how to fuse: simple, complete, average linkage

13. Module 12: PCA

    1. Reduce the dimensions:
       1. Create the new dimension (z): take a linear combination of all the variables 
       2. Scale the variables with the mean of 0; Maximize the variance (a lot of spread of data, to preserve information) 
          1. Constraint pi to make sure it would go to infinite
          2. Green line is the new dimension (pi value telling you the direction)
          3. Not multicollinearity 
    2. Not working in real world business problem because you completely lose interpretation; you have to go back loadings to understand z
    3. Useful if there are too many x variables with very little observations and you have to reduce the dimensions
    4. Biplot (z1-z2)
       1. Phi indicating directions 
       2. Make it interpretable
       3. If you have too many variables, you may need more than 2 components, biplot cannot see the whole picture
    5. Screeplot 
       1. PVE (proportion of variance explained)
       2. CPVE
    6. The number of components cannot exceed the number of variables

### Exam 

1. Bring Calculator and simple algorithms
   1. Neural network updating weights (one pass)
   2. SVM
2. Concept 
3. No explanations of functions and codes
4. Cheatsheet (3); handwritten
   1. Name on top 
   2. A4
5. Only cover topics of mini B
   1. But mean, standard deviation and basic things 
   2. Only the level of in class quiz; problems at the back of the book

