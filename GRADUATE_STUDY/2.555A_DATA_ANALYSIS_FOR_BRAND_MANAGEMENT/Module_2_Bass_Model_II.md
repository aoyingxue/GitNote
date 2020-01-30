### 2.1 Quarterly Forecast vs. Yearly

#### How do we forecast quarterly instead of yearly?

Scale the M, p, q

![image-20200117093620346](Module_2_Bass_Model_II.assets/image-20200117093620346.png)

Quarterly aggregated forecast to get annually forecast would be discrepancy

Monthly: divided by 12

### 2.2 Product Analogs

Parameters were precisely calculated for different analogs, so identifying analogs for products is important.  

Weights (**3 steps**)

1. How similar it is compared to your product (product similarity 1-10)
   1. ![image-20200117100741791](Module_2_Bass_Model_II.assets/image-20200117100741791.png)
2. How consumer reactions are similar when compared to how consumer reactions were when these products were launched (market similarity 1-10)
3. Give weights to the two types of similarity scores

![image-20200117101311068](Module_2_Bass_Model_II.assets/image-20200117101311068.png)

Weights has to be added to 1, so normalize the final scores

![image-20200117101434170](Module_2_Bass_Model_II.assets/image-20200117101434170.png)

Calculate the final p and q for these categories

![image-20200117101528763](Module_2_Bass_Model_II.assets/image-20200117101528763.png)

### 2.4 No Analogs Case

**Estimate p**: from the top to the bottom

![image-20200117101851384](Module_2_Bass_Model_II.assets/image-20200117101851384.png)

Best case - worst case - estimate (interval)

<img src="Module_2_Bass_Model_II.assets/image-20200117102020663.png" alt="image-20200117102020663" style="zoom:33%;" />

Just to make the new users easier but 3 steps are enough.

**Estimate q**: bound is 1 so if calculate out some number more than 1, then it's 1

![image-20200117102431141](Module_2_Bass_Model_II.assets/image-20200117102431141.png)

![image-20200117102536200](Module_2_Bass_Model_II.assets/image-20200117102536200.png)

### 2.5 Market Potential Estimation

#### **Estimating M**: 

- **The Chain Ratio method**: Identify various precedents that need to be in place for product adoption, and try to come up with conversion **probabilities** from one precedent condition to the next condition.
- **Survey Research**: Purchase Intention scales.

![image-20200117104448782](Module_2_Bass_Model_II.assets/image-20200117104448782.png)

### 2.7 Real-World Examples

##### Instagram’s worldwide monthly active users

1. Can be used not only product goods, but also durable or endurable products, or services
2. ![image-20200117105413513](Module_2_Bass_Model_II.assets/image-20200117105413513.png)

##### Snapchat’s daily active users (millions)

1. Quarterly also the same shape
2. Usually different region
3. ![image-20200117105422368](Module_2_Bass_Model_II.assets/image-20200117105422368.png)

##### Twitter’s worldwide monthly active users

1. Cumulative curve; also s-shaped
2. Monthly data
3. Whether use monthly data ... same
4. ![image-20200117105431047](Module_2_Bass_Model_II.assets/image-20200117105431047.png)

##### Music Album Sales (Physical and Digital) in the United States

1. Current adoption curve bell-shaped
2. ![image-20200117105439562](Module_2_Bass_Model_II.assets/image-20200117105439562.png)

##### Number of On-Demand Music Streams (Audio and Video) in the United States

1. Streaming increase so album sales drop down
2. Growing phase of bass model
3. ![image-20200117105450222](Module_2_Bass_Model_II.assets/image-20200117105450222.png)

##### Netflix’s Worldwide Streaming Subscribers

1. Growing phase of s-shaped
2. ![image-20200117105459124](Module_2_Bass_Model_II.assets/image-20200117105459124.png)

##### Vinyl LP Unit Sales in the United States

1. Steep uptake
2. ![image-20200117105507267](Module_2_Bass_Model_II.assets/image-20200117105507267.png)

##### The Slow Goodbye of Apple iPod

1. It grew it matured and it's close to dead.
2. ![image-20200117105518053](Module_2_Bass_Model_II.assets/image-20200117105518053.png)

##### Global shipments Smartphone Models in Q1-2018

1. In order to forecast **brand sales**, bass model is necessary but not sufficient. It gives the answer of how many units of the product category would sell. But also need the answer of how much of the share would my brand take (<u>logistic</u> regression)
2. ![image-20200117111431516](Module_2_Bass_Model_II.assets/image-20200117111431516.png)

### 2.9 Accounting for Replacements in the Bass Model

