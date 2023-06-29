------------------------- 
Tags: #python 
Date Created:  2023-06-28, @ 16:37

---
>[!info] Keywords
>*

In Python, an enum, short for enumeration, is a way to define a collection of named values that represent a set of possible options or choices. Enums are used to improve code readability, maintainability, and to enforce the use of specific values


```python 
# enums:
from enum import Enum
class Color(Enum):
	RED = 1
	GREEN = 2
	BLUE = 3 

print(Color)
print(type(Color))
print(Color.GREEN)
print(Color.GREEN.name)
print(Color.GREEN.value)
```

```output
<enum 'Color'>
<class 'enum.EnumMeta'> 
Color.GREEN 
GREEN 
2
```

### Use Case: 
- Enums in Python provide a way to define and work with a limited set of values, ensuring that only valid options are used and making your code more expressive and self-documenting.
- code becomes more concise and easier to manage
- 

>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> [ChatGPT](https://chat.openai.com/)
> 
> 
