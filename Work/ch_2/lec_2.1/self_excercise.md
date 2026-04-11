# 📊 Self Excercise - 2.1

---

## Q1. What is missing value imputation in data preprocessing?

**Answer:**  
Missing value imputation is the process of replacing missing or null values in a dataset with substituted values to maintain data integrity and enable proper analysis or machine learning modeling.

---

## Q2. Why is handling missing values important before applying machine learning models?

**Answer:**  
- Most ML algorithms cannot handle missing values directly  
- Missing data can bias results  
- It reduces model accuracy  
- Ensures consistency and reliability of the dataset  

---

## Q3. What are the main strategies for dealing with missing data?

**Answer:**  
1. **Deletion Methods**
   - Remove rows or columns with missing values  

2. **Imputation Methods**
   - Mean, median, mode
   - Constant value
   - Predictive models  

3. **Advanced Techniques**
   - KNN imputation  
   - Regression imputation  

---

## Q4. How does the Simple Imputer handle missing numerical values?

**Answer:**  
The Simple Imputer replaces missing numerical values using:
- Mean (average)
- Median (middle value)
- Constant (fixed number)

---

## Q5. What are the common strategies (mean, median, constant) used for imputing numerical data?

**Answer:**  
- **Mean:** Average of all values  
- **Median:** Middle value (robust to outliers)  
- **Constant:** Replace with a fixed number (e.g., 0 or -1)  

---

## Q6. In what scenarios is median imputation preferred over mean imputation?

**Answer:**  
Median is preferred when:
- Data contains **outliers**
- Data is **skewed**
- Need a more **robust central value**

---

## Q7. How does the Simple Imputer handle missing categorical values?

**Answer:**  
It replaces missing categorical values using:
- Most frequent value (mode)
- Constant value (e.g., "Unknown")

---

## Q8. What is the difference between filling categorical data with a constant value vs. most frequent value?

**Answer:**  
- **Constant Value:**
  - Adds a new category (e.g., "Unknown")
  - Useful when missing has meaning  

- **Most Frequent:**
  - Replaces with most common category
  - Maintains distribution  

---

## Q9. Why might imputing missing categorical values with "Unknown" or "Other" be useful?

**Answer:**  
- Preserves missing information  
- Avoids misleading assumptions  
- Helps models identify missing patterns  

---

## Q10. What is most frequent imputation in the context of categorical data?

**Answer:**  
It replaces missing values with the **mode** (most commonly occurring category) in the dataset.

---

## Q11. What are the advantages and disadvantages of using most frequent imputation?

**Answer:**  

### Advantages:
- Simple and fast  
- Maintains data distribution  
- Works well with categorical data  

### Disadvantages:
- Can introduce bias  
- Over-representation of dominant category  
- Ignores variability  

---

## Q12. Give a real-world example where most frequent imputation can be applied effectively.

**Answer:**  
In a **customer dataset**, if the "Country" column has missing values:
- Replace missing values with the most common country (e.g., "India")

This works well when:
- Most users belong to one region  
- Missing data is minimal