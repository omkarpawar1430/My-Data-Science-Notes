
Tags: #python 

------------------------------------------


[Python RegEx](https://www.w3schools.com/python/python_regex.asp)

- python string literals
    
    
    Python string literals are a way of representing strings in code. A string is a sequence of characters enclosed in quotes, such as single quotes (`''`) or double quotes (`""`). String literals can be used to define strings directly in code, or they can be used to represent strings that are read from external sources, such as files or user input.
    
    In Python, string literals can be used to represent a wide variety of characters, including letters, digits, whitespace, and special characters. To represent special characters in a string, such as newline characters (`\\n`) or tab characters (`\\t`), escape sequences are used. An escape sequence is a backslash (`\\`) followed by a special code that represents the desired character.
    
    For example, the string literal `'Hello, world!'` represents the string "Hello, world!", while the string literal `"This is a string."` represents the string "This is a string.". To represent a string with a newline character, we can use the escape sequence `\\n`, like this: `"This is a \\n multi-line string."`. This would represent the string "This is a" on one line, followed by a newline character, followed by the string "multi-line string." on the next line.
    
    Overall, string literals are an important part of Python syntax, and are used extensively in Python code to represent and manipulate text data.
    

A RegEx, or Regular Expression, is a sequence of characters that forms a search pattern.

RegEx can be used to check if a string contains the specified search pattern.

- methods to match
    
    The **`re`** module in Python provides several functions for working with regular expressions:
    
    - **`re.search(pattern, string, flags=0)`** - This function searches the string for the first occurrence of the regular expression pattern and returns a match object if a match is found. It searches the entire string, not just the beginning, and stops at the first match.
    - **`re.match(pattern, string, flags=0)`** - This function searches the string only from the beginning for the regular expression pattern and returns a match object if a match is found. If the pattern is found at the beginning of the string, then **`re.match()`** returns a match object. Otherwise, it returns **`None`**.
    - **`re.findall(pattern, string, flags=0)`** - This function searches the string for all occurrences of the regular expression pattern and returns a list of strings containing all matches. If capturing groups are used in the pattern, then **`re.findall()`** returns a list of tuples, where each tuple contains the captured groups for each match.
    - **`re.sub(pattern, repl, string, count=0, flags=0)`** - This function replaces all occurrences of the regular expression pattern in the string with the replacement string **`repl`** and returns the resulting string. The **`count`** parameter specifies the maximum number of replacements to make. If **`count`** is not specified or is zero, then all occurrences are replaced.
    
    In summary, **`re.search()`** and **`re.match()`** are used for finding a single match in a string, while **`re.findall()`** is used for finding all matches in a string. **`re.sub()`** is used for replacing matches in a string with a new string. All of these functions take a regular expression pattern as input, along with optional flags that modify the behavior of the pattern matching.
    
    - re.compile()
        
        The **`re.compile()`** function in Python's **`re`** module is used to compile a regular expression pattern into a regular expression object. This object can then be used to perform various operations such as searching for matches, replacing patterns in strings, splitting strings, and so on.
        
        Compiling a regular expression pattern using **`re.compile()`** has several advantages. First, it can improve performance by pre-compiling the pattern so that it can be reused multiple times without being re-evaluated. This is especially useful when you need to perform the same pattern matching operation many times in a loop or in different parts of your code.
        
        Second, the compiled regular expression object can be passed as an argument to various other functions in the **`re`** module, such as **`re.search()`**, **`re.match()`**, **`re.findall()`**, and **`re.sub()`**. This allows you to reuse the same compiled pattern object in multiple places, which can make your code more concise and easier to read.
        
        Finally, the **`re.compile()`** function allows you to specify various options that control how the regular expression pattern is compiled and how matches are searched for. For example, you can specify options such as **`re.IGNORECASE`** to make the pattern case-insensitive, or **`re.MULTILINE`** to enable multi-line matching. These options are specified as optional flags in the second argument of the **`re.compile()`** function.
        

**Metacharacters**

**Special Sequences**

| Character | Description | Example |
| --- | --- | --- |
| \A | Returns a match if the specified characters are at the beginning of the string | "\AThe" |
| \b | Returns a match where the specified characters are at the beginning or at the end of a word(the "r" in the beginning is making sure that the string is being treated as a "raw string") | r"\bain"r"ain\b" |
| \B | Returns a match where the specified characters are present, but NOT at the beginning (or at the end) of a word(the "r" in the beginning is making sure that the string is being treated as a "raw string") | r"\Bain"r"ain\B" |
| \d | Returns a match where the string contains digits (numbers from 0-9) | "\d" |
| \D | Returns a match where the string DOES NOT contain digits | "\D" |
| \s | Returns a match where the string contains a white space character | "\s" |
| \S | Returns a match where the string DOES NOT contain a white space character | "\S" |
| \w | Returns a match where the string contains any word characters (characters from a to Z, digits from 0-9, and the underscore _ character) | "\w" |
| \W | Returns a match where the string DOES NOT contain any word characters | "\W" |
| \Z | Returns a match if the specified characters are at the end of the string | "Spain\Z" |

---

Sets

A set is a set of characters inside a pair of square brackets `[]` with a special meaning:

| Set | Description |
| --- | --- |
| [arn] | Returns a match where one of the specified characters (a, r, or n) is present |
| [a-n] | Returns a match for any lower case character, alphabetically between a and n |
| [^arn] | Returns a match for any character EXCEPT a, r, and n |
| [0123] | Returns a match where any of the specified digits (0, 1, 2, or 3) are present |
| [0-9] | Returns a match for any digit between 0 and 9 |
| [0-5][0-9] | Returns a match for any two-digit numbers from 00 and 59 |
| [a-zA-Z] | Returns a match for any character alphabetically between a and z, lower case OR upper case |
| [+] | In sets, +, *, ., |, (), $,{} has no special meaning, so [+] means: return a match for any + character in the string |

---

- \d, \w & \s
    
    Whitespace characters can be used in a variety of scenarios in text processing and regular expressions. Here are some practical scenarios where we might want to use whitespace characters:
    
    1. Parsing text: Whitespace characters can be used to separate different parts of a string, such as words or numbers. For example, if we have a string containing a list of numbers separated by spaces, we can use whitespace characters as delimiters to parse the individual numbers. We can do this using a regular expression like **`r'\s+'`** to match one or more whitespace characters.
    2. Cleaning text: Whitespace characters can be used to remove unwanted spaces or line breaks from a string. For example, we might want to remove leading or trailing whitespace from a string, or remove any extra spaces between words. We can do this using a regular expression like **`r'^\s+|\s+$|\s+(?=\s)'`** to match and replace whitespace characters.
    3. Validating input: Whitespace characters can be used to validate input from users or external sources, such as email addresses or passwords. For example, we might want to check that a user's password does not contain any spaces, since many systems do not allow spaces in passwords. We can do this using a regular expression like **`r'\s'`** to match whitespace characters.
    
    Overall, whitespace characters are a useful tool in text processing and regular expressions, and can help us perform a variety of tasks, such as parsing, cleaning,
    
- Use
    
    The above information provides an understanding of the basic concepts of regular expressions, including shorthand character classes like **`\d`**, **`\w`**, and **`\s`**. With this knowledge, we can solve a wide variety of text processing problems, such as:
    
    - Validating input: Regular expressions can be used to check if a user input matches a specific format, such as an email address or phone number. We can use shorthand character classes like **`\d`** and **`\w`** to match specific types of characters, and combine them with other regular expression elements to create complex patterns.
    - Parsing text: Regular expressions can be used to extract specific information from text, such as dates, names, or URLs. We can use shorthand character classes and other regular expression elements to create patterns that match the desired text, and then use functions like **`re.findall()`** or **`re.search()`** to extract the matching text.
    - Cleaning text: Regular expressions can be used to remove unwanted characters or formatting from text, such as HTML tags or punctuation. We can use shorthand character classes and other regular expression elements to match the unwanted text, and then use functions like **`re.sub()`** to replace it with a desired replacement string.
    
    Overall, regular expressions are a powerful tool for text processing, and the shorthand character classes like **`\d`**, **`\w`**, and **`\s`** are key elements of many regex patterns. By understanding how to use these elements, we can solve a wide range of text processing problems in our code.
    
- \D,\W & \S
    - **`\D`** matches any character that is not a digit (0-9).
    - **`\W`** matches any character that is not a word character, which includes letters, digits, and underscores. This includes punctuation and special characters.
    - **`\S`** matches any character that is not a whitespace character, which includes spaces, tabs, and line breaks.
    
    These shorthand character classes can be useful when we want to match everything except a specific type of character, or when we want to negate a regular expression pattern that matches a specific type of character.
    
    ```python
    import re
    
    # Define a regular expression that matches non-digits
    pattern = r"\D+"
    
    # Test the regular expression by searching for matches in a string
    string = "abc123def456"
    matches = re.findall(pattern, string)
    
    # Print the matches
    print(matches)
    ```
    
- Greedy and Non-Greedy Quantifiers
    
    I assume you meant to ask about the difference between **`.*`** and **`.*?`** in regular expressions.
    
    In regular expressions, **`.*`** is a greedy quantifier that matches any character (except for line breaks) zero or more times. This means that it will match as many characters as possible, while still allowing the rest of the regular expression pattern to match. For example, the regular expression **`a.*b`** would match the string "aabbccbbddeebbb", returning "aabccbbddeeb" as a match.
    
    On the other hand, **`.*?`** is a non-greedy quantifier that also matches any character zero or more times, but it matches as few characters as possible, while still allowing the rest of the regular expression pattern to match. For example, the regular expression **`a.*?b`** would match the same string "aabbccbbddeebbb", but it would return "aab" as a match.
    
    So, the difference between **`.*`** and **`.*?`** is that **`.*`** is greedy, and matches as many characters as possible, while **`.*?`** is non-greedy, and matches as few characters as possible.
    
    We can also use other quantifiers, such as **`+`** or **`?`**, with **`.*`** and **`.*?`** to modify their behavior. For example, **`.+`** matches one or more characters, and **`.+?`** matches one or more characters, but matches as few characters as possible. The same applies to**`?`** quantifier as well.
    
- re. search(): we can give an argument as re. ignore case which ignores the case of the letter while matching.



The `re` module in Python provides support for regular expressions. Regular expressions are a powerful tool for pattern matching and string manipulation.

Here's some detailed information about the `re` module:

-   **Regular Expression Functions:**
    -   `re.search(pattern, string, flags=0)`: Searches for a match of the pattern anywhere in the string. Returns a match object if a match is found, or `None` otherwise.
    -   `re.match(pattern, string, flags=0)`: Checks if the pattern matches at the beginning of the string. Returns a match object if a match is found, or `None` otherwise.
    -   `re.findall(pattern, string, flags=0)`: Returns all non-overlapping matches of the pattern in the string as a list of strings.
    -   `re.finditer(pattern, string, flags=0)`: Returns an iterator yielding match objects for all non-overlapping matches of the pattern in the string.
    -   `re.sub(pattern, repl, string, count=0, flags=0)`: Replaces all occurrences of the pattern in the string with the replacement string `repl`. Returns the modified string.
    -   `re.split(pattern, string, maxsplit=0, flags=0)`: Splits the string by the occurrences of the pattern. Returns a list of substrings.
-   **Regular Expression Patterns:**
    -   Regular expressions are composed of various pattern elements that define the matching rules. Some common elements include:
        -   `.`: Matches any character except a newline.
        -   `[]`: Matches any single character within the brackets.
        -   `*`: Matches zero or more occurrences of the preceding element.
        -   `+`: Matches one or more occurrences of the preceding element.
        -   `?`: Matches zero or one occurrence of the preceding element.
        -   `^`: Matches the start of a string.
        -   `$`: Matches the end of a string.
        -   `|`: Matches either the expression before or after the `|`.
        -   `(...)` or `(?:...)`: Groups patterns together.
-   **Flags:**
    -   Flags modify the behavior of regular expression functions. Some commonly used flags include:
        -   `re.IGNORECASE` or `re.I`: Performs case-insensitive matching.
        -   `re.MULTILINE` or `re.M`: Enables multiline matching.
        -   `re.DOTALL` or `re.S`: Allows the `.` to match newline characters as well.
-   **Match Objects:**
    -   When a match is found, regular expression functions return match objects. Match objects have methods and attributes to access information about the match, such as the matched string, matched groups, or the position of the match.

The `re` module provides a wide range of functionality for working with regular expressions. It is a powerful tool for pattern matching, search, and manipulation of strings based on complex matching rules.

---------------------
#### links:
[[]]
[[]]