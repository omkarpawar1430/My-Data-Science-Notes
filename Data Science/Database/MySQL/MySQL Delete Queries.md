
Tags: #mysql 

------------------------------------------
### `DROP DATABASE db_name`: Deletes the whole data base💀

### Deleting All Records from a Table: 

```MySQL
DELETE FROM emp;
#or
TRUNCATE TABLE table_name_;

```

### Deleting a single record: 

Before Deleting ![[Pasted image 20230727105826.png]]

```MySQL
mysql> DELETE FROM emp WHERE department_id = 40;
```

After Deleting
![[Pasted image 20230727110354.png]]

>[!danger]
>**Note:** Be careful when deleting records in a table! Notice the `WHERE` clause in the `DELETE` statement. The `WHERE` clause specifies which record(s) should be deleted. If you omit the `WHERE` clause, all records in the table will be deleted!

-------------

### Deleting Referential Integrity Violations

```mysql
mysql> DELETE FROM emp
    -> WHERE department_id NOT IN (SELECT DEPT_NO FROM dep);
Query OK, 0 rows affected (0.01 sec)

```

--------------------

### Deleting Duplicated

```mysql
mysql> select * from dupes order by 1;
+------+----------+
| id   | name     |
+------+----------+
|    1 | napolean |
|    2 | napolean |
|    3 | napolean |
|    4 | dynamite |
|    5 | omkar    |
|    6 | omkar    |
|    8 | napolean |
+------+----------+
```

```mysql

mysql> DELETE FROM dupes WHERE id NOT IN  (SELECT MIN(id) FROM (SELECT id, name from dupes) tmp GROUP BY name);
Query OK, 4 rows affected (0.01 sec)

```

after deleting duplicating
```mysql

mysql> SELECT * FROM dupes;
+------+----------+
| id   | name     |
+------+----------+
|    1 | napolean |
|    4 | dynamite |
|    5 | omkar    |
+------+----------+

```

------

### Deleting Records Referenced from Another Table

```mysql
mysql> SELECT * FROM dept_acc;
+--------+-------------+
| deptno | acc_name    |
+--------+-------------+
|     10 | Broker Foot |
|     10 | Flesh Wound |
|     10 | Fire        |
|     30 | flood       |
+--------+-------------+
```

### `HAVING`

```mysql
mysql> DELETE FROM emp
    -> WHERE department_id IN ( SELECT deptno FROM dept_acc Group by deptno HAVING COUNT(*) >= 2);
```

```
mysql> SELECT name, department_id FROM emp;
+----------------+---------------+
| name           | department_id |
+----------------+---------------+
| Jane Smith     |          NULL |
| Sarah Williams |          NULL |
| Emily Johnson  |            20 |
| Michael Brown  |            30 |
| James Wilson   |            30 |
+----------------+---------------+
```




---------------------
#### links:
[[]]
[[]]