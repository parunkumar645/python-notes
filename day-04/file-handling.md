# Python File Handling

## Definition

**File handling** in Python refers to the process of working with files on your computer - creating, reading, updating, and deleting files. Python provides built-in functions and methods to work with files easily.

## Why Use File Handling?

1. **Store Data Permanently**: Save information that persists after the program ends
2. **Process Large Datasets**: Work with data too large to fit in memory
3. **Share Data**: Create files that can be shared with other programs
4. **Save Program Output**: Store results for later use
5. **Read Input Data**: Load configuration or user data from files

## Basic File Operations

### 1. Opening a File

```python
# Syntax: open(filename, mode)
file = open("example.txt", "r")  # Open for reading (default)
```

Common file modes:
- `"r"` - Read (default)
- `"w"` - Write (creates new file or overwrites existing)
- `"a"` - Append (adds to end of existing file)
- `"r+"` - Read and write

### 2. Reading from a File

```python
# Read entire file
file = open("example.txt", "r")
content = file.read()
print(content)
file.close()

# Read line by line
file = open("example.txt", "r")
for line in file:
    print(line.strip())  # strip() removes the newline character
file.close()
```

### 3. Writing to a File

```python
# Write to a file (overwrites existing content)
file = open("example.txt", "w")
file.write("Hello, world!")
file.close()

# Append to a file (adds to existing content)
file = open("example.txt", "a")
file.write("\nAppended line")
file.close()
```

### 4. Closing a File

Always close files when you're done with them:

```python
file = open("example.txt", "r")
# Do something with the file
file.close()
```

### 5. The `with` Statement (Recommended)

The `with` statement automatically closes the file when you're done:

```python
# Automatically closes the file when the block ends
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
# File is automatically closed here
```

## Examples

### Example 1: Reading an Entire File

```python
# Reading an entire file at once
with open("sample.txt", "r") as file:
    content = file.read()
    print(content)
```

### Example 2: Reading Line by Line

```python
# Reading a file line by line
with open("sample.txt", "r") as file:
    for line in file:
        print(line.strip())  # strip() removes the newline character
```

### Example 3: Writing to a New File

```python
# Writing content to a file
with open("output.txt", "w") as file:
    file.write("First line of text\n")
    file.write("Second line of text\n")
    file.write("Third line of text")
```

### Example 4: Appending to an Existing File

```python
# Appending content to an existing file
with open("output.txt", "a") as file:
    file.write("\nThis line is appended to the file")
    file.write("\nAnother appended line")
```

### Example 5: Working with CSV Files

```python
# Reading and writing CSV files
import csv

# Writing to a CSV file
with open("data.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["Name", "Age", "City"])
    writer.writerow(["John", 25, "New York"])
    writer.writerow(["Alice", 30, "London"])
    writer.writerow(["Bob", 35, "Paris"])

# Reading from a CSV file
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

## Practice Questions

1. Write a Python program to read the first 5 lines of a text file named "story.txt".

2. Create a program that counts the number of lines, words, and characters in a text file.

3. Write a program that reads a file named "numbers.txt" containing one number per line, and calculates their sum and average.

4. Create a program that takes user input and appends it to a file named "journal.txt", with each entry on a new line and preceded by the current date.

5. Write a program that copies the contents of one file to another, but converts all text to uppercase.