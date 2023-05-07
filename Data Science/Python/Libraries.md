
Tags: #python 

------------------------------------------


### Some Useful Libraries:
#### [[Pandas]]:
#### PyInputPlus:
- Info
    
    PyInputPlus is a Python library that provides enhanced input processing and validation functions beyond those offered by the built-in **`input()`** function. It is designed to make it easier for developers to get correct and validated input from users and reduce the risk of errors and vulnerabilities caused by incorrect or malicious user input.
    
    PyInputPlus includes several features that make it a powerful tool for input handling, such as:
    
    1. Validation of input data: PyInputPlus can validate user input based on different criteria, such as minimum and maximum values, regular expressions, and allowed values. This helps to ensure that input data meets the desired criteria.
    2. Type conversion of input data: PyInputPlus can convert input data to the desired data type automatically, such as converting a string input to an integer or a float. This makes it easier for developers to work with input data in their programs.
    3. Timeout feature: PyInputPlus allows developers to set a timeout for user input, which automatically raises an exception if the user does not provide input within the specified time limit. This can help to prevent long waits for user input and keep the program running smoothly.
    4. Retry feature: PyInputPlus allows developers to set a maximum number of retries for user input, which automatically prompts the user to re-enter input if the input does not meet the validation criteria. This helps to ensure that the input data is correct and reduces the risk of errors caused by invalid input.
    
    Overall, PyInputPlus is a powerful tool for input handling in Python, and it can save developers a lot of time and effort in handling user input in their programs.
    

```python
import pyinputplus as pyip

# Get integer input from the user
age = pyip.inputInt("Please enter your age: ")

# Get a yes/no response from the user
is_student = pyip.inputYesNo("Are you a student? (y/n): ")

# Get an input that matches a regular expression
phone_number = pyip.inputRegex(r'\d{3}-\d{3}-\d{4}', "Please enter your phone number (format: XXX-XXX-XXXX): ")

# Get input within a range of values
favorite_number = pyip.inputInt("Please enter your favorite number (between 1 and 100): ", min=1, max=100)

print(f"Your age is {age}, you are a student: {is_student}, your phone number is {phone_number}, and your favorite number is {favorite_number}.")
```

- Why imported as **pypi**
    - PyInputPlus is commonly imported with the alias `pypi` (short for PyPI, the Python Package Index) to make it easier and more concise to use in code. By using the alias `pypi`, developers can refer to PyInputPlus functions and classes with shorter and more readable names, which can make the code easier to understand and maintain. The alias `pypi` is not mandatory and developers can use any valid Python identifier to alias the PyInputPlus module. However, `pypi` is a common choice and has become a convention in the Python community, making it more recognizable and easier to understand for other developers.
-
#### PyPDF2: 
---
- 🔗 Links
    
    [Welcome to PyPDF2 — PyPDF2  documentation](https://pypdf2.readthedocs.io/en/3.0.0/)
    
    [PyPDF2 Library for Working with PDF Files in Python](https://www.analyticsvidhya.com/blog/2021/09/pypdf2-library-for-working-with-pdf-files-in-python/)
    
    [Document objects — python-docx 0.8.11 documentation](https://python-docx.readthedocs.io/en/latest/api/document.html)
    

```python
# the PyPDF2 library in Python to extract text from a PDF file paragraph-wise. 
# Here's a simple code snippet to get you started:

import PyPDF2

# Open the PDF file
pdf_file = open('example.pdf', 'rb')

# Create a PDF reader object
pdf_reader = PyPDF2.PdfFileReader(pdf_file)

# Loop through each page in the PDF
for page_num in range(pdf_reader.numPages):
    # Get the page object
    page_obj = pdf_reader.getPage(page_num)
    
    # Extract the text from the page
    page_text = page_obj.extractText()
    
    # Split the text into paragraphs
    paragraphs = page_text.split('\n\n')
    
    # Loop through each paragraph and print it
    for paragraph in paragraphs:
        print(paragraph)
    
# Close the PDF file
pdf_file.close()
```
#### [[RegEx]]:

#### Shutil:
[https://youtu.be/wII2JhNACJE](https://youtu.be/wII2JhNACJE)





#### Links:
---------------------

[[]]
[[]]