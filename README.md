
<div>
  
<!--banner-->
 
<img align="center" width="752" height="583" alt="Image" src="https://github.com/user-attachments/assets/fc296cf2-016e-4121-a18d-d7eabe113067" />
 
  

<p align="center">
  <img src="https://github.com/user-attachments/assets/bd324116-fee4-471f-85fd-4d22c3efe18f" width="1920" 
</p>

<h1 align="center">📘 SQL Notes for Data Analysts</h1>
<p align="center">
  A beginner-friendly cheat sheet to SQL concepts that are crucial for data analysis and business intelligence.
</p>

---

## 📊 Basic Numerical Operations & Sorting

```sql
<  <=  >  >=
```

- These are the **basic numerical operators** used in SQL.
- Use `AND`, `OR`, `BETWEEN`, `IN` to filter records with multiple conditions.
- Sort results using the `ORDER BY` clause.
  - Default sort: `ASC` (ascending).
  - Use `DESC` for descending sort.

```sql
SELECT * FROM employees ORDER BY salary DESC;
```

- Use `LIMIT` to fetch top `N` rows and `OFFSET` to skip rows:

```sql
SELECT * FROM employees ORDER BY salary DESC LIMIT 5 OFFSET 10;
```

---

## 🧱 Essential SQL Clauses

- `SELECT`, `FROM`, `WHERE` — the **foundation** of every SQL query.
- `*` selects **all columns** from a table:

```sql
SELECT * FROM products;
```

- Use `USE database_name;` to select a specific database.
- Count rows using:

```sql
SELECT COUNT(*) FROM orders;
```

- Get unique values with `DISTINCT`:

```sql
SELECT DISTINCT country FROM customers;
```

- Use `%` for wildcard search and `LIKE` to filter patterns:

```sql
SELECT * FROM users WHERE name LIKE 'A%';
```

---

## 📈 Summary Analytics (AD-HOC Analysis)

- Learn to generate insights on the fly with *AD-HOC Analysis*.
- Common functions:

```sql
MAX(), MIN(), AVG()
```

- Use `AS` to rename *(Alias)* a column:

```sql
SELECT AVG(salary) AS average_salary FROM employees;
```

- `GROUP BY` groups rows and aggregates data:

```sql
SELECT department, AVG(salary) FROM employees GROUP BY department;
```

---

## 🧠 Query Execution Order in SQL

The correct order of SQL query execution is:

```text
FROM → WHERE → GROUP BY → HAVING → ORDER BY
```

- `GROUP BY` + `HAVING` are often used together:

```sql
SELECT department, COUNT(*) 
FROM employees 
GROUP BY department 
HAVING COUNT(*) > 5;
```

- `WHERE` filters **before** grouping, while `HAVING` filters **after** grouping.
- `NOTE:` The Column you use in **HAVING** should be present in **SELECT** clause whereas **WHERE** can use columns that is not present in select clause as well.
---

## 🛠 Derived Columns & Business Use Cases

- You can **derive new columns** from existing ones:

```sql
SELECT price * quantity AS revenue FROM sales;
```

- Common business metrics:
  - **Revenue**
  - **Profit**
  - **Currency & Unit Conversions**

- Use `IF` and `CASE` for conditional logic:
> **IF** `IF(condition, value_if_true, value_if_false)`

```sql
SELECT 
  name,
  IF(score >= 90, 'A',
    IF(score >= 75, 'B', 'C')
  ) AS grade
FROM students;
```





> **CASE** 

           

```sql
SELECT 
  name,
  CASE 
    WHEN score >= 90 THEN 'A'
    WHEN score >= 75 THEN 'B'
    ELSE 'C'
  END AS grade
FROM students;
```

---

## 📌 Final Tips

✅ Practice regularly on real-world datasets  
✅ Use platforms like LeetCode, Hackerrank, Mode Analytics  
✅ Focus on writing readable and optimized SQL

---

> 🚀📚 *Created 💛 by [Athar](https://github.com/athar-ansari)*  
 
