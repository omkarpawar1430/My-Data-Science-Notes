---
tags:
  - python
date: 2023-10-22T16:44:00
aliases:
---
>[!info] Keywords
>* `r`, `w`, `a`, `x`, `r+`, `w+`, `a+`, `rb`, `wb`, `rt`, `wt`
>* `with`
>* `open()`, `close()`

File Handling is used for dealing with files by using Python's magic. You can read, write, append files for creating documents or storing documents separately in files.

You can also use OS libraries to play with folders. 

###  Why file handling?

1. **Persistence of Data**: File handling allows you to store data in a more ==permanent== and persistent way. ==Data stored in variables is lost when the program terminates, but data in files can be retrieved and used in future sessions.==

2. **Data Storage and Retrieval**: You can ==store and retrieve== large datasets that may not fit into memory. Files enable you to work with data that's too big to keep entirely in RAM.

3. **Data Sharing**: Files are a common way to share data between different programs or across different systems. You can write data to a file in one program and read it in another, making it a universal data exchange format.

4. **Data Backup**: You can create backups of important data by saving it to files. This is crucial for data integrity and recovery in case of unexpected system failures.

5. **Data Persistence**: Storing data in files is essential for long-term data persistence, such as storing application configurations, user preferences, or logs.

6. **Data Processing**: You can read and write data in chunks or records, which is useful for data processing tasks like sorting, filtering, and aggregation.

7. **Structured Data Storage**: Files allow you to store structured data in various formats like CSV, JSON, XML, and databases. This facilitates data interchange and integration with other systems.

8. **Historical Data**: Files can store historical data, logs, or records that can be useful for auditing, analysis, and compliance.

9. **Flexibility**: You can work with a wide range of file formats, including text, binary, and specialized formats like images, audio, or documents.

10. **Data Security**: Files can be protected with file permissions, encryption, and access control mechanisms, providing a level of data security that in-memory data structures don't offer.

11. **Offline Data Access**: Files allow you to access data even when you're offline or disconnected from a network or database.

### Practical Usecase:

1. **Data Loading and Saving**: Reading data from files (e.g., CSV, JSON) and saving data back to files is a fundamental use case in data science and analysis. You can use libraries like `pandas` to load and save datasets.

```python
import pandas as pd

# Load data from a CSV file
data = pd.read_csv('data.csv')

#doing some process on data or just read it.

# Save data to a JSON file
data.to_json('data.json')
```

2. **Logging**: Logging is essential for tracking and debugging. Python's built-in `logging` module can be used to write log messages to a file.

```python
import logging

logging.basicConfig(filename='app.log', level=logging.DEBUG)
logging.debug('This is a debug message')
```

3. **Configuration Management**: Storing configuration parameters in a file, such as an INI file, allows easy configuration changes without modifying the code.

```python
import configparser

config = configparser.ConfigParser()
config.read('config.ini')

# Access configuration values
api_key = config['API']['key']
```

4. **Web Scraping**: When scraping data from websites, you often save the scraped data to files for further analysis. Libraries like `requests` and `Beautiful Soup` are commonly used.

```python
import requests
from bs4 import BeautifulSoup

# Send an HTTP request
response = requests.get('https://example.com')

# Parse and save the content to a file
soup = BeautifulSoup(response.text, 'html.parser')
with open('scraped_data.html', 'w') as file:
    file.write(soup.prettify())
```

5. **Text Analysis**: Reading text data from files and performing text analysis, such as sentiment analysis or natural language processing, is a common application.

```python
# Read text data from a file
with open('text.txt', 'r') as file:
    text = file.read()

# Perform text analysis on the content
```

6. **Image Processing**: Working with image files often involves opening, modifying, and saving images using libraries like `Pillow`.

```python
from PIL import Image

# Open an image
img = Image.open('image.jpg')

# Modify and save the image
img.thumbnail((100, 100))
img.save('thumbnail.jpg')
```

7. **Database Interactions**: Saving and loading data from databases often involves working with files, especially when using databases like SQLite.

```python
import sqlite3

# Connect to an SQLite database file
conn = sqlite3.connect('my_database.db')

# Perform database operations
```

8. **Machine Learning Model Serialization**: Saving and loading machine learning models to and from files allows you to reuse models without retraining them.

```python
import joblib

# Save a trained model to a file
model = train_model()
joblib.dump(model, 'model.pkl')

# Load the model for predictions
loaded_model = joblib.load('model.pkl')
```

These are just a few examples of practical use cases for file handling in Python. File handling is essential in a wide range of applications, from data science and web development to automation and system administration.

### Different Modes in File Handling: 

