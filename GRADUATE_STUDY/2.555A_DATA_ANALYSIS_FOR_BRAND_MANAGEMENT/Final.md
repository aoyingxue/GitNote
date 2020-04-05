## Final Exam

> Student ID: 474878
>
> Yuki Ao

1. SUV

   1. Estimated coefficients are below:

      |      | Est             |
      | ---- | --------------- |
      | p    | 0.0062          |
      | q    | 0.0584          |
      | m    | 22,644,939.3438 |
      | Ad   | 0.0546          |

      ![image-20200226181742608](https://tva1.sinaimg.cn/large/0082zybpgy1gcana4m9v3j30vr0u0wi8.jpg)

      The advertising coefficient means the advertising sensitivity for customers. 

      The sign of the advertising sensitivity is positive, which means the customers have good impressions of the advertising and they will be more likely to purchase after they look at the ads. More ads exposed, more likely the customers to purchase.

   2. If using the GBM equation assuming the advertising stays the same and calculating by excel, the sales prediction of quarter 43 would be 377948.706≈377949. 

      | salespred | cum_salespred |
      | --------- | ------------- |
      | 377949    | 13396762      |

      If using the prediction given by Number Analytics, the prediction is 379434 unit sales for quarter 43. The small difference may be probably caused by the assumption of advertising in quarter 43. 

      | salespred | cum_salespred |
      | --------- | ------------- |
      | 379434    | 13410983      |

2. Soft Drink

   |              | Coefficients |
   | ------------ | ------------ |
   | $\alpha_y$   | 1.54167382   |
   | $\beta_{1y}$ | -2.3013794   |
   | $\beta_{2y}$ | 0.5630182    |
   | $\beta_{3y}$ | 0.68932975   |
   | $\beta_{4y}$ | 1.53371219   |

   As for the interpretations, $\alpha_y$ is the brand equity or strength of the brand. $exp(\alpha_y)=4.67$ represents the baseline sales if the product is priced \$1. (But in reality because of its p-value, it should be considered insignificant. )

    $\beta_{1y}$ is the own price elasticity of y. It means that if y's price decreases by 1%, the sales of y will increase by 2.30%. 

    $\beta_{2y}$ is the cross price elasticity and also y's vulnerability. It means that if the price of x decreases by 1%, the sales of y will decrease by 0.56%. 

    $\beta_{3y}$ is the "deal" multiplier. It means that the sales will increase by a multiple exp(0.68)=1.99 times if it chose to make a deal or discount at the store in a given time. 

    $\beta_{4y}$ is the feature multiplier. It means that the sales will increase by a multiple exp(1.53)=4.64 times if it chose to increase the feature advertising in a given time. 

3. Perfume 

   The estimations of the coefficients are below:

   |                      | Coefficients |
   | -------------------- | ------------ |
   | Intercept            | 4.03083816   |
   | price elasticity     | -2.4958155   |
   | ad elasticity (beta) | 0.19638847   |
   | ln(adpp1)            | 0.15407042   |
   | ln(adpp2)            | 0.11354376   |

   In result, the total advertising elasticity should be the sum of the coefficients of ad, adpp1 and adpp2, which is equal to 0.46400265.  (But in reality because of its p-value, the coefficient of adpp2 should be considered insignificant.)

   Recalculation is shown below:

   |                                                            | elasticity |
   | ---------------------------------------------------------- | ---------- |
   | ad persistence from t to t+1                               | 1.00962239 |
   | ad persistence from t+1 to t+2                             | 0.73696019 |
   | average persistence from one period to next period (gamma) | 0.87329129 |
   | dynamic advertising elasticity  (beta/1-gamma)             | 1.54992083 |

   It means the total elasticity of the perfume brand assuming infinity carryover should be 1.54992083. 