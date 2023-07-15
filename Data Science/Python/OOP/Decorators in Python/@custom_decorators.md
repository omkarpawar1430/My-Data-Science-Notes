------------------------- 
Tags: #python 
Date Created:  2023-06-29, @ 17:30

---
>[!info] Keywords
>*


### Function Decorator:

```python
#function as decorator: 
def uppercase_decorator(func): # nested function wrapping the inner function
    def wrapper():
        result = func()
        return result.upper()
    return wrapper


@uppercase_decorator
def greet():
    return "hello"

print(greet())
```

```output
HELLO
```

### Method Decorator: 

```python
def uppercase_decorator(func):
    def wrapper(self):
        result = func(self)
        return result.upper()
    return wrapper

class Greeting:
    @uppercase_decorator
    def greet(self):
        
        return "hello"

greeting = Greeting()
print(greeting.greet())
```

```output
HELLO
```

### Class Decorators:


>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> [ChatGPT](https://chat.openai.com/)
> 
> 
