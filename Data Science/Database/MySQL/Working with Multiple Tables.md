
Tags: #mysql #database 
Date Created:  2023-07-22, @ 15:50

------------------------------------------
### Tables from `ecom` database:

![[Pasted image 20230722155715.png]]
```MYSQL
mysql> SELECT * FROM Orders;
+---------+------------+------------+------------+-----------+
| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
+---------+------------+------------+------------+-----------+
|   10278 |          5 |          8 | 1996-08-12 |         2 |
|   10280 |          5 |          2 | 1996-08-14 |         1 |
|   10308 |          2 |          7 | 1996-09-18 |         3 |
|   10355 |          4 |          6 | 1996-11-15 |         1 |
|   10365 |          3 |          3 | 1996-11-27 |         2 |
|   10383 |          4 |          8 | 1996-12-16 |         3 |
|   10384 |          5 |          3 | 1996-12-16 |         3 |
+---------+------------+------------+------------+-----------+
7 rows in set (0.00 sec)

mysql> SELECT * FROM Products;
+-----------+------------------------------+------------+------------+---------------------+-------+
| ProductID | ProductName                  | SupplierID | CategoryID | Unit                | Price |
+-----------+------------------------------+------------+------------+---------------------+-------+
|         1 | Chais                        |          1 |          1 | 10 boxes x 20 bags  | 18.00 |
|         2 | Chang                        |          1 |          1 | 24 - 12 oz bottles  | 19.00 |
|         3 | Aniseed Syrup                |          1 |          2 | 12 - 550 ml bottles | 10.00 |
|         4 | Chef Anton's Cajun Seasoning |          2 |          2 | 48 - 6 oz jars      | 22.00 |
|         5 | Chef Anton's Gumbo Mix       |          2 |          2 | 36 boxes            | 21.35 |
+-----------+------------------------------+------------+------------+---------------------+-------+
5 rows in set (0.00 sec)

mysql> SELECT * FROM Shippers;
+-----------+------------------+----------------+
| ShipperID | ShipperName      | Phone          |
+-----------+------------------+----------------+
|         1 | Speedy Express   | (503) 555-9831 |
|         2 | United Package   | (503) 555-3199 |
|         3 | Federal Shipping | (503) 555-9931 |
+-----------+------------------+----------------+
```

----------
## WORKING WITH MULTIPLE TABLES:

### `UNION ALL`
Stacking One Rowset atop Another.

The `UNION` operator is used to combine the result-set of two or more `SELECT` statements.

- Every `SELECT` statement within `UNION` must have the same number of columns
- The columns must also have similar data types
- The columns in every `SELECT` statement must also be in the same order

```MySQL
SELECT CustomerID FROM Customers UNION ALL SELECT CustomerID FROM Orders;
```

```Output
+------------+
| CustomerID |
+------------+
|          1 |
|          2 |
|          3 |
|          4 |
|          5 |
|          5 |
|          5 |
|          2 |
|          4 |
|          3 |
|          4 |
|          5 |
+------------+
```

- With Multiple Columns:
The `UNION` operator selects only distinct values by default. To allow duplicate values, use `UNION ALL`:

```MySQL

SELECT CustomerID, CustomerName AS Customer_Name_and_OrderID FROM Customers UNION ALL SELECT CustomerID, OrderID FROM Orders;
```

```Output
+------------+------------------------------------+
| CustomerID | Customer_Name_and_OrderID          |
+------------+------------------------------------+
|          1 | Alfreds Futterkiste                |
|          2 | Ana Trujillo Emparedados y helados |
|          3 | Antonio Moreno Taquería            |
|          4 | Around the Horn                    |
|          5 | Berglunds snabbköp                 |
|          5 | 10278                              |
|          5 | 10280                              |
|          2 | 10308                              |
|          4 | 10355                              |
|          3 | 10365                              |
|          4 | 10383                              |
|          5 | 10384                              |
+------------+------------------------------------+
```


### `UNION`
Removes Duplicates. 
```MySQL
SELECT CustomerID FROM Customers UNION SELECT CustomerID FROM Orders;
```

```Output
+------------+
| CustomerID |
+------------+
|          1 |
|          2 |
|          3 |
|          4 |
|          5 |
+------------+
```

-------

###  Combining Related Rows

```MySQL
mysql> SELECT C.CustomerID, C.Address, O.OrderID FROM Customers C, Orders O
    -> WHERE C.CustomerID = O.CustomerID;
```

