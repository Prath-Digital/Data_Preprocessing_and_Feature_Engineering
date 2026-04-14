# Self Excercise - 2.4

---

## Q1. What are outliers in the context of machine learning datasets?
**Answer:**  
Outliers are data points that significantly differ from the majority of the observations in a dataset. In machine learning, they are extreme values that deviate markedly from other observations and do not follow the general pattern or distribution of the data.

---

## Q2. Why can outliers negatively impact machine learning models?
**Answer:**  
Outliers can negatively impact models in several ways:
- They can skew statistical measures like mean and standard deviation.
- Distance-based algorithms (e.g., KNN, K-Means) can be heavily influenced by them.
- They may lead to overfitting, especially in linear regression and neural networks.
- They can distort feature scaling (StandardScaler, MinMaxScaler).
- They reduce overall model generalization and increase prediction error on normal data.

---

## Q3. Give two real-world examples of situations where outliers may occur in data.
**Answer:**  

1. **Fraud Detection in Banking:** A customer's transaction amount is usually between ₹500–₹50,000, but suddenly there is a transaction of ₹25,00,000. This is a clear outlier indicating possible fraud.

2. **Healthcare - Patient Age or Blood Pressure:** In a dataset of adult patients, recording an age of 150 years or a systolic blood pressure of 300 mmHg would be an outlier (likely due to data entry error or rare medical condition).

---

## Q4. What are some common strategies for handling outliers (removal, transformation, capping)?
**Answer:**  

- **Removal:** Simply delete the outlier rows (useful when outliers are due to errors and dataset is large).
- **Transformation:** Apply log, square root, or Box-Cox transformation to reduce the impact of extreme values.
- **Capping (Winsorization):** Replace outliers with the nearest acceptable value (e.g., cap at 1st and 99th percentile).
- **Imputation:** Replace outliers with mean/median (less common) or use robust statistical methods.
- **Model-based:** Use algorithms that are robust to outliers (e.g., Random Forest, Robust Regression, Isolation Forest).

---

## Q5. What is the Z-score in statistics?
**Answer:**  
The Z-score (standard score) measures how many standard deviations a data point is away from the mean of the dataset.  

**Formula:**  
$$ Z = \frac{X - \mu}{\sigma} $$  

where:  
- \( X \) = data point  
- \( \mu \) = mean of the dataset  
- \( \sigma \) = standard deviation of the dataset

---

## Q6. How is the Z-score used to detect outliers in a dataset?
**Answer:**  
1. Calculate the mean (\( \mu \)) and standard deviation (\( \sigma \)) of the feature.
2. Compute the Z-score for every data point.
3. Any data point whose absolute Z-score exceeds a certain threshold is flagged as an outlier.

This method assumes the data is approximately normally distributed.

---

## Q7. What threshold values are commonly used to classify a data point as an outlier using Z-scores?
**Answer:**  

- **Most common threshold:** \( |Z| > 3 \) (data point is more than 3 standard deviations away from the mean).
- **Moderate threshold:** \( |Z| > 2.5 \)
- **Conservative threshold:** \( |Z| > 2 \)

In practice, **3** is the most widely used threshold for outlier detection.

---

## Q8. What are the advantages and disadvantages of the Z-score method?
**Answer:**  

**Advantages:**
- Simple and easy to understand.
- Works well with normally distributed data.
- Computationally efficient.

**Disadvantages:**
- Highly sensitive to outliers itself (mean and std are affected by outliers).
- Assumes normal distribution — performs poorly on skewed data.
- Not robust for small datasets or non-Gaussian distributions.

---

## Q9. What is the Interquartile Range (IQR) in statistics?
**Answer:**  
The Interquartile Range (IQR) is a measure of statistical dispersion. It is the difference between the third quartile (Q3) and the first quartile (Q1).  

**Formula:**  
$$ IQR = Q3 - Q1 $$  

- Q1 = 25th percentile  
- Q3 = 75th percentile  

IQR represents the middle 50% of the data and is robust to extreme values.

---

## Q10. How does the IQR method identify outliers in a dataset?
**Answer:**  
The IQR method (also called the Tukey method) defines outliers as:

- **Lower bound:** \( Q1 - 1.5 \times IQR \)
- **Upper bound:** \( Q3 + 1.5 \times IQR \)

Any data point below the lower bound or above the upper bound is considered an outlier.

This is also known as the **1.5 × IQR rule**.

---

## Q11. Why is the IQR method often preferred for skewed data distributions?
**Answer:**  
The IQR method is **non-parametric** and **robust** because:
- It does not depend on the mean or standard deviation.
- It is based on percentiles (quartiles), which are not influenced by extreme values.
- It works well even when the data is skewed, asymmetric, or non-normal.
- It is less sensitive to the presence of outliers compared to the Z-score method.

---

## Q12. Give one practical example of how outlier detection with IQR can be applied in a real dataset.
**Answer:**  

**Example:** House Price Prediction Dataset  

Suppose you have a dataset containing house prices in Surat, Gujarat. Most houses are priced between ₹25 lakh to ₹1.5 crore, but a few luxury villas are priced at ₹15–20 crore.

- Using IQR method on the `price` column:
  - Q1 = ₹45 lakh
  - Q3 = ₹1.2 crore
  - IQR = ₹75 lakh
  - Upper bound = ₹1.2cr + 1.5×₹75lakh = ₹2.325 crore

Any house priced above ₹2.325 crore would be flagged as an outlier. These extreme values can then be capped, removed, or analyzed separately depending on business requirements.

---

**End of Document**