
Tags: #python 

------------------------------------------

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


---------------------
#### links:
[[]]
[[]]