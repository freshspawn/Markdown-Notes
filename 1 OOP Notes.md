## Object Oriented Programming 



## Abstract Classes

Abstract classes are any class that contain an abstract method. An abstract class is allowed to contain other methods however. Typically abstract methods are formally defined with the @abstractmethod dectorator. Any abstract class must define each abstract method in their children. Otherwise, we should raise an error  

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)

# Uncommenting the following line would raise an error
# shape = Shape()  # Can't instantiate abstract class Shape with abstract methods area, perimeter

rectangle = Rectangle(10, 20)
print(f"Area: {rectangle.area()}, Perimeter: {rectangle.perimeter()}")

```

### Usage of the from abc import ABC , abstract method

In Python, to formally declare a method as an abstract method, you generally use the @abstractmethod decorator from the abc (Abstract Base Classes) module.

By using @abstractmethod, you're enforcing that any subclass must implement the abstract methods. If a subclass fails to implement all the abstract methods, it can't be instantiated. Otherwise without the @abstractmethod decorator, there is nothing enforcing that a subclass must implement all the abstract methods.


## Static Methods

Static methods belong to the class itself rather than an object. A static method doesn't access or modify class state or instance state, and it doesn't take a self argument (which refers to an instance) or a cls argument (which refers to the class).

### Example of Static Method

```python

class Math:
    @staticmethod
    def factorial(n):
        if n == 0:
            return 1
        else:
            return n * Math.factorial(n-1)

 #You can call the static method using the class name, without creating an instance.
result = Math.factorial(5)
print(result)  # Output will be 120

```

#### Quick Note

Note that unlike abstract classes, we do not need to import any module to use the @staticmethod decorator. This is because it is a default python feature.


#### Semantic Meaning

Also static methods typically have some relation to the class itself 