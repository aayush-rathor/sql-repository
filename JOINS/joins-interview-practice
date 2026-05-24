# Most Asked SQL JOIN Practical Interview Questions

---

# 1. Get Employee Name with Department Name

## Question:
Write a query to display employee names along with their department names.

## Query:
```sql
SELECT e.emp_name,
       d.department_name
FROM employees e
INNER JOIN departments d
ON e.dept_id = d.dept_id;
```

---

# 2. Find Employees Without Department

## Question:
Find employees who are not assigned to any department.

## Query:
```sql
SELECT e.emp_name
FROM employees e
LEFT JOIN departments d
ON e.dept_id = d.dept_id
WHERE d.dept_id IS NULL;
```

---

# 3. Get All Departments Even Without Employees

## Question:
Display all departments including departments with no employees.

## Query:
```sql
SELECT d.department_name,
       e.emp_name
FROM departments d
LEFT JOIN employees e
ON d.dept_id = e.dept_id;
```

---

# 4. Find Employee and Their Manager Name

## Question:
Display employee name and their manager name.

## Query:
```sql
SELECT e.emp_name AS employee_name,
       m.emp_name AS manager_name
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.emp_id;
```

---

# 5. Find Duplicate Records After JOIN

## Question:
Find duplicate employee records after JOIN.

## Query:
```sql
SELECT e.emp_id,
       COUNT(*) AS duplicate_count
FROM employees e
JOIN salary s
ON e.emp_id = s.emp_id
GROUP BY e.emp_id
HAVING COUNT(*) > 1;
```

---

# 6. Find Highest Salary Employee Department Wise

## Question:
Find highest salary employee from each department.

## Query:
```sql
SELECT e.emp_name,
       d.department_name,
       e.salary
FROM employees e
JOIN departments d
ON e.dept_id = d.dept_id
WHERE (e.dept_id, e.salary) IN (
    SELECT dept_id,
           MAX(salary)
    FROM employees
    GROUP BY dept_id
);
```

---

# 7. Find Customers Without Orders

## Question:
Find customers who never placed an order.

## Query:
```sql
SELECT c.customer_name
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;
```

---

# 8. Get Total Orders Per Customer

## Question:
Display total orders placed by each customer.

## Query:
```sql
SELECT c.customer_name,
       COUNT(o.order_id) AS total_orders
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
GROUP BY c.customer_name;
```

---

# 9. Find Products Never Sold

## Question:
Find products that were never sold.

## Query:
```sql
SELECT p.product_name
FROM products p
LEFT JOIN order_details od
ON p.product_id = od.product_id
WHERE od.product_id IS NULL;
```

---

# 10. Multi-Table JOIN Query

## Question:
Display order details with customer name and product name.

## Query:
```sql
SELECT o.order_id,
       c.customer_name,
       p.product_name
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id
JOIN products p
ON o.product_id = p.product_id;
```

---

# 11. Find Second Highest Salary Using JOIN

## Query:
```sql
SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);
```

---

# 12. Find Employees Earning More Than Department Average

## Query:
```sql
SELECT e.emp_name,
       e.salary,
       d.department_name
FROM employees e
JOIN departments d
ON e.dept_id = d.dept_id
WHERE e.salary > (
    SELECT AVG(salary)
    FROM employees
    WHERE dept_id = e.dept_id
);
```

---

# 13. Display Department Wise Employee Count

## Query:
```sql
SELECT d.department_name,
       COUNT(e.emp_id) AS employee_count
FROM departments d
LEFT JOIN employees e
ON d.dept_id = e.dept_id
GROUP BY d.department_name;
```

---

# 14. Find Employees Joined in Same Department

## Query:
```sql
SELECT e1.emp_name,
       e2.emp_name,
       e1.dept_id
FROM employees e1
JOIN employees e2
ON e1.dept_id = e2.dept_id
AND e1.emp_id <> e2.emp_id;
```

---

# 15. Find Missing Records Between Two Tables

## Query:
```sql
SELECT a.id
FROM table_a a
LEFT JOIN table_b b
ON a.id = b.id
WHERE b.id IS NULL;
```

---

# 16. FULL OUTER JOIN Example

## Query:
```sql
SELECT e.emp_name,
       d.department_name
FROM employees e
FULL OUTER JOIN departments d
ON e.dept_id = d.dept_id;
```

---

# 17. CROSS JOIN Example

## Query:
```sql
SELECT s.size_name,
       c.color_name
FROM sizes s
CROSS JOIN colors c;
```

---

# 18. Find Employee with Latest Salary Record

## Query:
```sql
SELECT e.emp_name,
       s.salary
FROM employees e
JOIN salary s
ON e.emp_id = s.emp_id
WHERE s.salary_date = (
    SELECT MAX(salary_date)
    FROM salary
    WHERE emp_id = e.emp_id
);
```

---

# 19. Find Common Records Between Two Tables

## Query:
```sql
SELECT a.id
FROM table_a a
INNER JOIN table_b b
ON a.id = b.id;
```

---

# 20. Anti JOIN Query

## Question:
Find records present in first table but not second table.

## Query:
```sql
SELECT a.*
FROM table_a a
LEFT JOIN table_b b
ON a.id = b.id
WHERE b.id IS NULL;
```

---

# Most Important JOIN Concepts Asked Practically

- INNER JOIN
- LEFT JOIN
- SELF JOIN
- Multiple JOINs
- Duplicate Handling
- NULL Handling
- Aggregation with JOIN
- JOIN + Window Functions
- Anti JOIN
- Performance Optimization

---

# Real-Time Interview Tips

- Explain relationship between tables first
- Use aliases properly
- Handle NULLs carefully
- Mention why you used specific JOIN
- Avoid SELECT *
- Explain business logic clearly

---
