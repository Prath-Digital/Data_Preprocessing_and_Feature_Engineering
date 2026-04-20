# 📘 Self Excercise - 3.5

---

## Q1. What is feature construction in machine learning?

**Answer:**
Feature construction is the process of creating new features from existing data to improve model performance. These new features help the model better understand patterns in the data.

---

## Q2. Why is feature construction important for improving model performance?

**Answer:**

* Enhances data representation
* Captures hidden patterns
* Improves model accuracy
* Helps simplify complex relationships

---

## Q3. Give an example of creating a new feature from existing ones.

**Answer:**
If you have:

* `Length = 5`
* `Width = 4`

You can create:

* `Area = Length × Width = 20`

---

## Q4. What is feature splitting, and when is it useful?

**Answer:**
Feature splitting means breaking a single feature into multiple parts.
It is useful when:

* Data contains combined information
* You need more granular insights

---

## Q5. How can feature splitting help in handling categorical or text data?

**Answer:**

* Converts complex text into structured parts
* Extracts meaningful components
* Helps models process text effectively

Example:
`"2026-04-20"` → Year = 2026, Month = 04, Day = 20

---

## Q6. Provide one real-world example where feature splitting is applied.

**Answer:**
In e-commerce:
Full address → Split into:

* City
* State
* ZIP code

This helps in delivery prediction and regional analysis.

---

## Q7. What is the purpose of using FunctionTransformer in scikit-learn?

**Answer:**
It allows you to apply custom transformations to features in a pipeline without creating a new class.

---

## Q8. What is a log transformation, and how does it help with skewed data?

**Answer:**
Log transformation reduces skewness by compressing large values.

Example:

* Before: 1, 10, 1000
* After log: 0, 1, 3

---

## Q9. What is a reciprocal transformation, and when is it useful?

**Answer:**
Reciprocal transformation uses:
`1 / x`

Useful when:

* Data has large values
* You want to reduce the impact of outliers

---

## Q10. What is a square root transformation, and how does it stabilize variance?

**Answer:**
Square root transformation uses:
`√x`

It:

* Reduces variance
* Makes data more normally distributed

---

## Q11. What are the risks of applying transformations like log or reciprocal to numerical features?

**Answer:**

* Cannot apply log to zero or negative values
* May distort data interpretation
* Can reduce model interpretability
* Risk of over-transformation

---

## Q12. Give one practical example of using a transformation to improve model interpretability.

**Answer:**
In income prediction:

* Income is highly skewed
* Apply log transformation

This:

* Makes relationships linear
* Helps models like linear regression perform better

---

# ✅ Quick Summary (Action Plan)

* ✔ Use feature construction to create meaningful new variables
* ✔ Use feature splitting to break complex data
* ✔ Apply transformations (log, sqrt, reciprocal) carefully
* ✔ Always check data distribution before and after transformation
* ✔ Use pipelines (like FunctionTransformer) for clean workflows