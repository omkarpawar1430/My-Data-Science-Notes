
Tags: #mysql 

------------------------------------------
#### Basic: 
0. `show tables;`: shows tables from selected data base 
1. `select * from table_name;`: shows whole table ,  `*` means you are selecting all of the values
```
mysql> select * from coffee_table;
+------+------------+-------------+----------+
| id   | name       | region      | roast    |
+------+------------+-------------+----------+
|    1 | Omkar      | Technoworld | medium   |
|    2 | docker run | mexico      | medium   |
|    3 | helpdesk   | honduras    | medium   |
|    4 | on-call    | peru        | dark     |
|    5 | ifconfig   | tanzania    | blonde   |
|    6 | traceroute | bali        | med-dark |
+------+------------+-------------+----------+
6 rows in set (0.00 sec)
```
2. `select * from table_name where condition;`: Gives you ability to apply conditions 
```
mysql> select * from coffee_table where roast = 'medium';
+------+------------+-------------+--------+
| id   | name       | region      | roast  |
+------+------------+-------------+--------+
|    1 | Omkar      | Technoworld | medium |
|    2 | docker run | mexico      | medium |
|    3 | helpdesk   | honduras    | medium |
+------+------------+-------------+--------+
3 rows in set (0.00 sec)

```
3. `select * from table_name where cond1 and cond2;`  :to return rows that satisfy multiple conditions. Similar to `and` we can use `or` and `not`.  
```
mysql> select * from coffee_table where roast = 'medium' and region = 'mexico';
+------+------------+--------+--------+
| id   | name       | region | roast  |
+------+------------+--------+--------+
|    2 | docker run | mexico | medium |
+------+------------+--------+--------+
```
4. `select col1, col2, ... from table_name;`:to see values for specific columns rather than for all the columns.
```
mysql> select name, roast from coffee_table;
+------------+----------+
| name       | roast    |
+------------+----------+
| Omkar      | medium   |
| docker run | medium   |
| helpdesk   | medium   |
| on-call    | dark     |
| ifconfig   | blonde   |
| traceroute | med-dark |
+------------+----------+
6 rows in set (0.00 sec)
```
5. `select old_col_name as new_col_name from coffee_table;`: in here  `as`  keywords replaces old name with new name for columns. We can use multiple `as` separated by comma `,`
```
mysql> select name as customer from coffee_table;
+------------+
| customer   |
+------------+
| Omkar      |
| docker run |
| helpdesk   |
| on-call    |
| ifconfig   |
| traceroute |
+------------+
```
6. `select concat(col1,' any_message ', col2) as col_title from table_name where codition;`  : concatenating two columns form tables 
```
mysql> select concat(name,' is from ', region) as location from coffee_table where roast = 'medium';
+---------------------------+
| location                  |
+---------------------------+
| Omkar is from Technoworld |
| docker run is from mexico |
| helpdesk is from honduras |
+---------------------------+
3 rows in set (0.00 sec)
```
7. Using conditional Loops:
```
mysql> SELECT
    ->   name,
    ->   (CASE roast
    ->     WHEN 'medium' THEN 'Ready'
    ->     ELSE 'Not Ready'
    ->   END) AS status
    -> FROM coffee_table;
+------------+-----------+
| name       | status    |
+------------+-----------+
| Omkar      | Ready     |
| docker run | Ready     |
| helpdesk   | Ready     |
| on-call    | Not Ready |
| ifconfig   | Not Ready |
| traceroute | Not Ready |
+------------+-----------+
6 rows in set (0.00 sec)

```
8. `select * from table_name limit integer;`:  `int` as how many rows you want to fetch
	If you set limit to be more than records than we have then it give all records without error 💀
```
mysql> select * from coffee_table limit 3;
+------+------------+-------------+--------+
| id   | name       | region      | roast  |
+------+------------+-------------+--------+
|    1 | Omkar      | Technoworld | medium |
|    2 | docker run | mexico      | medium |
|    3 | helpdesk   | honduras    | medium |
+------+------------+-------------+--------+

```
9. `mysql> select * from coffee_table order by rand() limit 3;` : Returning n Random Records from a Table
```
mysql> select * from coffee_table order by rand() limit 3;
+------+----------+-------------+--------+
| id   | name     | region      | roast  |
+------+----------+-------------+--------+
|    3 | helpdesk | honduras    | medium |
|    4 | on-call  | peru        | dark   |
|    1 | Omkar    | Technoworld | medium |
+------+----------+-------------+--------+
3 rows in set (0.00 sec)
```
10. `select * from table_name where col_name IS NULL;` :  to check if given column has null values or not : `IS NOT NULL`
```MySQL
mysql> select * from coffee_table where roast IS NOT NULL;
+------+------------+-------------+----------+
| id   | name       | region      | roast    |
+------+------------+-------------+----------+
|    1 | Omkar      | Technoworld | medium   |
|    2 | docker run | mexico      | medium   |
|    3 | helpdesk   | honduras    | medium   |
|    4 | on-call    | peru        | dark     |
|    5 | ifconfig   | tanzania    | blonde   |
|    6 | traceroute | bali        | med-dark |
+------+------------+-------------+----------+
6 rows in set (0.00 sec)
```

