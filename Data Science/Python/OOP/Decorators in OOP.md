------------------------- 
Tags: #python 
Date Created:  2023-06-15, @ 09:48

---
>[!info] Keywords
>* @dataclass 

decorators are a powerful feature that allow you to modify the behavior of functions, methods, or classes **without directly changing their source code**. Decorators provide a way to wrap or enhance the functionality of a target object by adding additional code before or after its execution.

### Use Cases:
- Adding logging or timing functionality to functions or methods.
- Implementing caching mechanisms to avoid redundant computations.
- Enforcing authorization or authentication checks for access control.
- Modifying the behavior of classes or methods based on certain conditions.

By using decorators, you can keep your code **modular**, **reusable**, and easier to maintain. Decorators provide a clean and elegant way to extend or modify the functionality of objects without modifying their original source code.

-----
## Types of Decorators: 
1. [[@custom_decorators]]: we can create a nested function which acts as decorator
1. `@classmethod`: Defines a class method within a class.
2. `@property`: Defines a method as a property of a class, allowing attribute-like access.
3. `@abstractmethod`: Declares an abstract method within an abstract base class.
4. [[@staticmethod]]: Defines a static method within a class.
6. `@property`: Defines a method as a property of a class, allowing attribute-like access.
7. `@abstractmethod`: Declares an abstract method within an abstract base class.
9. `@property`: Defines a method as a property of a class, allowing attribute-like access.
10. `@abstractmethod`: Declares an abstract method within an abstract base class.
11. [[@dataclass]]: Automatically generates boilerplate code for classes that hold data.
12. `@functools.wraps`: Preserves the original function's metadata when defining decorators.
13. `@functools.lru_cache`: Caches the results of a function, improving its performance for repeated calls with the same arguments.
14. `@contextlib.contextmanager`: Defines a context manager using a generator function.


------



>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> https://www.geeksforgeeks.org/decorators-in-python/
> 

