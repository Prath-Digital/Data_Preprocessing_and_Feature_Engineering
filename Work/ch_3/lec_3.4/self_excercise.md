# 📘 Self Excercise - 3.4

---

## Q1. What is feature scaling, and why is it important in machine learning?

**Answer:**

Feature scaling is the process of transforming numerical features so that they are on a similar scale.

### Why it is important:
- Prevents features with large values from dominating
- Improves model performance and accuracy
- Speeds up training
- Helps distance-based algorithms work correctly

---

## Q2. What types of machine learning algorithms are most affected by unscaled features?

**Answer:**

- K-Nearest Neighbors (KNN)
- K-Means Clustering
- Support Vector Machines (SVM)
- Linear Regression / Logistic Regression
- Neural Networks

---

## Q3. What is standardization, and what formula is used to standardize data?

**Answer:**

Standardization transforms data so that:
- Mean = 0
- Standard Deviation = 1

Formula:
z = (x - μ) / σ

---

## Q4. Why does standardization often result in data with mean 0 and standard deviation 1?

**Answer:**

- Subtracting mean → centers data at 0  
- Dividing by standard deviation → scales spread to 1  

---

## Q5. What is normalization, and how is it different from standardization?

**Answer:**

Normalization rescales data to range [0, 1].

Formula:
x' = (x - min) / (max - min)

Difference:
- Normalization → fixed range  
- Standardization → mean 0, std 1  

---

## Q6. Give one real-world example where normalization is preferred over standardization.

**Answer:**

Image processing:
- Pixel values (0–255) → scaled to (0–1)

---

## Q7. What is MinMax scaling, and how does it transform the feature range?

**Answer:**

Rescales values to [0, 1]:

x' = (x - min) / (max - min)

---

## Q8. What are the advantages and drawbacks of MinMax scaling?

**Answer:**

Advantages:
- Preserves distribution
- Bounded values

Drawbacks:
- Sensitive to outliers

---

## Q9. What is MaxAbs scaling, and in what situations is it useful?

**Answer:**

x' = x / |max|

Useful for:
- Sparse data

---

## Q10. How does MaxAbs scaling differ from MinMax scaling?

**Answer:**

- MinMax → [0,1]  
- MaxAbs → [-1,1]  
- MaxAbs preserves sign  

---

## Q11. What is Robust scaling, and how does it handle outliers?

**Answer:**

x' = (x - median) / IQR

Uses median & IQR → resistant to outliers

---

## Q12. Why is median and IQR used in Robust scaling?

**Answer:**

- Less affected by extreme values  
- Better for skewed datasets  

---

# ✅ Summary

- Standardization → default choice  
- Normalization → neural networks  
- MaxAbs → sparse data  
- Robust → outliers
