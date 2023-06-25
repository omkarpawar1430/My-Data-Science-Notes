
Tags: #python 

------------------------------------------

### List Comprehension : 
Here's the syntax for list comprehension in Python:

```python

new_list = [expression for item in iterable if condition]
```

-   `expression` is the operation that is performed on each item of the iterable.
-   `item` is a variable that represents each item of the iterable.
-   `iterable` is the original list, range of numbers, or any iterable object.
-   `condition` is an optional condition that filters the items of the iterable.

Here's an example of list comprehension to create a new list of squares of the numbers from 1 to 10:

`squares = [i**2 for i in range(1, 11)] print(squares)`

Output:


`[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`

In this example, we used list comprehension to create a new list `squares` that contains the squares of the numbers from 1 to 10. The expression `i**2` is performed on each item `i` in the range `range(1, 11)`, which generates the numbers from 1 to 10.



---------------------
#### links:
[[]]
[[]]