# Week 3 - Hypothesis Testing and Inferential Statistics

## 1. Inferential statistics 
**Descriptive statistics** summarise the data you have.<br>
Examples: mean, median, standard deviation, graphs.
**Inferential statistics** use a sample to say something about a population.<br>
Examples: confidence intervals, t-tests, chi-square tests, ANOVA.

## 2. Standard error of the mean 
**Standard error (SE)** as a measure tied to sample size and reliability. The key idea is:<br>
- **Standard deviation (SD)** tells you how spread out the raw data are.
- **Standard error (SE)** tells you how precise your sample mean is as an estimate of the population mean.

A formula to know:
```R
SE = SD / sqrt(n)
```
If sample size `n` gets bigger, the denominator gets bigger so the **SE gets smaller**.<br>
That means the estimate becomes **more stable and more reliable**.<br>
This links that larger sample sizes improve reliability.<br>

**SD** = spread of the data<br>
**SE** = precision of the mean<br>

## 3. Confidence intervals
A confidence interval example on a mean and standard error, showing how a 95% confidence interval can be built around the sample mean:
``` R
95% CI = mean ± 1.96 * SE
```
A **95% confidence interval** gives a plausible range for the population mean.

If mean = 75 and SE = 3, then:
```R
75 ± (1.96 * 3)
75 ± 5.88
```
The CI is:
```R
69.12 to 80.88
```
Therefore 95% confident that the population mean lies between 69.12 and 80.88.

## 4. Hypothesis testing
A standard structure:
- **H0 (null hypothesis)**: no difference / no effect
- **H1 (alternative hypothesis)**: there is a difference / effect
- choose alpha, usually **0.05**
- calculate a test statistic and p-value
- if **p < 0.05**, reject H0

An example, question: "Are dogs faster than mice?"
- **H0**: dogs are not faster than mice
- **H1**: dogs are faster than mice

Basic flow:
1. State the hypotheses
2. Check assumptions
3. Choose the correct test
4. Run the test
5. Interpret the p-value
6. Write the conclusion properly

## 5. P-value
Evidence against the null hypothesis and shows the decision rule **p < 0.05**. A t-test example where a p-value of 0.01 is considered statistically significant.<br>
A p-value is the probability of getting results at least this extreme **if the null hypothesis were true**.

## 6. Choosing the right test
Should first check assumptions like **normality** and variance before choosing a **parametric** or **non-parametric** test.<br>

Summary:
- Compare **two means**, normal data, independent groups -> **independent t-test**
- Compare **two means**, same people before/after -> **paired t-test**
- Data not normal for two groups -> **Mann–Whitney U** or **Wilcoxon signed-rank**, depending on design
- Compare **proportions / counts -> chi-square**
- Compare **more than two means -> ANOVA**.

## 7. Normality testing
The **Shapiro-Wilk test** states that:
- **H0**: data are normally distributed
- **H1**: data are not normally distributed
```R
shapiro.test(x)
```
`p > 0.05 ->` no strong evidence against normality
`p < 0.05 ->` evidence the data are not normal
Helps decide whether a parametric test like a t-test is appropriate.

## 8. Type I and Type II errors
Type I error:<br>
You say there is a significant effect when there really is none.<br>
This is a **false positive**.

Type II error:
You fail to detect a real effect.<br>
This is a **false negative**.

- **Type I** = "I found something that isn’t really there"
- **Type II** = "I missed something that really is there"

## 9. Statistical power
Power as the probability of getting a significant result when the alternative hypothesis is actually true and gives the expression:
```R
power = 1 - beta
```
Where beta is the probability of a Type II error.<br>

What affects power / Power increases if: 
- increase sample size
- use a higher alpha
- use a one-sided test

Low power means you may miss real effects.<br>
That is why larger samples matter so much in experiments and why the simulation practical is important.

## 10. Effect size
**Cohen’s d** and the usual interpretation:
- small = 0.2
- medium = 0.5
- large = 0.8

Formula:
```R
d = abs(mean1 - mean2) / pooled_sd
```
Why effect size matters:<br>
A p-value tells you whether an effect is statistically significant.<br>
An effect size tells you whether the effect is **small or large in practical terms**.

Distinction is important:
- a tiny effect can be significant with a huge sample
- a meaningful effect might fail to reach significance with a very small sample