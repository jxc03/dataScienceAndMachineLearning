# Week 3 - Hypothesis Testing and Inferential Statistics

## Main ideas
Focused on using sample data to make conclusions about populations. Key topics included standard error, confidence intervals, hypothesis testing, p-values, statistical power, effect size and outliers.

## Key concepts
- Inferential statistics help estimate population patterns from sample data.
- Standard error shows how precise the sample mean is.
- Confidence intervals provide a plausible range for the population mean.
- Hypothesis testing compares a null hypothesis against an alternative hypothesis.
- A p-value below 0.05 is usually treated as statistically significant.
- Power is the probability of detecting a true effect.

## Useful R functions
`mean()`, `sd()`, `sqrt()`, `t.test()`, `shapiro.test()`, `scale()`, `boxplot()`, `IQR()`, `power.t.test()`

## Reflection
Seeing how larger sample sizes make estimates more stable and improve power. The simulation practical helped connect theory with repeated experiments in R.

### 1. Inferential statistics 
**Descriptive statistics** summarise the data you have.<br>
Examples: mean, median, standard deviation, graphs.
**Inferential statistics** use a sample to say something about a population.<br>
Examples: confidence intervals, t-tests, chi-square tests, ANOVA.

### 2. Standard error of the mean 
**Standard error (SE)** as a measure tied to sample size and reliability. The key idea is:<br>
- **Standard deviation (SD)** tells you how spread out the raw data are.
- **Standard error (SE)** tells you how precise your sample mean is as an estimate of the population mean.

A formula to know:
```
SE = SD / sqrt(n)
```

If sample size n gets bigger, the denominator gets bigger so the SE gets smaller.<br>
That means the estimate becomes more stable and more reliable.<br>
This links that larger sample sizes improve reliability.<br>

SD = spread of the data<br>
SE = precision of the mean<br>