# Self Exercise - 2.2

## Q1. What is the Missing Indicator method in handling missing values?

**Answer:**\
The Missing Indicator method involves creating a new binary variable (0
or 1) that indicates whether a value was missing in the original
feature. This allows models to capture the fact that data was missing,
which may itself carry important information.

------------------------------------------------------------------------

## Q2. How does the Missing Indicator help preserve missingness information in a dataset?

**Answer:**\
It preserves missingness by explicitly encoding whether a value was
missing, rather than hiding it through imputation. This helps models
learn patterns related to missing data.

------------------------------------------------------------------------

## Q3. What are the advantages of using a Missing Indicator in predictive modeling?

**Answer:**\
- Retains missingness information\
- Improves model performance when missingness is informative\
- Simple to implement\
- Works well with tree-based models

------------------------------------------------------------------------

## Q4. What is Random Sample Imputation?

**Answer:**\
Random Sample Imputation replaces missing values with randomly selected
values from the observed (non-missing) data in the same feature.

------------------------------------------------------------------------

## Q5. How does Random Sample Imputation differ from mean/median imputation?

**Answer:**\
- Mean/Median: Uses a fixed value → reduces variance\
- Random Sampling: Uses actual data points → preserves distribution and
variance

------------------------------------------------------------------------

## Q6. In what type of datasets is Random Sample Imputation particularly useful?

**Answer:**\
- When data is not normally distributed\
- When preserving variance is important\
- When missingness is random (MCAR)

------------------------------------------------------------------------

## Q7. What is the KNN Imputer in handling missing data?

**Answer:**\
KNN Imputer fills missing values using the average (or majority) of the
nearest neighbors based on feature similarity.

------------------------------------------------------------------------

## Q8. How does the KNN Imputer use "nearest neighbors" to impute missing values?

**Answer:**\
It calculates distance between data points, finds the K closest rows,
and imputes the missing value using their values.

------------------------------------------------------------------------

## Q9. What role does the parameter k (number of neighbors) play in KNN Imputation?

**Answer:**\
- Small k: More sensitive to noise\
- Large k: More stable but less precise\
- Controls bias-variance tradeoff

------------------------------------------------------------------------

## Q10. How does KNN Imputation differ from univariate imputation methods like mean or median?

**Answer:**\
- KNN: Uses relationships between multiple features\
- Mean/Median: Uses only one feature\
- KNN captures patterns; univariate methods do not

------------------------------------------------------------------------

## Q11. What are the limitations of using KNN Imputation?

**Answer:**\
- Computationally expensive\
- Sensitive to feature scaling\
- Curse of dimensionality\
- Requires careful choice of k

------------------------------------------------------------------------

## Q12. Give one practical example where KNN Imputer can be more effective than simple imputation methods.

**Answer:**\
In a healthcare dataset, missing blood pressure values can be estimated
using similar patients (age, weight, medical history). KNN works better
than mean because it considers patient similarity.
