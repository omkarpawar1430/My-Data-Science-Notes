---
tags:
  - python
date: 2023-10-22T16:41:00
aliases:
  - for loop
  - while loop
---
>[!info] Keywords
>* `break`, `continue` and `pass`
>* `for` and `while` loops

1. `break`:
   - `break` is used in loops (like `for` and `while`) to exit the loop prematurely.
   - When `break` is encountered, it terminates the current loop and continues with the next code after the loop.
   - It's often used when you want to stop a loop when a certain condition is met.

Example:
```python
for i in range(1, 6):
    if i == 3:
        break
    print(i)
```
Output:
```
1
2
```

2. `continue`:
   - `continue` is used in loops to skip the current iteration and move to the next iteration.
   - When `continue` is encountered, the rest of the code inside the current loop iteration is skipped, and the loop proceeds with the next iteration.
   - It's useful when you want to avoid executing specific code within a loop under certain conditions.

Example:
```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```
Output:
```
1
2
4
5
```

3. `pass`:
   - `pass` is a placeholder statement in Python.
   - It does nothing when executed and is often used as a placeholder for future code.
   - It's useful when you need to create a code structure that does nothing at the moment but will be filled in later.

Example:
```python
for i in range(1, 6):
    if i == 3:
        pass
    else:
        print(i)
```
Output:
```
1
2
4
5
```


>[!summary] 
>1. 
>2. 

------
### Interview Questions:

1. Can you explain what the `break` statement is used for in Python, and in what type of constructs it is typically employed?
    
2. How does the `continue` statement differ from the `break` statement in Python, and when would you use `continue` in a loop?
    
3. What is the purpose of the `pass` statement in Python, and in what scenarios might you use it in your code?
    
4. Can you provide an example where the `break` statement is used to prematurely exit a loop? What is the expected output in such a case?
    
5. Give an example of using the `continue` statement to skip a specific iteration within a loop. What is the output in this example?
    
6. When might you use the `pass` statement as a placeholder in your Python code, and how can it be useful in programming?

----
### Links:
>[!cite]
> 🤝 Connect with Me: https://linktr.ee/omkarpawar1430
