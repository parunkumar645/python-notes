# Python Dictionaries

## Definition
A dictionary in Python is an unordered collection of key-value pairs. Each key is connected to a value, creating a key-value pair. Dictionaries are defined by enclosing comma-separated key-value pairs within curly braces `{}` where each key and value are separated by a colon. Keys must be unique and immutable (strings, numbers, tuples), while values can be of any type.

## Why Use Dictionaries?
1. **Fast Lookups**: Dictionaries provide O(1) time complexity for retrieving values by their keys, making them extremely efficient for lookups.
2. **Associative Mapping**: They create a natural mapping between keys and values, perfect for representing real-world relationships.
3. **Flexible Structure**: Values can be of any data type, including other dictionaries, allowing for complex data structures.
4. **Data Organization**: Dictionaries organize data in a logical, easily accessible way, much like a real dictionary.
5. **Efficient Data Processing**: They excel at tasks like counting occurrences, grouping, and transforming data based on keys.

## Examples

### Example 1: Creating and Accessing Dictionaries
```python
# Creating dictionaries
empty_dict = {}  # Empty dictionary
person = {"name": "John", "age": 30, "city": "New York"}
mixed_types = {"string": "hello", "integer": 42, "list": [1, 2, 3], "float": 3.14}

# Alternative creation using dict() constructor
another_person = dict(name="Alice", age=25, city="Boston")

# Accessing values using keys
print(person["name"])  # John
print(person["age"])   # 30

# Accessing with get() method (safer, returns None if key doesn't exist)
print(person.get("city"))    # New York
print(person.get("country")) # None

# Providing default value with get()
print(person.get("country", "USA"))  # USA (default value if key not found)

# Checking if a key exists
print("name" in person)    # True
print("country" in person) # False

# Getting all keys, values, and items
print(person.keys())    # dict_keys(['name', 'age', 'city'])
print(person.values())  # dict_values(['John', 30, 'New York'])
print(person.items())   # dict_items([('name', 'John'), ('age', 30), ('city', 'New York')])
```

### Example 2: Modifying Dictionaries
```python
student = {"name": "Emma", "age": 18, "grade": "A"}

# Adding new key-value pairs
student["school"] = "Lincoln High"
print(student)  # {'name': 'Emma', 'age': 18, 'grade': 'A', 'school': 'Lincoln High'}

# Updating existing values
student["age"] = 19
print(student)  # {'name': 'Emma', 'age': 19, 'grade': 'A', 'school': 'Lincoln High'}

# Update multiple key-value pairs simultaneously
student.update({"grade": "A+", "year": "Senior"})
print(student)  # {'name': 'Emma', 'age': 19, 'grade': 'A+', 'school': 'Lincoln High', 'year': 'Senior'}

# Removing key-value pairs
removed_age = student.pop("age")
print(f"Removed age: {removed_age}")  # Removed age: 19
print(student)  # {'name': 'Emma', 'grade': 'A+', 'school': 'Lincoln High', 'year': 'Senior'}

# Remove and return the last inserted item (Python 3.7+ maintains insertion order)
last_item = student.popitem()
print(f"Last item: {last_item}")  # Last item: ('year', 'Senior')
print(student)  # {'name': 'Emma', 'grade': 'A+', 'school': 'Lincoln High'}

# Remove a specific key
del student["school"]
print(student)  # {'name': 'Emma', 'grade': 'A+'}

# Clear all items
student.clear()
print(student)  # {}
```

### Example 3: Nested Dictionaries and Complex Structures
```python
# Nested dictionary
users = {
    "user1": {
        "name": "Alice Smith",
        "email": "alice@example.com",
        "roles": ["admin", "user"],
        "active": True
    },
    "user2": {
        "name": "Bob Johnson",
        "email": "bob@example.com",
        "roles": ["user"],
        "active": False
    }
}

# Accessing nested values
print(users["user1"]["name"])    # Alice Smith
print(users["user2"]["roles"])   # ['user']

# Adding new nested data
users["user3"] = {
    "name": "Charlie Brown",
    "email": "charlie@example.com",
    "roles": ["user"],
    "active": True
}

# Modifying nested values
users["user2"]["active"] = True
users["user1"]["roles"].append("manager")

print(users["user1"]["roles"])  # ['admin', 'user', 'manager']
print(users["user2"]["active"]) # True

# Dictionary with mixed data structures
course = {
    "name": "Python Programming",
    "students": ["Alice", "Bob", "Charlie"],
    "scores": {
        "Alice": [85, 90, 88],
        "Bob": [75, 70, 82],
        "Charlie": [95, 92, 98]
    },
    "average": 86.1
}

# Accessing complex structures
print(course["scores"]["Charlie"])  # [95, 92, 98]
print(course["students"][0])       # Alice
```

