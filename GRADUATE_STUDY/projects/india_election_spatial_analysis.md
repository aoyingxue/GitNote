## Spatial Analysis in ArcGIS (OLS+GWR)

1. Way to represent **Spatial proximity** (automatically calculated in ArcGIS)

   1. For each point, identify spatial relationship with others

      1. A binary indicator stating whether two points or centroids are within a certain distance of each other (1=yes, 0=no)
      2. **K nearest neighbors**: A binary indicator stating whether point A is one of the ___ (1, 5, 10, 15, etc) nearest neighbors of B (1=yes, 0=no)

   2. Weight/link matrix

      1. pairwise spatial relationships

         ![img](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfqb3cxraig30d307daa0.gif)

2. Process

   1. Data Preparation 

      1. X: 

         1. unique id (demanded by ArcGIS)
         2. party name 
         3. All the related attributes (elector's demo & demo of ac) 
         4. ac-level geometry

      2. Y: vote shares of each party in each constituency (ac-level)

         ![image-20200612175701010](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfqyqzk4sqj31700neae2.jpg)

   2. Run OLS regression model to select important features

      ![image-20200612175044673](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfqyzn8d3hj317c05gt9m.jpg)

      1. Test for spatial autocorrelation in OLS residuals

   3. Run a GWR model (or some other spatial model) for prediction

3. **OLS (ordinary least square)** 

   1. Automatically tests for **non-stationarity** 

      1. The relationship among the data changes based on location.

   2. Tests for **multicollinearity** 

      1. Remove redundant variables and select important features

   3. Only deals with **non-dummy outcome variables**  

   4. Dependent and Explanatory variables should be **numeric** fields containing a variety of values. OLS cannot solve when variables have all the same value. 

      1. *<u>How to deal with party names, gender or caste, etc?</u>* 

   5. The **Unique ID** field links model predictions to each feature. 

      ![image-20200612221605267](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfqyvzrmqdj31400nujxf.jpg)

4. **GWR (geographically weighted regression)** 

   ![Geographically Weighted Regression](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfqyvoxqygj30bo050wem.jpg)

   https://desktop.arcgis.com/en/arcmap/10.3/tools/spatial-statistics-toolbox/geographically-weighted-regression.htm

   1. How GWR works: https://pro.arcgis.com/en/pro-app/tool-reference/spatial-statistics/how-geographicallyweightedregression-works.htm
   2. **Prediction** 

5. Other resources
   1. Spatial analysis in R

      1. Package spdep / sp 

         1. Need to determine **SWM** (Spatial Weights Matrix) manually
         2. Different ways to generate spatial relationship
            1. $g \in {0,1}^{n×n}$ And then count walks (k near neighbors)
            2. Others 

         3. http://zhihu.geoscene.cn/article/3519

https://zhuanlan.zhihu.com/p/63166668

### Demo Results

