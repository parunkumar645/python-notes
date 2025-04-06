# Python Classes and Objects

## Definition

**Class**: A class is a blueprint or template that defines the attributes (data) and methods (functions) that characterize a specific type of object.

**Object**: An object is an instance of a class - a concrete entity created using the class blueprint.

## Why Use Classes and Objects?

1. **Organization**: Group related data and functions together
2. **Reusability**: Create multiple instances with the same structure
3. **Encapsulation**: Hide implementation details and expose only what's necessary
4. **Real-world modeling**: Model real-world entities in code
5. **Code maintenance**: Easier to update and maintain related functionality

## Basic Class Structure

```python
class ClassName:
    # Class attributes (shared by all instances)
    class_attribute = value
    
    # Constructor method (initializes new objects)
    def __init__(self, param1, param2):
        # Instance attributes (unique to each instance)
        self.attribute1 = param1
        self.attribute2 = param2
    
    # Instance methods (actions an object can perform)
    def method_name(self):
        # Do something
        return something
```

## Examples

### Example 1: Simple Class and Object

```python
# Define a simple class
class Dog:
    # Class attribute
    species = "Canis familiaris"
    
    # Constructor (initializes instance attributes)
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # Instance method
    def bark(self):
        return "Woof!"

# Create objects (instances of the Dog class)
buddy = Dog("Buddy", 5)
max = Dog("Max", 3)

# Access attributes
print(buddy.name)        # Output: Buddy
print(max.age)           # Output: 3
print(buddy.species)     # Output: Canis familiaris

# Call methods
print(max.bark())        # Output: Woof!
```

### Example 2: Methods with Parameters

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

# Create a rectangle object
rect = Rectangle(5, 10)

# Use methods
print(rect.area())       # Output: 50
print(rect.perimeter())  # Output: 30
```

### Example 3: Modifying Attributes

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def birthday(self):
        self.age += 1
        return f"{self.name} is now {self.age} years old!"

# Create a person
john = Person("John", 25)

# Before birthday
print(john.age)          # Output: 25

# After birthday
print(john.birthday())   # Output: John is now 26 years old!
print(john.age)          # Output: 26
```

### Example 4: Class and Instance Attributes

```python
class Student:
    # Class attribute - same for all instances
    school = "Python High School"
    
    def __init__(self, name, grade):
        # Instance attributes - unique to each instance
        self.name = name
        self.grade = grade

# Create students
alice = Student("Alice", 95)
bob = Student("Bob", 87)

print(alice.school)      # Output: Python High School
print(bob.school)        # Output: Python High School

# Change class attribute (affects all instances)
Student.school = "Coding Academy"

print(alice.school)      # Output: Coding Academy
print(bob.school)        # Output: Coding Academy
```

### Example 5: Simple Inheritance

```python
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        return "Some sound"

# Child class inherits from Animal
class Cat(Animal):
    def speak(self):
        return "Meow!"

# Another child class
class Dog(Animal):
    def speak(self):
        return "Woof!"

# Create objects
animal = Animal("Generic Animal")
cat = Cat("Whiskers")
dog = Dog("Rex")

print(animal.speak())    # Output: Some sound
print(cat.speak())       # Output: Meow!
print(dog.speak())       # Output: Woof!
```

## Practice Questions

1. Create a `Car` class with attributes for `brand`, `model`, and `year`. Add a method called `description()` that returns a string with the car's details.

2. Create a `BankAccount` class with attributes for `owner` and `balance`. Add methods for `deposit(amount)` and `withdraw(amount)`. Make sure the balance cannot go below zero.

3. Create a `Circle` class with an attribute for `radius`. Include methods to calculate the circle's `area()` and `circumference()`.

4. Extend Example 4 by adding a `get_grade_letter()` method to the `Student` class that returns "A" for grades 90-100, "B" for 80-89, and so on.

5. Create a parent `Shape` class and two child classes, `Square` and `Triangle`. Each should have appropriate attributes and an `area()` method.