- Using `WHERE` condition:

```MySQL
SELECT CustomerName, Country FROM Customers WHERE Country = 'Mexico';

```

```output
+------------------------------------+---------+
| CustomerName                       | Country |
+------------------------------------+---------+
| Ana Trujillo Emparedados y helados | Mexico  |
| Antonio Moreno Taquería            | Mexico  |
+------------------------------------+---------+

```

---

#### `IN`
- looking for multiple values at same time

```mysql
SELECT ContactName, Country FROM Customers WHERE Country IN ('Germany', 'France', 'UK');
```

```output
+--------------+---------+
| ContactName  | Country |
+--------------+---------+
| Maria Anders | Germany |
| Thomas Hardy | UK      |
+--------------+---------+
```

- using `NOT` with `IN`:

```MySQL

SELECT ContactName, Country FROM Customers WHERE Country NOT IN ('Germany', 'France', 'UK');
```

```Output
+--------------------+---------+
| ContactName        | Country |
+--------------------+---------+
| Ana Trujillo       | Mexico  |
| Antonio Moreno     | Mexico  |
| Christina Berglund | Sweden  |
+--------------------+---------+
```

---------
#### `BETWEEN`

Selects values within a given range. The values can be numbers, text, or dates.
The `BETWEEN` operator is inclusive: begin and end values are included.

```MySQL
 SELECT * FROM Products WHERE Price BETWEEN 10 AND 20;
```

```Output
+-----------+---------------+------------+------------+---------------------+-------+
| ProductID | ProductName   | SupplierID | CategoryID | Unit                | Price |
+-----------+---------------+------------+------------+---------------------+-------+
|         1 | Chais         |          1 |          1 | 10 boxes x 20 bags  | 18.00 |
|         2 | Chang         |          1 |          1 | 24 - 12 oz bottles  | 19.00 |
|         3 | Aniseed Syrup |          1 |          2 | 12 - 550 ml bottles | 10.00 |
+-----------+---------------+------------+------------+---------------------+-------+
```

#### `DISTINCT`
works like `unique()` from pandas and shows unique entries only

```mysql
SELECT DISTINCT Country FROM Customers;
```

```Output
+---------+
| Country |
+---------+
| Germany |
| Mexico  |
| UK      |
| Sweden  |
+---------+
```

13. `SELECT COUNT(DISTINCT Country) FROM Customers;`: gives count of unique values

```MYSQL
mysql> SELECT COUNT(DISTINCT Country) FROM Customers;
+-------------------------+
| COUNT(DISTINCT Country) |
+-------------------------+
|                       4 |
+-------------------------+

```


#### Sorting Query Result:

![[Pasted image 20230515195314.png]]
1. `select name, hire_date from emp where manager_id = 1 order by salary asc;`: Returning Query Results in a Specified Order , ==by default `order by` is set to `asc`==
```
mysql> select name, hire_date from emp where manager_id = 1 order by salary asc;
+--------------+------------+
| name         | hire_date  |
+--------------+------------+
| Mark Johnson | 2022-03-10 |
| Olivia Davis | NULL       |
| Jane Smith   | 2021-05-15 |
| James Wilson | 2022-09-05 |
+--------------+------------+
4 rows in set (0.00 sec)

```
2. Sorting by Multiple Fields: `order by`
```
mysql> select name, hire_date from emp where manager_id = 1 order by salary asc;
+----------------+------+------------+
| name           | age  | hire_date  |
+----------------+------+------------+
| Jane Smith     |   30 | 2021-05-15 |
| Sarah Williams |   28 | NULL       |
| Emily Johnson  |   35 | 2022-06-20 |
| John Doe       |   25 | 2022-01-01 |
| Mark Johnson   | NULL | 2022-03-10 |
| James Wilson   |   40 | 2022-09-05 |
| Michael Brown  |   32 | 2023-02-12 |
| Olivia Davis   | NULL | NULL       |
+----------------+------+------------+
8 rows in set (0.01 sec)

```
3. Sorting by Sub strings : `order by substr`
```
mysql> select name,role from emp order by substr(role, length(role)-1);
+----------------+-----------+
| name           | role      |
+----------------+-----------+
| James Wilson   | salesman  |
| John Doe       | manager   |
| Olivia Davis   | president |
| Jane Smith     | clerk     |
| Mark Johnson   | clerk     |
| Sarah Williams | analyst   |
| Emily Johnson  | analyst   |
| Michael Brown  | analyst   |
+----------------+-----------+
8 rows in set (0.00 sec)

```
4. Dealing with Nulls When Sorting
```
mysql> select name, age from (
    -> select name, age,
    -> case when age is null then 0 else 1 end as is_null
    -> from emp ) x
    -> order by is_null desc,age;
+----------------+------+
| name           | age  |
+----------------+------+
| John Doe       |   25 |
| Sarah Williams |   28 |
| Jane Smith     |   30 |
| Michael Brown  |   32 |
| Emily Johnson  |   35 |
| James Wilson   |   40 |
| Mark Johnson   | NULL |
| Olivia Davis   | NULL |
+----------------+------+
8 rows in set (0.00 sec)

```


---------------------
#### links:
[[MySQL Maths Queries]]
[[MySQL Pattern Match]]
[[]]