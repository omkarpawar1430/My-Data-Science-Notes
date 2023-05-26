
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
3. 


---------------------
#### links:
[[]]
[[]]