- `r`: open an existing file for a read operation.
- `w`: open an existing file for a write operation. If the file already contains some data then it will be overridden but if the file is not present then it creates the file as well.
- `a`: open an existing file for append operation. It won’t override existing data.
- `r+`: To read and write data into the file. The previous data in the file will be overridden.
- `w+`: To write and read data. It will override existing data.
- `a+`: To append and read data from the file. It won’t override existing data.
### Example Code

1. **Read Mode (`'r'`):**
   - This mode is used for **reading an existing file**.

```python
# Open a file in read mode
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```

2. **Write Mode (`'w'`):**
   - This mode is used for **creating a new file or overwriting an existing file**.

```python
# Open a file in write mode
with open('new_file.txt', 'w') as file:
    file.write("This is a new file with some content.")
```

3. **Append Mode (`'a'`):**
   - This mode is used for **appending data** to an existing file.

```python
# Open a file in append mode
with open('existing_file.txt', 'a') as file:
    file.write("This is additional content appended to the file.")
```

4. **Exclusive mode** (`x`):
	In file handling, 'x' is a mode that represents "exclusive creation" in Python. When you open a file with the 'x' mode, it is used for creating a new file. If the file already exists, attempting to open it with 'x' mode will raise a `FileExistsError` exception, preventing accidental overwriting of existing files.

Here's an example of how to use 'x' mode to create a new file:

```python
with open('new_file.txt', 'x') as file:
    file.write("This is a new file created using 'x' mode.")
```

In this example, a new file called 'new_file.txt' is created, and the text is written to it. If 'new_file.txt' already exists in the same directory, an error will be raised. This mode is useful when you want to ensure that you don't accidentally overwrite an existing file while creating a new one.

-----

1. **Binary Read Mode (`'rb'`):**
   - This mode is used for reading binary files.

```python
# Open a binary file in read mode
with open('binary_data.bin', 'rb') as file:
    binary_data = file.read()
    # You can work with binary data here
```

5. **Binary Write Mode (`'wb'`):**
   - This mode is used for writing binary data to a file.

```python
# Open a file in binary write mode
with open('binary_output.bin', 'wb') as file:
    binary_data = b'\x48\x65\x6c\x6c\x6f'  # Binary data (e.g., bytes)
    file.write(binary_data)
```

6. **Text Read Mode with Encoding (`'r'` or `'rt'`):**
   - This mode is used for reading a text file with a specific encoding.

```python
# Open a text file with a specific encoding in read mode
with open('text_file.txt', 'rt', encoding='utf-8') as file:
    content = file.read()
    print(content)
```

7. **Text Write Mode with Encoding (`'w'` or `'wt'`):**
   - This mode is used for writing text to a file with a specific encoding.

```python
# Open a text file with a specific encoding in write mode
with open('new_text_file.txt', 'wt', encoding='utf-8') as file:
    file.write("This is a text file with encoding specified.")
```

**Extra:** 

1. **`r+` Mode (Read and Write):**
   - `r+` is used to open a file for both reading and writing.
   - It **does not truncate** the file, meaning it doesn't clear existing data.
   - You can read, write, and modify data within the file using this mode.
   - If the file doesn't exist, it will raise an error.

Example:

```python
# Open a file in 'r+' mode
with open('data.txt', 'r+') as file:
    content = file.read()
    file.write("This data will be written to the file.")
```

2. **`w+` Mode (Write and Read):**
   - `w+` is used to open a file for both writing and reading.
   - It truncates the file, removing all existing data.
   - You can write new data and read from the file.
   - If the file doesn't exist, it creates a new file.

Example:

```python
# Open a file in 'w+' mode
with open('new_data.txt', 'w+') as file:
    file.write("This is new data written to the file.")
    content = file.read()
```

3. **`a+` Mode (Append and Read):**
   - `a+` is used to open a file for both appending and reading.
   - It does not truncate the file, allowing you to add new data without overwriting the existing content.
   - You can read and append data to the file.
   - If the file doesn't exist, it creates a new file.

Example:

```python
# Open a file in 'a+' mode
with open('existing_data.txt', 'a+') as file:
    content = file.read()
    file.write("This data is appended to the end of the file.")
```

>[!bug]
>Remember to use the `with` statement to ensure that the file is automatically closed when you're done with it, which is good practice to prevent resource leaks.

The `with` statement in Python is used for better and more reliable resource management, especially when working with external resources like files. It simplifies the code and ensures that the associated resources are properly acquired and released.

```python
# Without 'with' statement
file = open('example.txt', 'r')
content = file.read()
file.close()

# With 'with' statement
with open('example.txt', 'r') as file:
    content = file.read()
# 'file' is automatically closed when the block is exited

# If an exception occurs in the 'with' block, the file is still closed properly.
```

>[!summary] 
>1. 
>2. 

------
### Interview Questions:
1. Why to use `with`? #iq
2. 
----
### Links:
>[!cite]
> 🤝 Connect with Me: https://linktr.ee/omkarpawar1430