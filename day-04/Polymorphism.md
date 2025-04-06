# Python Polymorphism

## Definition

**Polymorphism** means "many forms" and in programming, it refers to the ability of different classes to be treated as instances of the same class through inheritance. It allows you to use a single interface with different underlying forms (data types).

## Why Use Polymorphism?

1. **Simplifies Code**: Write functions that work with objects of different types
2. **Flexibility**: Allows objects to be processed in a uniform way
3. **Extensibility**: Makes it easy to add new classes without changing existing code
4. **Consistent Interface**: Objects of different classes respond to the same method names
5. **DRY Principle**: Avoids duplicate code when similar operations are performed across different types

## Types of Polymorphism in Python

### 1. Method Overriding (Runtime Polymorphism)
When a child class provides a specific implementation of a method that is already defined in its parent class.

### 2. Method Overloading (Compile-time Polymorphism)
Python doesn't support traditional method overloading, but achieves similar functionality using default arguments and variable-length arguments.

### 3. Duck Typing
"If it walks like a duck and quacks like a duck, it's a duck." Objects are defined by their behavior (methods) rather than their class.

## Examples

### Example 1: Basic Method Overriding

```python
class Animal:
    def speak(self):
        return "Animal makes a sound"

class Dog(Animal):
    def speak(self):
        return "Dog says Woof!"

class Cat(Animal):
    def speak(self):
        return "Cat says Meow!"

# Create objects
animal = Animal()
dog = Dog()
cat = Cat()

# Each object's speak() method is called
print(animal.speak())  # Output: Animal makes a sound
print(dog.speak())     # Output: Dog says Woof!
print(cat.speak())     # Output: Cat says Meow!
```

### Example 2: Polymorphic Function

```python
def animal_sound(animal):
    return animal.speak()

# Using the same function with different objects
animal = Animal()
dog = Dog()
cat = Cat()

print(animal_sound(animal))  # Output: Animal makes a sound
print(animal_sound(dog))     # Output: Dog says Woof!
print(animal_sound(cat))     # Output: Cat says Meow!
```

### Example 3: Duck Typing

```python
class Duck:
    def swim(self):
        return "Duck swimming"
    
    def sound(self):
        return "Quack quack"

class Person:
    def swim(self):
        return "Person swimming"
    
    def sound(self):
        return "Hello world"

# Function doesn't care about class type, just that the methods exist
def make_sound_and_swim(entity):
    print(entity.sound())
    print(entity.swim())

# Using with different objects
duck = Duck()
person = Person()

make_sound_and_swim(duck)
# Output:
# Quack quack
# Duck swimming

make_sound_and_swim(person)
# Output:
# Hello world
# Person swimming
```

### Example 4: Polymorphism with Class Methods

```python
class Shape:
    def area(self):
        return 0

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return 3.14 * self.radius * self.radius

# Calculate areas using polymorphism
shapes = [Rectangle(5, 4), Circle(7), Rectangle(2, 3)]

# Using the same method name for different objects
for shape in shapes:
    print(f"Area: {shape.area()}")

# Output:
# Area: 20
# Area: 153.86
# Area: 6
```

### Example 5: Polymorphism with Built-in Functions

```python
# len() function is polymorphic - works with different types
print(len("Hello"))           # Output: 5
print(len([1, 2, 3, 4]))      # Output: 4
print(len({"a": 1, "b": 2}))  # Output: 2

# + operator is polymorphic - behavior changes based on data type
print(2 + 3)                  # Output: 5 (addition)
print("Hello" + " World")     # Output: Hello World (concatenation)
print([1, 2] + [3, 4])        # Output: [1, 2, 3, 4] (list concatenation)
```

## Practice Questions

1. Create a parent class `Vehicle` with a method `description()` and child classes `Car`, `Motorcycle`, and `Truck`. Override the `description()` method in each child class to return a specific description.

2. Write a function that takes different shape objects and prints their areas. Create classes for `Square`, `Triangle`, and `Circle` with appropriate `area()` methods.

3. Create a system that demonstrates polymorphism using animal sounds. Define an `Animal` class with a `make_sound()` method and at least three subclasses that override this method.

4. Implement a simple calculator function that uses polymorphism to perform different operations based on the operator passed.

5. Design a simple game with different character types (Warrior, Mage, Archer) that inherit from a base Character class. Each should have a `attack()` method that behaves differently.