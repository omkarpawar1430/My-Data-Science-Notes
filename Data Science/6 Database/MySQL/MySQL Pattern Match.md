------------------------- 
Tags: #mysql 
Date Created:  2023-07-12, @ 10:53

---
>[!info] Keywords
>* 

|Symbol|Description|Example|
|---|---|---|
|%|Represents zero or more characters|bl% finds bl, black, blue, and blob|
|\_|Represents a single character|h_t finds hot, hat, and hit|

LIKE Operator                | Description                                              
------------------------------|----------------------------------------------------------
WHERE CustomerName LIKE 'a%' | Finds any values that start with "a"                     
WHERE CustomerName LIKE '%a' | Finds any values that end with "a"                       
WHERE CustomerName LIKE '%or%' | Finds any values that have "or" in any position         
WHERE CustomerName LIKE '\_r%' | Finds any values that have "r" in the second position    
WHERE CustomerName LIKE 'a_%' | Finds any values that start with "a" and are at least 2 characters in length
WHERE CustomerName LIKE 'a__%' | Finds any values that start with "a" and are at least 3 characters in length
WHERE ContactName LIKE 'a%o' | Finds any values that start with "a" and ends with "o"

#### Starts with give word or letter:

```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName LIKE 'a%';
```

```Output
+------------------------------------+
| CustomerName                       |
+------------------------------------+
| Alfreds Futterkiste                |
| Ana Trujillo Emparedados y helados |
| Antonio Moreno Taquería            |
| Around the Horn                    |
+------------------------------------+
```

#### Ends with given word or letter:

```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName LIKE '%a';
```

```Output
+--------------------------+
| CustomerName             |
+--------------------------+
| Antonio Moreno Taquería  |
+--------------------------+
```

#### Starts with and Ends with given letter:
                                     
```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName LIKE 'a%e';
```

```Output
+---------------------+
| CustomerName        |
+---------------------+
| Alfreds Futterkiste |
+---------------------+
```

#### Between other letters:

```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName LIKE '%on%';
```

```Output
+--------------------------+
| CustomerName             |
+--------------------------+
| Antonio Moreno Taquería  |
+--------------------------+
```

#### Letter at second position:

```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName LIKE '_r%';
```

```Output
+-----------------+
| CustomerName    |
+-----------------+
| Around the Horn |
+-----------------+
```

#### starting with given letter and must have given number of words in it

```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName LIKE 'a__%';
```
In this case minimum number of letters should be **3** ( i.e. `_`  represents any other letter... so number of underscores tells about how many other letters pattern should have.)
```Output
+------------------------------------+
| CustomerName                       |
+------------------------------------+
| Alfreds Futterkiste                |
| Ana Trujillo Emparedados y helados |
| Antonio Moreno Taquería            |
| Around the Horn                    |
+------------------------------------+
```

#### Using `NOT LIKE`

```MySQL
SELECT CustomerName FROM Customers WHERE CustomerName NOT LIKE 'a%';
```

```Output
+---------------------+
| CustomerName        |
+---------------------+
| Berglunds snabbköp  |
+---------------------+

```

>[!summary] 
>1. 
>2. 

----
>[!cite]
> Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> [ChatGPT](https://chat.openai.com/)
> https://www.w3schools.com/MySQL/mysql_like.asp
> 
