# Self Excercise - 2.5

---

## Q1: What is the percentile method for detecting outliers?

The **percentile method** (also called percentile-based outlier detection) is a statistical technique that identifies outliers by defining thresholds based on the relative position of data points within the sorted dataset.

Percentiles divide the data into 100 equal parts. For example:
- The 95th percentile is the value below which 95% of the observations fall.
- Common practice: Values **below the 1st or 5th percentile** and **above the 99th or 95th percentile** are flagged as outliers.

This method is non-parametric (does not assume any specific data distribution like normality) and focuses on the empirical distribution of the data.

---

## Q2: How are lower and upper percentile thresholds used to identify outliers?

1. Sort the dataset in ascending order.
2. Calculate the desired lower percentile (e.g., 1st or 5th) and upper percentile (e.g., 99th or 95th).
3. Any data point **below the lower threshold** or **above the upper threshold** is considered an outlier.

**Example:**
- For a relaxed approach: Use 5th percentile (lower) and 95th percentile (upper).
- For stricter detection: Use 1st percentile (lower) and 99th percentile (upper).

Values outside these thresholds can then be removed, capped, or investigated further. This approach is simple and works well for both symmetric and skewed data.

---

## Q3: What is the difference between the percentile method and the IQR method?

| Aspect                  | Percentile Method                          | IQR Method                                      |
|-------------------------|--------------------------------------------|-------------------------------------------------|
| **Basis**              | Fixed percentiles (e.g., 1%/99%)          | Quartiles (Q1, Q3) and 1.5 × IQR               |
| **Focus**              | Entire data distribution (tails)          | Middle 50% of the data (interquartile range)   |
| **Sensitivity**        | More flexible; adjustable thresholds      | Fixed multiplier (usually 1.5); less flexible  |
| **Best for**           | Skewed or non-normal data                 | Roughly symmetric or mildly skewed data        |
| **Outlier Definition** | Extreme tails of the empirical distribution | Points beyond Q1 - 1.5×IQR or Q3 + 1.5×IQR    |

**Key Difference:**  
The IQR method focuses on the spread of the central data and is robust to extreme values, while the percentile method directly targets the tails using chosen cutoffs (e.g., 5%/95%). Percentile is often more intuitive for highly skewed real-world data.

---

## Q4: In what type of datasets is the percentile method most useful?

The percentile method is most useful in:
- **Skewed or non-normal distributions** (common in real-world data like income, prices, sensor readings, or usage metrics).
- **Large datasets** where empirical percentiles are reliable.
- **Situations requiring domain-specific flexibility** (e.g., setting aggressive 1%/99% thresholds for fraud detection or relaxed 5%/95% for general cleaning).
- Datasets with heavy tails or when you want to control the exact percentage of data flagged as outliers.

It is less ideal for very small datasets where percentiles may be unstable.

---

## Q5: What are the advantages of using the percentile method for outlier detection?

- **Simple and intuitive** — Easy to understand and implement (no complex formulas).
- **Flexible** — You can choose any percentile thresholds based on domain knowledge.
- **Robust to distribution assumptions** — Works well without assuming normality.
- **Effective for skewed data** — Handles heavy-tailed or asymmetric distributions better than some parametric methods.
- **Customizable sensitivity** — Adjust thresholds to be strict or lenient as needed.

---

## Q6: What are the limitations of the percentile method?

- **Arbitrary thresholds** — Choosing 1%/99% vs. 5%/95% is subjective and may require domain expertise.
- **Sensitive in small datasets** — Percentiles can be unstable with limited samples.
- **May flag legitimate extremes** — In naturally heavy-tailed data (e.g., wealth distribution), true high values might be incorrectly removed.
- **No consideration of multivariate relationships** — Treats each feature independently.
- **Potential loss of information** — If outliers are removed without investigation, valuable insights (e.g., rare events) may be lost.

---

## Q7: What is Winsorization in the context of data preprocessing?

**Winsorization** (named after Charles P. Winsor) is a technique that **caps** extreme values (outliers) instead of removing them.

**How it works:**
- Choose a percentile level (e.g., 5% winsorization).
- Replace all values **below the 5th percentile** with the 5th percentile value.
- Replace all values **above the 95th percentile** with the 95th percentile value.

This limits the influence of outliers while **retaining all observations** in the dataset. It is commonly used in statistical analysis and machine learning preprocessing to create more robust models.

---

## Q8: How does Winsorization differ from outlier removal techniques?

- **Outlier Removal (Trimming):** Completely deletes data points identified as outliers. This reduces sample size and can discard potentially useful information.
- **Winsorization (Capping):** Keeps every data point but replaces extreme values with the nearest non-extreme value (at the chosen percentile). Sample size remains unchanged.

**Main Difference:**  
Removal eliminates influence entirely; Winsorization reduces but does not eliminate the contribution of extreme points. Winsorization is a form of "soft" handling, while removal is "hard."

---

## Q9: Why is Winsorization sometimes preferred over outright deleting outliers?

- **Preserves sample size** — Especially important for small or imbalanced datasets.
- **Retains data volume** — All observations contribute (albeit with capped extremes), improving statistical power.
- **Reduces bias from deletion** — Deleting legitimate but extreme values (e.g., high-value customers) can distort analysis.
- **Better for downstream modeling** — Many ML algorithms perform better with capped rather than missing data.
- **Maintains data integrity** — Keeps the number of records intact for tasks like aggregation or training.

---

## Q10: Explain how Winsorization affects the mean and variance of a dataset.

- **Mean:** Winsorization typically pulls the mean toward the center by reducing the pull of extreme high or low values. The winsorized mean is more robust and less sensitive to outliers than the original arithmetic mean.
- **Variance / Standard Deviation:** It **decreases variance** because extreme deviations from the mean are reduced (capped values are closer to the center). The dataset appears less dispersed after winsorization.

**Example Effect:**  
Original data with a few very high values → inflated mean and high variance.  
After winsorization → mean lowers (for right-skewed data) and variance shrinks significantly, leading to more stable statistical estimates.

---

## Q11: What are the risks of over-Winsorizing data?

- **Loss of data variability** — Over-capping hides genuine extremes and reduces the natural spread of the data.
- **Introduction of bias** — Excessive modification can distort the underlying distribution and lead to incorrect conclusions.
- **Reduced statistical power** — Artificially lowered variance may produce over-optimistic confidence intervals or p-values.
- **Masking important signals** — Rare but meaningful events (e.g., fraud spikes or breakthrough performance) may be suppressed.
- **Over-simplification** — The dataset may no longer reflect real-world variability, harming model generalization in some cases.

**Best Practice:** Always justify the percentage (e.g., 1–5% per tail) and compare statistics before/after winsorization.

---

## Q12: Give one real-world scenario where Winsorization can improve the robustness of a model.

**Scenario: Financial Fraud Detection or Credit Risk Modeling**

In credit card transaction datasets, a few users may have extremely high spending due to legitimate large purchases, errors, or rare events. These outliers can heavily influence regression or anomaly detection models, causing unstable predictions or false positives.

**Application of Winsorization:**
- Cap transaction amounts at the 99th percentile.
- This reduces the disproportionate impact of rare high-value transactions without deleting records.
- Result: The model becomes more robust to noise, generalizes better on new data, and focuses on typical spending patterns while still accounting for high spenders (now capped). Performance metrics (e.g., AUC, stability) often improve.