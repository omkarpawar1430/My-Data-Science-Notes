
Tags: 
Date Created:  2023-06-28, @ 09:34

------------------------------------------

```python
def print_my_values(*args, **kwargs): # The *args and **kwargs parameter allows us to pass any number of arguments to the function.

print(type(args)) # type of args in tuple...

print(args)

print(type(kwargs)) # type of kwargs is dict...

print(kwargs)

  

print_my_values(23, 23, 2, 234, name='your_name', age = '343', gender = 'male')
```

```Output:
<class 'tuple'> 
(23, 23, 2, 234) 
<class 'dict'> 
{'name': 'your_name', 'age': '343', 'gender': 'male'}
```

### Use Case: 
We use `*args` and `**kwargs` where we are not sure of how many number of arguments we are going to get from the user. 

---------------------
#### links:
