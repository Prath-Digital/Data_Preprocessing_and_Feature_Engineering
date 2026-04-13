# 📘 Self Excercise - 2.3

---

## Q1. What is Multivariate Imputation by Chained Equations (MICE)?
**Answer:**  
MICE is a statistical technique used to handle missing data by imputing (filling in) missing values multiple times using predictive models. Instead of filling with a single value, it generates multiple plausible values based on relationships between variables.

---

## Q2. How does MICE differ from simple imputation methods like mean or median imputation?
**Answer:**  

**Mean/Median Imputation:**
- Uses a single value  
- Ignores relationships between variables  
- Reduces data variability  

**MICE:**
- Uses multiple imputations  
- Preserves relationships between variables  
- Produces more realistic datasets  

---

## Q3. What is the basic working principle of the MICE algorithm?
**Answer:**  
1. Initialize missing values (e.g., mean imputation)  
2. Select one variable with missing values  
3. Treat it as the target and others as predictors  
4. Train a model and predict missing values  
5. Replace missing values  
6. Repeat for all variables  
7. Iterate multiple times until convergence  

---

## Q4. Why is MICE considered a multivariate imputation technique?
**Answer:**  
Because it uses multiple variables (features) simultaneously to predict missing values, capturing relationships between them.

---

## Q5. How does MICE handle missing values column by column?
**Answer:**  
- Imputes one column at a time  
- Uses other columns as predictors  
- Repeats the process in cycles (iterations)  

---

## Q6. What does “chained equations” mean in the context of the MICE algorithm?
**Answer:**  
It refers to the sequential process where each variable’s missing values are estimated using a model, and the output is passed to the next variable—forming a chain of equations.

---

## Q7. What types of models can be used in MICE for predicting missing values?
**Answer:**  

- Linear Regression → Continuous variables  
- Logistic Regression → Binary variables  
- Polynomial Regression → Non-linear data  
- Decision Trees / Random Forest → Complex patterns  

---

## Q8. What are the advantages of using MICE over single imputation methods?
**Answer:**  

- Maintains data variability  
- Reduces bias  
- Uses relationships between variables  
- Provides multiple datasets for better statistical inference  

---

## Q9. What are the limitations or challenges of using the MICE algorithm?
**Answer:**  

- Computationally expensive  
- Requires multiple iterations  
- Assumes missing data is Missing At Random (MAR)  
- Sensitive to model selection  

---

## Q10. In what kind of datasets is MICE particularly useful?
**Answer:**  

- Datasets with multiple missing values  
- Medical datasets  
- Survey data  
- Financial datasets  

---

## Q11. How does MICE help in reducing bias compared to single imputation methods?
**Answer:**  

- Uses predictive models instead of constant values  
- Incorporates uncertainty via multiple imputations  
- Preserves statistical properties of the dataset  

---

## Q12. Give one real-world application where MICE can be effectively applied in data preprocessing.
**Answer:**  

**Healthcare Example:**  
In patient records, missing values like blood pressure or cholesterol can be predicted using other features (age, weight, medical history), improving diagnostic model accuracy.

---

# 🧠 Example: Applying MICE in Python

```python
from sklearn.experimental import enable_iterative_imputer
from sklearn.impute import IterativeImputer
import pandas as pd

df = pd.read_csv("data.csv")

imputer = IterativeImputer()
df_imputed = imputer.fit_transform(df)

df_imputed = pd.DataFrame(df_imputed, columns=df.columns)

print(df_imputed.head())
```