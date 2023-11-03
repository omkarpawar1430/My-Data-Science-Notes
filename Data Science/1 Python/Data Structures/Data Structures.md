
Tags: #python

------------------------------------------
There are four data structures in python which have unique characteristics:
Tuples, sets, dictionaries (dicts), and lists are all fundamental data structures in Python, but they have distinct characteristics and use cases:

1. [[List]]
    
    - Ordered collection of elements.
    - Elements are accessed by their position (index).
    - Allows duplicate elements.
    - Mutable, meaning you can add, modify, and remove elements.
    - Created using square brackets, e.g., `[1, 2, 3]`.
2. [[Tuple]]
    
    - Ordered collection of elements.
    - Elements are accessed by their position (index).
    - Allows duplicate elements.
    - Immutable, meaning once created, you cannot change its content (add, modify, or remove elements).
    - Created using parentheses, e.g., `(1, 2, 3)`.
3. [[Set]]
    
    - Unordered collection of unique elements.
    - Elements have no specific position (no indexing).
    - Does not allow duplicate elements.
    - Mutable, meaning you can add and remove elements.
    - Created using curly braces or the `set()` constructor, e.g., `{1, 2, 3}`.
4. [[Dictionary]]
    
    - Collection of key-value pairs.
    - Keys are used to access values.
    - Keys are unique within a dictionary.
    - Mutable, meaning you can add, modify, and remove key-value pairs.
    - Created using curly braces with key-value pairs, e.g., `{"name": "Alice", "age": 30}`.

Each of these data structures serves different purposes:

- Lists are typically used for ordered collections of items where duplicates are allowed and you need to access elements by their position.
    
- Tuples are like lists but are used when you want an immutable, ordered collection. This can be useful to represent something that shouldn't change, like coordinates.
    
- Sets are used when you need an unordered collection of unique elements. They're useful for tasks like removing duplicates from a list.
    
- Dictionaries are used when you need to associate values (the "values") with keys. This is handy for looking up values based on some identifier.
    

Understanding when and how to use these data structures is fundamental in Python programming and, by extension, in data science, where you often work with collections of data. You would choose the one that best fits the specific requirements of your task

### [[Strings]]


---------------------
#### links:

Refer to local Notebooks in VS code / W3School 