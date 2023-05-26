
Tags: #mysql 

------------------------------------------
```
mysql> select * from dep;
+---------+------------+----------+
| DEPT_NO | DNAME      | LOC      |
+---------+------------+----------+
|      10 | Accounting | New York |
|      20 | Research   | Dallas   |
|      30 | Sales      | Chicago  |
|      40 | Operations | Boston   |
+---------+------------+----------+
-----------------------------------------------------------------
mysql> select * from emp;
+----+----------------+------+---------------------------+---------------+---------+------------+------------+---------------+
| id | name           | age  | email                     | address       | salary  | hire_date  | manager_id | department_id |
+----+----------------+------+---------------------------+---------------+---------+------------+------------+---------------+
|  1 | John Doe       |   25 | johndoe@example.com       | 123 Main St   | 5000.00 | 2022-01-01 |       NULL |            10 |
|  2 | Jane Smith     |   30 | janesmith@example.com     | 456 Elm St    | 6000.00 | 2021-05-15 |          1 |          NULL |
|  3 | Mark Johnson   | NULL | markjohnson@example.com   | 789 Oak St    |    NULL | 2022-03-10 |          1 |            10 |
|  4 | Sarah Williams |   28 | sarahwilliams@example.com | NULL          | 5500.00 | NULL       |       NULL |          NULL |
|  5 | Emily Johnson  |   35 | emilyjohnson@example.com  | 789 Oak St    | 7000.00 | 2022-06-20 |          2 |            20 |
|  6 | Michael Brown  |   32 | michaelbrown@example.com  | 321 Pine St   | 6500.00 | 2023-02-12 |          2 |            30 |
|  7 | Olivia Davis   | NULL | oliviadavis@example.com   | 987 Maple St  | 5500.00 | NULL       |          1 |            40 |
|  8 | James Wilson   |   40 | jameswilson@example.com   | 654 Cherry St | 8000.00 | 2022-09-05 |          1 |            30 |
+----+----------------+------+---------------------------+---------------+---------+------------+------------+---------------+

```

1. Stacking One Row set atop Another
```
mysql> select name as name_N_DName, department_id from emp where department_id = 10
    -> union all
    -> select DNAME, DEPT_NO from dep;
+--------------+---------------+
| name_N_DName | department_id |
+--------------+---------------+
| John Doe     |            10 |
| Mark Johnson |            10 |
| Accounting   |            10 |
| Research     |            20 |
| Sales        |            30 |
| Operations   |            40 |
+--------------+---------------+
6 rows in set (0.00 sec)

```
2. Combining Related Rows: A join is an operation that combines rows from two tables into one.
```
mysql> select e.name,  d.LOC
    -> from emp e, dep d
    -> where e.department_id = d.DEPT_NO
    -> and e.department_id = 10; 
+--------------+----------+
| name         | LOC      |
+--------------+----------+
| John Doe     | New York |
| Mark Johnson | New York |
+--------------+----------+
2 rows in set (0.00 sec)

```
3. 











---------------------
#### links:
[[]]
[[]]