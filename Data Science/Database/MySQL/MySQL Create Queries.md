
Tags: #mysql 

------------------------------------------
1. `create database name_of_database;`:  create database with a given name

```
mysql> create database Employee_Data;
Query OK, 1 row affected (0.02 sec)
```

>[!bug]
> You have to select that database that you just created before doing any modifications in it.
> `use name_of_database;` : selects database to work with

---

2. `create table table_name(column_title column_type(len), ...);`: creates table with column name and type , accepts only letters or numbers less than or equal to `len`.

```
mysql> CREATE TABLE YourTableName (
    ->   id INT PRIMARY KEY,
    ->   name VARCHAR(50),
    ->   age INT,
    ->   email VARCHAR(100),
    ->   address VARCHAR(100),
    ->   salary DECIMAL(10, 2),
    ->   hire_date DATE,
    ->   manager_id INT,
    ->   department_id INT
    -> );
Query OK, 0 rows affected (0.06 sec)
```

-------

3. `insert into table_name values (1, 'Omkar', 'Technoworld', 'medium');`:  Inserts values into table
```
mysql> INSERT INTO YourTableName (id, name, age, email, address, salary, hire_date, manager_id, department_id)
    -> VALUES
    ->   (5, 'Emily Johnson', 35, 'emilyjohnson@example.com', '789 Oak St', 7000.00, '2022-06-20', 2, 1),
    ->   (6, 'Michael Brown', 32, 'michaelbrown@example.com', '321 Pine St', 6500.00, '2023-02-12', 2, 2),
    ->   (7, 'Olivia Davis', NULL, 'oliviadavis@example.com', '987 Maple St', 5500.00, NULL, 1, 2),
    ->   (8, 'James Wilson', 40, 'jameswilson@example.com', '654 Cherry St', 8000.00, '2022-09-05', 1, 2);
Query OK, 4 rows affected (0.01 sec)
```

>[!bug]
>Make sure that values that you are inserting should match the table you created. i.e. number of entries, type of each entry and it's length 

---


---------------------
#### links:
[[]]
[[]]