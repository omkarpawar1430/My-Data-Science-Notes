
Tags: #mysql

------------------------------------------
### Turning on MySQL:
1. `sudo mysql` : start MySQL on Linux terminal
2. `show databases;`: shows list of all the databases in the system
## CRUD:
### Create:
1. `create database name_of_database;`:  create database with a given name
>[!bug]
> You have to select that database that you just created before doing any modifications in it.
> `use name_of_database;` : selects database to work with

2. `create table table_name(column_title column_type(len), ...);`: creates table with column name and type , accepts only letters or numbers less than or equal to `len`.
3. `insert into table_name values (1, 'Omkar', 'Technoworld', 'medium');`:  Inserts values into table
>[!bug]
>Make sure that values that you are inserting should match the table you created. i.e. number of entries, type of each entry and it's length 

### Read:
1. `select * from table_name;`: shows whole table ,  `*` means you are selecting all of the values
2. 



---------------------
#### links:
[[]]
[[]]