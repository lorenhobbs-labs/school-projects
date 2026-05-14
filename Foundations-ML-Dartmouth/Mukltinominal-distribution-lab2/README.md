# Categorical MLE Analysis: Die Roll Fairness

An engineering and statistical evaluation calculating the Maximum Likelihood Estimation (MLE) for categorical data. This project analyzes a dataset containing rolls of an unknown multi-sided die to reconstruct its properties and determine if the underlying generator is statistically fair.

## 📊 Overview & Methodology

The project models the problem using a **categorical distribution** (a single multinomial trial). Given \(N\) trials and \(K\) possible outcomes, the log-likelihood function is formulated as:

\[\ell(\boldsymbol{\mu}) = \sum_{k=1}^K m_k \ln \mu_k\]

Where:
* **\(K\)**: Number of distinct categories (sides of the die).
* **\(N\)**: Total number of trials (total rolls).
* **\(m_k\)**: Observed parameter count for face \(k\).
* **\(\mu_k\)**: Probability of landing on face \(k\).

Using optimization via **Lagrange Multipliers** subject to the probability constraint \(\sum_{k=1}^K \mu_k = 1\), the analytic Maximum Likelihood Estimator for any individual face reduces to the empirical frequency:

\[\hat{\mu}_k = \frac{m_k}{N}\]

---

## 🔬 Experiment Metrics & Finding Summary

Based on the empirical evaluation executed within the notebook on the `die_rolls.csv` dataset, the metrics conclude the following parameter values:

* **Number of Sides (\(K\)):** 20 sides.
* **Theoretical Fair Value (\(1/K\)):** \(0.0500\) (\(5.000\%\)).
* **Maximum Observed Absolute Deviation:** \(0.0062\) (Detected on Face 12).
* **Sum of all MLE Probabilities (\(\sum \mu_k\)):** \(1.0000\)

### Fairness Determination
**Conclusion: The die is fair.** 
The empirical probabilities calculated via MLE hover uniformly close to the theoretical baseline (\(0.0500\)) across all 20 faces. The maximum deviation of \(0.0062\) falls safely within the expected bounds of normal random sampling noise over finite trials, proving there is no systematic loading or geometric bias in the data generation process.

---

## 📁 Repository Structure

```text
die-roll-mle/
├── die_rolls.csv                         # Source categorical dataset
├── Mukltinomial distribution lab 2.ipynb   # Complete analysis implementation
├── .gitignore                            # Git tracking exclusions
├── README.md                             # Project documentation
└── requirements.txt                      # Environment dependencies
```

---

## 🚀 Environment Setup & Execution

### 1. Replicate the Environment
Ensure Python 3.8+ is installed. Clone the repository and install dependencies using `pip`:

```bash
# Clone the repository
git clone github.com
cd die-roll-mle

# Install project dependencies
pip install -r requirements.txt
```
