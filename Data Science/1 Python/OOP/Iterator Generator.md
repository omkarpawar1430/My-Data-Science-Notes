------------------------- 
Tags: #python 
Date Created:  2023-06-02, @ 17:30

---
>[!info] Keywords
>* `yeild`
>* `__iter__()` and `__next__()`

### **Generator**:
==A generator is a special type of **iterator** ==that can be defined using a function with the `yield` keyword instead of `return`. It allows you to generate a sequence of values dynamically without storing them in memory all at once.

Example of a generator function:

```python

def my_generator(data):
    for item in data:
        yield item * 2

# Usage:
my_list = [1, 2, 3, 4, 5]
for item in my_generator(my_list):
    print(item)

```

In the above example, `my_generator()` is a generator function. It takes the `data` as input 
and yields each item in the `data` multiplied by 2. The `yield` statement ==pauses the function's execution and returns the value, but remembers the state so that it can resume where it left off in the next iteration.==

Both iterators and generators provide a way to iterate over a sequence of values, but they differ in their implementation. Iterators are typically defined using classes and the iterator protocol, while generators are defined using functions and the `yield` keyword. Generators are often more concise and convenient for creating sequences dynamically, while iterators offer more flexibility for customizing the iteration process.
==lazy evaluation==

---
### Iterator:
An iterator is an object that implements the iterator protocol, which consists of the `__iter__()` and `__next__()` methods. It allows you to iterate over a sequence of elements, such as a list or a custom object.

>[!note]
>The methods with double underscores before and after their names, such as `__iter__()` and `__next__()`, are known as **dunder methods** or **magic methods** in Python.

Example of an iterator using a Python class:

```python 

class MyIterator:
    def __init__(self, data):
        self.data = data
        self.index = 0
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.index >= len(self.data):
            raise StopIteration
        value = self.data[self.index]
        self.index += 1
        return value

# Usage:
my_list = [1, 2, 3, 4, 5]
my_iterator = MyIterator(my_list)
for item in my_iterator:
    print(item)


```

In the above example, `MyIterator` is a custom iterator class. It stores the data in an internal variable `data` and maintains the current index position using `index`. The `__iter__()` method returns the iterator object itself, and the `__next__()` method returns the next element in the sequence until there are no more elements, at which point it raises the `StopIteration` exception.
custom iterators may generate all the values in advance, consuming more memory.
# Generator VS Iterator

The main difference between iterators and generators lies in their implementation and the way they are used.

1. Implementation:
    
    - Iterators: Iterators are implemented using **classes that define the `__iter__()` and `__next__()` methods**. The `__iter__()` method returns the iterator object itself, and the `__next__()` method returns the next value in the sequence.
    - Generators: Generators are implemented using functions or generator expressions that **use the `yield` keyword** to return values. The `yield` statement allows the function to pause its execution and resume where it left off in the next iteration.
    
1. Memory Usage:
    
    - Iterators: Iterators often require more memory because they **store the entire sequence of values in memory**, either [[explicitly or implicitly]].
    - Generators: Generators are memory-efficient as they generate values on the fly, producing one value at a time and keeping a minimal memory footprint. They **don't store the entire sequence of values in memory**.
3. Ease of Use:
    
    - Iterators: Iterators provide a more flexible and customizable iteration process. They allow you to define **complex iteration logic** by implementing the `__iter__()` and `__next__()` methods explicitly.
    - Generators: Generators are more concise and convenient to use. They **automatically implement the iterator protocol**, and you can define the iteration logic using a simple `yield` statement, making them easier to write and understand.
4. Usage Scenarios:
    
    - Iterators: Iterators are useful when you need to iterate over a sequence of values that require **custom iteration logic or involve complex calculations**. They can be used in scenarios where you want fine-grained control over the iteration process.
    - Generators: Generators are suitable when you want to **generate a sequence of values dynamically without storing them all in memory at once.** They are handy for processing large datasets, infinite sequences, or situations where **lazy evaluation** is desired.

>[!summary] 
>Iterators and generators serve the purpose of iterating over a sequence of values, but **generators offer a more concise and memory-efficient way of generating values on the fly**, while iterators provide more **flexibility and customization** options for complex iteration scenarios.

----
>[!cite]
> 🤝 Connect with Me: https://linktr.ee/omkarpawar1430
> 
> https://docs.python.org/3/library/itertools.html
