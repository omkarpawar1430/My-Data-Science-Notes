
Tags: #python 

------------------------------------------

**We will use `@dataclass` decorator on our class when we only want to use it for storing some class variables. Else we can use normal class with `__int__` method.**

----

The dataclasses module is a new feature in Python 3.7 that provides a way to create data classes. Data classes are regular Python classes, but they have some special features that make them easier to use for storing data.

The dataclasses module provides a decorator, `dataclass()`, that can be used to create data classes. The decorator takes a class definition as its argument and adds some special methods to the class. These methods include:

- `__init__()`: This method is called when an object of the class is created. It is used to initialize the object's attributes.
- `__repr__()`: This method is called when the class is represented as a string. It is used to return a string representation of the object.
- `__eq__()`: This method is called when two objects of the class are compared for equality. It is used to return True if the objects are equal and False if they are not equal.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __repr__(self):
        return f"Person(name='{self.name}', age={self.age})"
    
    def __eq__(self, other):
        if isinstance(other, Person):
            return self.name == other.name and self.age == other.age
        return False

# taking many lines of code 😥
##########################################
# creating objects: 
Person1 = Person('omkar', 23)
Person2 = Person('omkar', 23)
Person3 = Person('omkar', 44)

print(Person1)
print(Person2)
print(Person3)

print('-----------------------------------------')

print(Person1 == Person2)  
print(Person1 == Person3)  

```

```output
Person(name='omkar', age=23) 
Person(name='omkar', age=23) 
Person(name='omkar', age=44) 
----------------------------------------- 
True 
False
```

In addition to these special methods, the dataclasses module also provides some other features that make data classes easier to use. For example, data classes can be easily serialized and deserialized. This means that they can be easily stored in a file or transmitted over a network.

Overall, the dataclasses module provides a powerful and easy-to-use way to create data classes in Python. If you are working with data in Python, I highly recommend using data classes.

Here is an example of how to use the dataclasses module:

Python

```python
from dataclasses import dataclass

@dataclass
class Person:
    name: str
    age: int

# Giving the same result in 3 line of code 🤩
##########################################
# creating objects: 

Person1 = Person('omkar', 23)
Person2 = Person('omkar', 23)
Person3 = Person('omkar', 44)

print(Person1)
print(Person2)
print(Person3)

print('-----------------------------------------')

print(Person1 == Person2)  
print(Person1 == Person3)  

```


```
Person(name='omkar', age=23) 
Person(name='omkar', age=23) 
Person(name='omkar', age=44) 
----------------------------------------- 
True 
False
```

As you can see, the dataclasses module automatically generated the `__init__()`, `__repr__()`, and `__eq__()` methods for the `Person` class. This makes it very easy to create and use data classes in Python.

### Why use ?
Here are some of the benefits of using the @dataclass decorator:

- **Reduces boilerplate code:** The @dataclass decorator automatically generates special methods for a class, such as **init**(), **repr**(), and **eq**(). This can **help to reduce the amount of code that needs to be written.**
- **Makes classes more concise and readable:** The @dataclass decorator can help to make classes more concise and readable by automatically generating special methods. This can make code easier to understand and maintain.
- **Provides a consistent API:** The @dataclass decorator provides a consistent API for creating data classes. This can make it easier to work with data classes in different projects.

If you are creating a **class that is primarily used to store data**, and that does not need to define a lot of custom methods, then you should consider using the @dataclass decorator.

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
