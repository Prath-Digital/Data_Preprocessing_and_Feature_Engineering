# 📊 Self Excercise - 3.1

---

## Q1. What are mixed variables in a dataset?

**Answer:**  
Mixed variables refer to datasets that contain both:
- **Numerical variables** (e.g., age, salary)
- **Categorical variables** (e.g., gender, city)

These datasets require special preprocessing because different variable types need different handling techniques.

---

## Q2. Give an example of a dataset containing both numerical and categorical variables.

**Answer:**  
Example: Customer dataset

| Name | Age | Gender | Income | City |
|------|-----|--------|--------|------|
| A    | 25  | Male   | 50000  | Delhi |
| B    | 30  | Female | 60000  | Mumbai |

- Numerical: Age, Income  
- Categorical: Gender, City  

---

## Q3. Why is it challenging to handle mixed variables in data preprocessing?

**Answer:**  
Challenges include:
- Different data types require different transformations
- Machine learning models need numerical input
- Encoding categorical variables can increase dimensionality
- Risk of losing meaning during transformation

---

## Q4. What strategies can be applied to preprocess mixed variable datasets?

**Answer:**  
Common strategies:
1. **Separate variables** (numerical & categorical)
2. **Scale numerical data** (Normalization/Standardization)
3. **Encode categorical data**
   - One-hot encoding
   - Label encoding
4. **Use pipelines** to automate preprocessing
5. **Handle missing values separately for each type**

---

## Q5. Why are date and time variables important in data analysis?

**Answer:**  
Date/time variables help:
- Identify trends over time
- Capture seasonality patterns
- Improve predictions (e.g., sales increase on weekends)
- Enable time-based grouping and analysis

---

## Q6. What challenges arise when working with date and time data in machine learning?

**Answer:**  
Challenges include:
- Not directly usable by models
- Different formats (DD/MM/YYYY, MM/DD/YYYY)
- Time zones and inconsistencies
- Cyclical nature (e.g., months repeat)
- Missing or incorrect timestamps

---

## Q7. What are some common transformations performed on date and time variables?

**Answer:**  
Common transformations:
- Extract:
  - Year
  - Month
  - Day
  - Weekday
- Convert to timestamp
- Create features:
  - Is_weekend
  - Hour of day
- Cyclical encoding:
  - sin/cos transformation for months or hours

---

## Q8. Give a real-world example of using date/time features to improve predictive modeling.

**Answer:**  
Example: **E-commerce sales prediction**

- Extract:
  - Day of week → weekend sales higher
  - Month → festive season boost
- Result:
  - Better demand forecasting
  - Improved inventory planning

---

## Q9. What is Complete Case Analysis (CCA) in handling missing data?

**Answer:**  
Complete Case Analysis (CCA) means:
- Removing all rows that contain **any missing values**

Only complete records are used for analysis.

---

## Q10. What are the advantages of using Complete Case Analysis?

**Answer:**  
Advantages:
- Simple and easy to implement
- No need for imputation
- Works well when missing data is very small

---

## Q11. What are the limitations of Complete Case Analysis in machine learning projects?

**Answer:**  
Limitations:
- Loss of valuable data
- Reduced dataset size
- Can introduce bias if data is not missing randomly
- Poor performance on small datasets

---

## Q12. In what situations is Complete Case Analysis a reasonable approach to deal with missing values?

**Answer:**  
CCA is suitable when:
- Missing data is **very small (<5%)**
- Data is missing **completely at random (MCAR)**
- Dataset is large enough to handle data loss
- Simplicity is preferred over complexity