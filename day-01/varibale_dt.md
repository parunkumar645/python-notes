# Python Study Notes

## 1. Variables in Python

### Definition
Variables in Python are named containers that store data values. They are used to reference and manipulate data within a program. Python uses dynamic typing, which means you don't need to declare a variable's type before using it.

### Syntax
```python
variable_name = value
```
- Variable names must start with a letter or underscore
- Can contain letters, numbers, and underscores
- Cannot use reserved keywords
- Case-sensitive (age and Age are different variables)

### Examples

#### Example 1: Basic Variable Assignment
```python
name = "John"
age = 25
print(name)  # Output: John
print(age)   # Output: 25
```

#### Example 2: Multiple Assignment
```python
x, y, z = 10, 20, 30
print(x)  # Output: 10
print(y)  # Output: 20
print(z)  # Output: 30
```

#### Example 3: Changing Variable Values
```python
counter = 1
print(counter)  # Output: 1
counter = counter + 1
print(counter)  # Output: 2
counter += 1    # Shorthand for counter = counter + 1
print(counter)  # Output: 3
```

#### Example 4: Variable Naming Conventions
```python
# Valid variable names
student_name = "Alice"
_private = "Hidden"
total2 = 100

# Invalid variable names (would cause errors)
# 2total = 200      # Cannot start with a number
# my-var = 300      # Hyphens not allowed
# class = "Python"  # Cannot use reserved keywords
```

#### Example 5: Type Conversion
```python
num_str = "42"
num_int = int(num_str)
print(num_str)     # Output: 42 (as string)
print(num_int)     # Output: 42 (as integer)
print(num_int + 8) # Output: 50 (numeric addition)
print(num_str + "8") # Output: 428 (string concatenation)
```

### Practice Questions

1. Create a variable named `city` with the value "New York" and display it.
2. Write a program that swaps the values of two variables `a` and `b` without using a third variable.
3. Create three variables in a single line that store your name, age, and favorite color.
4. What will be the output of the following code?
   ```python
   x = 10
   x += 5
   x *= 2
   print(x)
   ```
5. Write a program that converts temperature from Celsius to Fahrenheit using the formula: F = (C × 9/5) + 32

---

## 2. Data Types in Python

### Definition
Data types in Python classify the type of data a variable can hold. Python has several built-in data types that define the operations possible on the data and the way it's stored in memory.

### Syntax
Python determines data type automatically when you assign a value:
```python
# No explicit syntax for declaring type
variable_name = value  # Type is inferred from the value
```

To check the data type:
```python
type(variable_name)
```

### Examples

#### Example 1: Numeric Data Types
```python
# Integer
age = 25
print(type(age))  # Output: <class 'int'>

# Float
height = 5.9
print(type(height))  # Output: <class 'float'>

# Complex
complex_num = 3 + 4j
print(type(complex_num))  # Output: <class 'complex'>
```

#### Example 2: Text Data Type (String)
```python
name = "Python"
message = 'Hello, World!'
multi_line = """This is a
multi-line string"""

print(type(name))  # Output: <class 'str'>
print(name[0])     # Output: P (accessing character by index)
print(name[0:2])   # Output: Py (slicing)
print(len(name))   # Output: 6 (string length)
```

#### Example 3: Boolean Data Type
```python
is_active = True
has_permission = False

print(type(is_active))  # Output: <class 'bool'>
print(not is_active)    # Output: False
print(is_active and has_permission)  # Output: False
print(is_active or has_permission)   # Output: True
```

#### Example 4: Sequence Data Types
```python
# List (mutable ordered collection)
fruits = ["apple", "banana", "cherry"]
print(type(fruits))  # Output: <class 'list'>
fruits.append("orange")
print(fruits)  # Output: ['apple', 'banana', 'cherry', 'orange']

# Tuple (immutable ordered collection)
coordinates = (10, 20)
print(type(coordinates))  # Output: <class 'tuple'>
# coordinates[0] = 15  # This would raise an error

# Range
numbers = range(5)
print(list(numbers))  # Output: [0, 1, 2, 3, 4]
```

#### Example 5: Mapping and Set Data Types
```python
# Dictionary (key-value pairs)
person = {
    "name": "Alice",
    "age": 30,
    "city": "London"
}
print(type(person))  # Output: <class 'dict'>
print(person["name"])  # Output: Alice

# Set (unordered collection of unique items)
colors = {"red", "blue", "green"}
print(type(colors))  # Output: <class 'set'>
colors.add("red")  # Adding duplicate (will be ignored)
print(colors)  # Output: {'red', 'blue', 'green'}
```

### Practice Questions

1. Create variables for each of the following data types: integer, float, string, boolean, list, tuple, and dictionary.
2. Write a program that demonstrates type conversion between string and numeric types.
3. Create a list of 5 different fruits, then create a tuple from that list. What's the difference in behavior when you try to modify both?
4. Write code to create a dictionary containing information about a book (title, author, year, pages).
5. What will be the output of the following code?
   ```python
   x = [1, 2, 3]
   y = x
   y.append(4)
   print(x)
   ```

---

## 3. Keywords in Python

### Definition
Keywords in Python are reserved words that have special meanings and purposes and cannot be used as variable names or identifiers. They are used to define the syntax and structure of the Python language.

### Syntax
Keywords don't have a specific syntax as they are part of Python's syntax themselves. They are simply used in code according to their purpose.

### Examples

#### Example 1: Control Flow Keywords
```python
# if, elif, else
age = 18
if age < 18:
    print("Minor")
elif age == 18:
    print("Just turned adult")
else:
    print("Adult")

# for, while, break, continue
for i in range(5):
    if i == 2:
        continue  # Skip iteration when i is 2
    if i == 4:
        break     # Exit loop when i is 4
    print(i)      # Output: 0, 1, 3
```

#### Example 2: Function and Class Definition Keywords
```python
# def, return
def greet(name):
    return f"Hello, {name}!"

message = greet("Python")
print(message)  # Output: Hello, Python!

# class
class Person:
    def __init__(self, name):
        self.name = name
        
    def say_hello(self):
        return f"{self.name} says hello!"

person = Person("Alice")
print(person.say_hello())  # Output: Alice says hello!
```

#### Example 3: Exception Handling Keywords
```python
# try, except, finally
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("This always executes")
    
# raise
def check_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative")
    return age

try:
    check_age(-5)
except ValueError as e:
    print(e)  # Output: Age cannot be negative
```

#### Example 4: Module-related Keywords
```python
# import, from, as
import math
print(math.pi)  # Output: 3.141592653589793

from datetime import datetime as dt
current_time = dt.now()
print(current_time)
```

#### Example 5: Boolean Operation Keywords
```python
# and, or, not, is, in
x = 5
y = 10

print(x > 0 and y > 0)  # Output: True
print(x > 10 or y > 5)  # Output: True
print(not x == y)       # Output: True

numbers = [1, 2, 3, 4, 5]
print(3 in numbers)     # Output: True
print(6 in numbers)     # Output: False

a = [1, 2, 3]
b = [1, 2, 3]
c = a
print(a is b)  # Output: False (different objects with same value)
print(a is c)  # Output: True (same object)
```

### Practice Questions

1. List at least 10 Python keywords from memory.
2. Write a program using `if`, `elif`, and `else` to categorize a person's age: child (0-12), teenager (13-19), adult (20-64), senior (65+).
3. Create a function using `def` that takes two parameters and returns their sum. Then use this function in a program.
4. Write a program that uses a `try`-`except` block to handle division by zero.
5. Create a program that demonstrates the use of `for`, `while`, `break`, and `continue` keywords in a meaningful way.