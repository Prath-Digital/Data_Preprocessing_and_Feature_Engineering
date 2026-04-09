# 📊 Self Excercise - 1.2 

---

## Q1. What is a CSV file, and why is it widely used in data science?

**Answer:**
A CSV (Comma-Separated Values) file is a plain text file that stores tabular data where each row represents a record and columns are separated by commas.

**Why widely used:**
- Simple and lightweight
- Easy to read/write
- Compatible with almost all tools (Excel, Python, R, etc.)
- Human-readable format

---

## Q2. How can Python’s pandas library help in reading and writing CSV files?

**Answer:**
The pandas library provides powerful functions:

- **Read CSV:**
```python
import pandas as pd
df = pd.read_csv('file.csv')
```

- **Write CSV:**
```python
df.to_csv('output.csv', index=False)
```

**Benefits:**
- Handles large datasets efficiently
- Supports data cleaning and transformation
- Automatically detects headers and data types

---

## Q3. What are the limitations of CSV files compared to other formats?

**Answer:**
- No support for hierarchical/nested data
- No data types (everything is treated as text)
- Large files can be inefficient
- No metadata support
- No compression by default

---

## Q4. What is JSON, and how is it different from CSV?

**Answer:**
JSON (JavaScript Object Notation) is a structured data format using key-value pairs.

**Differences:**
| Feature | CSV | JSON |
|--------|-----|------|
| Structure | Tabular | Hierarchical |
| Data Types | No | Yes |
| Readability | Simple | More expressive |
| Use Case | Tables | APIs & nested data |

---

## Q5. Why is JSON often preferred for web data exchange?

**Answer:**
- Supports nested data
- Lightweight and fast
- Easy to parse in JavaScript and Python
- Widely used in APIs

---

## Q6. What is SQL, and how is it used for data storage and retrieval?

**Answer:**
SQL (Structured Query Language) is used to interact with databases.

**Uses:**
- Store data in tables
- Retrieve data using queries
- Update and delete records

**Example:**
```sql
SELECT * FROM students;
```

---

## Q7. What is an API, and why is it useful for data collection?

**Answer:**
An API (Application Programming Interface) allows communication between systems.

**Usefulness:**
- Fetch real-time data
- Automate data collection
- Access external services (weather, stock, etc.)

---

## Q8. What is the difference between a public API and a private API?

**Answer:**

| Type | Description |
|------|------------|
| Public API | Open for everyone |
| Private API | Restricted access |

---

## Q9. What role does authentication (like API keys) play in accessing APIs?

**Answer:**
Authentication ensures:
- Secure access
- User identification
- Usage tracking

---

## Q10. Why is it important to understand the structure and types of your data before analysis?

**Answer:**
- Helps in choosing correct methods
- Avoids errors
- Improves accuracy
- Ensures proper data cleaning

---

## Q11. What are common data quality issues encountered during data cleaning?

**Answer:**
- Missing values
- Duplicate records
- Incorrect data types
- Outliers
- Inconsistent formatting

---

## Q12. List three common techniques used for data cleaning in Python.

**Answer:**

1. **Handling Missing Values**
```python
df.fillna(0)
```

2. **Removing Duplicates**
```python
df.drop_duplicates()
```

3. **Type Conversion**
```python
df['column'] = df['column'].astype(int)
```

---

# 🎯 End of Lab
