## 1.1: What Is Text Mining?

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd34ffp7z9j30o20f8q3r.jpg" alt="image-20200322102640742" style="zoom: 40%;" />

### What is Text Data?

- Text is unstructured data produced by humans to be interpreted by other humans
- Can machines understand text?
- How do we convert unstructured text data into structured data?

### Why do text mining?

##### Unstructured text data are everywhere.

- Commercial contracts 
- Consumer surveys are (almost) all text data
  - Open-ended responses are of great value!
- Exchanges between customer service reps and customers
- News and media reports
- Financial earnings announcements and analyst reports

----------------

- We need to process <u>large volumes</u> of text data
- We can do it at relatively <u>low costs</u>
- Machines can detect latent patterns in the data that even manual analysis may struggle to identify

### Major Tasks in Text Mining

- <u>Classify</u> text documents into predefined categories (**classification**)

- Group text documents based on similarity of content (**clustering**)

- Summarize the meaning of a text document (**summarization**)

- Extract sentiment from text (**sentiment analysis**, emotions)

  <img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd34oy5orij30g00a03z7.jpg" alt="image-20200322103558575" style="zoom: 33%;" /> 

### Statistical Algorithms

- Many supervised and unsupervised machine learning algorithms are commonly used for both text data and numeric data:
  - Support Vector Machines, Naïve Bayes, decision trees, K-means clustering, etc.
- Some specialized text mining techniques:
  - <u>Latent Dirichlet Allocation</u> for **<u>topic modeling</u>**
  - Word embedding for text similarity

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd37euz539j30g80e8whh.jpg" alt="image-20200322121003984" style="zoom:40%;" /> 

## 1.2: Example: Loan Defaults

### How to Predict a Default on a Loan?

#### Typical data in an application:

- Financial strength (e.g., FICO score, income, debt, credit history)
- Demographics (e.g., gender and location)
- Loan details (e.g., amount and interest rate)

### What might a personal note reflect?

- Personality and mental states

  (1) word usage and writing styles are indicative of some **stable** inner traits as well as more **transient** states

  (2) these traits and states affect people’s financial behaviors

- Forward-looking information, future intensions

### Does an applicant’s written note help predict a loan default?

- Addition of text into a predictive model for loan defaults improves its performance by <u>almost 3%</u> 
- Text alone demonstrates a comparable predictive power to a “standard” model based on financial scores and other typical information

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd3dfofys3j30im0ge40r.jpg" alt="image-20200322153826751" style="zoom:50%;" />

>  straight line: 50% possibility

### Word clouds

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd3djfgyt1j31k50u04qd.jpg" alt="image-20200322154202129" style="zoom:50%;" />



## 1.3: Example: Toyota vs. Volvo

### Lift 

Lift is the ratio of the actual share of messages containing co-occurrences of two terms to the share we would expect to see if the two terms were distributed independently.

#### Compute the lift between terms A and B:

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd3dpotkj5j30cs03awf3.jpg" alt="image-20200322154804650" style="zoom:40%;" />

where:

- P(A) is the share of messages where term A occurs
- P(B) is the share of messages where term B occurs
- P(A,B) is the actual share of messages where both A and B co-occur

##### If Lift > 1:

- Terms A and B appear together more often than one would expect by mere chance
- Consumers associate term A and term B

#### Computing Lifts

###### **Step 1.** Compute the share of all messages with occurrence of a car model term for each brand:

![image-20200322154922178](https://tva1.sinaimg.cn/large/00831rSTgy1gd3dr0zltnj30o0078mxu.jpg)

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd3dr6xqe7j30ey086wf3.jpg" alt="image-20200322154932847" style="zoom:50%;" />

###### **Step 2.** Compute the observed share of all messages with co-occurrence of a car model and safety features for each brand:

<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gd3drlcsyzj30fg060jrx.jpg" alt="image-20200322154956391" style="zoom:50%;" />

###### **Step 3a.** Compute the share of all messages that mention Safety Terms: 

P(Safety) = 397 / 35,139 = 0.0113

###### **Step 3b.** Compute lifts: 

Lift(Safety, VolvoS40) = 0.0005 / (0.0165 x 0.0113) = **2.75**

Lift(Safety, Toyota Camry) = 0.0109 / (0.9835 x 0.0113) = **0.97**

## 1.4: Balto: Interview with CEO Marc Bernstein

