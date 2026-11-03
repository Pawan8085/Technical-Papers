
# Python PEP 8 Style Guide

## What is PEP 8?

- PEP 8 stands for Python Enhancement Proposal 8.
- It is the official style guide for writing Python code.
- It defines conventions for formatting and naming Python code.
- It helps make code readable, consistent, and easy to maintain.

##  Why Do We Need PEP 8?

1. **Readability:** Makes code easier to understand.
2. **Consistency:** Developers follow the same coding style.
3. **Maintainability:** Makes code easier to modify and debug.
4. **Team Collaboration:** Keeps code formatting consistent across a team.

## Important PEP 8 Guidelines

### 1. Indentation

- Use 4 spaces for each indentation level.
- Avoid mixing tabs and spaces.

```python
def calculate_sum():
    first_number = 10
    second_number = 20

    return first_number + second_number
```

### 2. Line Length

- Keep lines limited to 79 characters.
- For comments and docstrings, the recommended limit is 72 characters.

```python
# Good
total_amount = first_number + second_number

# Break long expressions into multiple lines
total_amount = (
    first_number
    + second_number
    + third_number
)
```

### 3. Naming Conventions

| Element | Naming Convention | Example |
|---|---|---|
| Variable | snake_case | `user_name` |
| Function | snake_case | `calculate_total()` |
| Class | PascalCase | `StudentDetails` |
| Constant | UPPER_CASE | `MAX_LIMIT` |
| Module | lowercase | `student.py` |
| Package | lowercase | `mypackage` |

```python
# Variables
user_name = "Pawan"

# Function
def calculate_total():
    pass

# Class
class StudentDetails:
    pass

# Constant
MAX_LIMIT = 100
```

### 4. Blank Lines

- Use two blank lines between top-level functions and classes.
- Use one blank line between methods inside a class.
- Use blank lines to separate logical sections of code.

```python
import math


def calculate_area(radius):
    return math.pi * radius * radius


def calculate_perimeter(radius):
    return 2 * math.pi * radius
```

### 5. Imports

- Imports should generally be placed at the top of the file.
- Write one import per line.
- Group imports in this order:
  1. Standard library imports
  2. Third-party imports
  3. Local application imports

```python
# Standard library
import os
import sys

# Third-party
import requests
import pandas

# Local application
from mypackage import utils
```

### 6. Spaces Around Operators

Use spaces around operators.

```python
# Good
total = first_number + second_number

# Avoid
total=first_number+second_number
```

### 7. Spaces After Commas

Use one space after commas.

```python
# Good
numbers = [10, 20, 30]

# Avoid
numbers = [10,20,30]
```

### 8. Avoid Unnecessary Spaces

Avoid unnecessary spaces inside brackets and parentheses.

```python
# Good
numbers = [10, 20, 30]
student = {"name": "Pawan"}

# Avoid
numbers = [ 10, 20, 30 ]
student = { "name": "Pawan" }
```

### 9. Comments

- Write comments that explain why something is done.
- Keep comments clear and meaningful.
- Use complete sentences where appropriate.

```python
# Good: Explain why we skip empty registration dates.
if not registration_date:
    continue
```

### 10. Docstrings

Use docstrings to describe modules, classes, and functions.

```python
def calculate_area(radius):
    """Calculate the area of a circle."""
    return 3.14 * radius * radius
```

### 11. Avoid Comparing Boolean Values

```python
# Good
if is_active:
    print("Active")

# Avoid
if is_active == True:
    print("Active")
```

### 12. Compare with None

Use `is` or `is not` when comparing with `None`.

```python
# Good
if user is None:
    print("User not found")

# Avoid
if user == None:
    print("User not found")
```

### 13. Use Meaningful Variable Names

Choose names that explain what the variable stores.

```python
# Good
total_runs = 250
player_name = "Virat"

# Avoid
x = 250
p = "Virat"
```

---

##  Useful PEP 8 Tools

### 1. Flake8

Flake8 checks Python code for style violations and common errors.

Install:

```bash
pip install flake8
```

Check a Python file:

```bash
flake8 main.py
```

Check an entire project:

```bash
flake8 .
```

### 2. Pylint

Pylint checks code quality and reports possible errors, style issues, and other improvements.

Install:

```bash
pip install pylint
```

Check a Python file:

```bash
pylint main.py
```

### 3. Black

Black automatically formats Python code.

Install:

```bash
pip install black
```

Format a Python file:

```bash
black main.py
```

Format the entire project:

```bash
black .
```

---

## Quick Revision

| Rule | Convention |
|---|---|
| Indentation | 4 spaces |
| Maximum line length | 79 characters |
| Comment/docstring line length | 72 characters |
| Variables | `snake_case` |
| Functions | `snake_case` |
| Classes | `PascalCase` |
| Constants | `UPPER_CASE` |
| Top-level functions/classes | Two blank lines |
| Methods inside classes | One blank line |
| Imports | At the top of the file |
| Spaces around operators | One space |
| Comparison with None | `is` / `is not` |

