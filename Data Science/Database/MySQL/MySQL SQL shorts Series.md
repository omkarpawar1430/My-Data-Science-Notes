1. What is the full form of SQL...
2. create db :  `Create Database collage_db;`
3
```
mysql> CREATE TABLE students(id INT(2), name VARCHAR(10), course_code INT(1), ye
ar INT(4));
Query OK, 0 rows affected, 3 warnings (0.06 sec)

```
4
```mysql
mysql> insert into students(id, name, course_code, year) values (1, 'Luffy', 1, 1);
Query OK, 1 row affected (0.01 sec)

mysql> select * from students;
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    1 | Luffy |           1 |    1 |
+------+-------+-------------+------+
1 row in set (0.00 sec)

```

```MYSQL
mysql> SELECT * FROM students WHERE course_code IN (2, 4);
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    4 | Ussop |           4 |    2 |
|    5 | Sanji |           2 |    2 |
|    3 | Nami  |           2 |    1 |
+------+-------+-------------+------+
3 rows in set (0.00 sec)

10
mysql> SELECT * FROM students WHERE course_code = 2 AND year = 1;
+------+------+-------------+------+
| id   | name | course_code | year |
+------+------+-------------+------+
|    3 | Nami |           2 |    1 |
+------+------+-------------+------+
1 row in set (0.00 sec)

mysql> SELECT * FROM students WHERE course_code = 2 OR year = 1;
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    1 | Luffy |           1 |    1 |
|    5 | Sanji |           2 |    2 |
|    3 | Nami  |           2 |    1 |
+------+-------+-------------+------+
3 rows in set (0.00 sec)


mysql> SELECT * FROM students WHERE course_code != 2;
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    1 | Luffy |           1 |    1 |
|    4 | Ussop |           4 |    2 |
|    2 | Zoro  |           1 |    3 |
+------+-------+-------------+------+

```

```mysql 
13 and 14 

mysql> SELECT * FROM students WHERE year IN (1, 2);
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    1 | Luffy |           1 |    1 |
|    4 | Ussop |           4 |    2 |
|    5 | Sanji |           2 |    2 |
|    3 | Nami  |           2 |    1 |
+------+-------+-------------+------+
4 rows in set (0.00 sec)

mysql> SELECT * FROM students WHERE year NOT IN (1, 2);
+------+------+-------------+------+
| id   | name | course_code | year |
+------+------+-------------+------+
|    2 | Zoro |           1 |    3 |
+------+------+-------------+------+
1 row in set (0.01 sec)

```

15
```MYSQL
mysql> SELECT * FROM courses WHERE fees BETWEEN 3000 AND 4000;
+------+------+------+
| code | name | fees |
+------+------+------+
|    1 | BA   | 3000 |
|    2 | BCOM | 3500 |
|    3 | BSC  | 4000 |
+------+------+------+

```
16
```MYSQL

mysql> SELECT DISTINCT(course_code) FROM students;
+-------------+
| course_code |
+-------------+
|           1 |
|           4 |
|           2 |
+-------------+

```

maths...
17 and 18 
```mysql
mysql> SELECT MIN(fees) FROM courses;
+-----------+
| MIN(fees) |
+-----------+
|      3000 |
+-----------+
1 row in set (0.01 sec)

mysql> SELECT MAX(fees) FROM courses;
+-----------+
| MAX(fees) |
+-----------+
|      5000 |
+-----------+

```

19, 20, 21...
```mysql
mysql> select COUNT(name) FROM courses;
+-------------+
| COUNT(name) |
+-------------+
|           4 |
+-------------+
1 row in set (0.00 sec)

mysql> SELECT AVG(fees) FROM courses;
+-----------+
| AVG(fees) |
+-----------+
| 3875.0000 |
+-----------+
1 row in set (0.00 sec)

mysql> SELECT SUM(fees) FROM courses;
+-----------+
| SUM(fees) |
+-----------+
|     15500 |
+-----------+
1 row in set (0.00 sec)

```

22 updatae
```mysql
mysql> select * from courses;
+------+------+------+
| code | name | fees |
+------+------+------+
|    1 | BA   | 3000 |
|    2 | BCOM | 3500 |
|    3 | BSC  | 4000 |
|    4 | BE   | 5000 |
+------+------+------+
4 rows in set (0.00 sec)

mysql> UPDATE courses SET fees = fees + 1500;
Query OK, 4 rows affected (0.02 sec)
Rows matched: 4  Changed: 4  Warnings: 0

mysql> select * From courses;
+------+------+------+
| code | name | fees |
+------+------+------+
|    1 | BA   | 4500 |
|    2 | BCOM | 5000 |
|    3 | BSC  | 5500 |
|    4 | BE   | 6500 |
+------+------+------+

```

23, 24, 25, 26, 27, 28
```mysql

mysql> SELECT * FROM students WHERE name LIKE 'L%';
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    1 | Luffy |           1 |    1 |
+------+-------+-------------+------+
1 row in set (0.00 sec)

mysql> SELECT * FROM students WHERE name LIKE '%i';
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    5 | Sanji |           2 |    2 |
|    3 | Nami  |           2 |    1 |
+------+-------+-------------+------+
2 rows in set (0.00 sec)

mysql> SELECT * FROM students WHERE name LIKE 'N%i';
+------+------+-------------+------+
| id   | name | course_code | year |
+------+------+-------------+------+
|    3 | Nami |           2 |    1 |
+------+------+-------------+------+
1 row in set (0.00 sec)

mysql> SELECT * FROM students WHERE name LIKE '%o%';
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    4 | Ussop |           4 |    2 |
|    2 | Zoro  |           1 |    3 |
+------+-------+-------------+------+
2 rows in set (0.00 sec)

mysql> SELECT * FROM students WHERE name LIKE '_a%';
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    5 | Sanji |           2 |    2 |
|    3 | Nami  |           2 |    1 |
+------+-------+-------------+------+
2 rows in set (0.00 sec)

mysql> SELECT * FROM students WHERE name NOt LIKE 'L%';
+------+-------+-------------+------+
| id   | name  | course_code | year |
+------+-------+-------------+------+
|    4 | Ussop |           4 |    2 |
|    5 | Sanji |           2 |    2 |
|    2 | Zoro  |           1 |    3 |
|    3 | Nami  |           2 |    1 |
+------+-------+-------------+------+

```

29, 30
```mysql


mysql> SELECT * FROM useless;
+------+------+
| id   | name |
+------+------+
|    1 | xyz  |
|    2 | abc  |
|    3 | efg  |
+------+------+
3 rows in set (0.00 sec)


mysql> DELETE FROM useless WHERE id = 2;
Query OK, 1 row affected (0.01 sec)

mysql> select * from useless;
+------+------+
| id   | name |
+------+------+
|    1 | xyz  |
|    3 | efg  |
+------+------+
2 rows in set (0.01 sec)


mysql> delete from useless;
Query OK, 2 rows affected (0.02 sec)

mysql> select * from useless;
Empty set (0.00 sec)


mysql> truncate table useless;
Query OK, 0 rows affected (0.10 sec)

mysql> select * from useless;
Empty set (0.00 sec)

```