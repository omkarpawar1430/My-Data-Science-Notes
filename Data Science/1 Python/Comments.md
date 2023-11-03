---
tags:
  - python
date: 2023-10-21T12:08:00
---
1. Comments can be used to explain Python code.
2. Comments can be used to make the code more readable.
3. Comments can be used to prevent execution when testing code.
### Single-line Comment
```python
# This is single line comment. 
```
### Multi-line Comment
```python
"""
This is a multiline
Comment.
We can use it to write 
multiple lines at once 
"""
```
### Doc Strings
These are not exactly like comments but similar like comments. It don't gets executed. It just provides information about the function. 
```python
def greet(name):
    """
    This function takes a name as an argument and
    returns a personalized greeting message.

    Parameters:
    name (str): The name of the person to greet.

    Returns:
    str: A greeting message including the person's name.
    """
    greeting = f"Hello, {name}! How are you today?"
    return greeting
```
### Interview Questions:
How do you comment in Python?  Why do we use comments ? #iq 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@datadecides
