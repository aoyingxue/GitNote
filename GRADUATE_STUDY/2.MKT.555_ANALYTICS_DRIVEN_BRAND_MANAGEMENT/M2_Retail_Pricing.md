## Pricing Decision Support Systems

- Data:Weekly,store-level supermarket scanner data for refrigerated orange juice.
- Decision Problem: Retail pricing recommendations for retailer using transaction data.

### Data

- Data comes from optical scanners which record all purchases. Originally installed for inventory tracking.
- Additionally information about in-store promotions and out-of-store advertising is provided.
- 33 UPCs or individual product types, reduced to top five groupings of products.
- Focus on each store separately.

![image-20200330114204525](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfka35idj30x00ksjvl.jpg)

![image-20200330114257508](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfl3k20sj30yy0jedha.jpg)

## Scan\*Pro Demand Model

- Relate movement of each product to its price changes 
- Consider prices of other products within the category
- Estimate the effects of feature ads and in-store displays

![image-20200330114517774](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfnjgtgcj313m0dcjt2.jpg)

![image-20200330114648327](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfp4997ij30sk06oaez.jpg)

## Price Optimization

- Most managers use **<u>heuristics</u>**
  - e.g., <u>Constant price markups</u> (25% over cost).
  - Price 5% below geographically nearest competitor.
  - 20% discount for the store-brand versus the national brand.
  - Influenced by representatives from Coca Cola or Pepsi.
- Algorithmic approach to price optimization
- Can solve problem analytically (for single product) or numerically (for multiple products).

### Price Optimization with 1 Brand

- Scan\*Pro Demand Model: ln(*q*)= *α* + e ln(*p*)
- Price Elasticity: <img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdcfr1fflyj30a4046dfx.jpg" alt="image-20200330114840047" style="zoom:33%;" /> (percentage change in sales/perc change in price: 交叉)
- Retail Profit: *Retail Profit* = *q* (*p* - *c*)
  - q: sales; how many units sold
  - P-c: profit margin associated with selling each unit
- Using calculus we can find the **optimal price**: (maximize the equation above) (because this is only 1 brand so the markup rule works) ![image-20200330114958531](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfseo54uj30lq062wey.jpg)

### Price Optimization with 2 Brands

The 1st brand's sales not only depend on the 1st brand price, but also the 2nd brand's price. Vice versa. (Own-price elasticity, cross-price elasticity)

![image-20200330115040439](https://tva1.sinaimg.cn/large/00831rSTgy1gdcft55utlj30pc0l6tb0.jpg)

#### Implications

- Suppose the 2 brands are <u>substitutes</u>, then if the retailer <u>raises</u> the price of brand A,
  - Consumers buy less of A but buy more of B, which lessens the blow of the price increase on A.
- Suppose the 2 brands are <u>complements</u>, then if the retailer <u>lowers</u> the price of brand A,
  - Consumers buy more of A and also buy more of B, which increases the attractiveness of the price decrease on A.

### Price Optimization with 3 Brands

![image-20200330115507573](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfxs23ghj311y0keq5u.jpg)

#### Easier Way

![image-20200330115702332](https://tva1.sinaimg.cn/large/00831rSTgy1gdcfzreffdj30uq0gqjt0.jpg)

### Price Optimization with 5 Brands – Easier Way

![image-20200330153441037](https://tva1.sinaimg.cn/large/00831rSTgy1gdcma7tgz6j316a0q8gox.jpg)

## How do price elasticities vary across stores within the chain?

![image-20200330153412251](https://tva1.sinaimg.cn/large/00831rSTgy1gdcm9qmidrj31ah0u0amd.jpg)

It will help to open a new store. 

## Lab

When estimating ScanPro model, if one var’s coefficient is insignificant, shall we re-run a new regression without that variable? Or shall we simply deem that coefficient as 0?

> Manageable coefficients in total, enough data to rely on. Pretend the coefficient as 0 and no need to re-run the model. 
>
> Feature is 0 or 1. Impact or not. 