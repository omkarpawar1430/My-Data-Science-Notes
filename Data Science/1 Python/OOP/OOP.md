
Tags: #python 

------------------------------------------

# Class & OOP

- Polymorphism
    
    [Polymorphism in Python - GeeksforGeeks](https://www.geeksforgeeks.org/polymorphism-in-python/)
    
   Polymorphism in Python refers to the ability of objects to take on many forms or have multiple behaviours. In simpler terms, it means that different objects can have the same method name, but behave differently based on the context in which they are called.
    
    For example, let's say we have a class called `Animal` with a method called `speak()`. We could then create two subclasses of `Animal` called `Dog` and `Cat`. Both `Dog` and `Cat` would inherit the `speak()` method from `Animal`, but they would implement it differently. The `Dog` class might define `speak()` as "woof", while the `Cat` class might define it as "meow".
    
    Now, if we were to create instances of both `Dog` and `Cat`, and call the `speak()` method on each of them, we would get different behavior depending on the context:


	

    ```python
    class Animal:
        def speak(self):
            pass
    
    class Dog(Animal):
        def speak(self): # same method speaks in different way in case of class dog and cat
            return "woof"
    
    class Cat(Animal):
        def speak(self):
            return "meow"
    
    dog = Dog()
    cat = Cat()
    
    print(dog.speak())  # Output: "woof"
    print(cat.speak())  # Output: "meow"
    
    ```
    
    In this example, we've defined a `Dog` class and a `Cat` class that both inherit from the `Animal` class. Each subclass has its own implementation of the `speak()` method. When we create instances of `Dog` and `Cat` and call the `speak()` method on them, we get different behavior depending on which object we're dealing with.
    
    This is just one example of polymorphism in Python. The concept of polymorphism is an important one in object-oriented programming, as it allows for more dynamic and flexible code.
    
- Encapsulation
    
    Encapsulation is an object-oriented programming concept that refers to the practice of hiding the internal data of an object from the outside world and allowing access to that data only through methods defined within the object's class. This helps to ensure that the object's data is not accidentally or maliciously modified or accessed inappropriately.
    
    For example, let's say we have a class called `Person` that has two attributes, `name` and `age`, and a method called `get_age()`. We could define these like so:
    
    ```python
    class Person:
        def __init__(self, name, age):
            self.name = name
            self.age = age
    
        def get_age(self):
            return self.age
    
    ```
    
    In this example, we've defined a `Person` class with two attributes, `name` and `age`, and a method called `get_age()` that allows us to access the `age` attribute. We've also defined an initializer method, `__init__()`, that takes two parameters, `name` and `age`, and assigns them to the corresponding attributes.
    
    Now, let's say we want to create a `Person` object and access its `age` attribute. We could do this like so:
    
    ```
    person = Person("John", 30)
    age = person.get_age()
    print(age)  # Output: 30
    
    ```
    
    In this example, we've created a `Person` object with a `name` of "John" and an `age` of 30, and then called the `get_age()` method to retrieve the `age` attribute. Because the `age` attribute is encapsulated within the `Person` object and can only be accessed through the `get_age()` method, we can be sure that the `age` attribute is not being modified or accessed inappropriately.
    
- Inheritance
    
    In Python, there are three types of inheritance:
    
    1. Single inheritance: This is the simplest type of inheritance, where a derived class inherits from a single base class. For example:
    
    ```python
    class Animal:
        def __init__(self, name):
            self.name = name
    
    class Dog(Animal):
        def __init__(self, name, breed):
            super().__init__(name)
            self.breed = breed
    
    my_dog = Dog("Buddy", "Labrador")
    print(my_dog.name)  # Output: "Buddy"
    print(my_dog.breed)  # Output: "Labrador"
    
    ```
    
    In this example, we've defined a `Dog` class that inherits from the `Animal` class. The `Dog` class has its own constructor that takes a `name` parameter and a `breed` parameter. The `super()` function is used to call the constructor of the base class, `Animal`, passing in the `name` parameter. This initializes the `name` attribute of the `Dog` object. The `breed` attribute is then initialized separately.
    
    1. Multiple inheritance: This is a type of inheritance where a derived class inherits from multiple base classes. For example:
    
    ```python
    class Animal:
        def __init__(self, name):
            self.name = name
    
    class Mammal:
        def __init__(self, age):
            self.age = age
    
    class Dog(Animal, Mammal):
        def __init__(self, name, age, breed):
            Animal.__init__(self, name)
            Mammal.__init__(self, age)
            self.breed = breed
    
    my_dog = Dog("Buddy", 3, "Labrador")
    print(my_dog.name)  # Output: "Buddy"
    print(my_dog.age)  # Output: 3
    print(my_dog.breed)  # Output: "Labrador"
    
    ```
    
    In this example, we've defined a `Dog` class that inherits from both the `Animal` and `Mammal` classes. The `Dog` class has its own constructor that takes a `name` parameter, an `age` parameter, and a `breed` parameter. The constructors of both the `Animal` and `Mammal` classes are called manually using the class name, passing in `self` and the appropriate parameters. This initializes the `name` and `age` attributes of the `Dog` object. The `breed` attribute is then initialized separately.
    
    1. Multi-level inheritance: This is a type of inheritance where a derived class inherits from a base class, and then another derived class inherits from that derived class. For example:
    
    ```python
    class Animal:
        def __init__(self, name):
            self.name = name
    
    class Mammal(Animal):
        def __init__(self, name, age):
            super().__init__(name)
            self.age = age
    
    class Dog(Mammal):
        def __init__(self, name, age, breed):
            super().__init__(name, age)
            self.breed = breed
    
    my_dog = Dog("Buddy", 3, "Labrador")
    print(my_dog.name)  # Output: "Buddy"
    print(my_dog.age)  # Output: 3
    print(my_dog.breed)  # Output: "Labrador"
    
    ```
    
    In this example, we've defined a `Dog` class that inherits from the `Mammal` class, which in turn inherits from the `Animal` class. The `Dog` class has its own constructor that takes a `name` parameter, an `age` parameter, and a `breed` parameter. The `super()` function is used to call the constructor of the `Mammal` class, passing in the `name` parameter and the `age` parameter. This initializes the `name` and `age` attributes of the `Dog` object. The `breed` attribute is then initialized separately.
    
    Python also supports a special type of inheritance called "hierarchical inheritance", where multiple derived classes inherit from the same base class.
    
- Method Overriding & Overloading
    
    **Method Overriding:**
    
    Method overriding is the practice of changing the implementation of a method in a derived class that is already defined in the base class. This is useful when we want to provide a different implementation of a method for a specific class, while still using the same method signature. In Python, method overriding is achieved by simply redefining a method in a derived class with the same name as a method in the base class.
    
    ```python
    class Animal:
      def speak(self):
        print("The animal makes a sound")
    
    class Dog(Animal):
      def speak(self):
        print("The dog barks")
    
    class Cat(Animal):
      def speak(self):
        print("The cat meows")
    
    a = Animal()
    a.speak()  # Output: "The animal makes a sound"
    
    d = Dog()
    d.speak()  # Output: "The dog barks"
    
    c = Cat()
    c.speak()  # Output: "The cat meows"
    
    ```
    
    In this example, we have three classes: `Animal`, `Dog`, and `Cat`. The `Animal` class has a method called `speak()`, which prints "The animal makes a sound". The `Dog` and `Cat` classes both inherit from `Animal` and override the `speak()` method with their own implementations. When we create instances of the `Dog` and `Cat` classes and call the `speak()` method on them, we get different behavior depending on the context.
    
    **Method Overloading:**
    
    Method overloading is the practice of defining multiple methods with the same name but different parameter lists. This allows us to create methods that can perform similar tasks but with different types or numbers of arguments. In Python, method overloading is not directly supported because Python does not have a way to define multiple methods with the same name. However, we can achieve similar functionality using default arguments and variable-length argument lists.
    
    ``` python

    class Calculator:
      def add(self, x, y):
        return x + y
    
      def add(self, x, y, z):
        return x + y + z
    
    calc = Calculator()
    
    print(calc.add(2, 3))  # Output: TypeError: add() missing 1 required positional argument: 'z'
    print(calc.add(2, 3, 4))  # Output: 9
    
    ```
    
    In this example, we have a `Calculator` class with two methods called `add()`. The first method takes two arguments and returns their sum. The second method takes three arguments and returns their sum. When we create an instance of the `Calculator` class and try to call the `add()` method with only two arguments, we get a `TypeError` because there is no method with that signature. When we call the `add()` method with three arguments, we get the expected result.
    
    Note that this is not true method overloading, because we have defined two separate methods with different names. However, we can achieve similar functionality using default arguments and variable-length argument lists:
    
    ``` python 
    class Calculator:
      def add(self, x, y, z=None):
        if z is None:
          return x + y
        else:
          return x + y + z
    
    calc = Calculator()
    
    print(calc.add(2, 3))  # Output: 5
    print(calc.add(2, 3, 4))  # Output: 9
    
    ```
    
    In this example, we have defined a single method called `add()` that takes two or three arguments. If the third argument is not provided, we assume it is `None` and only add the first two arguments. Otherwise, we add all three arguments. This allows us to achieve similar functionality to method overloading, even though we only have one method with one name.
    
- Static Methods
    
    In Python, a static method is a method that belongs to a class, but does not access or modify any instance data. Static methods are not associated with any particular instance of a class and do not receive any special first argument (like "self" or "cls").
    
    Static methods are often used for utility functions that are related to a class, but do not need to operate on any specific instance of the class. For example, a class representing dates might have a static method that takes a date string and parses it into a Date object.
    
    Here's an example of how we could define a static method in Python:
    
    ```python
    
    class MyClass:
        @staticmethod
        def my_static_method(x, y):
            return x + y
    
    ```
    
    In this example, we've defined a class called "MyClass" with a static method called "my_static_method()". The "@staticmethod" decorator is used to indicate that this method is a static method.
    
    We can call this static method on the class itself, rather than on an instance of the class:
    
    ```python
    
    result = MyClass.my_static_method(3, 4)
    print(result)  # Output: 7
    
    ```
    
    In this example, we're calling the "my_static_method()" method on the "MyClass" class itself, rather than on an instance of the class. This is possible because static methods do not operate on instance data.
    
    In summary, static methods in Python are methods that are associated with a class but do not operate on any specific instance of the class. They are often used for utility functions that are related to a class, but do not need to access or modify any instance data.





---------------------
#### links:
[[Decorators in OOP]]
[[]]