------------------------- 
Tags: #mysql 
Date Created:  2023-07-12, @ 10:10

---
>[!info] Keywords
>* min, max, count, avg, sum

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

>[!summary] 
>1. MySQL is capable of doing basic maths operations like `MIN()`, `MAX()`,`COUNT()`, `AVG()` and `SUM()`.

----
>[!cite]
> Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> [ChatGPT](https://chat.openai.com/)
> 
> 
