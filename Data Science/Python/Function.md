
Tags: #python

------------------------------------------
# Functions

- lambda function
    
    an anonymous function (also known as a lambda function) is a function that does not have a name. It is a way to create a small, one-time use function without having to define it explicitly with a name.
    
    In Python, a lambda function is a small, anonymous function that can take any number of arguments but only has one expression. Lambda functions are defined using the lambda keyword, and they are commonly used as simple functions that are needed only once, such as sorting or filtering.
    
    Lambda functions are useful when you need to pass a function as an argument to another function or when you want to define a function inline, without giving it a name.
    
    Here's an example of a simple lambda function that multiplies two numbers:
    
    ```python
    pythonCopy code
    multiply = lambda x, y: x * y
    
    ```
    
    This lambda function takes two arguments, **`x`** and **`y`**, and returns their product. The equivalent non-lambda function would look like this:
    
    ```python
    pythonCopy code
    def multiply(x, y):
        return x * y
    
    ```
    
    Lambda functions are typically used in situations where you don't want to define a named function, such as in filtering or mapping operations:
    
    ```python
    pythonCopy code
    # using lambda function in filter()
    numbers = [1, 2, 3, 4, 5]
    even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
    print(even_numbers) # Output: [2, 4]
    
    # using lambda function in map()
    numbers = [1, 2, 3, 4, 5]
    squares = list(map(lambda x: x ** 2, numbers))
    print(squares) # Output: [1, 4, 9, 16, 25]
    
    ```
    
    In the first example, a lambda function is used to filter even numbers from a list of integers. In the second example, a lambda function is used to calculate the square of each element in a list of integers.
    

---------------------
#### links:
[[args]]
[[]]