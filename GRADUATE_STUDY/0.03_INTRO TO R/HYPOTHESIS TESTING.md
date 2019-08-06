# I. Elements of Hypothesis Testing

## 7 Step Process of Testing

### Step 1: Null Hypothesis (H0) 零假设

> 零假设的内容一般是希望能证明为错误的假设，与零假设相对的是[备择假设](https://zh.wikipedia.org/w/index.php?title=备择假设&action=edit&redlink=1)（或**对立假设**），即希望证明是正确的另一种可能。从数学上来看，零假设和备择假设的地位是相等的，但是在统计学的实际运用中，常常需要强调一类假设为应当或期望实现的假设，例如在相关性检验中，一般会取“两者之间无关联”作为零假设，而在独立性检验中，一般会取“两者之间非独立”作为零假设。
>
> 如果一个统计检验的结果**拒绝**零假设（结论不支持零假设），而实际上真实的情况属于零假设，那么称这个检验犯了[第一类错误](https://zh.wikipedia.org/wiki/第一类错误)。反之，如果检验结果支持零假设，而实际上真实的情况属于备择假设，那么称这个检验犯了[第二类错误](https://zh.wikipedia.org/wiki/第二类错误)。通常的做法是，在保持第一类错误出现的机会在某个特定水平上的时候（即[显著性差异值](https://zh.wikipedia.org/wiki/显著性差异)或α值），尽量减少第二类错误出现的概率。
>
> [https://zh.wikipedia.org/wiki/%E9%9B%B6%E5%81%87%E8%AE%BE]: 	"Wiki"

- Population Parameters: numerical values that describe population

- Status quo: 现状 = Traditional Belief 传统结论

### Step 2: Alternate Hypothesis (H<sub>a</sub>) 备择假设

- Opposite Statement: 最终会在两个假设中选择其一	
- Research Hypothesis: 备择假设的另一个名字
- state new ideas
- Evidence from Sample Data

### Step 3: Choose Significance Level (𝛂)

- Probability (Pr) of Rejecting the Null Hypothesis when in fact the Null Hypothesis is True

- 这个错误名叫 **Type 1 Error**

- **𝛼**=Pr (Type 1 Error)

- 一般会选择小的数字作为pr：0.05/0.1/0.01

### Step 4: Calculate Test Statistics

- Evidence from Sample Data (support the null or alternate)
- t<sub>calc.</sub>, Z<sub>calc.</sub>, F<sub>calc</sub> (根据不同的population parameter)
- (Point Estimate – Hypothesized Value（在第一步里找到的）)/Standard Error (SE)

### Step 5: Rejection Rule

- looking for clear evidence to reject the Null Hypothesis

### Step 6: Make the Decision

- **Either Reject or Accept** the Null Hypothesis
- Note: not **ACCEPT** but **FAIL** to Reject（注意说辞）
- 就像刑法系统一样，At the end of a trial they either find enough evidence to prove the guilt or they don't have the required evidence to prove the guilt. Therefore they either declared guilty or not guilty. They will never declare that the person is innocent.
- 所以 we never accept the null hypothesis. By default the null hypothesis is true unless there is overwhelming evidence to rejected. 

### Step 7: Conclusion

- Simple Language
- Written about the alternate hypothesis
- State significance level 唯一的tech部分
- 结论只需要提到同不同意alternate就行了

练习：



## II. Concept - Hypothesis Testing for Slope

