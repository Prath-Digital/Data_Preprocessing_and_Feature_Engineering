# 📘 Self Excercise - 3.2

---

## Q1. Why is encoding categorical data necessary in machine learning?

**Answer:**
Machine learning models work with numerical data, not text. Categorical data (like "Red", "Blue") must be converted into numbers so algorithms can process them.

**Key Points:**
- Algorithms perform mathematical operations → need numbers
- Prevents errors during training
- Ensures consistency in model input

---

## Q2. What are the risks of leaving categorical variables unencoded when training ML models?

**Answer:**
Leaving categorical data unencoded can cause:

- ❌ Model errors (cannot process strings)
- ❌ Incorrect interpretations
- ❌ Reduced model performance

---

## Q3. What is Ordinal Encoding?

**Answer:**
Ordinal Encoding assigns numerical values to categories based on their order or ranking.

Example:
Low → 1  
Medium → 2  
High → 3  

---

## Q4. In what cases is Ordinal Encoding suitable?

**Answer:**
Use Ordinal Encoding when categories have a meaningful order.

Examples:
- Education level (School < College < PhD)
- Rating (Bad < Average < Good)

---

## Q5. What is the potential drawback of using Ordinal Encoding on non-ordinal categorical data?

**Answer:**
It introduces a false sense of order.

---

## Q6. Give a real-world example where Ordinal Encoding is the best choice.

**Answer:**
Customer Satisfaction:
Poor → 1  
Average → 2  
Good → 3  
Excellent → 4  

---

## Q7. What is Label Encoding, and how does it work?

**Answer:**
Label Encoding assigns a unique number to each category.

Example:
Apple → 0  
Banana → 1  
Mango → 2  

---

## Q8. How does Label Encoding differ from Ordinal Encoding?

| Feature | Label Encoding | Ordinal Encoding |
|--------|---------------|------------------|
| Purpose | Assign unique numbers | Represent order |
| Order Meaning | No | Yes |

---

## Q9. What problems can arise if Label Encoding is used on nominal (non-ordered) categories?

**Answer:**
It may introduce unintended relationships.

---

## Q10. What is One-Hot Encoding, and when should it be used?

**Answer:**
One-Hot Encoding creates separate binary columns for each category.

---

## Q11. What is the “dummy variable trap” in One-Hot Encoding, and how can it be avoided?

**Answer:**
It occurs due to multicollinearity when one variable can be predicted from others.

Solution:
- Drop one column

---

## Q12. Give one real-world example of applying One-Hot Encoding in a dataset.

**Answer:**
Car Color dataset transformed into binary columns.