# Python Programming Cheat Sheet

A comprehensive guide to Python programming and scripting.

---

## Table of Contents

1. [Introduction to Python](#1-introduction-to-python)
2. [Basic Syntax](#2-basic-syntax)
3. [Variables and Data Types](#3-variables-and-data-types)
4. [Operators](#4-operators)
5. [Control Flow](#5-control-flow)
6. [Functions](#6-functions)
7. [Modules and Packages](#7-modules-and-packages)
8. [Data Structures](#8-data-structures)
9. [File Handling](#9-file-handling)
10. [Exceptions](#10-exceptions)
11. [Object-Oriented Programming](#11-object-oriented-programming)
12. [Regular Expressions](#12-regular-expressions)
13. [Working with Libraries](#13-working-with-libraries)
14. [Decorators and Generators](#14-decorators-and-generators)
15. [Comprehensions](#15-comprehensions)
16. [Lambda Functions](#16-lambda-functions)
17. [Virtual Environments](#17-virtual-environments)
18. [Common Built-in Functions](#18-common-built-in-functions)
19. [Debugging and Testing](#19-debugging-and-testing)
20. [Useful Resources](#20-useful-resources)

---

## 1. Introduction to Python

- **Python** is a high-level, interpreted programming language.
- Supported paradigms include procedural, object-oriented, and functional programming.
- **Interpreted language:** No need to compile code before execution.
- **Python 3** is the current version; Python 2 has reached end-of-life as of 2020.

**Run a Python script:**

```bash
python script.py
```

**Interactive Python shell:**

```bash
python
```

[Back to Top](#table-of-contents)

---

## 2. Basic Syntax

- **Comments:** Lines starting with `#` are comments.
- **Multi-line comments:** Enclosed in triple quotes `''' comment '''` or `""" comment """`.
- **Indentation:** Used to define code blocks (functions, loops, conditionals). Indentation is critical and typically uses 4 spaces.
- **No semicolons:** Statements end with a newline character.
- **Case sensitivity:** Python is case-sensitive.

**Hello World Example:**

```python
print("Hello, World!")
```

[Back to Top](#table-of-contents)

---

## 3. Variables and Data Types

### Variables

- No need to declare variables explicitly; they are created upon assignment.
- Variable names are case-sensitive and must start with a letter or underscore.

**Assignment:**

```python
x = 5
name = "Alice"
```

### Data Types

- **Numeric Types:**
  - `int` (e.g., `1`, `42`)
  - `float` (e.g., `3.14`, `2.0`)
  - `complex` (e.g., `1+2j`)

- **Boolean:**
  - `True` or `False`

- **String:**
  - Enclosed in single `'` or double `"` quotes (e.g., `'hello'`, `"hello"`)

- **NoneType:**
  - `None` represents the absence of a value.

**Check Data Type:**

```python
type(x)
```

### Type Casting

- Convert between data types.

```python
int("42")       # Returns 42
float("3.14")   # Returns 3.14
str(100)        # Returns "100"
```

[Back to Top](#table-of-contents)

---

## 4. Operators

### Arithmetic Operators

- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division (returns float)
- `//` Floor Division (returns integer quotient)
- `%` Modulus (remainder)
- `**` Exponentiation

**Examples:**

```python
a = 10
b = 3

print(a + b)   # Output: 13
print(a - b)   # Output: 7
print(a * b)   # Output: 30
print(a / b)   # Output: 3.333...
print(a // b)  # Output: 3
print(a % b)   # Output: 1
print(a ** b)  # Output: 1000
```

### Comparison Operators

- `==` Equal to
- `!=` Not equal to
- `>` Greater than
- `<` Less than
- `>=` Greater than or equal to
- `<=` Less than or equal to

### Logical Operators

- `and` Logical AND
- `or` Logical OR
- `not` Logical NOT

**Examples:**

```python
x = 5
print(x > 3 and x < 10)   # Output: True
print(x > 3 or x > 10)    # Output: True
print(not(x > 3 and x < 10))  # Output: False
```

### Assignment Operators

- `=` Simple assignment
- `+=` Addition assignment (`x += 3` is equivalent to `x = x + 3`)
- `-=` Subtraction assignment
- `*=` Multiplication assignment
- `/=` Division assignment
- `//=` Floor division assignment
- `%=` Modulus assignment
- `**=` Exponentiation assignment

**Example:**

```python
x = 5
x += 3
print(x)  # Output: 8
```

### Membership Operators

- `in` Checks if a value is present in a sequence
- `not in` Checks if a value is not present in a sequence

**Example:**

```python
fruits = ["apple", "banana", "cherry"]
print("banana" in fruits)      # Output: True
print("grape" not in fruits)   # Output: True
```

[Back to Top](#table-of-contents)

---

## 5. Control Flow

### Conditional Statements

**If Statement:**

```python
x = 10

if x > 5:
    print("x is greater than 5")
```

**If-Else Statement:**

```python
x = 4

if x > 5:
    print("x is greater than 5")
else:
    print("x is not greater than 5")
```

**Elif Statement:**

```python
x = 5

if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")
```

### Loops

**For Loop:**

```python
for i in range(5):
    print(i)
```

- `range(5)` generates numbers from `0` to `4`.

**While Loop:**

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

### Loop Control Statements

- `break`: Exits the loop.
- `continue`: Skips to the next iteration.
- `pass`: Does nothing (useful as a placeholder).

**Example with break and continue:**

```python
for i in range(10):
    if i == 3:
        continue  # Skip the rest of the loop when i == 3
    if i == 7:
        break     # Exit the loop when i == 7
    print(i)
```

[Back to Top](#table-of-contents)

---

## 6. Functions

- Functions are defined using the `def` keyword.

**Function Definition:**

```python
def greet(name):
    return "Hello, " + name
```

**Function Call:**

```python
message = greet("Alice")
print(message)  # Output: Hello, Alice
```

### Default Arguments

```python
def greet(name="Guest"):
    return "Hello, " + name

print(greet())           # Output: Hello, Guest
print(greet("Bob"))      # Output: Hello, Bob
```

### Keyword Arguments

```python
def info(name, age):
    print("Name:", name)
    print("Age:", age)

info(age=25, name="Carol")
```

### Variable-Length Arguments

- **Args (Non-Keyword Arguments):**

```python
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_numbers(1, 2, 3))  # Output: 6
```

- **Kwargs (Keyword Arguments):**

```python
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Dave", age=30)
```

[Back to Top](#table-of-contents)

---

## 7. Modules and Packages

### Importing Modules

- Import the entire module:

```python
import math
print(math.sqrt(16))  # Output: 4.0
```

- Import specific attributes:

```python
from math import sqrt
print(sqrt(16))  # Output: 4.0
```

- Import with an alias:

```python
import numpy as np
```

### Creating a Module

- Save your functions in a `.py` file (e.g., `my_module.py`).

**my_module.py**

```python
def greet(name):
    return "Hello, " + name
```

**Using the module:**

```python
import my_module

print(my_module.greet("Alice"))
```

### Packages

- A package is a directory containing an `__init__.py` file.
- It can contain multiple modules.

**Directory Structure:**

```
my_package/
    __init__.py
    module1.py
    module2.py
```

**Importing from a Package:**

```python
from my_package import module1
```

[Back to Top](#table-of-contents)

---

## 8. Data Structures

### Lists

- Ordered, mutable collections.

**Creating a List:**

```python
fruits = ["apple", "banana", "cherry"]
```

**Accessing Elements:**

```python
print(fruits[0])    # Output: apple
print(fruits[-1])   # Output: cherry
```

**List Methods:**

- `append()`: Adds an element to the end.
- `insert()`: Inserts an element at a specified index.
- `remove()`: Removes the first occurrence of a value.
- `pop()`: Removes and returns element at index.
- `sort()`: Sorts the list.
- `reverse()`: Reverses the list.

**Example:**

```python
fruits.append("orange")
fruits.insert(1, "mango")
fruits.remove("banana")
item = fruits.pop()
```

### Tuples

- Ordered, immutable collections.

**Creating a Tuple:**

```python
colors = ("red", "green", "blue")
```

**Accessing Elements:**

```python
print(colors[1])  # Output: green
```

### Sets

- Unordered collections of unique elements.

**Creating a Set:**

```python
numbers = {1, 2, 3, 4}
```

**Set Methods:**

- `add()`: Adds an element.
- `remove()`: Removes an element (raises KeyError if not found).
- `discard()`: Removes an element if present.
- `union()`: Returns a new set with elements from both sets.
- `intersection()`: Returns a set of elements common to both sets.
- `difference()`: Returns a set of elements in one set but not in another.

**Example:**

```python
numbers.add(5)
numbers.remove(2)
```

### Dictionaries

- Unordered collections of key-value pairs.

**Creating a Dictionary:**

```python
person = {"name": "Alice", "age": 25, "city": "New York"}
```

**Accessing Values:**

```python
print(person["name"])  # Output: Alice
```

**Dictionary Methods:**

- `keys()`: Returns a view of keys.
- `values()`: Returns a view of values.
- `items()`: Returns a view of key-value pairs.
- `get(key, default)`: Returns value for key or a default value if key not found.
- `update()`: Updates the dictionary with another dictionary or key-value pairs.

**Example:**

```python
person["email"] = "alice@example.com"
age = person.get("age", 0)
```

**Iterating Over Dictionaries:**

```python
for key, value in person.items():
    print(f"{key}: {value}")
```

[Back to Top](#table-of-contents)

---

## 9. File Handling

### Opening and Closing Files

**Open a File:**

```python
file = open("filename.txt", "mode")
```

**Modes:**

- `'r'`: Read (default)
- `'w'`: Write (overwrites file)
- `'a'`: Append (adds to the end of the file)
- `'r+'`: Read and write
- `'wb'`: Write binary
- `'rb'`: Read binary

**Close a File:**

```python
file.close()
```

### Reading Files

**Read Entire File:**

```python
file = open("example.txt", "r")
content = file.read()
file.close()
```

**Read Lines:**

```python
file = open("example.txt", "r")
lines = file.readlines()
file.close()
```

### Writing to Files

```python
file = open("example.txt", "w")
file.write("Hello, File!")
file.close()
```

### Using `with` Statement

- Automatically handles file closing.

```python
with open("example.txt", "r") as file:
    content = file.read()
```

[Back to Top](#table-of-contents)

---

## 10. Exceptions

- Handle errors gracefully using try-except blocks.

### Try-Except Block

```python
try:
    # Risky code
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

### Catching Multiple Exceptions

```python
try:
    # Some code
except (ValueError, TypeError) as e:
    print("An error occurred:", e)
```

### Finally Clause

- Runs code regardless of whether an exception occurred.

```python
try:
    # Some code
except:
    # Handle exception
finally:
    # Cleanup code
```

### Raising Exceptions

```python
raise ValueError("Invalid value")
```

[Back to Top](#table-of-contents)

---

## 11. Object-Oriented Programming

- Python supports classes and objects.

### Defining a Class

```python
class Person:
    # Constructor
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # Method
    def greet(self):
        print(f"Hello, my name is {self.name}.")
```

### Creating Objects

```python
p1 = Person("Alice", 25)
p1.greet()  # Output: Hello, my name is Alice.
```

### Inheritance

**Subclassing:**

```python
class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id
```

### Method Overriding

```python
class Student(Person):
    def greet(self):
        print(f"Hi, I'm {self.name}, and I'm a student.")

p = Student("Bob", 20, "S123")
p.greet()  # Output: Hi, I'm Bob, and I'm a student.
```

### Encapsulation

- Private attributes (by convention, prefix with `_` or `__`).

```python
class Secret:
    def __init__(self):
        self.__secret = "Top Secret!"

    def reveal(self):
        return self.__secret

s = Secret()
print(s.reveal())  # Output: Top Secret!
```

[Back to Top](#table-of-contents)

---

## 12. Regular Expressions

- Use the `re` module for pattern matching.

### Importing `re` Module

```python
import re
```

### Common Functions

- `re.match(pattern, string)`: Checks for a match at the beginning of the string.
- `re.search(pattern, string)`: Searches for a match anywhere in the string.
- `re.findall(pattern, string)`: Returns all matches as a list.
- `re.sub(pattern, repl, string)`: Replaces matches with a string.

### Example Usage

**Match:**

```python
pattern = r"hello"
text = "hello world"

if re.match(pattern, text):
    print("Match found!")
```

**Search:**

```python
pattern = r"world"
if re.search(pattern, text):
    print("Search successful!")
```

**Findall:**

```python
text = "abc 123 def 456"
numbers = re.findall(r"\d+", text)
print(numbers)  # Output: ['123', '456']
```

**Substitute:**

```python
text = "Hello, Bob!"
new_text = re.sub(r"Bob", "Alice", text)
print(new_text)  # Output: Hello, Alice!
```

### Common Patterns

- `\d` Digit
- `\w` Word character (alphanumeric + underscore)
- `\s` Whitespace
- `.` Any character except newline
- `^` Start of string
- `$` End of string
- `*` 0 or more occurrences
- `+` 1 or more occurrences
- `?` 0 or 1 occurrence
- `{n}` Exactly n occurrences
- `{n,}` n or more occurrences
- `[...]` Character set

[Back to Top](#table-of-contents)

---

## 13. Working with Libraries

### Installing Packages with `pip`

- Install a package:

```bash
pip install package_name
```

- Install a specific version:

```bash
pip install package_name==1.0.0
```

- Upgrade a package:

```bash
pip install --upgrade package_name
```

### Commonly Used Libraries

- **NumPy**: Numerical computing.
  
  ```python
  import numpy as np
  arr = np.array([1, 2, 3])
  ```

- **Pandas**: Data manipulation and analysis.
  
  ```python
  import pandas as pd
  df = pd.read_csv("data.csv")
  ```

- **Matplotlib**: Data visualization.
  
  ```python
  import matplotlib.pyplot as plt
  plt.plot([1, 2, 3], [4, 5, 6])
  plt.show()
  ```

- **Requests**: HTTP library.
  
  ```python
  import requests
  response = requests.get("http://example.com")
  print(response.text)
  ```

- **BeautifulSoup**: Web scraping.
  
  ```python
  from bs4 import BeautifulSoup
  soup = BeautifulSoup(html_content, 'html.parser')
  ```

- **Flask**: Web development framework.
  
  ```python
  from flask import Flask
  app = Flask(__name__)

  @app.route('/')
  def hello():
      return "Hello, World!"

  if __name__ == '__main__':
      app.run()
  ```

[Back to Top](#table-of-contents)

---

## 14. Decorators and Generators

### Decorators

- Functions that modify the behavior of other functions.

**Creating a Decorator:**

```python
def decorator_function(original_function):
    def wrapper_function(*args, **kwargs):
        # Code before
        result = original_function(*args, **kwargs)
        # Code after
        return result
    return wrapper_function
```

**Using a Decorator:**

```python
@decorator_function
def display():
    print("Display function")

display()
```

### Generators

- Functions that return an iterator using the `yield` keyword.

**Creating a Generator Function:**

```python
def generator():
    yield 1
    yield 2
    yield 3

g = generator()
print(next(g))  # Output: 1
print(next(g))  # Output: 2
```

**Using Generators in Loops:**

```python
for value in generator():
    print(value)
```

[Back to Top](#table-of-contents)

---

## 15. Comprehensions

### List Comprehensions

```python
squares = [x ** 2 for x in range(10)]
```

### Dictionary Comprehensions

```python
d = {x: x ** 2 for x in range(5)}
```

### Set Comprehensions

```python
s = {x for x in range(10) if x % 2 == 0}
```

### Nested Comprehensions

```python
matrix = [[i * j for j in range(3)] for i in range(3)]
```

[Back to Top](#table-of-contents)

---

## 16. Lambda Functions

- Anonymous, inline functions defined with the `lambda` keyword.

**Syntax:**

```python
lambda arguments: expression
```

**Example:**

```python
add = lambda x, y: x + y
print(add(2, 3))  # Output: 5
```

**Using with `map()`, `filter()`, and `reduce()`:**

```python
numbers = [1, 2, 3, 4, 5]

# Map
squares = list(map(lambda x: x ** 2, numbers))

# Filter
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))

# Reduce
from functools import reduce
product = reduce(lambda x, y: x * y, numbers)
```

[Back to Top](#table-of-contents)

---

## 17. Virtual Environments

- Isolate project dependencies using virtual environments.

### Creating a Virtual Environment

- Using the `venv` module (Python 3):

```bash
python -m venv myenv
```

### Activating the Virtual Environment

- **On Windows:**

```bash
myenv\Scripts\activate
```

- **On Unix or MacOS:**

```bash
source myenv/bin/activate
```

### Deactivating the Environment

```bash
deactivate
```

### Requirements File

- To freeze dependencies:

```bash
pip freeze > requirements.txt
```

- To install from a requirements file:

```bash
pip install -r requirements.txt
```

[Back to Top](#table-of-contents)

---

## 18. Common Built-in Functions

- `print()`: Prints output to console.
- `len()`: Returns the length of an object.
- `range()`: Generates a sequence of numbers.
- `type()`: Returns the type of an object.
- `int()`, `float()`, `str()`: Type casting functions.
- `input()`: Reads input from the user.
- `open()`: Opens a file.
- `sum()`: Sums elements of an iterable.
- `min()`, `max()`: Returns the smallest or largest item.
- `abs()`: Returns the absolute value.
- `round()`: Rounds a number.
- `enumerate()`: Adds a counter to an iterable.

[Back to Top](#table-of-contents)

---

## 19. Debugging and Testing

### Debugging with `print()` Statements

- Simple but effective for small scripts.

### Using the `logging` Module

```python
import logging

logging.basicConfig(level=logging.DEBUG)
logging.debug("This is a debug message")
```

### Using the `pdb` Module

- Python's built-in debugger.

**Starting the Debugger:**

```python
import pdb
pdb.set_trace()
```

### Unit Testing with `unittest`

**Example Test Case:**

```python
import unittest

class TestMath(unittest.TestCase):
    def test_addition(self):
        self.assertEqual(1 + 1, 2)

if __name__ == '__main__':
    unittest.main()
```

### DocTests

- Write tests in docstrings.

```python
def add(a, b):
    """
    Adds two numbers.

    >>> add(2, 3)
    5
    """
    return a + b

if __name__ == "__main__":
    import doctest
    doctest.testmod()
```

[Back to Top](#table-of-contents)

---

## 20. Useful Resources

- **Official Python Documentation:** [https://docs.python.org/3/](https://docs.python.org/3/)
- **Learn Python:** [https://www.learnpython.org/](https://www.learnpython.org/)
- **PyPI - Python Package Index:** [https://pypi.org/](https://pypi.org/)
- **Real Python:** [https://realpython.com/](https://realpython.com/)
- **Python Tutor (Visualize Code):** [http://pythontutor.com/](http://pythontutor.com/)
- **Stack Overflow:** [https://stackoverflow.com/](https://stackoverflow.com/)
- **Python Package 'this':** Open a Python shell and type `import this` to read "The Zen of Python" by Tim Peters.

[Back to Top](#table-of-contents)
