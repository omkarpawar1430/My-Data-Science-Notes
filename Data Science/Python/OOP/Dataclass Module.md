
Tags: #python 

------------------------------------------
**We will use `@dataclass` decorator on our class when we only want to use it for storing some class variables. Else we can use normal class with `__int__` method.**

----

The dataclasses module is a new feature in Python 3.7 that provides a way to create data classes. Data classes are regular Python classes, but they have some special features that make them easier to use for storing data.

The dataclasses module provides a decorator, `dataclass()`, that can be used to create data classes. The decorator takes a class definition as its argument and adds some special methods to the class. These methods include:

- `__init__()`: This method is called when an object of the class is created. It is used to initialize the object's attributes.
- `__repr__()`: This method is called when the class is represented as a string. It is used to return a string representation of the object.
- `__eq__()`: This method is called when two objects of the class are compared for equality. It is used to return True if the objects are equal and False if they are not equal.

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

person = Person(name="John Doe", age=30)

print(person)
```


This code will print the following output:

Code snippet

```
Person(name='John Doe', age=30)
```

As you can see, the dataclasses module automatically generated the `__init__()`, `__repr__()`, and `__eq__()` methods for the `Person` class. This makes it very easy to create and use data classes in Python.



---------------------
#### links:
[[]]
[[]]