```Output
+------------+--------------------------------+---------+
| CustomerID | Address                        | OrderID |
+------------+--------------------------------+---------+
|          5 | Berguvsvägen 8                 |   10278 |
|          5 | Berguvsvägen 8                 |   10280 |
|          2 | Avda. de la Constitución 2222  |   10308 |
|          4 | 120 Hanover Sq.                |   10355 |
|          3 | Mataderos 2312                 |   10365 |
|          4 | 120 Hanover Sq.                |   10383 |
|          5 | Berguvsvägen 8                 |   10384 |
+------------+--------------------------------+---------+
```

### `INNER JOIN`

Alternative way to the above method. Works the same with `JOIN` only. 

```MySQL

mysql> SELECT C.CustomerID, C.Address, O.OrderID FROM Customers C INNER JOIN Orders O ON (C.CustomerID = O.CustomerID);
```

```Output
+------------+--------------------------------+---------+
| CustomerID | Address                        | OrderID |
+------------+--------------------------------+---------+
|          5 | Berguvsvägen 8                 |   10278 |
|          5 | Berguvsvägen 8                 |   10280 |
|          2 | Avda. de la Constitución 2222  |   10308 |
|          4 | 120 Hanover Sq.                |   10355 |
|          3 | Mataderos 2312                 |   10365 |
|          4 | 120 Hanover Sq.                |   10383 |
|          5 | Berguvsvägen 8                 |   10384 |
+------------+--------------------------------+---------+
```

```MySQL
mysql> SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate FROM Orders INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```

```Output
+---------+------------------------------------+------------+
| OrderID | CustomerName                       | OrderDate  |
+---------+------------------------------------+------------+
|   10278 | Berglunds snabbköp                 | 1996-08-12 |
|   10280 | Berglunds snabbköp                 | 1996-08-14 |
|   10308 | Ana Trujillo Emparedados y helados | 1996-09-18 |
|   10355 | Around the Horn                    | 1996-11-15 |
|   10365 | Antonio Moreno Taquería            | 1996-11-27 |
|   10383 | Around the Horn                    | 1996-12-16 |
|   10384 | Berglunds snabbköp                 | 1996-12-16 |
+---------+------------------------------------+------------+
```

There are other types of [[MySQL JOIN]]s out there. 

-----------

### Creating Table out of Existing Table as View:

```MySQL
mysql> CREATE VIEW V
    -> AS
    -> SELECT CustomerID, ContactName, Country
    -> FROM Customers;

mysql> SELECT * FROM V;
```

```Output
Query OK, 0 rows affected (0.02 sec)

+------------+--------------------+---------+
| CustomerID | ContactName        | Country |
+------------+--------------------+---------+
|          1 | Maria Anders       | Germany |
|          2 | Ana Trujillo       | Mexico  |
|          3 | Antonio Moreno     | Mexico  |
|          4 | Thomas Hardy       | UK      |
|          5 | Christina Berglund | Sweden  |
+------------+--------------------+---------+
```

-------

```MySQL

mysql> SELECT C.CustomerID, C.ContactName, C.Address from Customers C, V WHERE C.CustomerID = V.CustomerID and C.ContactName = V.ContactName and C.Country = 'Mexico';
```

```Output
+------------+----------------+--------------------------------+
| CustomerID | ContactName    | Address                        |
+------------+----------------+--------------------------------+
|          2 | Ana Trujillo   | Avda. de la Constitución 2222  |
|          3 | Antonio Moreno | Mataderos 2312                 |
+------------+----------------+--------------------------------+
```

-----

### Retrieving Values from One Table That Do Not Exist in Another

```MySQL

mysql> SELECT CustomerID, CustomerName FROM Clients WHERE CustomerID NOT IN (SELECT CustomerID FROM Customers);
```

```Output

+------------+----------------------------+
| CustomerID | CustomerName               |
+------------+----------------------------+
|          6 | Blauer See Delikatessen    |
|          7 | Blondel père et fils       |
|          8 | Bólido Comidas preparadas  |
|          9 | Bon app'                   |
|         10 | Bottom-Dollar Marketse     |
+------------+----------------------------+

```

