---
tags:
  - python
date: 2023-11-04T10:03:00
aliases:
---
>[!info] Keywords
>* logging and debugging 
>* debug, info, warning, error and critical


>**Logging in Python:**
> - **Purpose:** Logging is the process of ==recording events==, errors, or other information during the execution of a program. It's crucial for monitoring and troubleshooting applications.
> 
> **Debugging in Python:**
> - **Purpose:** Debugging is the process of ==identifying and fixing errors== or issues in your code. 
> 
> **Logging allows developers to track the activity of the program, while debugging helps them identify and fix errors.**
> 
>logging is a useful for debugging, troubleshooting, and monitoring your program. 

-----
### Different Levels of Logging :
Logging in Python is the process of recording events that occur during the execution of a program. These events can include errors, warnings, and informational messages. The main purpose of logging is **to provide a record of what happened in the program**, so that developers can troubleshoot problems and improve the program's performance.

The logging module in Python provides **different levels of logging**, which are used to indicate the [[severity]] of a message. The different levels are:
![[Pasted image 20230506091346.png]]
**DEBUG**: This level is used for messages that are only relevant during ==development and debugging==. It provides detailed information about the program's execution and is not usually used in production environments.

Example: "Function X was called with argument Y"

**INFO**: This level is used ==to provide general information== about the program's execution. It can be used to track the progress of the program and ==provide status updates==.

Example: "The program has started successfully"

**WARNING**: This level is used for messages that indicate ==potential problems or issues that may cause errors in the program==. It is usually used to alert developers to potential issues that need to be addressed.

Example: "The file could not be found"

**ERROR**: This level is used for messages that ==indicate actual errors== in the program. It is used to alert developers to problems that need to be fixed.

Example: "Division by zero error occurred"

**CRITICAL**: This level is used for messages that indicate ==severe errors that may cause the program to crash or stop functioning==. It is used to alert developers to critical issues that need immediate attention.

Example: "The database connection is lost"

-------
### Sample Code : 

![[logging and debugging.canvas|logging and debugging]]
#### simple logging
```python
# importing module
import logging

# Create and configure root logger
logging.basicConfig(filename="newfile.log",
format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
filemode='w')

# Creating an object
logger = logging.getLogger()

# Setting the threshold of logger to DEBUG
logger.setLevel(logging.DEBUG) # can be changable according if your code is in testing or production phase 

# Test messages
logger.debug("Harmless debug Message")
logger.info("Just an information")
logger.warning("Its a Warning")
logger.error("Did you try to divide by zero")
logger.critical("Internet is down")
```
----
#### logging at different levels

By configuring multiple handlers, you can ensure that log messages are appropriately directed to their respective destinations, making it easier to manage and analyze the logs efficiently.

```python
import logging

# Create a logger
logger = logging.getLogger('my_logger')
logger.setLevel(logging.DEBUG)  # Set the logger's level to the lowest level

# Create a file handler for DEBUG and INFO messages
debug_info_handler = logging.FileHandler('debug_info.log')
debug_info_handler.setLevel(logging.DEBUG)  # Set the handler's level to DEBUG
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
debug_info_handler.setFormatter(formatter)
logger.addHandler(debug_info_handler)

# Create another file handler for WARNING and above
warning_error_handler = logging.FileHandler('warning_error.log')
warning_error_handler.setLevel(logging.WARNING)  # Set the handler's level to WARNING
warning_error_handler.setFormatter(formatter)
logger.addHandler(warning_error_handler)

# Log messages at different levels
logger.debug('This is a debug message')  # Goes to 'debug_info.log'
logger.info('This is an info message')    # Goes to 'debug_info.log'
logger.warning('This is a warning message')  # Goes to 'warning_error.log'
logger.error('This is an error message')  # Goes to 'warning_error.log'

```
------
#### logging in console and files
```python
import logging

# Create a logger
logger = logging.getLogger('my_logger')
logger.setLevel(logging.DEBUG)

# Create a formatter with your desired log message format
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')

# Create a file handler to log to a file
file_handler = logging.FileHandler('my_log_file.log')
file_handler.setLevel(logging.DEBUG)  # Set the desired log level for file logging
file_handler.setFormatter(formatter)

# Create a stream handler to log to the console
console_handler = logging.StreamHandler()
console_handler.setLevel(logging.INFO)  # Set the desired log level for console logging
console_handler.setFormatter(formatter)

# Add both handlers to the logger
logger.addHandler(file_handler)
logger.addHandler(console_handler)

# Now you can log messages, and they will be logged to both the file and the console
logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message')
logger.error('This is an error message')
logger.critical('This is a critical message')

```
----
#### logging in json format
```python
import logging
import json

# Step 1: Configure the logger
logging.basicConfig(level=logging.INFO)

# Step 2: Create a custom formatter for JSON formatting
class JsonFormatter(logging.Formatter):
    def format(self, record):
        log_data = {
            'timestamp': self.formatTime(record, self.datefmt),
            'level': record.levelname,
            'message': record.getMessage(),
        }
        return json.dumps(log_data)

# Step 3: Set the custom formatter for the root logger
root_logger = logging.getLogger()
handler = logging.StreamHandler()  # You can use other handlers for different outputs
handler.setFormatter(JsonFormatter())
root_logger.addHandler(handler)

# Step 4: Log structured data
data = {
    'user_id': 123,
    'action': 'click',
    'page': 'homepage',
}

logging.info("User interaction", extra=data)

```
-----
### common log `format` options:

1. `'%(asctime)s'`: The time when the log record was created. This is typically represented as a timestamp in a human-readable format.

