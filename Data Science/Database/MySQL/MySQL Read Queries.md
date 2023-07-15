
Tags: #mysql 
💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar

------------------------------------------
#### Basic Reading Queries: 

#### `SHOW TABLES;`

`show tables;`: shows tables FROM SELECTed data base 

```MySQL
SHOW TABLES;
```

```Output
+---------------------+
| Tables_in_nc_coffee |
+---------------------+
| coffee_table        |
+---------------------+
```

#### `SELECT ... FROM ...`

 `SELECT * FROM table_name;`: shows whole table ,  `*` means you are SELECTing all of the values

```mysql
SELECT * FROM coffee_table;
```

``` output
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
```

 `SELECT col1, col2, ... FROM table_name;`:to see values for specific columns rather than for all the columns.

```mysql
SELECT name, roast FROM coffee_table;
```

```output
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
```

#### `WHERE`

`SELECT * FROM table_name WHERE condition;`: Gives you ability to apply conditions 

```mysql
SELECT * FROM coffee_table WHERE roast = 'medium';
```

```output
+------+------------+-------------+--------+
| id   | name       | region      | roast  |
+------+------------+-------------+--------+
|    1 | Omkar      | Technoworld | medium |
|    2 | docker run | mexico      | medium |
|    3 | helpdesk   | honduras    | medium |
+------+------------+-------------+--------+
```

#### `AND`, `OR` and `NOT`

`SELECT * FROM table_name WHERE cond1 and cond2;`  :to return rows that satisfy multiple conditions. You can use  `and` `or` and `not` for checking multiple conditions.   

```mysql
SELECT * FROM coffee_table WHERE roast = 'medium' and region = 'mexico';
```

```output
+------+------------+--------+--------+
| id   | name       | region | roast  |
+------+------------+--------+--------+
|    2 | docker run | mexico | medium |
+------+------------+--------+--------+
```

#### `AS`

 `SELECT old_col_name as new_col_name FROM coffee_table;`: in here  `as`  keywords replaces old name with new name for columns. We can use multiple `as` separated BY comma `,`

```mysql
SELECT name AS customer FROM coffee_table;
```

```output
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

#### `CONCAT()`

`SELECT concat(col1,' any_message ', col2) as col_title FROM table_name WHERE codition;`  : concatenating two columns form tables 

```mysql
SELECT concat(name,' is FROM ', region) as location FROM coffee_table WHERE roast = 'medium';
```

```output
+---------------------------+
| location                  |
+---------------------------+
| Omkar is FROM Technoworld |
| docker run is FROM mexico |
| helpdesk is FROM honduras |
+---------------------------+
```

Using conditional Loops:

```mysql
mysql> SELECT
    ->   name,
    ->   (CASE roast
    ->     WHEN 'medium' THEN 'Ready'
    ->     ELSE 'Not Ready'
    ->   END) AS status
    -> FROM coffee_table;
```

```output
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
```

#### `LIMIT`

`SELECT * FROM table_name LIMIT integer;`:  `int` as how many rows you want to fetch
	(If you set limit to be more than records than we have then it give all records without error 💀)

```MySQL
SELECT * FROM coffee_table LIMIT 3;
```

```Output
+------+------------+-------------+--------+
| id   | name       | region      | roast  |
+------+------------+-------------+--------+
|    1 | Omkar      | Technoworld | medium |
|    2 | docker run | mexico      | medium |
|    3 | helpdesk   | honduras    | medium |
+------+------------+-------------+--------+
```

#### `RAND()`

`mysql> SELECT * FROM coffee_table ORDER BY rand() limit 3;` : Returning n Random Records FROM a Table

```MySQL
SELECT * FROM coffee_table ORDER BY rand() LIMIT 3;
```

```Output
+------+----------+-------------+--------+
| id   | name     | region      | roast  |
+------+----------+-------------+--------+
|    3 | helpdesk | honduras    | medium |
|    4 | on-call  | peru        | dark   |
|    1 | Omkar    | Technoworld | medium |
+------+----------+-------------+--------+
```

#### `IS NULL` and `IS NOT NULL`

`SELECT * FROM table_name WHERE col_name IS NULL;` :  to check if given column has null values or not : `IS NOT NULL`

```MySQL
SELECT * FROM coffee_table WHERE roast IS NOT NULL;
```

```Output
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

SELECTs values within a given range. The values can be numbers, text, or dates.
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

-----

#### `DISTINCT`

works like `unique()` FROM pandas and shows unique entries only

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

#### `COUNT()`

`SELECT COUNT(DISTINCT Country) FROM Customers;`: gives count of unique values

```MYSQL
SELECT COUNT(DISTINCT Country) FROM Customers;
```

```Output
+-------------------------+
| COUNT(DISTINCT Country) |
+-------------------------+
|                       4 |
+-------------------------+
```
-----


### Sorting Query Result:

![[Pasted image 20230515195314.png]]

#### `ORDER BY ... ASC / DESC`

 `SELECT name, hire_date FROM emp WHERE manager_id = 1 ORDER BY salary ASC;`: Returning Query Results in a Specified ORDER , ==BY default `ORDER BY` is set to `ASC`==
 
```MySQL
SELECT name, hire_date FROM emp WHERE manager_id = 1 ORDER BY salary ASC;
```

```Output
+--------------+------------+
| name         | hire_date  |
+--------------+------------+
| Mark Johnson | 2022-03-10 |
| Olivia Davis | NULL       |
| Jane Smith   | 2021-05-15 |
| James Wilson | 2022-09-05 |
+--------------+------------+
```

Sorting BY Multiple Fields: `ORDER BY`

```MySQL
SELECT name, hire_date FROM emp WHERE manager_id = 1 ORDER BY salary ASC;
```

```Output
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
```

#### `ORDER BY SUBSTR()`

Sorting BY Sub strings : `ORDER BY substr`

```MySQL
SELECT name,role FROM emp ORDER BY substr(role, length(role)-1);
```

```Output
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
```

 Dealing with Nulls When Sorting 🧠

```MySQL
mysql> SELECT name, age FROM (
    -> SELECT name, age,
    -> CASE WHEN age IS null THEN 0 END 1 END AS is_null
    -> FROM emp ) x
    -> ORDER BY is_null DESC,age;
```

```
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
```

---------------------
>[!cite]
>Author:  [Omkar Pawar](https://www.linkedin.com/in/omkarpawar1430/): https://www.linkedin.com/in/omkarpawar1430/
>[[MySQL Maths Queries]]
>[[MySQL Pattern Match]]

