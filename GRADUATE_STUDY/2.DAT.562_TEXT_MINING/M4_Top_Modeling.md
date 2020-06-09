## Introduction

### Topics

- A "topic" is a cluster of words that frequently occur together
- Topic do not have names, topic labels are created by humans
  - The order of the words reflect their <u>frequency</u> 
- Different “topics” can have words in common 

<img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqo4ryrxgj30m40gcgum.jpg" alt="image-20200411191628972" style="zoom:50%;" />

## Latent Dirichlet Allocation (LDA)

**An approach to topic modeling: Discovering and describing topics in documents** 

- <u>Latent</u> means <u>unobserved</u> by the analyst:
  - Distribution of topics in a document is latent
  - Distribution of words in a topic is latent, too
- Dirichlet is a probability distribution:
  - Both topics in a document and words in a topic are assumed to follow Dirichlet distributions
- Allocation means finding the topics in documents and words in topics
- The Latent Dirichlet Allocation (LDA) approach to topic modeling assumes that the number of topics is known 

![image-20200411192218071](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqoat7sytj31ki0p84go.jpg)

## The Dirichlet <u>Distribution</u>

#### Simplex 

All probabilities are above 0 and add to 1. 

#### The Dirichlet Distribution

- Probability distribution over simplexes (“distribution over distributions”)

<img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqssghxr8j30k20dugp6.jpg" alt="image-20200411215738929" style="zoom:50%;" />

- K: length of the simplex x
- All x add up to 1

![image-20200411220307534](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqsy3k3arj30ik0fcgsu.jpg)

- Sample A: little variation, pretty close to the sample mean; not much variation between elements of each vector
- **Sample B**: the same sample mean as sample a; variation across rows is very large; **large difference** between elements of each row; **sparsity** 
  - **A sparse vector is a vector with zero-valued elements**  
  - **Dirichlet parameter 𝛼 < 1 will induce sparseness**  
- Sample C: the sample mean and each row shows that the first number is always smaller than the 2nd number; the sample variance is very low

![image-20200411222029789](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqtg6qlvrj312c0n6k3u.jpg)

#### Conclusion

- We will use this distribution to model the distribution of topics in documents and distribution of words in topics
- The support of the distribution are simplexes:
  - vectors [x1, …,xn], xi≥0, all xi sum to 1.
- The distribution is described by parameter vector 𝛼 = [𝛼1,…, 𝛼n]
  - Hyperparameter, i.e. we set its value
  - Set 0<𝛼k<1 to induce sparsity 

## Latent Dirichlet Allocation (LDA)

![image-20200411223813247](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqtym5dsoj319o0km19j.jpg)

- Topics are not in the document. They are latent and need to be inferred. They need allocation to be done by a machine. 

![image-20200411230113329](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdqumk0x5aj316a0gethh.jpg)

- Total =1
- Allocate based on the probability to use the word in each topic

![image-20200411230440482](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdquq59fnij317s0h6qdh.jpg)

- 20% of the words will be distributed to topic 1, and 80% to topic 2.

#### Results: 

<img src="/Users/aoyingxue/Library/Application%20Support/typora-user-images/image-20200411230750776.png" alt="image-20200411230750776" style="zoom:50%;" />

A human decides on the number of topics in the Latent Dirichlet Allocation (LDA) topic model

## Evaluation

### What is a good topic model?

- Topics are coherent
- Topic assignment to documents makes sense

### How to evaluate a topic model?

- Human-centric methods: 
  - Storytelling
  - Topic intrusion and word intrusion
- Formal metrics:
  - Log-likelihood score
  - Perplexity metric 
  - Topic coherence metric

### Storytelling

Human judgement is crucial

<img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gdquxxs81uj30sg0kyall.jpg" alt="image-20200411231209660" style="zoom:50%;" />

### Word Intrusion 

- Introduce an **intruder** word
- Can a human reliably tell which word is an intruder? 
  - If yes, the topic is topically coherent (good)
  - If no, the topic has no discernible theme (bad)

<img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gdquyucktwj30jw0ek0zv.jpg" alt="image-20200411231302580" style="zoom:50%;" />

### Topic Intrusion

- Look at the document and four topics:
  - Three of the topics are the highest probability topics assigned to that document 
  - The fourth topic (“intruder”) is chosen randomly from the low-probability topics

<img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1gdquzlhmxoj30jy0e6grr.jpg" alt="image-20200411231345943" style="zoom:50%;" />

### Formal metrics

- Log-likelihood score:
  - Maximize the probability of observed text
  - Higher value are better
- <u>Perplexity</u> (“confusion”) metric:
  - The universe of the probability to observe a sample text, normalized by the number of words in that text
  - Minimize the amount of perplexity
  - <u>Lower values are better</u>
- Topic <u>coherence</u> metric: (it's the best)
  - “sky”, “blue”, “birds”, ”sun” are frequently used together
  - Maximize average coherence across topics
  - <u>Higher values are better</u>

### What defines an LDA topic model performance?

- Selected number of topics
  - If number of topics is too small, you'll be forcing topics to forge or combine, creating topic incoherence
  - If number of topics is too large, topics might be too similar to each other
- Dirichlet hyperparameters 𝝰 and 𝛃
  - Do documents combine many topics or do topics vary a lot between documents?
- Some technical parameters related to estimation algorithms 

Generative: means it simulates how the human works