### Example 4: Dictionary Comprehensions and Common Patterns
```python
# Dictionary comprehension
squares = {x: x**2 for x in range(1, 6)}
print(squares)  # {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# Dictionary comprehension with conditions
even_squares = {x: x**2 for x in range(1, 11) if x % 2 == 0}
print(even_squares)  # {2: 4, 4: 16, 6: 36, 8: 64, 10: 100}

# Converting two lists into a dictionary
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
name_to_age = dict(zip(names, ages))
print(name_to_age)  # {'Alice': 25, 'Bob': 30, 'Charlie': 35}

# Counting occurrences in a list
fruits = ["apple", "banana", "apple", "orange", "banana", "apple"]
fruit_count = {}

for fruit in fruits:
    fruit_count[fruit] = fruit_count.get(fruit, 0) + 1

print(fruit_count)  # {'apple': 3, 'banana': 2, 'orange': 1}

# Counting with Counter from collections (more elegant)
from collections import Counter
word_counts = Counter(fruits)
print(dict(word_counts))  # {'apple': 3, 'banana': 2, 'orange': 1}

# Grouping items
students = [
    {"name": "Alice", "grade": "A"},
    {"name": "Bob", "grade": "B"},
    {"name": "Charlie", "grade": "A"},
    {"name": "Dave", "grade": "B"}
]

grade_groups = {}
for student in students:
    grade = student["grade"]
    if grade not in grade_groups:
        grade_groups[grade] = []
    grade_groups[grade].append(student["name"])

print(grade_groups)  # {'A': ['Alice', 'Charlie'], 'B': ['Bob', 'Dave']}
```

### Example 5: Advanced Dictionary Methods and Operations
```python
# Using setdefault (get value or set default if key doesn't exist)
contacts = {"Alice": "123-456-7890"}
contacts.setdefault("Alice", "111-111-1111")  # Already exists, so no change
contacts.setdefault("Bob", "222-222-2222")    # Doesn't exist, so value is set

print(contacts)  # {'Alice': '123-456-7890', 'Bob': '222-222-2222'}

# Dictionary union (Python 3.9+)
dict1 = {"a": 1, "b": 2}
dict2 = {"b": 3, "c": 4}

# Merging dictionaries with | operator (Python 3.9+)
merged = dict1 | dict2
print(merged)  # {'a': 1, 'b': 3, 'c': 4}  (note: dict2's value for 'b' overwrites dict1's)

# Merging with ** unpacking (works in earlier Python versions)
merged_old = {**dict1, **dict2}
print(merged_old)  # {'a': 1, 'b': 3, 'c': 4}

# Creating a default dictionary
from collections import defaultdict

# Default dictionary with int as default_factory (starts at 0)
word_count = defaultdict(int)
for word in ["apple", "orange", "apple", "banana", "apple"]:
    word_count[word] += 1

print(dict(word_count))  # {'apple': 3, 'orange': 1, 'banana': 1}

# Default dictionary with list as default_factory
grouped_words = defaultdict(list)
words = ["apple", "bat", "car", "apple", "banana", "car"]
for word in words:
    grouped_words[word[0]].append(word)

print(dict(grouped_words))  # {'a': ['apple', 'apple'], 'b': ['bat', 'banana'], 'c': ['car', 'car']}

# OrderedDict (maintains insertion order in older Python versions)
from collections import OrderedDict
ordered = OrderedDict([('first', 1), ('second', 2), ('third', 3)])
ordered['fourth'] = 4
print(ordered)  # OrderedDict([('first', 1), ('second', 2), ('third', 3), ('fourth', 4)])

# Note: Regular dictionaries preserve insertion order in Python 3.7+
```

## Practice Questions

1. **Basic:** Create a dictionary to store information about a person including name, age, and favorite color. Write code to print each piece of information.

2. **Intermediate:** Write a function `word_frequency` that takes a string as input and returns a dictionary containing each word and its frequency in the string. Ignore case and punctuation.

3. **Challenge:** Create a function `invert_dictionary` that takes a dictionary as input and returns a new dictionary where the keys and values are swapped. Handle the case where multiple keys might have the same value.

4. **Applied:** Write a program to manage a simple phone book using dictionaries. Allow users to add contacts, look up phone numbers by name, delete contacts, and list all contacts. Structure your code to handle these operations efficiently.

5. **Advanced:** Implement a `NestedDictionary` class that makes it easier to work with deeply nested dictionaries. Include methods to:
   - Get a value at a specified path (e.g., `get_value(["user", "address", "city"])`)
   - Set a value at a specified path
   - Delete a value at a specified path
   - Check if a path exists
   
   Make sure your implementation handles cases where intermediate keys don't exist.