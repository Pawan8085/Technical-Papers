
# 🐍 Python General Cheat Sheet

## 🖨️ Basic Input and Output

```python
# Display output
print("Hello, World!")

# Print multiple values
print("Name:", "Pawan")

# Print without a newline
print("Hello", end=" ")
print("World")

# Take user input
name = input("Enter your name: ")

# Convert input to an integer
age = int(input("Enter your age: "))

# Convert input to a float
price = float(input("Enter price: "))
```

## 🔢 Variables and Data Types

```python
# Integer
age = 25

# Float
price = 99.99

# String
name = "Pawan"

# Boolean
is_active = True

# None
result = None

# Check data type
print(type(age))
print(type(name))

```

### Type Conversion

```python
# Integer to float
number = float(10)

# Float to integer
number = int(10.5)

# Integer to string
number = str(100)

# String to integer
number = int("100")

# String to float
number = float("10.5")
```

## ➕ Operators

### Arithmetic Operators

```python
a = 10
b = 3

print(a + b)   # Addition
print(a - b)   # Subtraction
print(a * b)   # Multiplication
print(a / b)   # Division
print(a // b)  # Floor division
print(a % b)   # Modulus
print(a ** b)  # Exponentiation
```

### Comparison Operators

```python
a == b   # Equal
a != b   # Not equal
a > b    # Greater than
a < b    # Less than
a >= b   # Greater than or equal
a <= b   # Less than or equal
```

### Logical Operators

```python
a and b  # True if both are True
a or b   # True if at least one is True
not a    # Reverses the boolean value
```

### Assignment Operators

```python
x = 10
x += 5
x -= 2
x *= 3
x /= 2
x //= 2
x %= 3
x **= 2
```

### Membership and Identity Operators

```python
# Membership
"a" in "apple"
"z" not in "apple"

# Identity
a is b
a is not b
```

##  🔀 Conditional Statements

```python
age = 20

if age >= 18:
    print("Adult")
elif age >= 13:
    print("Teenager")
else:
    print("Child")
```

### Nested if

```python
age = 25
has_id = True

if age >= 18:
    if has_id:
        print("Allowed")
    else:
        print("ID required")
else:
    print("Not allowed")
```

### Ternary Operator

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

##  🔁 Loops

### for Loop

```python
# Iterate over a string
for character in "Python":
    print(character)

# Using range()
for number in range(5):
    print(number)

# Specify start and stop
for number in range(1, 6):
    print(number)

# Specify step
for number in range(1, 10, 2):
    print(number)
```

### while Loop

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

### Loop Control Statements

```python
# break: Exit the loop
for number in range(10):
    if number == 5:
        break
    print(number)

# continue: Skip current iteration
for number in range(5):
    if number == 2:
        continue
    print(number)

```

##  🔧 Functions

```python
# Function without parameters
def greet():
    print("Hello!")

# Function with parameters
def greet(name):
    print(f"Hello, {name}!")

# Function with return value
def add(a, b):
    return a + b

# Default parameters
def greet(name="Guest"):
    print(f"Hello, {name}!")

# Keyword arguments
def introduce(name, age):
    print(name, age)

introduce(age=25, name="Pawan")

# Variable-length positional arguments
def add_numbers(*args):
    total = 0
    for number in args:
        total += number
    return total

# Variable-length keyword arguments
def display_info(**kwargs):
    print(kwargs)
```


### Scope

```python
# Global variable
name = "Pawan"

def greet():
    # Local variable
    message = "Hello"
    print(name)
    print(message)
```

##  📦 Modules and Imports

```python
# Import complete module
import math

# Import specific function
from math import sqrt

# Import with alias
import datetime as dt

# Import multiple functions
from math import ceil, floor
```

### Common Built-in Modules

```python
import math
import random
import datetime
import os
import sys
```

##  ⚠️ Exception Handling

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")

else:
    print("Result:", result)

finally:
    print("Execution completed.")
```

### Raise an Exception

```python
age = 15

if age < 18:
    raise ValueError("Age must be 18 or above")
```



## 🛠️ Useful Built-in Functions

```python
# Length
len("Python")

# Type
type(10)

# Convert to integer
int("10")

# Absolute value
abs(-10)

# Power
pow(2, 3)

# Minimum and maximum
min(10, 20, 30)
max(10, 20, 30)

# Sum
sum((10, 20, 30))

# Rounding
round(10.567, 2)

# Range
range(1, 5)

# Enumerate
enumerate("Python")

# Check conditions
all((True, True, True))
any((False, True, False))

# Sorted result
sorted((3, 1, 2))

# Help and documentation
help(print)
```

## 🧪 Debugging and Introspection

```python
# Display variable values
print(name)

# Inspect object type
type(name)

# Check available attributes and methods
dir(name)

# Get documentation
help(str)

# Debug using breakpoint
breakpoint()
```

##  🧹 Common Python Syntax

```python
# Single-line comment
# This is a comment

# Multi-line string / documentation
"""
This is a documentation string.
"""

# Multiple assignments
a, b = 10, 20

# Swap values
a, b = b, a

# Check whether a value is None
if result is None:
    print("No result")

# Main entry point
if __name__ == "__main__":
    print("Program started")
```
