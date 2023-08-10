
Tags: #mysql 
Date Created:  2023-07-22, @ 11:48

------------------------------------------
### INNER JOIN
![IMAGE](https://www.w3schools.com/MySQL/img_innerjoin.gif)


```MySQL
mysql> SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
    -> FROM Orders
    -> INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
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

---------
### LEFT JOIN
![image2](https://www.w3schools.com/MySQL/img_leftjoin.gif)
```MySQL
mysql> SELECT Customers.CustomerName, Orders.OrderID
    -> FROM Customers
    -> LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
    -> ORDER BY Customers.CustomerName;
```

```Output
+------------------------------------+---------+
| CustomerName                       | OrderID |
+------------------------------------+---------+
| Alfreds Futterkiste                |    NULL |
| Ana Trujillo Emparedados y helados |   10308 |
| Antonio Moreno Taquería            |   10365 |
| Around the Horn                    |   10383 |
| Around the Horn                    |   10355 |
| Berglunds snabbköp                 |   10384 |
| Berglunds snabbköp                 |   10280 |
| Berglunds snabbköp                 |   10278 |
+------------------------------------+---------+
```

-----
### RIGHT JOIN
![image4](https://www.w3schools.com/MySQL/img_rightjoin.gif)

```MySQL
mysql> SELECT Customers.CustomerName, Orders.OrderID FROM Customers RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID ORDER BY Customers.CustomerN
ame;
```

```Output
+------------------------------------+---------+
| CustomerName                       | OrderID |
+------------------------------------+---------+
| Ana Trujillo Emparedados y helados |   10308 |
| Antonio Moreno Taquería            |   10365 |
| Around the Horn                    |   10355 |
| Around the Horn                    |   10383 |
| Berglunds snabbköp                 |   10278 |
| Berglunds snabbköp                 |   10280 |
| Berglunds snabbköp                 |   10384 |
+------------------------------------+---------+
```

----------
### CROSS JOIN

![image3](https://www.w3schools.com/MySQL/img_crossjoin.png)

>[!note]
>`CROSS JOIN` can potentially return very large result-sets!

```MySQL
mysql> SELECT Customers.CustomerName, Orders.OrderID
    -> FROM Customers
    -> CROSS JOIN Orders
    -> WHERE Customers.CustomerID=Orders.CustomerID;
```

```Output
+------------------------------------+---------+
| CustomerName                       | OrderID |
+------------------------------------+---------+
| Berglunds snabbköp                 |   10278 |
| Berglunds snabbköp                 |   10280 |
| Ana Trujillo Emparedados y helados |   10308 |
| Around the Horn                    |   10355 |
| Antonio Moreno Taquería            |   10365 |
| Around the Horn                    |   10383 |
| Berglunds snabbköp                 |   10384 |
+------------------------------------+---------+
```

>[!warning]
> If you add a `WHERE` clause (if table1 and table2 has a relationship), the `CROSS JOIN` will produce the same result as the `INNER JOIN` clause:

---------------------
#### links:
https://www.w3schools.com/MySQL/mysql_join.asp 
