# Project 1 Report: Rafael Singer and Katie Baek

## 1. Exact F2

| Environment | Time Elapsed | Estimate      |
| ----------- | ------------ | ------------- |
| GCP         | 76s          | 8,567,966,130 |
| Local       | 39s          | 8,567,966,130 |

## 2. Tug-of-War

Parameters: Width: 10, Depth: 3

| Environment | Time Elapsed | Estimate       |
| ----------- | ------------ | -------------- |
| GCP         | 579s         | 10,146,147,119 |
| Local       | 156s         | 10,418,861,797 |

## 3. BJKST

Parameters: Bucket Size: 5200, Trials: 5

| Environment | Time Elapsed | Estimate    |
| ----------- | ------------ | ----------- |
| GCP         | 40s          | 8,763,392.0 |
| Local       | 11s          | 8,646,656.0 |

## 4. Algorithm Comparisons

### BJKST vs. Exact F0

| Algorithm | Environment | Time Elapsed | Estimate    |
| --------- | ----------- | ------------ | ----------- |
| Exact F0  | GCP         | 66s          | 7,406,649   |
| BJKST     | GCP         | 40s          | 8,763,392.0 |
| BJKST     | Local       | 11s          | 8,646,656.0 |

The BJKST Algorithm with 5 trials and a bucket size of 5200 ran significantly faster than the exact F0 calculation, both on GCP (40s vs 66s) and locally. The error rate was approximately 18% on GCP and 17% on local execution, showing consistent accuracy across different environments.

### Tug-of-War vs. Exact F2

| Algorithm  | Environment | Time Elapsed | Estimate       |
| ---------- | ----------- | ------------ | -------------- |
| Exact F2   | GCP         | 76s          | 8,567,966,130  |
| Exact F2   | Local       | 39s          | 8,567,966,130  |
| Tug-of-War | GCP         | 579s         | 10,146,147,119 |
| Tug-of-War | Local       | 156s         | 10,418,861,797 |

Surprisingly, the Tug-of-War F2 approximation took significantly longer to execute than the exact F2 calculation in both environments:

- On GCP: ~7.6x slower (579s vs 76s)
- Locally: ~4x slower (156s vs 39s)

The estimates showed an error rate of approximately 18-21% compared to the exact F2 value. While Tug-of-War provides theoretical benefits for very large datasets, in this implementation it proved less efficient than the exact calculation. This suggests that for datasets of this size, the exact F2 calculation might be the better choice in terms of both accuracy and performance.
