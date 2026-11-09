# A/A and A/B Simulations: Calibration, Power, and Sample Size

[Русский](README.md) | **English** · [Portfolio](../README.en.md)

## Objective

Evaluate statistical test calibration under the null hypothesis and assess how sample size affects the power to detect a conversion uplift.

## Data and Experiment Setup

Synthetic data with a baseline conversion probability of 10%.

- Users were assigned to groups using salted MD5 hashing with a 50/50 allocation.
- A/A simulations tested the behavior of statistical methods when no treatment effect was present.
- A/B simulations introduced an increase in conversion from 10% to 11%, equivalent to a 1 percentage point absolute or 10% relative uplift.

## Approach

- Simulated 1,000 iterations to examine p-value distributions.
- Compared chi-square tests, Welch's t-test, Mann–Whitney U test, and bootstrap.
- Used the Kolmogorov–Smirnov test to examine uniformity of A/A p-values.
- Estimated statistical power across different sample sizes.

## Key Findings

### A/A Calibration

The simulations did not detect significant deviations from uniform p-value distributions for the four tested methods at the 5% significance level.

| Method | Kolmogorov–Smirnov test p-value |
|---|---:|
| Chi-square | 0.7346 |
| Welch's t-test | 0.7276 |
| Mann–Whitney U | 0.7332 |
| Bootstrap | 0.6034 |

![A/A simulation: p-value distributions for the four methods](figures/aa-pvalues.png)

### A/B Statistical Power

In the saved simulation results, the methods produced similar power curves.

- At 20,000 users in total, estimated power was approximately 63–65%.
- Approximately 30,000 users in total were needed to reach 80% power for the simulated uplift, or about 15,000 users per group.

These are approximate results read from the saved simulation plot.

![Estimated statistical power by total sample size](figures/ab-power.png)

## Materials

- [Analysis notebook with saved results](analysis.ipynb)

Educational analytical project using synthetic data. Notebook and figure labels are in Russian.
