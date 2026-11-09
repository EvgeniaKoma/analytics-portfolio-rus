# Subscription Pricing A/B Test: Experiment Audit and Revenue Analysis

[Русский](README.md) | **English** · [Portfolio](../README.en.md)

## Business Question

Can an increase in subscription conversion offset the revenue impact of reducing the subscription price?

This project analyzes a pricing experiment in a mobile subscription product, where the price was reduced from 400 to 160 units for new users, with a 50/50 experiment split.

## Data

Synthetic user activity and purchase data covering the periods before and during the experiment.

## Approach

- Audited experiment assignments, user uniqueness, and audience eligibility.
- Checked sample ratio mismatch (SRM), group comparability, and potential experiment conflicts.
- Analyzed subscription and activation conversion using chi-square tests.
- Compared average revenue per user (ARPU) using Welch's t-test and bootstrap.

## Key Findings

- Subscription conversion increased significantly in the treatment group.
- No statistically significant difference in ARPU was detected.
- The absence of statistical significance does not establish ARPU equivalence.
- Experiment duration and the available follow-up period limited the assessment of subscription renewals and longer-term revenue.

## Materials

- [Analysis notebook with saved results](analysis.ipynb)
- [Presentation (PDF)](presentation.pdf)

Educational analytical project using synthetic data. Notebook and presentation are in Russian.
