# Financial Statistical Analysis Toolkit

## Overview

A Python-based statistical toolkit designed to apply **descriptive statistics, hypothesis testing, and statistical inference** to financial and economic data.

The project provides reusable statistical functions that can help analyze financial data, test assumptions, compare financial groups, identify significant relationships, and support data-driven economic decisions.

The primary focus is not only calculating statistical measures, but also understanding **what the statistical results mean from a financial decision-making perspective**.

---

## Objective

The objective of this project is to build reusable statistical functions that can be applied to financial datasets such as:

* Stock returns
* Portfolio returns
* Asset prices
* Interest rates
* Inflation
* GDP and economic indicators
* Trading strategies
* Financial risk metrics

The toolkit can be used as a statistical foundation before applying machine learning or quantitative models.

---

## Statistical Components

### 1. Descriptive Statistics

Functions for summarizing and understanding financial data.

Examples:

* Mean
* Median
* Variance
* Standard Deviation
* Range
* MAD (Median Absolute Deviation)
* Skewness
* Kurtosis
* Percentiles
* Z-Score
* Coefficient of Variation

### 2. Hypothesis Testing

Statistical tests for evaluating financial and economic assumptions.

Examples:

* One-sample tests
* Two-sample tests
* Paired tests
* Proportion tests
* Parametric hypothesis tests
* Non-parametric hypothesis tests

### 3. Statistical Inference

Methods for making conclusions about a population using sample data.

Examples:

* Confidence intervals
* Population mean inference
* Difference between means
* Variance inference
* Proportion inference
* Statistical significance

---

## Financial Applications

The statistical functions can be applied to questions such as:

### Stock Return Analysis

> Is the average return of a stock significantly different from zero?

### Strategy Evaluation

> Does Strategy A generate significantly different returns compared with Strategy B?

### Portfolio Analysis

> Is the return of Portfolio A significantly higher than Portfolio B?

### Risk Analysis

> How volatile is an asset's return distribution?

### Market Analysis

> Are two market periods statistically different?

### Economic Analysis

> Is there statistically significant evidence of a change in an economic indicator?

These statistical tests provide quantitative evidence that can support financial and economic decisions.

---

## Example Decision-Making Workflow

```text
Financial / Economic Data
          ↓
Data Cleaning
          ↓
Descriptive Statistics
          ↓
Distribution / Variability Analysis
          ↓
Hypothesis Formulation
          ↓
Statistical Test
          ↓
p-value / Confidence Interval
          ↓
Statistical Decision
          ↓
Financial / Economic Interpretation
```

---

## Example

Suppose we want to determine whether a trading strategy generates a positive average return.

### Hypothesis

```text
H₀: Mean strategy return = 0

H₁: Mean strategy return > 0
```

After performing the statistical test:

```text
p-value < significance level
```

we reject the null hypothesis.

### Financial Interpretation

There is statistical evidence that the strategy's average return is different from zero.

The statistical result can therefore be used as one input when evaluating whether the strategy deserves further financial analysis.

---

## Important Statistical Concepts

The project also emphasizes correct interpretation of:

* Null hypothesis
* Alternative hypothesis
* Significance level
* p-value
* Type I error
* Type II error
* Confidence interval
* Statistical significance
* Practical significance

A statistically significant result does not automatically imply that an investment or economic decision is profitable. Statistical evidence should be combined with financial context, risk, transaction costs, and other relevant factors.

---

## Technologies

* Python
* NumPy
* Pandas
* SciPy
* Matplotlib
* Jupyter Notebook

---


## Key Learning Outcomes

Through this project, I implemented statistical methods from scratch and applied them to financial and economic use cases.

The project demonstrates understanding of:

* Descriptive statistics
* Probability and statistical inference
* Hypothesis testing
* Confidence intervals
* Statistical decision-making
* Financial data analysis
* Interpretation of statistical results

---

## Future Improvements

* Add time-series statistical tests
* Add stationarity tests such as ADF
* Add correlation and dependence analysis
* Add regression-based statistical inference
* Add automated statistical reporting
* Add financial risk analysis
* Add statistical test selection based on data characteristics

---

## Disclaimer

This project is intended for **educational and analytical purposes**.

Statistical significance alone should not be treated as investment advice or as a guarantee of future financial performance.
