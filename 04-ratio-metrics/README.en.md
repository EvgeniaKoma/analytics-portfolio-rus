# CTR Experiment Analysis: Comparing Methods for Ratio Metrics

[Русский](README.md) | **English** · [Portfolio](../README.en.md)

## Business Question

How should the required sample size and experiment results be evaluated when the target metric is a ratio, such as click-through rate (CTR)?

CTR is calculated as total clicks divided by total views.

## Data and Experiment Setup

Synthetic data for a CTR experiment.

Sample size planning assumptions:

- Relative minimum detectable effect (MDE): 10%
- Significance level: 5%
- Target statistical power: 80%
- Control/treatment allocation: 90/10

## Approach

Compared four methods for sample size estimation and experiment analysis:

- Delta method
- Linearization
- Poisson bootstrap
- Bucketization with Welch's t-test

Bootstrap and bucketization sample size simulations used 1,000 iterations per evaluated sample size. The simulation setup included 1,000 bootstrap reweightings per iteration and 50 buckets per group for bucketization.

## Key Findings

### Required Sample Size

| Method | Control | Treatment | Total users |
|---|---:|---:|---:|
| Delta method | 2,901 | 323 | 3,224 |
| Linearization | 2,901 | 323 | 3,224 |
| Poisson bootstrap | ≈3,600 | ≈400 | ≈4,000 |
| Bucketization | ≈4,950 | ≈550 | ≈5,500 |

The delta method and linearization produced the same analytical sample size estimate. In the saved simulations, bootstrap required a somewhat larger sample, while bucketization showed lower statistical power.

For Poisson bootstrap, estimated power at 3,500 users was just below 80%; 4,000 was the first evaluated sample size above the target in the saved run. Simulation estimates are approximate and depend on the evaluated sample-size grid and random variation. Control/treatment counts for the simulations are approximate allocations.

![Poisson bootstrap: estimated power by total sample size](figures/bootstrap-power.png)

![Bucketization: estimated power by total sample size](figures/bucketization-power.png)

### Experiment Results

Observed CTR:

- Control: 31.04%
- Treatment: 32.66%
- Difference: approximately +1.62 percentage points, or +5.2% relative

| Method | p-value |
|---|---:|
| Delta method | 0.0915 |
| Linearization | 0.1107 |
| Poisson bootstrap | 0.0976 |
| Bucketization | 0.4088 |

None of the methods detected a statistically significant difference at the 5% significance level.

The observed relative uplift was below the 10% MDE used for sample size planning. A nonsignificant result does not establish equivalence between the groups.

## Materials

- [Analysis notebook with saved results](analysis.ipynb)

Educational analytical project using synthetic data. Notebook and figure labels are in Russian.