- ##### Product is never repeat purchased: Sales Curve is the Adoption Curve. (Very durable)

  - Sales(t) = the number of adoptions for the first time (N(t))
  - Sales curve is the same as the adoption
  - <img src="Module_2_Bass_Model_II.assets/image-20200117112021711.png" alt="image-20200117112021711" style="zoom:33%;" />

- ##### Product repeat purchased in every period after adoption: How would the sales curve look?

  - Computer memory chip (intel): business rely on DRAM microprocessors 
  - The ones who bought before will buy again, so sales(t)=A(t), already adoptions
  - <img src="Module_2_Bass_Model_II.assets/image-20200117112354854.png" alt="image-20200117112354854" style="zoom:25%;" />

> Think of a product that's intermediate between these two types of new products. It's a new product that is repeat purchased. It's not like washing machine, but it's not repeat purchased as fast as the DRAM chip. Now, what is such a product? Automobiles. In US, an average American  replaces their automobile once every ten years. So the replacement is every 10 periods. How do you predict sales? What would the curve look like? 

### 2.10 Motivating the Continuous Bass Model

#### In discrete time (incorrect, easier to explain)

![image-20200117114035719](Module_2_Bass_Model_II.assets/image-20200117114035719.png)

#### In continuous time (1st order differential equation) (correct)

![image-20200117114048588](Module_2_Bass_Model_II.assets/image-20200117114048588.png)

##### Answer: <img src="Module_2_Bass_Model_II.assets/image-20200117114201092.png" alt="image-20200117114201092" style="zoom:33%;" /> 

Can be forecasted every second

### 2.11 The Continuous Bass Model & How to Estimate p, q, M

![image-20200117114309890](Module_2_Bass_Model_II.assets/image-20200117114309890.png)

-  Discrete: recursive, you have to calculate one after one
- Continuous: only plug in the time you need to forecast

Will be the same when we use a quarter or yearly p/q

![image-20200117114754134](Module_2_Bass_Model_II.assets/image-20200117114754134.png)

![image-20200117114816934](Module_2_Bass_Model_II.assets/image-20200117114816934.png)

to minimize SSE

> Bayesian updation (if have one year data but don't want to use analogical solution): based on one year of data and update it; use the second year data and update it again; and then in a few years, p, q, M stay steady. 

### 2.12 Generalized Bass Model (GBM) 

![image-20200117115207577](Module_2_Bass_Model_II.assets/image-20200117115207577.png)

Stuff: marketing action of the product (in this case = price)

![image-20200117115137824](Module_2_Bass_Model_II.assets/image-20200117115137824.png)

b: additional parameter (price sensitivity, <0)

<img src="Module_2_Bass_Model_II.assets/image-20200117115430236.png" alt="image-20200117115430236" style="zoom:25%;" /><img src="Module_2_Bass_Model_II.assets/image-20200117115501566.png" alt="image-20200117115501566" style="zoom:25%;" /><img src="Module_2_Bass_Model_II.assets/image-20200117115517645.png" alt="image-20200117115517645" style="zoom:25%;" />

In GBM, you will get the same adoption in period 2 as you would get in period 3 under the continuous bass model. Because prices decreased and those who would adopt in period 3 accelerate their adoption in period 2. 

#### Price & advertising

![image-20200117120542747](Module_2_Bass_Model_II.assets/image-20200117120542747.png)

b1<0: price sensitivity

b2>0: advertising sensitivity of consumers 

![image-20200117120746498](Module_2_Bass_Model_II.assets/image-20200117120746498.png)

----------------

### Lab

<img src="Module_2_Bass_Model_II.assets/image-20200117151344889.png" alt="image-20200117151344889" style="zoom:40%;" />

<img src="Module_2_Bass_Model_II.assets/image-20200117151402983.png" alt="image-20200117151402983" style="zoom:40%;" />

- Time & actual_sales: real data
- Salespred: marketer cares about this, it's the prediction (forecast); default: only forecast 5 years, other than that you have to do it yourself. 
- Actual_cum_sales: A
- Cum_salespred: $\hat{A}$ 

<img src="Module_2_Bass_Model_II.assets/image-20200117151621983.png" alt="image-20200117151621983" style="zoom:40%;" />

- Purple: N(t)
- Predicted: $\hat{N}(t)$ 
- Well explained by bass model; can believe the predictions; can calculate $R^2$ to prove its credibility 

#### Generalized bass model

<img src="Module_2_Bass_Model_II.assets/image-20200117152424505.png" alt="image-20200117152424505" style="zoom:40%;" />

Price parameter is definitely negative

When making forecast, you have to determine next year's price before forecast N(t) because the price will affect the prediction. 