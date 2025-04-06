# Python Inheritance

## Definition

**Inheritance** is a fundamental concept in object-oriented programming (OOP) that allows a class (called a child or derived class) to inherit attributes and methods from another class (called a parent or base class). This promotes code reuse and establishes a relationship between classes.

## Why Use Inheritance?

1. **Code Reusability**: Avoid duplicating code by sharing common attributes and methods
2. **Logical Hierarchy**: Model real-world relationships ("is-a" relationships)
3. **Method Overriding**: Customize behavior in child classes
4. **Extensibility**: Add new features without modifying existing code
5. **Polymorphism**: Allow objects of different classes to be treated as objects of a common parent class

## Basic Inheritance Syntax

```python
# Parent/Base class
class ParentClass:
    # Parent class attributes and methods
    def parent_method(self):
        return "This method is from the parent class"

# Child/Derived class
class ChildClass(ParentClass):
    # Child class inherits all attributes and methods from parent
    # Child class can also have its own attributes and methods
    def child_method(self):
        return "This method is from the child class"
```

## Examples

### Example 1: Basic Inheritance

```python
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name
    
    def eat(self):
        return f"{self.name} is eating"
    
    def sleep(self):
        return f"{self.name} is sleeping"

# Child class
class Dog(Animal):
    def bark(self):
        return f"{self.name} says Woof!"

# Create an instance of the child class
my_dog = Dog("Buddy")

# Access methods from the parent class
print(my_dog.eat())     # Output: Buddy is eating
print(my_dog.sleep())   # Output: Buddy is sleeping

# Access method from the child class
print(my_dog.bark())    # Output: Buddy says Woof!
```

### Example 2: Method Overriding

```python
# Parent class
class Vehicle:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color
    
    def display_info(self):
        return f"A {self.color} vehicle made by {self.brand}"
    
    def move(self):
        return "The vehicle is moving"

# Child class
class Car(Vehicle):
    def __init__(self, brand, color, model):
        # Call parent class constructor
        super().__init__(brand, color)
        self.model = model
    
    # Override the display_info method
    def display_info(self):
        return f"A {self.color} {self.brand} {self.model} car"
    
    # Add new method
    def honk(self):
        return "Beep! Beep!"

# Create a car object
my_car = Car("Toyota", "blue", "Corolla")

print(my_car.display_info())  # Output: A blue Toyota Corolla car
print(my_car.move())          # Output: The vehicle is moving
print(my_car.honk())          # Output: Beep! Beep!
```

### Example 3: Multi-level Inheritance

```python
# Base class
class Animal:
    def eat(self):
        return "I can eat"

# Intermediate class
class Dog(Animal):
    def bark(self):
        return "I can bark"

# Derived class
class Labrador(Dog):
    def color(self):
        return "I am usually yellow or black"

# Create a Labrador object
my_lab = Labrador()

# Access methods from all classes in the hierarchy
print(my_lab.eat())    # From Animal class
print(my_lab.bark())   # From Dog class
print(my_lab.color())  # From Labrador class
```

### Example 4: Multiple Inheritance

```python
# First parent class
class Swimmer:
    def swim(self):
        return "I can swim"

# Second parent class
class Flyer:
    def fly(self):
        return "I can fly"

# Child class inheriting from multiple parents
class Duck(Swimmer, Flyer):
    def quack(self):
        return "Quack!"

# Create a Duck object
donald = Duck()

# Access methods from all parent classes
print(donald.swim())   # From Swimmer class
print(donald.fly())    # From Flyer class
print(donald.quack())  # From Duck class
```

### Example 5: `super()` Function

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def introduce(self):
        return f"Hi, I'm {self.name} and I'm {self.age} years old."

class Student(Person):
    def __init__(self, name, age, student_id):
        # Call the parent class's __init__ method
        super().__init__(name, age)
        self.student_id = student_id
    
    def introduce(self):
        # Call the parent class's introduce method and extend it
        basic_intro = super().introduce()
        return f"{basic_intro} My student ID is {self.student_id}."

# Create a Student object
alice = Student("Alice", 20, "A12345")

print(alice.introduce())  # Output: Hi, I'm Alice and I'm 20 years old. My student ID is A12345.
```

## Practice Questions

1. Create a base class `Shape` with a method `area()` that returns 0. Then create derived classes `Rectangle` and `Circle` that override the `area()` method with their specific area calculations.

2. Create a class hierarchy for a school system: a base class `Person` with attributes like name and age, and derived classes `Student` and `Teacher` with additional specific attributes and methods.

3. Design a simple banking system with a base class `Account` and derived classes `SavingsAccount` and `CheckingAccount`. Each should have appropriate methods for deposit, withdrawal, and interest calculations.

4. Create a scenario using multiple inheritance: design `ElectricCar` and `SolarCar` classes that inherit from both a `Vehicle` class and appropriate energy source classes.

5. Implement a class hierarchy for different types of employees in a company, using inheritance to represent their relationships, shared attributes, and specialized methods.