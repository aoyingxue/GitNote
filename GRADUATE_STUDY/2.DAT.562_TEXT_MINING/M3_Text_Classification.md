## Overview 

### Classification Task

- **Objective**: Given k classes, decide to which class a piece of text belongs

### Supervised Machine Learning

- Category (class) labels are available
- Training data
  - The machine learns the association between the labels and features
- Testing data
  - Validate and test the predictive power of the model

### Major Steps

- Feature extraction
  - “Bag-of-words”, TF-IDF, n-grams
- Dimensionality reduction (Feature selection) - classification
- Model training
  - Naïve Bayes Classifier
  - Decision trees / Random forests
  - Support Vector Machines
  - Logistic regression / Logit
  - Deep learning
- Model evaluation
  - Confusion matrix
  - F-score
  - Receiver operating characteristic (ROC) curve

## Feature Selection

### Why do feature selection?

- To find terms that help discriminate between classification categories
- Text data:
  - Come from <u>heterogeneous</u> sources (e.g., different authors for social media posts)
  - Sparse
  - High-dimensional (too many features to begin with)
    - Only a small subset of original features will be used for prediction
    - With too many features and not much data - overfit

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjblgqqa8j30qk07waar.jpg" alt="image-20200405104347413" style="zoom:50%;" />

### How to select features for text classification?

- What is the <u>co-occurrence</u> of terms and classification categories?
  - An <u>un-discriminating</u> feature will be randomly distributed across all categories
- Measures of association between categories and features: (filter methods)
  - Gini index
  - Conditional entropy 
  - Χ^2-statistic

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjbm9sfdjj30ge074gmm.jpg" alt="image-20200405104438217" style="zoom: 50%;" />

### Gini Index

Determine if term j does a good job discriminating between categories 

![image-20200405152110524](https://tva1.sinaimg.cn/large/00831rSTgy1gdjjm14qbpj310g0dkgn0.jpg)

#### The Gini Index for Term *j*

- Take all documents containing a particular term *j*

- How <u>imbalanced</u> is the distribution of categories in that set of documents?

  - A <u>discriminating</u> feature will show <u>imbalance</u>
  - Term j has good discriminating properties and therefore can be a good feature if it creates an imbalanced distribution of class labels for documents that contain term j

- Poorly discriminating feature j: $P(1|j)≈P(2|j)≈...≈P(k|j)≈1/k$

- Perfectly discriminating feature *j*: *P(r|j)=1* for some category r

- **Gini index: $G(j) = 1 - ∑_r[P(r|j)]^2$** 

- Gini=0: it means that the term is perfectly discriminating.

- Gini=1/k: not helpful for classification task at all

  ![image-20200405122018707](https://tva1.sinaimg.cn/large/00831rSTgy1gdjedtxmotj30ic07emyt.jpg)

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjbqswxw4j30mk0cgta1.jpg" alt="image-20200405104859644" style="zoom:50%;" />

> Normalized gini index will replace P with f.

![image-20200405152150440](https://tva1.sinaimg.cn/large/00831rSTgy1gdjjmowulvj30zq0ai0tn.jpg)

### Conditional Entropy

#### Entropy is the measure of “<u>impurity</u>”

-  Define:
  - P(red) is a fraction of red balls
  - P(**black**) is a fraction of black balls
- Entropy in a jar with balls of two colors:
  - E = -P(red) × log2[P(red)] - P(**black**) × log2[P(**black**)]

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjbvub6j4j30lw0a6q7b.jpg" alt="image-20200405105349345" style="zoom:50%;" />

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjbw2tifbj30em0b2gm6.jpg" alt="image-20200405105405126" style="zoom:50%;" />

- Entropy also measures our surprise, or our certainty, in the outcome of a random variable. High entropy means low certainty. 

### Conditional Entropy for Term j

$E(j) = ∑_{h=j,−j} [fh*\{ -P(1|h)*log P(1|h) -...- P(k|h)*logP(k|h)\}]$ 

- Conditional entropy measures how the presence or absence of term j affects our certainty of being able to determine the class label
  - For perfectly discriminating term j, E(j) = 0
  - If term j is not discriminating at all, E(j)= log(k)

## $χ^2-Statistic$ 

### Does term j = *Advertising* help predict the text category?

- Categories r = Marketing, Finance
- Number of documents = 1,000
- 10% of the documents belong to category *r=Marketing*
- Term *j = Advertising* is present in 20% of documents

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjc1ecszzj30i608e3zg.jpg" alt="image-20200405105910509" style="zoom:50%;" />

### What is the observed and expected co-occurrences of term *j* and the category *r*?

- Number of documents = 1,000
- 10% of the documents belong to category *r =* Marketing
- Term *j =* Advertising is present in 20% of documents

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjc2e8bkpj30ie08k0tt.jpg" alt="image-20200405110008089" style="zoom:50%;" />

### The Χ2-statistic

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjc40rzu3j30aq07e3yu.jpg" alt="image-20200405110142160" style="zoom:50%;" />

- What does it mean when the observed co- occurrence is different from the expected one?
- It can signal that term *j* and category *k* are not independent:
  - that is term *j* is predictive of category k
- Χ2-statistic measures the strength of relationship between term j and category k

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjc56x5gnj30v00d0dig.jpg" alt="image-20200405110247481" style="zoom:50%;" />

### The Χ2-statistic (k classes)

- What is the difference between observed and expected co- occurrences of term *j* and the classification categories?

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjc5vnexaj30bc040aa4.jpg" alt="image-20200405110329674" style="zoom:50%;" />

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gdjc64x5n0j30t6052751.jpg" alt="image-20200405110345334" style="zoom:50%;" />

