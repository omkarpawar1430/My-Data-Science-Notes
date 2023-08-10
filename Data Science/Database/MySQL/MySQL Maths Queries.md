------------------------- 
Tags: #mysql #database 
Date Created:  2023-07-12, @ 10:10

---
>[!info] Keywords
>* min, max, count, avg, sum and group by 

```MYSQL
mysql> SELECT ProductName, Price FROM Products;
```

``` Output
+------------------------------+-------+
| ProductName                  | Price |
+------------------------------+-------+
| Chais                        | 18.00 |
| Chang                        | 19.00 |
| Aniseed Syrup                | 10.00 |
| Chef Anton's Cajun Seasoning | 22.00 |
| Chef Anton's Gumbo Mix       | 21.35 |
+------------------------------+-------+
```

----

### `MIN()` and `MAX()`:
Returns the minimum and maximum entry. 

```MySQL
SELECT MIN(Price) AS LowestPrice FROM Products;
```

```Output
+-------------+
| LowestPrice |
+-------------+
|       10.00 |
+-------------+
```

```MySQL
SELECT MAX(Price) AS HighestPrice FROM Products;
```

```Output
+--------------+
| HighestPrice |
+--------------+
|        22.00 |
+--------------+
```
-----

### `COUNT()` 
The `COUNT()` function returns the number of rows that matches a specified criterion.

```MySQL
SELECT COUNT(ProductID) FROM Products;
```

```Output
+------------------+
| COUNT(ProductID) |
+------------------+
|                5 |
+------------------+
```

Counting Rows in a Table
```MySQL 
mysql> SELECT COUNT(*) FROM  Products;
+----------+
| COUNT(*) |
+----------+
|        5 |
+----------+
```

>[!INFO]
>Null values are ignored. 

----

### `AVG()`
Returns average value of the Numerical columns.

```MySQL
SELECT AVG(Price) FROM Products;
```

```Output
+------------+
| AVG(Price) |
+------------+
|  18.070000 |
+------------+
```

---

### `SUM()`
Returns sum of the Numerical Columns.

```MySQL
SELECT SUM(Price) FROM Products;
```

```Output
+------------+
| SUM(Price) |
+------------+
|      90.35 |
+------------+
```

Generating a Running Total
```mysql

mysql> SELECT ProductName, Price, SUM(Price) OVER (ORDER BY Price) AS running_total FROM Products;
```

```
+------------------------------+-------+---------------+
| ProductName                  | Price | running_total |
+------------------------------+-------+---------------+
| Aniseed Syrup                | 10.00 |         10.00 |
| Chais                        | 18.00 |         28.00 |
| Chang                        | 19.00 |         47.00 |
| Chef Anton's Gumbo Mix       | 21.35 |         68.35 |
| Chef Anton's Cajun Seasoning | 22.00 |         90.35 |
+------------------------------+-------+---------------+

```

Finding percentage Total
```MySQL

mysql> SELECT (SUM(
    -> CASE WHEN department_id = 30 THEN salary END)/SUM(salary)
    -> )*100 AS pct
    -> FROM emp;
```

```
+-----------+
| pct       |
+-----------+
| 38.949939 |
+-----------+
```

### `GROUP BY`

```MySQL
mysql> SELECT COUNT(CustomerID), Country
    -> FROM Customers
    -> GROUP BY Country;
```

```Output
+-------------------+---------+
| COUNT(CustomerID) | Country |
+-------------------+---------+
|                 1 | Germany |
|                 2 | Mexico  |
|                 1 | UK      |
|                 1 | Sweden  |
+-------------------+---------+
```

- Another one with Count

```MySQL
mysql> SELECT COUNT(CustomerID), Country
    -> FROM Customers
    -> GROUP BY Country
    -> ORDER BY COUNT(CustomerID) DESC;
```

```Output
+-------------------+---------+
| COUNT(CustomerID) | Country |
+-------------------+---------+
|                 2 | Mexico  |
|                 1 | Germany |
|                 1 | UK      |
|                 1 | Sweden  |
+-------------------+---------+
```



>[!summary] 
>1. MySQL is capable of doing basic maths operations like `MIN()`, `MAX()`,`COUNT()`, `AVG()` , `SUM()` `GROUP BY`

----
>[!cite]
> Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> [ChatGPT](https://chat.openai.com/)