-------
### Retrieving Rows from One Table That Do Not Correspond to Rows in Another
emp table:
![[Pasted image 20230727110354.png]]
dep table:
```dep
mysql> select * from dep;
+---------+------------+----------+
| DEPT_NO | DNAME      | LOC      |
+---------+------------+----------+
|      10 | Accounting | New York |
|      20 | Research   | Dallas   |
|      30 | Sales      | Chicago  |
|      40 | Operations | Boston   |
+---------+------------+----------+
```

- what we want is to find that in which department there are no employees
>expected output `|      40 | Operations | Boston   |`

```MySQL

mysql> SELECT dep.*, emp.name, emp.department_id FROM dep left join emp ON (dep.DEPT_NO = emp.department_id) WHERE emp.department_id is null;
```

```Output
+---------+------------+--------+------+---------------+
| DEPT_NO | DNAME      | LOC    | name | department_id |
+---------+------------+--------+------+---------------+
|      40 | Operations | Boston | NULL |          NULL |
+---------+------------+--------+------+---------------+
```

>🤔 Why are we writing `WHERE` clause?
>output without `WHERE`

```output
mysql> SELECT dep.*, emp.name, emp.department_id FROM dep left join emp ON (dep.DEPT_NO = emp.department_id);
+---------+------------+----------+---------------+---------------+
| DEPT_NO | DNAME      | LOC      | name          | department_id |
+---------+------------+----------+---------------+---------------+
|      10 | Accounting | New York | Mark Johnson  |            10 |
|      10 | Accounting | New York | John Doe      |            10 |
|      20 | Research   | Dallas   | Emily Johnson |            20 |
|      30 | Sales      | Chicago  | James Wilson  |            30 |
|      30 | Sales      | Chicago  | Michael Brown |            30 |
|      40 | Operations | Boston   | NULL          |          NULL |
+---------+------------+----------+---------------+---------------+
```

Because when we are trying to get values that are not present in table `emp` we get `NULL` .

-----------

### Adding Joins to a Query Without Interfering with Other Joins
point 3.6 from SQL Cookbook

values in employee bonus table
```mysql
mysql> SELECT * FROM emp_bonus;
+------+-------------+------+
| id   | date        | type |
+------+-------------+------+
|    2 | 14-FEB-2022 |    1 |
|    5 | 14-FEB-2022 |    2 |
|    3 | 14-DEC-2022 |    3 |
+------+-------------+------+
```

> not every employee got the bonus

still as result of our query we want to see name, location of the department and date if that employee got bonus. thing is we want to see all employees name and department location even if they haven't got any bonus. 

```MySQL

mysql> SELECT emp.name, dep.LOC, emp_bonus.date FROM emp join dep ON (emp.department_id = dep.DEPT_NO) LEFT JOIN emp_bonus ON (emp.id = emp_bonus.id);
```

```Output
+---------------+----------+-------------+
| name          | LOC      | date        |
+---------------+----------+-------------+
| John Doe      | New York | NULL        |
| Mark Johnson  | New York | 14-DEC-2022 |
| Emily Johnson | Dallas   | 14-FEB-2022 |
| Michael Brown | Chicago  | NULL        |
| James Wilson  | Chicago  | NULL        |
+---------------+----------+-------------+
```

by first joining the `emp` with `dep` and then applying `LEFT JOIN` on top of it we get desired result. there are few employees missing because in first `JOIN` there are some `NULL` values. 

-----------

### Identifying and Avoiding Cartesian Products

```MySQL

mysql> SELECT emp.name, dep.LOC
    -> FROM emp, dep
    -> WHERE emp.department_id = 10;
```

```
+--------------+----------+
| name         | LOC      |
+--------------+----------+
| Mark Johnson | New York |
| John Doe     | New York |
| Mark Johnson | Dallas   |
| John Doe     | Dallas   |
| Mark Johnson | Chicago  |
| John Doe     | Chicago  |
| Mark Johnson | Boston   |
| John Doe     | Boston   |
+--------------+----------+
```
This is not an expected result as it is giving employee name many times with different cities. 

```Mysql
mysql> SELECT emp.name, dep.LOC FROM emp, dep WHERE emp.department_id = 10
    -> and
    -> dep.DEPT_NO = emp.department_id;
```

```
+--------------+----------+
| name         | LOC      |
+--------------+----------+
| John Doe     | New York |
| Mark Johnson | New York |
+--------------+----------+
```
This is the right result we were looking for. 


--------



-----
### links:
Database is from W3School's MySQL Tutorial. 
Reference from: O-Reilly-SQL-Cookbook-2nd-Edition-Final

