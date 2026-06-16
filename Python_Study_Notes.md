# 🐍 Python Study Notes — Complete Guide
> Based on TutorialsPoint Python Tutorial | Written in simple, easy-to-understand language

---

## Table of Contents
1. [Introduction](#1-introduction)
2. [Basic Syntax & Variables](#2-basic-syntax--variables)
3. [Data Types](#3-data-types)
4. [Operators](#4-operators)
5. [Control Flow (if/elif/else)](#5-control-flow)
6. [Loops](#6-loops)
7. [Functions](#7-functions)
8. [Strings](#8-strings)
9. [Lists](#9-lists)
10. [Tuples](#10-tuples)
11. [Sets](#11-sets)
12. [Dictionaries](#12-dictionaries)
13. [File Handling](#13-file-handling)
14. [Object-Oriented Programming (OOP)](#14-object-oriented-programming-oop)
15. [Exception Handling](#15-exception-handling)
16. [Advanced Topics](#16-advanced-topics)
17. [Useful Built-in Functions](#17-useful-built-in-functions)
18. [Practice Problems](#18-practice-problems)

---

## 1. Introduction

### What is Python?
Python is a **high-level, interpreted** programming language. "High-level" means it's close to human language. "Interpreted" means code runs line by line without needing to compile first.

- Created by **Guido van Rossum** in 1991
- Current stable version: **Python 3.13**
- Used in: AI, Machine Learning, Web Development, Data Science, Automation

### Why Python?
- Free and open source
- Easy to read and write (like English)
- Massive library support (NumPy, Pandas, Django, etc.)
- Used by Google, NASA, Netflix, Instagram, Uber

### Your First Python Program
```python
# This is a comment — Python ignores it
print("Hello, World!")   # Output: Hello, World!

# Getting user input
name = input("Enter your name: ")
print("Hello,", name)
```

---

## 2. Basic Syntax & Variables

### Indentation — Python's Most Important Rule
Unlike other languages that use `{ }`, Python uses **indentation (spaces)** to define code blocks. Always use **4 spaces**.

```python
if 5 > 3:
    print("Five is greater")   # 4 spaces — inside the block
    print("Still inside")
print("Outside the block")     # No indent — outside
```

> ⚠️ Mixing tabs and spaces causes errors. Always use spaces.

### Variables
A variable is a **labelled container** for storing data. No need to declare type — just assign.

```python
name = "Alice"       # string
age = 25             # integer
height = 5.6         # float
is_student = True    # boolean

# Multiple assignment at once
x, y, z = 1, 2, 3

# Same value to multiple variables
a = b = c = 0

# Check type
print(type(name))   # <class 'str'>
```

### Variable Naming Rules
- Must start with a letter or underscore (`_`)
- Cannot start with a number
- Can contain letters, numbers, and underscores
- Case-sensitive (`age` and `Age` are different)
- Cannot use Python keywords (`if`, `for`, `while`, etc.)

```python
# Valid names
my_name = "Alice"
_score = 99
userName = "Bob"    # camelCase (allowed but not preferred)
user_name = "Bob"   # snake_case (Python standard)

# Invalid names
2name = "X"    # ❌ starts with number
my-name = "X"  # ❌ hyphen not allowed
```

### Comments
```python
# Single-line comment

"""
Multi-line comment
(technically a docstring, but works as comment)
"""
```

---

## 3. Data Types

### Core Data Types

| Type | Example | Description |
|------|---------|-------------|
| `int` | `42`, `-7`, `0` | Whole numbers |
| `float` | `3.14`, `-0.5` | Decimal numbers |
| `str` | `"hello"`, `'world'` | Text |
| `bool` | `True`, `False` | Yes/No values |
| `list` | `[1, 2, 3]` | Ordered, changeable |
| `tuple` | `(1, 2, 3)` | Ordered, fixed |
| `dict` | `{"a": 1}` | Key-value pairs |
| `set` | `{1, 2, 3}` | Unique unordered values |
| `NoneType` | `None` | Represents "nothing" |

### Type Conversion (Casting)
```python
# Convert between types
x = int("10")       # string → int → 10
y = float(5)        # int → float → 5.0
z = str(42)         # int → string → "42"
b = bool(0)         # int → bool → False (0 is False, anything else is True)
nums = list((1,2,3)) # tuple → list

# Check the type
print(type(x))      # <class 'int'>
print(isinstance(x, int))  # True
```

### Truthy and Falsy Values
```python
# These are all False in a boolean context:
bool(0)       # False
bool("")      # False (empty string)
bool([])      # False (empty list)
bool(None)    # False
bool({})      # False (empty dict)

# Everything else is True
bool(1)       # True
bool("hi")    # True
bool([1,2])   # True
```

---

## 4. Operators

### Arithmetic Operators
```python
a, b = 10, 3

print(a + b)   # 13   → Addition
print(a - b)   # 7    → Subtraction
print(a * b)   # 30   → Multiplication
print(a / b)   # 3.33 → Division (always returns float)
print(a // b)  # 3    → Floor division (drops decimal)
print(a % b)   # 1    → Modulus (remainder)
print(a ** b)  # 1000 → Exponentiation (10³)
```

### Comparison Operators
```python
x = 5
print(x == 5)   # True  → Equal to
print(x != 3)   # True  → Not equal to
print(x > 3)    # True  → Greater than
print(x < 10)   # True  → Less than
print(x >= 5)   # True  → Greater than or equal
print(x <= 4)   # False → Less than or equal
```

### Logical Operators
```python
print(True and False)   # False → Both must be True
print(True or False)    # True  → At least one must be True
print(not True)         # False → Reverses the boolean

# Real example
age = 25
has_id = True
can_enter = age >= 18 and has_id   # True
```

### Assignment Operators
```python
x = 10
x += 5    # x = x + 5  → 15
x -= 3    # x = x - 3  → 12
x *= 2    # x = x * 2  → 24
x /= 4    # x = x / 4  → 6.0
x //= 2   # x = x // 2 → 3.0
x **= 2   # x = x ** 2 → 9.0
x %= 4    # x = x % 4  → 1.0
```

### Membership & Identity Operators
```python
fruits = ["apple", "banana", "mango"]

# Membership operators
print("apple" in fruits)     # True
print("grape" not in fruits) # True

# Identity operators (checks if same object in memory)
a = [1, 2, 3]
b = a           # b points to same object
c = [1, 2, 3]   # c is a different object

print(a is b)   # True  → same object
print(a is c)   # False → same value, different object
print(a == c)   # True  → same value
```

---

## 5. Control Flow

### if / elif / else
Think of it as: "IF this is true, do X. ELSE IF that's true, do Y. OTHERWISE, do Z."

```python
marks = 75

if marks >= 90:
    print("Grade: A")
elif marks >= 75:
    print("Grade: B")       # This will print
elif marks >= 60:
    print("Grade: C")
else:
    print("Grade: F")
```

### Nested if
```python
age = 20
has_ticket = True

if age >= 18:
    if has_ticket:
        print("You can enter!")
    else:
        print("Please buy a ticket.")
else:
    print("Must be 18+ to enter.")
```

### Shorthand (Ternary Operator)
One-line if-else for simple conditions:
```python
# Syntax: value_if_true if condition else value_if_false
result = "Pass" if marks >= 40 else "Fail"
print(result)   # Pass

# Equivalent to:
if marks >= 40:
    result = "Pass"
else:
    result = "Fail"
```

### match-case Statement (Python 3.10+)
Like a cleaner version of multiple if-elif chains:
```python
day = "Monday"

match day:
    case "Monday":
        print("Start of work week")
    case "Friday":
        print("Weekend soon!")
    case "Saturday" | "Sunday":  # Multiple values
        print("Weekend!")
    case _:                      # Default (like else)
        print("Midweek")
```

---

## 6. Loops

### for Loop — Use when you know how many times
```python
# Loop over a range
for i in range(5):           # 0, 1, 2, 3, 4
    print(i)

for i in range(2, 10, 2):   # start=2, stop=10, step=2 → 2,4,6,8
    print(i)

# Loop over a list
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)

# Loop with index using enumerate
for index, fruit in enumerate(fruits):
    print(index, fruit)
# 0 apple
# 1 banana
# 2 mango

# Loop over string
for char in "Hello":
    print(char)   # H, e, l, l, o
```

### while Loop — Use when you don't know how many times
```python
count = 0
while count < 5:
    print(count)
    count += 1    # Always update the condition variable!
# 0, 1, 2, 3, 4

# while with user input
while True:
    answer = input("Type 'quit' to stop: ")
    if answer == "quit":
        break
    print("You typed:", answer)
```

### break, continue, pass
```python
# break → Stop the loop completely
for i in range(10):
    if i == 5:
        break         # Loop stops at 5
    print(i)          # Prints 0, 1, 2, 3, 4

# continue → Skip this iteration, continue to next
for i in range(10):
    if i % 2 == 0:
        continue      # Skip even numbers
    print(i)          # Prints 1, 3, 5, 7, 9

# pass → Do nothing (placeholder for empty block)
for i in range(5):
    pass    # Loop runs but nothing happens
```

### Nested Loops
```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(i * j, end=" ")
    print()   # New line after each row
# 1 2 3
# 2 4 6
# 3 6 9
```

### for-else and while-else
The `else` block runs only if the loop completed WITHOUT hitting a `break`:
```python
for i in range(5):
    if i == 10:      # Never true
        break
else:
    print("Loop finished normally")   # This prints

# Useful for search:
numbers = [1, 3, 5, 7, 9]
target = 4
for num in numbers:
    if num == target:
        print("Found!")
        break
else:
    print("Not found")   # Prints because 4 is not in list
```

---

## 7. Functions

### Defining and Calling
```python
def greet(name):
    """Say hello to someone."""   # Docstring — explains the function
    print(f"Hello, {name}!")

greet("Alice")    # → Hello, Alice!
greet("Bob")      # → Hello, Bob!
```

### Return Values
```python
def add(a, b):
    return a + b

result = add(3, 5)
print(result)   # 8

# Return multiple values
def min_max(numbers):
    return min(numbers), max(numbers)

lo, hi = min_max([3, 1, 4, 1, 5, 9])
print(lo, hi)   # 1 9
```

### Default Arguments
```python
def power(base, exponent=2):   # exponent defaults to 2
    return base ** exponent

print(power(3))        # 9 (3²)
print(power(2, 10))    # 1024
```

### Keyword Arguments
```python
def describe(name, age, city):
    print(f"{name}, {age}, from {city}")

describe("Alice", 25, "Mumbai")                  # Positional
describe(age=25, city="Mumbai", name="Alice")    # Keyword (any order!)
describe("Alice", city="Mumbai", age=25)         # Mixed
```

### Arbitrary Arguments (*args and **kwargs)
```python
# *args — accepts any number of positional arguments (as tuple)
def total(*numbers):
    return sum(numbers)

print(total(1, 2, 3))        # 6
print(total(1, 2, 3, 4, 5))  # 15

# **kwargs — accepts any number of keyword arguments (as dict)
def show_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

show_info(name="Alice", age=25, city="Mumbai")
```

### Lambda (Anonymous Functions)
Short one-line functions without a name:
```python
# Regular function
def square(x):
    return x ** 2

# Lambda equivalent
square = lambda x: x ** 2
print(square(5))   # 25

# Commonly used with sorted(), map(), filter()
names = ["Charlie", "Alice", "Bob"]
names.sort(key=lambda n: len(n))    # Sort by length
print(names)   # ['Bob', 'Alice', 'Charlie']

numbers = [1, 2, 3, 4, 5, 6]
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)   # [2, 4, 6]

doubled = list(map(lambda x: x * 2, numbers))
print(doubled) # [2, 4, 6, 8, 10, 12]
```

### Variable Scope (Local vs Global)
```python
x = 10   # Global variable

def my_func():
    y = 20          # Local variable (only inside function)
    print(x)        # Can access global x → 10
    print(y)        # Local y → 20

my_func()
print(x)    # 10 ✓
# print(y)  # ❌ Error! y doesn't exist outside

# Modify global inside function
count = 0

def increment():
    global count    # Tell Python to use global count
    count += 1

increment()
print(count)   # 1
```

---

## 8. Strings

### Creating Strings
```python
s1 = 'Single quotes'
s2 = "Double quotes"
s3 = """Multi-line
string using triple quotes"""

# Raw strings (ignore escape characters)
path = r"C:\Users\Alice\Desktop"   # r prefix
```

### String Indexing and Slicing
```python
s = "Hello, World!"
#    0123456789...

print(s[0])       # H   → first character
print(s[-1])      # !   → last character
print(s[0:5])     # Hello → from 0 up to (not including) 5
print(s[7:])      # World! → from 7 to end
print(s[:5])      # Hello → from start to 5
print(s[::2])     # Hlo ol! → every 2nd character
print(s[::-1])    # !dlroW ,olleH → reversed string
```

### Common String Methods
```python
s = "  Hello, World!  "

print(s.strip())              # "Hello, World!"  → remove whitespace
print(s.lstrip())             # "Hello, World!  " → left only
print(s.rstrip())             # "  Hello, World!" → right only
print(s.upper())              # "  HELLO, WORLD!  "
print(s.lower())              # "  hello, world!  "
print(s.title())              # "  Hello, World!  " (capitalize each word)
print(s.replace("World", "Python"))  # "  Hello, Python!  "
print(s.split(","))           # ['  Hello', ' World!  ']
print(",".join(["a","b","c"])) # "a,b,c"
print(s.find("World"))        # 9 → index of "World" (-1 if not found)
print(s.count("l"))           # 3 → count occurrences
print(s.startswith("  Hello")) # True
print(s.endswith("!  "))      # True
print("hello".center(11, "*"))  # "***hello***"
```

### String Formatting
```python
name = "Alice"
age = 25

# f-strings (Best — Python 3.6+)
print(f"Name: {name}, Age: {age}")
print(f"Next year: {age + 1}")
print(f"Pi is approximately {3.14159:.2f}")  # 2 decimal places

# .format() method
print("Name: {}, Age: {}".format(name, age))
print("Name: {n}, Age: {a}".format(n=name, a=age))

# % operator (old style)
print("Name: %s, Age: %d" % (name, age))
```

### Escape Characters
```python
print("He said \"Hello\"")   # He said "Hello"
print("Line1\nLine2")         # Newline
print("Tab\there")            # Tab
print("Backslash: \\")        # Backslash
print("C:\\Users\\Alice")     # Windows path
```

---

## 9. Lists

Lists are **ordered, changeable** collections. They can hold mixed data types.

### Creating Lists
```python
fruits = ["apple", "banana", "mango"]
mixed = [1, "hello", 3.14, True]    # Mixed types allowed
nested = [[1, 2], [3, 4], [5, 6]]   # Lists inside lists
empty = []
```

### Accessing Items
```python
fruits = ["apple", "banana", "mango", "orange", "grape"]

print(fruits[0])      # apple (first)
print(fruits[-1])     # grape (last)
print(fruits[1:3])    # ['banana', 'mango']
print(fruits[:3])     # ['apple', 'banana', 'mango']
print(fruits[2:])     # ['mango', 'orange', 'grape']
print(fruits[::2])    # ['apple', 'mango', 'grape'] (every 2nd)
```

### Modifying Lists
```python
fruits = ["apple", "banana", "mango"]

# Add items
fruits.append("grape")         # Add to end
fruits.insert(1, "kiwi")       # Insert at index 1
fruits.extend(["pear", "fig"]) # Add multiple items

# Remove items
fruits.remove("banana")   # Remove by value (first occurrence)
fruits.pop()              # Remove and return last item
fruits.pop(0)             # Remove and return item at index 0
del fruits[1]             # Delete by index
fruits.clear()            # Remove all items

# Modify
fruits[0] = "pineapple"  # Change first item
```

### List Operations
```python
nums = [3, 1, 4, 1, 5, 9, 2, 6]

print(len(nums))        # 8 → length
print(sum(nums))        # 31 → sum
print(min(nums))        # 1 → minimum
print(max(nums))        # 9 → maximum
print(nums.count(1))    # 2 → count occurrences of 1
print(nums.index(5))    # 4 → index of first 5

nums.sort()             # Sort in place (ascending)
nums.sort(reverse=True) # Sort descending
nums.reverse()          # Reverse in place

sorted_copy = sorted(nums)   # Returns sorted copy, original unchanged
```

### List Comprehension — Pythonic Way
```python
# Normal way
squares = []
for x in range(6):
    squares.append(x ** 2)

# Pythonic way — same result!
squares = [x ** 2 for x in range(6)]
# [0, 1, 4, 9, 16, 25]

# With condition
evens = [x for x in range(20) if x % 2 == 0]
# [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

# Nested list comprehension
matrix = [[i * j for j in range(1, 4)] for i in range(1, 4)]
# [[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

### Copying Lists
```python
original = [1, 2, 3]

# Wrong way — both point to same list!
wrong_copy = original
wrong_copy.append(4)
print(original)    # [1, 2, 3, 4] ← original changed!

# Correct ways
copy1 = original.copy()
copy2 = list(original)
copy3 = original[:]       # Slicing
```

---

## 10. Tuples

Tuples are **ordered but immutable** (cannot be changed after creation). Think: locked list.

```python
# Creating tuples
point = (3, 7)
colors = ("red", "green", "blue")
single = (42,)        # Single item MUST have comma!
empty = ()

# Access (same as list)
print(colors[0])      # red
print(colors[-1])     # blue
print(colors[1:])     # ('green', 'blue')

# Unpacking
x, y = point
print(x, y)           # 3 7

r, g, b = colors
print(r, g, b)        # red green blue

# Extended unpacking
first, *rest = (1, 2, 3, 4, 5)
print(first)   # 1
print(rest)    # [2, 3, 4, 5]

# Swap variables using tuples
a, b = 5, 10
a, b = b, a           # Elegant swap!
print(a, b)   # 10 5

# Tuple methods (limited because immutable)
t = (1, 2, 2, 3, 2)
print(t.count(2))   # 3 → count occurrences
print(t.index(3))   # 3 → index of first 3
```

### When to Use Tuple vs List?
- Use **tuple** for fixed data: coordinates, RGB colours, days of week, database records
- Use **list** for data that changes: shopping cart, user inputs, scores

---

## 11. Sets

Sets are **unordered collections of unique items** — no duplicates!

```python
# Creating sets
s = {1, 2, 3, 2, 1}
print(s)         # {1, 2, 3} — duplicates removed automatically

empty_set = set()   # Note: {} creates empty dict, not set!

# Add and remove
s.add(4)
s.discard(2)    # Remove safely (no error if not found)
s.remove(1)     # Remove (raises error if not found)

# Membership check (very fast!)
print(3 in s)    # True
print(5 in s)    # False

# Remove duplicates from a list
nums = [1, 2, 2, 3, 3, 3, 4]
unique = list(set(nums))   # [1, 2, 3, 4]
```

### Set Operations (Math!)
```python
a = {1, 2, 3, 4, 5}
b = {4, 5, 6, 7, 8}

print(a | b)          # Union: {1,2,3,4,5,6,7,8}
print(a.union(b))     # Same as above

print(a & b)                   # Intersection: {4, 5}
print(a.intersection(b))       # Same as above

print(a - b)                   # Difference: {1, 2, 3} (in a but not b)
print(a.difference(b))         # Same as above

print(a ^ b)                           # Symmetric diff: {1,2,3,6,7,8}
print(a.symmetric_difference(b))       # Same as above

# Subset and superset
print({1, 2}.issubset(a))     # True (1,2 are all in a)
print(a.issuperset({1, 2}))   # True
```

---

## 12. Dictionaries

Dictionaries store **key-value pairs** — like a real dictionary with words (keys) and definitions (values).

### Creating and Accessing
```python
student = {
    "name": "Alice",
    "age": 20,
    "marks": [85, 90, 78],
    "city": "Mumbai"
}

# Access by key
print(student["name"])              # Alice
print(student.get("age"))          # 20
print(student.get("grade", "N/A")) # N/A (default if key missing, no error)
```

### Modifying Dictionaries
```python
# Add or update
student["age"] = 21           # Update existing key
student["grade"] = "A"        # Add new key

# Remove
del student["city"]           # Delete key-value pair
removed = student.pop("age")  # Remove and return value
student.popitem()             # Remove last inserted item (Python 3.7+)
student.clear()               # Remove all items

# Update from another dict
student.update({"age": 21, "score": 95})
```

### Looping Through Dictionaries
```python
student = {"name": "Alice", "age": 20, "city": "Mumbai"}

# Loop over keys
for key in student:
    print(key)

# Loop over values
for value in student.values():
    print(value)

# Loop over key-value pairs
for key, value in student.items():
    print(f"{key}: {value}")

# Get all keys and values
print(student.keys())    # dict_keys(['name', 'age', 'city'])
print(student.values())  # dict_values(['Alice', 20, 'Mumbai'])
```

### Nested Dictionaries
```python
school = {
    "student1": {"name": "Alice", "grade": "A"},
    "student2": {"name": "Bob",   "grade": "B"},
}

print(school["student1"]["name"])   # Alice
print(school["student2"]["grade"])  # B

# Loop through nested dict
for id, info in school.items():
    print(f"{id}: {info['name']} → {info['grade']}")
```

### Dictionary Comprehension
```python
# Create dict from two lists
keys = ["a", "b", "c"]
values = [1, 2, 3]
d = {k: v for k, v in zip(keys, values)}
# {'a': 1, 'b': 2, 'c': 3}

# Squares dict
squares = {x: x**2 for x in range(6)}
# {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

## 13. File Handling

### Writing to a File
```python
# 'w' = write (creates file or overwrites existing)
with open("notes.txt", "w") as f:
    f.write("Hello, Python!\n")
    f.write("Learning file handling.\n")

# 'a' = append (adds to end of existing file)
with open("notes.txt", "a") as f:
    f.write("New line added!\n")
```

### Reading a File
```python
# Read entire file
with open("notes.txt", "r") as f:
    content = f.read()
    print(content)

# Read line by line (memory-efficient for large files)
with open("notes.txt", "r") as f:
    for line in f:
        print(line.strip())   # .strip() removes newline

# Read all lines into a list
with open("notes.txt") as f:
    lines = f.readlines()   # ['Hello, Python!\n', ...]
```

### File Modes Summary
| Mode | Meaning |
|------|---------|
| `'r'` | Read (default). Error if file doesn't exist |
| `'w'` | Write. Creates file. Overwrites existing content |
| `'a'` | Append. Creates file. Adds to existing content |
| `'x'` | Create. Error if file already exists |
| `'r+'` | Read and write |
| `'b'` | Binary mode (e.g., `'rb'`, `'wb'`) |

### Handling File Errors
```python
try:
    with open("missing.txt", "r") as f:
        print(f.read())
except FileNotFoundError:
    print("File not found!")
```

---

## 14. Object-Oriented Programming (OOP)

OOP is a way to model real-world things in code using **classes** and **objects**.

- **Class** = Blueprint (e.g., Car design)
- **Object** = Real thing made from blueprint (e.g., your car)

### Creating a Class
```python
class Dog:
    # Class variable (shared by all objects)
    species = "Canis lupus familiaris"

    # Constructor — runs when object is created
    def __init__(self, name, age):
        self.name = name    # Instance variable
        self.age = age

    # Method (function inside class)
    def bark(self):
        print(f"{self.name} says: Woof!")

    def info(self):
        return f"Name: {self.name}, Age: {self.age}"

    # String representation
    def __str__(self):
        return f"Dog({self.name}, {self.age})"

# Create objects
dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

dog1.bark()             # Buddy says: Woof!
print(dog2.info())      # Name: Max, Age: 5
print(dog1.species)     # Canis lupus familiaris
print(dog1)             # Dog(Buddy, 3)
```

### Inheritance
```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print("Some sound")

    def eat(self):
        print(f"{self.name} is eating")

class Dog(Animal):   # Dog inherits from Animal
    def speak(self):  # Override parent method
        print(f"{self.name} says: Woof!")

class Cat(Animal):
    def speak(self):
        print(f"{self.name} says: Meow!")

d = Dog("Buddy")
c = Cat("Whiskers")

d.speak()    # Buddy says: Woof!
c.speak()    # Whiskers says: Meow!
d.eat()      # Buddy is eating (inherited from Animal)
```

### super() — Call Parent's Method
```python
class Animal:
    def __init__(self, name):
        self.name = name

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)   # Call Animal's __init__
        self.breed = breed

d = Dog("Buddy", "Labrador")
print(d.name, d.breed)   # Buddy Labrador
```

### Encapsulation (Private Attributes)
```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance    # Private (double underscore)

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def get_balance(self):
        return self.__balance

account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())   # 1500
# print(account.__balance)     # ❌ AttributeError!
```

### Key OOP Concepts at a Glance
| Concept | Meaning |
|---------|---------|
| **Encapsulation** | Hiding internal data using private attributes |
| **Inheritance** | A class can reuse code from a parent class |
| **Polymorphism** | Different classes can have same method name but different behaviour |
| **Abstraction** | Hiding complex implementation, exposing simple interface |

---

## 15. Exception Handling

Errors (exceptions) are normal. Handle them gracefully so your program doesn't crash.

### try / except / else / finally
```python
try:
    # Code that might cause an error
    num = int(input("Enter a number: "))
    result = 100 / num

except ValueError:
    print("Please enter a valid number!")

except ZeroDivisionError:
    print("Cannot divide by zero!")

except Exception as e:
    print(f"Something went wrong: {e}")   # Catch any other error

else:
    print(f"Result: {result}")  # Runs ONLY if no error occurred

finally:
    print("This ALWAYS runs, error or not!")
```

### Common Exceptions
| Exception | When it happens |
|-----------|----------------|
| `ValueError` | Wrong value: `int("abc")` |
| `TypeError` | Wrong type: `"2" + 2` |
| `ZeroDivisionError` | Division by zero |
| `IndexError` | `list[99]` — out of range |
| `KeyError` | `dict["missing_key"]` |
| `FileNotFoundError` | File doesn't exist |
| `NameError` | Variable not defined |
| `AttributeError` | Object has no such attribute |
| `ImportError` | Module not found |
| `RecursionError` | Too many nested function calls |

### Raising Exceptions
```python
def divide(a, b):
    if b == 0:
        raise ValueError("Divider cannot be zero!")
    return a / b

try:
    print(divide(10, 0))
except ValueError as e:
    print(f"Error: {e}")   # Error: Divider cannot be zero!
```

### Custom Exceptions
```python
class AgeError(Exception):
    """Raised when age is invalid"""
    pass

def set_age(age):
    if age < 0 or age > 150:
        raise AgeError(f"Invalid age: {age}")
    return age

try:
    set_age(-5)
except AgeError as e:
    print(f"Custom Error: {e}")
```

---

## 16. Advanced Topics

### List/Dict/Set Comprehensions
```python
# List comprehension
squares = [x**2 for x in range(10)]

# With condition
evens = [x for x in range(20) if x % 2 == 0]

# Dict comprehension
word_lengths = {word: len(word) for word in ["hi", "hello", "hey"]}

# Set comprehension
unique_squares = {x**2 for x in [-2, -1, 0, 1, 2]}  # {0, 1, 4}
```

### Lambda Functions
```python
# Short anonymous functions
double = lambda x: x * 2
add = lambda x, y: x + y

# Commonly used with sorted, map, filter
nums = [3, 1, 4, 1, 5, 9]
print(sorted(nums, reverse=True))              # [9, 5, 4, 3, 1, 1]
print(list(map(lambda x: x**2, nums)))         # [9, 1, 16, 1, 25, 81]
print(list(filter(lambda x: x > 3, nums)))     # [4, 5, 9]
```

### Decorators
A decorator adds behaviour to a function without modifying it:
```python
def timer(func):
    import time
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} took {end - start:.4f}s")
        return result
    return wrapper

@timer    # Same as: my_function = timer(my_function)
def my_function():
    total = sum(range(1000000))
    return total

my_function()   # Prints time taken
```

### Generators — Memory-Efficient Iteration
```python
# Regular function builds entire list in memory
def make_squares_list(n):
    return [x**2 for x in range(n)]

# Generator yields one value at a time — very memory efficient!
def make_squares_gen(n):
    for x in range(n):
        yield x**2

gen = make_squares_gen(5)
print(next(gen))   # 0
print(next(gen))   # 1

for sq in make_squares_gen(5):
    print(sq)       # 0, 1, 4, 9, 16

# Generator expression (like list comp with () instead of [])
gen = (x**2 for x in range(5))
```

### Closures
A function that remembers its outer scope:
```python
def counter(start=0):
    count = start

    def increment():
        nonlocal count
        count += 1
        return count

    return increment

c = counter(10)
print(c())   # 11
print(c())   # 12
print(c())   # 13
```

### Recursion
A function that calls itself:
```python
def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))   # 120 (5 × 4 × 3 × 2 × 1)

# Fibonacci sequence
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print([fibonacci(i) for i in range(8)])
# [0, 1, 1, 2, 3, 5, 8, 13]
```

### Modules and Imports
```python
# Import standard library modules
import math
import random
import datetime

print(math.sqrt(16))         # 4.0
print(math.pi)               # 3.14159...
print(random.randint(1, 10)) # Random int 1-10
print(datetime.date.today()) # Today's date

# Import specific function
from math import sqrt, pi
print(sqrt(25))  # 5.0

# Import with alias
import numpy as np
import pandas as pd
```

---

## 17. Useful Built-in Functions

```python
# Type and conversion
type(x)          # Type of x
int(x)           # Convert to integer
float(x)         # Convert to float
str(x)           # Convert to string
bool(x)          # Convert to boolean
list(x)          # Convert to list
tuple(x)         # Convert to tuple
set(x)           # Convert to set

# Math
abs(-5)          # 5 → absolute value
round(3.7)       # 4 → round to nearest int
round(3.14159, 2) # 3.14 → round to 2 decimal places
pow(2, 10)       # 1024 → 2^10
min(3, 1, 4)     # 1
max(3, 1, 4)     # 4
sum([1,2,3])     # 6

# Sequences
len([1,2,3])          # 3
range(5)              # 0,1,2,3,4
range(2, 8, 2)        # 2,4,6
sorted([3,1,2])       # [1,2,3]
reversed([1,2,3])     # [3,2,1]
enumerate(["a","b"])  # (0,"a"), (1,"b")
zip([1,2],[3,4])      # (1,3), (2,4)

# Functional
map(func, iterable)      # Apply func to each item
filter(func, iterable)   # Keep items where func is True
any([False, True, False]) # True → at least one True
all([True, True, False])  # False → all must be True

# Input/Output
print("Hello")
x = input("Enter: ")

# Object info
dir(x)       # List all attributes/methods of x
help(str)    # Show documentation for str
id(x)        # Memory address of x
```

---

## 18. Practice Problems

### Beginner Level

**Problem 1: Odd or Even**
```python
num = int(input("Enter a number: "))
if num % 2 == 0:
    print(f"{num} is Even")
else:
    print(f"{num} is Odd")
```

**Problem 2: FizzBuzz**
```python
# Print 1-100. For multiples of 3 print "Fizz",
# for 5 print "Buzz", for both print "FizzBuzz"
for i in range(1, 101):
    if i % 15 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```

**Problem 3: Sum of Digits**
```python
def sum_of_digits(n):
    return sum(int(d) for d in str(abs(n)))

print(sum_of_digits(1234))   # 10
```

**Problem 4: Simple Calculator**
```python
def calculate(a, op, b):
    if op == "+": return a + b
    elif op == "-": return a - b
    elif op == "*": return a * b
    elif op == "/": return a / b if b != 0 else "Error: Division by zero"
    else: return "Unknown operator"

print(calculate(10, "+", 5))   # 15
print(calculate(10, "/", 0))   # Error: Division by zero
```

---

### Intermediate Level

**Problem 5: Reverse a String**
```python
def reverse_string(s):
    return s[::-1]

# Without slicing:
def reverse_string_v2(s):
    result = ""
    for char in s:
        result = char + result
    return result

print(reverse_string("Hello"))    # olleH
print(reverse_string("Python"))   # nohtyP
```

**Problem 6: Count Word Frequency**
```python
def word_frequency(sentence):
    words = sentence.lower().split()
    freq = {}
    for word in words:
        freq[word] = freq.get(word, 0) + 1
    return freq

text = "the cat sat on the mat the cat"
print(word_frequency(text))
# {'the': 3, 'cat': 2, 'sat': 1, 'on': 1, 'mat': 1}
```

**Problem 7: Check Palindrome**
```python
def is_palindrome(s):
    s = s.lower().replace(" ", "")
    return s == s[::-1]

print(is_palindrome("racecar"))     # True
print(is_palindrome("A man a plan a canal Panama"))  # True
print(is_palindrome("hello"))       # False
```

**Problem 8: Find Second Largest**
```python
def second_largest(nums):
    unique = sorted(set(nums), reverse=True)
    return unique[1] if len(unique) >= 2 else None

print(second_largest([3, 1, 4, 1, 5, 9, 2, 6]))   # 6
```

---

### Advanced Level

**Problem 9: Timer Decorator**
```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        elapsed = time.time() - start
        print(f"{func.__name__} took {elapsed:.4f} seconds")
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(0.5)
    return "Done!"

print(slow_function())
# slow_function took 0.5002 seconds
# Done!
```

**Problem 10: Stack Implementation**
```python
class Stack:
    def __init__(self):
        self._data = []

    def push(self, item):
        self._data.append(item)

    def pop(self):
        if self.is_empty():
            raise IndexError("Stack is empty")
        return self._data.pop()

    def peek(self):
        if self.is_empty():
            raise IndexError("Stack is empty")
        return self._data[-1]

    def is_empty(self):
        return len(self._data) == 0

    def size(self):
        return len(self._data)

    def __str__(self):
        return str(self._data)

s = Stack()
s.push(1)
s.push(2)
s.push(3)
print(s.peek())   # 3
print(s.pop())    # 3
print(s)          # [1, 2]
```

**Problem 11: Fibonacci Generator**
```python
def fibonacci_gen():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

fib = fibonacci_gen()
first_10 = [next(fib) for _ in range(10)]
print(first_10)   # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

---

## Quick Reference Cheatsheet

```python
# ── TYPES ───────────────────────────────────────────
int, float, str, bool, list, tuple, dict, set, None

# ── PRINT & INPUT ────────────────────────────────────
print("text", end="\n")         # print with newline
print("a", "b", sep=", ")      # print with separator
name = input("Prompt: ")        # get user input

# ── CONDITIONALS ─────────────────────────────────────
if x > 0: ...
elif x == 0: ...
else: ...
result = "yes" if x else "no"   # ternary

# ── LOOPS ────────────────────────────────────────────
for i in range(start, stop, step): ...
for item in iterable: ...
while condition: ...
break / continue / pass

# ── FUNCTIONS ────────────────────────────────────────
def func(a, b=10, *args, **kwargs): return a + b
lambda x: x * 2

# ── STRING ───────────────────────────────────────────
s[0], s[-1], s[1:4], s[::-1]
f"{var:.2f}", s.upper(), s.split(), ",".join(list)

# ── LIST ─────────────────────────────────────────────
l.append(x), l.insert(i,x), l.remove(x), l.pop(i)
l.sort(), sorted(l), l.reverse(), l.copy()
[expr for x in l if cond]

# ── DICT ─────────────────────────────────────────────
d[k], d.get(k, default), d.keys(), d.values(), d.items()
{k: v for k, v in pairs}

# ── EXCEPTIONS ───────────────────────────────────────
try: ... except Error as e: ... else: ... finally: ...
raise ValueError("message")

# ── FILES ────────────────────────────────────────────
with open("f.txt", "r") as f: content = f.read()
with open("f.txt", "w") as f: f.write("text")

# ── CLASSES ──────────────────────────────────────────
class MyClass(Parent):
    def __init__(self, x): self.x = x
    def method(self): return self.x
```

---

*Happy Coding! 🐍 Practice every day — even 30 minutes makes a huge difference.*
