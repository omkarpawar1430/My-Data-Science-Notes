
Tags: #mysql 

------------------------------------------

1. `ALTER TABLE YourTableName RENAME TO NewTableName;`: change the current table name.
```
mysql> show tables;
+-----------------------+
| Tables_in_employee_db |
+-----------------------+
| department            |
| emp                   |
+-----------------------+
2 rows in set (0.00 sec)

mysql> ALTER TABLE department RENAME TO dep;
Query OK, 0 rows affected (0.04 sec)

mysql> show tables;
+-----------------------+
| Tables_in_employee_db |
+-----------------------+
| dep                   |
| emp                   |   
+-----------------------+
2 rows in set (0.00 sec)
```

2. To add new column to existing Table:
```
UPDATE YourTableName
SET city = 'New York'
WHERE id = 1;
```

>[!warning]
>Be careful when updating records. If you omit the `WHERE` clause, ALL records will be updated!

-----------

## INSERTING QUERIES

### Inserting new record/records

```MySQL
mysql> INSERT INTO dep (DEPT_NO, DNAME, LOC)
    -> values(50, 'Programming', 'Baltimore'), 
    -> (60, 'new_dep', 'new_loc');
```

we can multiple records at same time. 

```Output

mysql> SELECT * FROM dep;
+---------+-------------+-----------+
| DEPT_NO | DNAME       | LOC       |
+---------+-------------+-----------+
|      10 | Accounting  | New York  |
|      20 | Research    | Dallas    |
|      30 | Sales       | Chicago   |
|      40 | Operations  | Boston    |
|      50 | Programming | Baltimore |
|      60 | new_dep     | new_loc   |
+---------+-------------+-----------+

```

### INSERTING DEFAULT VALUES

```mysql
CREATE TABLE Table_Name_ (id INT DEFAULT 23)
```

>[!note]
>First create a Table with default value  then we can use below queries

```MySQL
mysql> INSERT INTO def values();
```

```Output
mysql> SELECT * FROM def;
+------+---------+
| id   | pension |
+------+---------+
|    0 |       0 |
+------+---------+
```

- MORE QUERIES

```MySQL
mysql> INSERT INTO def (id) VALUES (1);
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO def (pension) VALUES(234);
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO def VALUES(2, 3434);
Query OK, 1 row affected (0.01 sec)

```

```Output
mysql> SELECT * FROM def;
+------+---------+
| id   | pension |
+------+---------+
|    0 |       0 |
|    1 |       0 |
|    0 |     234 |
|    2 |    3434 |
+------+---------+
```

-------

### Copying Rows from One Table into Another

```MYSQL
mysql> CREATE TABLE east_dep(DEPT_NO INT(2), DEPT_NAME VARCHAR(50), LOC VARCHAR(50));
Query OK, 0 rows affected, 1 warning (0.06 sec)

mysql> INSERT INTO east_dep(DEPT_NO, DEPT_NAME, LOC)
    -> SELECT DEPT_NO, DNAME, LOC
    -> FROM dep
    -> WHERE LOC IN ('New York', 'Boston');
Query OK, 2 rows affected (0.02 sec)
Records: 2  Duplicates: 0  Warnings: 0
```

```
mysql> SELECT * FROM east_dep;
+---------+------------+----------+
| DEPT_NO | DEPT_NAME  | LOC      |
+---------+------------+----------+
|      10 | Accounting | New York |
|      40 | Operations | Boston   |
+---------+------------+----------+
```

------------
### Copying a Table Definition

```MySQL

mysql> CREATE TABLE dep_2
    -> AS
    -> SELECT * FROM dep
    -> WHERE 1 = 0;
Query OK, 0 rows affected (0.06 sec)
Records: 0  Duplicates: 0  Warnings: 0

```

>[!note]
> `WHERE 1 = 0` is required to change setting so it will not copy any rows.






```Mysql
mysql> SELECT * FROM dep_2;
Empty set (0.00 sec)
/*we have succesfully copeid the structer of dep*/ 
```

### Syntax for writing Comment `/*comment*/`

>When using Create Table As Select (CTAS), all rows from your query will be used to populate the new table you are creating unless you specify a false condition in the WHERE clause. In the solution provided, the expression “1 = 0” in the WHERE clause of the query causes no rows to be returned. Thus, the result of the CTAS statement is an empty table based on the columns in the SELECT clause of the query. - O-Reilly-SQL-Cookbook-2nd-Edition-Final


-----------

## UPDATING QUERIES

### Modifying Records in a Table

```MySQL
mysql> UPDATE emp
    -> SET salary = salary*1.10
    -> WHERE department_id = 30;
```

giving employees in department 30, 10% hike.

```Output

mysql> select name, salary, department_id FROM emp;
+----------------+---------+---------------+
| name           | salary  | department_id |
+----------------+---------+---------------+
| John Doe       | 5000.00 |            10 |
| Jane Smith     | 6000.00 |          NULL |
| Mark Johnson   |    NULL |            10 |
| Sarah Williams | 5500.00 |          NULL |
| Emily Johnson  | 7000.00 |            20 |
| Michael Brown  | 7150.00 |            30 |
| James Wilson   | 8800.00 |            30 |
+----------------+---------+---------------+

```

------------------

### In case If you just want to see the updated values instead of making changes in original table

```MySQL

mysql> SELECT name, salary as current_sal, salary*0.10 as amt_to_add, salary*1.10 as new_sal FROM emp WHERE department_id = 20;
```

```Output
+---------------+-------------+------------+-----------+
| name          | current_sal | amt_to_add | new_sal   |
+---------------+-------------+------------+-----------+
| Emily Johnson |     7000.00 |   700.0000 | 7700.0000 |
+---------------+-------------+------------+-----------+
```

--------

### Updating When Corresponding Rows Exist

```MySQL

mysql> UPDATE emp
    -> SET salary = salary*1.50
    -> WHERE id in (SELECT id FROM emp_bonus);

Query OK, 2 rows affected (0.02 sec)
Rows matched: 3  Changed: 2  Warnings: 0

```

```Output
mysql> SELECT name, salary FROM emp;
+----------------+----------+
| name           | salary   |
+----------------+----------+
| John Doe       |  5000.00 |
| Jane Smith     |  9000.00 |
| Mark Johnson   |     NULL |
| Sarah Williams |  5500.00 |
| Emily Johnson  | 10500.00 |
| Michael Brown  |  7150.00 |
| James Wilson   |  8800.00 |
+----------------+----------+

```

----

### Updating with Values from Another Table

new_sal table
```
mysql> SELECT * FROM new_sal;
+---------+------+
| dept_no | sal  |
+---------+------+
|      10 | 4000 |
+---------+------+
```

```MySQL
mysql> UPDATE emp, new_sal SET emp.salary = new_sal.sal WHERE emp.department_id = new_sal.dept_no;
Query OK, 2 rows affected (0.02 sec)
```

```Output
mysql> SELECT name, salary, department_id FROM emp;
+----------------+----------+---------------+
| name           | salary   | department_id |
+----------------+----------+---------------+
| John Doe       |  4000.00 |            10 |
| Jane Smith     |  9000.00 |          NULL |
| Mark Johnson   |  4000.00 |            10 |
| Sarah Williams |  5500.00 |          NULL |
| Emily Johnson  | 10500.00 |            20 |
| Michael Brown  |  7150.00 |            30 |
| James Wilson   |  8800.00 |            30 |
+----------------+----------+---------------+
```

-----------






-------
### links:
https://www.w3schools.com/MySQL/mysql_update.asp
### Books:
O-Reilly-SQL-Cookbook-2nd-Edition-Final
