# Foundations of Data Science
**Technest 2: Foundations of Data Science (Python)**  
**UC Berkeley's Data 8 course, Spring 2021**  
**Final Grades: A**

All code in this course uses Python.

## Projects and Notebooks

### Hypothesis Testing
This notebook demonstrates how to perform hypothesis testing, a fundamental concept in data science. The following sections provide a detailed walkthrough of different types of hypothesis tests, how to simulate test statistics under the null hypothesis, and how to interpret the results.

#### How to do a Hypothesis Test
1. **Formulate Hypotheses**:
   - Null hypothesis: A completely specified chance model (e.g. "The coin is fair.").
   - Alternative hypothesis: The viewpoint from the question (e.g. "The coin is not fair.").

2. **Define Test Statistic**:
   - Often the difference or absolute difference between group means.
   - Compute the value of the test statistic in your data.

3. **Simulate the Test Statistic under the Null Hypothesis**:
   - Simulate the test statistic many times under the null hypothesis.

4. **Compare Results**:
   - Compare the observed test statistic to its empirical distribution under the null hypothesis.

5. **Draw a Conclusion**:
   - Compare the P-value to the P-value cutoff.

#### Examples of Hypothesis Testing
- **One Sample: One Category (e.g. percent of flowers that are purple)**
  - Test Statistic: empirical_percent, abs(empirical_percent - null_percent)
  - Simulation: sample_proportions(n, null_dist)

- **One Sample: More Than 2 Categories (e.g. ethnicity distribution of jury panel)**
  - Test Statistic: tvd(empirical_dist, null_dist)
  - Simulation: sample_proportions(n, null_dist)

- **One Sample: Numerical Data (e.g. scores in a lab section)**
  - Test Statistic: empirical_mean, abs(empirical_mean - null_mean)
  - Simulation: population_data.sample(n, with_replacement=False)

- **Two Samples: Underlying Values (e.g. birth weights of smokers vs. non-smokers)**
  - Test Statistic: group_a_mean - group_b_mean, abs(group_a_mean - group_b_mean)
  - Simulation: empirical_data.sample(with_replacement=False)

#### Definition of the P-value
- **Formal name**: observed significance level
- **Definition**: The chance (probability) under the null hypothesis that the test statistic is equal to the observed value or is even further in the direction of the alternative hypothesis.

#### Conventions About Inconsistency
- **Inconsistent with the null**: The test statistic is in the tail of the empirical distribution under the null hypothesis.
- **Statistically significant**: The area in the tail is less than 5%.
- **Highly statistically significant**: The area in the tail is less than 1%.

### Example Projects
#### 1. Mendel and Pea Flowers
- **Null Hypothesis**: Each plant has a 75% chance of having purple flowers.
- **Alternative Hypothesis**: The chance is not 75%.
- **Test Statistic**: Empirical percentage of purple flowers.
- **Conclusion**: Fail to reject the null hypothesis. The evidence is not sufficient to reject the claim.

#### 2. Alameda County Jury Panels
- **Null Hypothesis**: The distribution of ethnicities of the jury panels is the same as the eligible jurors.
- **Alternative Hypothesis**: The jury panels are not distributed according to eligible jurors' probabilities.
- **Test Statistic**: Total Variation Distance (TVD).
- **Conclusion**: Reject the null hypothesis. The evidence is sufficient to reject the claim.

#### 3. The GSI's Defense
- **Null Hypothesis**: The section's average score is like a random sample from the whole class.
- **Alternative Hypothesis**: The section's average score is significantly lower.
- **Test Statistic**: Empirical mean of scores.
- **Conclusion**: Fail to reject the null hypothesis. The evidence is not sufficient to reject the claim.

#### 4. Birth Weights of Smokers vs. Non-Smokers (A/B Testing)
- **Null Hypothesis**: The distributions of birth weights of the babies in the two groups are the same.
- **Alternative Hypothesis**: The babies of mothers who smoked weigh less on average.
- **Test Statistic**: Difference between group means.
- **Conclusion**: Reject the null hypothesis. The evidence is sufficient to reject the claim.
