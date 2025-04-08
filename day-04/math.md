# Math in Python - Student Notes

## 1. Definition

Python provides various ways to perform mathematical operations, both through built-in operators and through specialized modules like the `math` library. Mathematical operations are fundamental to programming and are used for calculations, data analysis, scientific computing, and many other applications.

### Built-in Math Operators:
- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division (returns float)
- `//` Floor Division (returns integer)
- `%` Modulo (remainder)
- `**` Exponentiation (power)

### Math Library:
Python's `math` module provides additional mathematical functions for more advanced operations like trigonometry, logarithms, and other mathematical calculations.

## 2. Basic Examples

### Example 1: Basic Arithmetic Operations
```python
# Basic arithmetic operations
a = 10
b = 3

addition = a + b        # 13
subtraction = a - b     # 7
multiplication = a * b  # 30
division = a / b        # 3.3333...
floor_division = a // b # 3
modulo = a % b          # 1
power = a ** b          # 1000

print(f"Addition: {addition}")
print(f"Subtraction: {subtraction}")
print(f"Multiplication: {multiplication}")
print(f"Division: {division}")
print(f"Floor Division: {floor_division}")
print(f"Modulo: {modulo}")
print(f"Power: {power}")
```

### Example 2: Working with the Math Module
```python
import math

# Using various math functions
result1 = math.sqrt(16)      # Square root: 4.0
result2 = math.sin(math.pi/2)  # Sine of 90°: 1.0
result3 = math.log10(100)    # Log base 10: 2.0
result4 = math.ceil(4.2)     # Ceiling: 5
result5 = math.floor(4.8)    # Floor: 4

print(f"Square root of 16: {result1}")
print(f"Sin(π/2): {result2}")
print(f"Log10(100): {result3}")
print(f"Ceiling of 4.2: {result4}")
print(f"Floor of 4.8: {result5}")
```

### Example 3: Order of Operations
```python
# Python follows the PEMDAS rule:
# Parentheses, Exponents, Multiplication/Division, Addition/Subtraction
result = 10 + 3 * 2    # 16 (not 26)
result2 = (10 + 3) * 2  # 26
result3 = 2 ** 3 + 4    # 12 (not 64)

print(f"10 + 3 * 2 = {result}")
print(f"(10 + 3) * 2 = {result2}")
print(f"2 ** 3 + 4 = {result3}")
```

### Example 4: Rounding Numbers
```python
# Different ways to round numbers
num = 3.75

# Built-in round function
rounded = round(num)      # 4
rounded_decimal = round(num, 1)  # 3.8

# Using math module
import math
floor_value = math.floor(num)    # 3
ceiling_value = math.ceil(num)   # 4
truncated = math.trunc(num)      # 3

print(f"Original number: {num}")
print(f"Rounded: {rounded}")
print(f"Rounded to 1 decimal: {rounded_decimal}")
print(f"Floor: {floor_value}")
print(f"Ceiling: {ceiling_value}")
print(f"Truncated: {truncated}")
```

### Example 5: Working with Complex Calculations
```python
import math

# Calculate the area of a circle
radius = 5
area = math.pi * radius ** 2
circumference = 2 * math.pi * radius

# Calculate the hypotenuse of a right triangle
side1 = 3
side2 = 4
hypotenuse = math.sqrt(side1 ** 2 + side2 ** 2)

# Calculate compound interest
principal = 1000
rate = 0.05  # 5%
time = 3     # years
compound_interest = principal * (1 + rate) ** time - principal

print(f"Area of circle: {area:.2f}")
print(f"Circumference: {circumference:.2f}")
print(f"Hypotenuse: {hypotenuse}")
print(f"Compound interest: ${compound_interest:.2f}")
```

## 3. Practice Questions

### Question 1
Write a Python program that calculates and prints the average of three numbers entered by the user.

### Question 2
Create a program that converts temperature from Celsius to Fahrenheit using the formula: F = (C × 9/5) + 32.

### Question 3
Write a function that calculates the area and perimeter of a rectangle, given its length and width as parameters.

### Question 4
Create a program that checks if a number is even or odd, and also determines if it's a prime number.

### Question 5
Write a program that calculates the simple interest using the formula: SI = (principal × rate × time) / 100. Allow the user to input all three values.