2. `'%(created)d'`: The timestamp when the log record was created, represented as the number of seconds since the epoch (January 1, 1970).

3. `'%(filename)s'`: The name of the source file where the logging call was made.

4. `'%(funcName)s'`: The name of the function where the logging call was made.

5. `'%(levelname)s'`: The log level, such as DEBUG, INFO, WARNING, ERROR, or CRITICAL.

6. `'%(message)s'`: The actual log message itself.

7. `'%(module)s'`: The name of the Python module where the logging call was made.

8. `'%(name)s'`: The name of the logger. Useful for distinguishing log messages from different parts of your application.

9. `'%(lineno)d'`: The line number in the source file where the logging call was made.

10. `'%(pathname)s'`: The full path to the source file where the logging call was made.

11. `'%(process)d'`: The process ID of the current Python process.

12. `'%(thread)d'`: The thread ID of the current thread.

13. `'%(threadName)s'`: The name of the current thread.

You can use these placeholders to create custom log message formats. For example: `'%(asctime)s - %(levelname)s - %(message)s'`.

-------------
### **`filemode` options:**
- `'w'` (write): This mode creates a new log file (or overwrites an existing one) for each run of your program. It's useful when you want to start with a fresh log file each time.
- `'a'` (append): This mode appends log entries to an existing log file, preserving previous log records. It's useful for continuously accumulating log data across multiple program runs.
==The choice between 'w' and 'a' depends on whether you want to keep a history of log messages or only retain the most recent ones.==
---------
### Different Methods Used:
Python's `logging` module provides various methods and classes for setting up and managing logging.

1. **`logging.getLogger(name=None)`**: Returns a logger with the specified name. If no name is provided, it returns the root logger.

2. **`logger.setLevel(level)`**: Sets the logging level for the logger. ==Messages with a level lower than the specified level will be ignored.==

3. **`logger.addHandler(handler)`**: Adds a log handler to the logger. Handlers determine where log messages are output, such as to a file or console.

4. **`logger.removeHandler(handler)`**: Removes a log handler from the logger.

5. **`logger.debug(msg, *args, **kwargs)`**: Logs a message with the DEBUG level.

6. **`logger.info(msg, *args, **kwargs)`**: Logs a message with the INFO level.

7. **`logger.warning(msg, *args, **kwargs)`**: Logs a message with the WARNING level.

8. **`logger.error(msg, *args, **kwargs)`**: Logs a message with the ERROR level.

9. **`logger.critical(msg, *args, **kwargs)`**: Logs a message with the CRITICAL level.

10. **`logger.log(level, msg, *args, **kwargs)`**: Logs a message with a specified log level.

11. **`logger.exception(msg, *args, **kwargs)`**: Logs a message with the ERROR level, including traceback information for the current exception.

12. ==**`logging.basicConfig(**kwargs)`**: Configures the root logger. This method allows you to specify log file, log level, format, and other options.==

13. **`logging.shutdown()`**: Performs an orderly shutdown of the logging system. This should be called at application exit to ensure that all log messages are processed.

14. **`logging.Formatter(fmt=None, datefmt=None, style='%')`**: Creates a log message formatter with the specified format, date format, and style. This formatter is used to format log messages.

15. **`logging.Handler(level=0)`**: The base class for log handlers. It can be subclassed to create custom log handlers.

16. **`logging.FileHandler(filename, mode='a', encoding=None, delay=False)`**: Creates a log handler that writes log messages to a specified file.

17. **`logging.StreamHandler(stream=None)`**: Creates a log handler that writes log messages to a stream (e.g., sys.stdout or sys.stderr).

18. **`logging.NullHandler()`**: Creates a handler that does nothing. It's often used as a placeholder when no real logging is needed.
------
### Summary: 

>[!summary] 
>logging and debugging are important aspects of software development in Python. The logging module provides different levels of logging, which are used to indicate the severity of a message. Each level has its own use and purpose, and can be used to track the progress of the program, identify potential issues, and fix errors.
>

------
### Interview Questions: #iq 

1. **What is logging, and why is it important in software development?**
    
2. **Explain the key components of Python's `logging` module.**
    
3. **What are the different logging levels provided by Python's `logging` module, and when would you use each of them in your applications?**
    
4. **How do you create a custom log format using Python's `logging` module, and why might you want to customize log message formats?**
    
5. **Can you describe the purpose of log handlers in the context of Python's `logging` module, and provide an example of when you might use multiple handlers in a logging configuration?**
    
6. **What is the purpose of loggers in Python's `logging` module, and how do they relate to log handlers?**
    
7. **Explain the significance of log levels when configuring log handlers. How do log levels impact which log messages are processed and where they are output?**
    
8. **Describe the 'filemode' option when configuring log file handlers. How does it impact log files, and what are the use cases for 'w' and 'a' modes?**
    
9. **How can you filter log messages at different levels to separate them into different log files using Python's `logging` module?**
    
10. **What is the purpose of formatters in the context of logging? Can you provide an example of a custom log message format and how it might be used in a real-world scenario?**
    
11. **In a Python application, how would you handle and log exceptions using the `logging` module, and why is this useful in debugging and error tracking?**
    
12. **What is the role of the root logger in Python's `logging` module, and when should you use it versus creating custom loggers?**
13. **In Python, what are the key benefits of using logging over print statements for debugging in data science projects? Please explain with examples.**

----
### Links:
>[!cite]
> 🤝 Connect with Me: https://linktr.ee/omkarpawar1430
> 
> https://www.simplilearn.com/tutorials/python-tutorial/python-logging#what_is_python_logging

