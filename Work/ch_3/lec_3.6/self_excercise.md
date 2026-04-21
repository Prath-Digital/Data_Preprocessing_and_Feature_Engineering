# Self Excercise - 3.6

---

## Q1. What is the purpose of the PowerTransformer in data preprocessing?

**Answer:**  
The PowerTransformer is used to make data more Gaussian (normal distribution). It stabilizes variance and reduces skewness, which helps many machine learning models perform better.

---

## Q2. How does the PowerTransformer help in stabilizing variance and making data more normal?

**Answer:**  
- It applies a power transformation (like Box-Cox or Yeo-Johnson).
- Reduces skewness in data.
- Makes distribution symmetric.
- Ensures constant variance across values.

---

## Q3. What is the Box-Cox transformation, and what assumptions does it make about the data?

**Answer:**  
Box-Cox is a power transformation technique that transforms data to make it more normally distributed.

**Assumptions:**
- Data must be positive (no zero or negative values).
- Data should be continuous.
- Data should not contain extreme outliers.

---

## Q4. Why can the Box-Cox transformation only be applied to positive data?

**Answer:**  
Because the mathematical formula involves logarithms and power operations that are undefined or invalid for zero or negative values.

---

## Q5. What is the Yeo-Johnson transformation, and how does it differ from the Box-Cox method?

**Answer:**  
Yeo-Johnson is similar to Box-Cox but can handle both positive and negative values.

**Difference:**
- Box-Cox → Only positive data
- Yeo-Johnson → Works with positive, zero, and negative data

---

## Q6. In what situations is Yeo-Johnson preferred over Box-Cox?

**Answer:**  
- When data contains zero or negative values
- When you don't want to preprocess data to make it positive
- When dataset has mixed value ranges

---

## Q7. What is a Column Transformer in scikit-learn?

**Answer:**  
ColumnTransformer is a tool in scikit-learn that allows different preprocessing techniques to be applied to different columns of a dataset.

---

## Q8. How does a Column Transformer help in preprocessing mixed data types (numerical and categorical)?

**Answer:**  
- Applies scaling (like StandardScaler) to numerical columns
- Applies encoding (like OneHotEncoder) to categorical columns
- Combines all transformed outputs into a single dataset

---

## Q9. What are the advantages of using a Column Transformer in a machine learning pipeline?

**Answer:**  
- Handles mixed data types efficiently
- Keeps preprocessing organized
- Reduces code complexity
- Works well with pipelines
- Prevents data leakage

---

## Q10. How can multiple transformations (e.g., scaling, encoding) be applied simultaneously using a ColumnTransformer?

**Answer:**  
By defining a list of transformations:

```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder

ct = ColumnTransformer([
    ("num", StandardScaler(), ["age", "salary"]),
    ("cat", OneHotEncoder(), ["gender", "city"])
])
```

---

## Q11. What is the benefit of using a Column Transformer instead of applying transformations separately?

**Answer:**  
- Applies all transformations in one step
- Ensures consistency
- Avoids manual errors
- Easier integration with pipelines
- Better reproducibility

---

## Q12. Give one practical example where a Column Transformer improves preprocessing efficiency.

**Answer:**  
In a dataset with:
- Numerical columns: age, salary
- Categorical columns: gender, city

Instead of preprocessing separately, ColumnTransformer:
- Scales numerical data
- Encodes categorical data
- Combines everything automatically