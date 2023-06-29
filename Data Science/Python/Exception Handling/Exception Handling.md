
Tags: #python 

------------------------------------------
Exception handling is a way to handle errors that occur during the execution of a Python program. It allows you to gracefully handle errors and prevent your program from crashing.

There are two main types of exceptions in Python:

- **Built-in exceptions:** These are exceptions that are built into the Python language. For example, the `ZeroDivisionError` exception is raised when you try to divide a number by zero.
- **User-defined exceptions:** These are exceptions that you create yourself. You can create user-defined exceptions by subclassing the `Exception` class.

To handle an exception, you use the `try` and `except` statements. The `try` statement tells Python to execute the code block that follows it. If an exception occurs, the `except` statement will handle the exception.

The syntax for the `try` and `except` statements is as follows:

Python

```
try:
    # Code that might raise an exception
except Exception as e:
    # Handle the exception
```

The `except` statement can be used to handle specific types of exceptions. For example, the following code will handle the `ZeroDivisionError` exception:

Python

```
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Division by zero!")
```

If the `try` block raises an exception that is not handled by the `except` statement, the exception will be propagated to the outer scopes of the program. If no exception handler is found, the program will crash.

In addition to the `try` and `except` statements, Python also provides the `finally` statement. The `finally` statement is executed regardless of whether or not an exception occurs. This can be useful for cleanup tasks, such as closing files or releasing resources.

The syntax for the `finally` statement is as follows:

Python

```
try:
    # Code that might raise an exception
except Exception as e:
    # Handle the exception
else:
	# runs when if exception is not raise
finally:
    # Cleanup tasks
```

Here is an example of how to use the `finally` statement:

Python

```
try:
    f = open("file.txt")
    text = f.read()
finally:
    f.close()
```

In this example, the `f.close()` method will be called regardless of whether or not an exception occurs. This ensures that the file is closed properly, even if an error occurs.

Exception handling is an essential part of writing robust and reliable Python programs. By using exception handling, you can prevent your programs from crashing and gracefully handle errors that occur.

---------
The `raise` keyword is used to raise an exception in Python. It can be used to raise a built-in exception, a user-defined exception, or a custom exception.

To raise a built-in exception, you can use the name of the exception as the argument to the `raise` keyword. For example, the following code will raise a `ZeroDivisionError` exception:

Python

```
raise ZeroDivisionError
```

To raise a user-defined exception, you can use an instance of the exception class as the argument to the `raise` keyword. For example, the following code will raise a `MyException` exception:

Python

```
raise MyException("This is my exception")
```

To raise a custom exception, you can use the `raise` keyword with a custom exception object. For example, the following code will raise a custom exception object that has the `message` attribute set to "This is my exception":

Python

```
exception = Exception("This is my exception")
raise exception
```

The `raise` keyword can also be used to reraise an exception that has already been raised. For example, the following code will reraise the `ZeroDivisionError` exception that was raised by the `division` function:

Python

```
def division(x, y):
    try:
        return x / y
    except ZeroDivisionError:
        raise

try:
    print(division(1, 0))
except ZeroDivisionError:
    print("Division by zero!")
```

The `raise` keyword can be used to raise an exception anywhere in a Python program. However, it is most commonly used in the `try` block of an exception handling statement.

Here is an example of how to use the `raise` keyword in an exception handling statement:

Python

```
try:
    x = int(input("Enter a number: "))
except ValueError:
    raise ValueError("Invalid input!")
```

In this example, the `try` block will try to convert the user input to an integer. If the input is not a valid integer, the `ValueError` exception will be raised. The `except` block will then handle the exception by reraising it. This will cause the program to print the error message and then exit.

The `raise` keyword is a powerful tool that can be used to handle exceptions in Python programs. By using the `raise` keyword, you can prevent your programs from crashing and gracefully handle errors that occur.


---------------------
#### links:
[exception.py](obsidian://open?vault=My%20Data%20Science%20Notes&file=Data%20Science%2FProject%20Pipeline%2Fexception.py)
