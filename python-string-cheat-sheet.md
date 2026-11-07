
# 🐍 Python String Cheat Sheet

## What is a String?

- A string is a sequence of characters.
- Strings are immutable, meaning they cannot be changed.
- In Python, strings can be written inside single quotes, double quotes, or triple quotes.

```python
name = "Pawan"
message = 'Hello World'
description = """This is a
multi-line string."""

print(name)
print(message)
print(description)
```

---

## Creating Strings

```python
# Single quotes
name = 'Pawan'

# Double quotes
city = "Bangalore"

# Triple quotes
message = """Hello,
Welcome to Python."""

# String using str()
number = str(100)

print(type(name))
print(type(number))
```

---

## String Indexing
- Positive indexing starts from `0`.
- Negative indexing starts from `-1` (last character).

```python
text = "Python"

# Positive indexing
print(text[0])  # P
print(text[2])  # t

# Negative indexing
print(text[-1])  # n
print(text[-2])  # o
```

### Index Position

| Character | P | y | t | h | o | n |
|---|---|---|---|---|---|---|
| Positive index | 0 | 1 | 2 | 3 | 4 | 5 |
| Negative index | -6 | -5 | -4 | -3 | -2 | -1 |

---

## String Slicing

- Slicing is used to extract a part of a string.
- Syntax: `string[start:end:step]`
- The ending index is excluded.

```python
text = "Python Programming"

# Basic slicing
print(text[0:6])    # Python

# Starting index omitted
print(text[:6])     # Python

# Ending index omitted
print(text[7:])     # Programming

# Step
print(text[0:6:2])  # Pto

# Copy entire string
print(text[:])
```

---

## String Immutability

- Strings are immutable.
- We cannot modify individual characters after creating a string.

```python
text = "Python"

# Not allowed
# text[0] = "J"
```

---

## String Operators

| Operator | Purpose | Example |
|---|---|---|
| `*` | Repetition | `"Hi" * 3` |
| `in` | Checks presence | `"Py" in "Python"` |
| `not in` | Checks absence | `"Java" not in "Python"` |

```python
first = "Hello"
second = "World"



# Repetition
print("Python " * 3)

# Membership
print("Py" in "Python")
print("Java" not in "Python")
```

---

## String Formatting

### f-Strings

- Used to insert variables and expressions inside strings.
- Prefix the string with `f`.

```python
name = "Pawan"
age = 25

print(f"My name is {name} and I am {age} years old.")

# Expressions
print(f"Next year I will be {age + 1}.")
```

### `format()` Method

```python
name = "Pawan"
age = 25

message = "My name is {} and I am {} years old."

print(message.format(name, age))
```

### Positional Formatting

```python
message = "My name is {0} and I am {1} years old."

print(message.format("Pawan", 25))
```

### Named Formatting

```python
message = "My name is {name} and I am {age} years old."

print(message.format(name="Pawan", age=25))
```

---

## Common String Methods

### Case Conversion

| Method | Purpose | Example |
|---|---|---|
| `upper()` | Converts to uppercase | `"hello".upper()` |
| `lower()` | Converts to lowercase | `"HELLO".lower()` |
| `capitalize()` | Capitalizes first character | `"hello world".capitalize()` |
| `title()` | Capitalizes each word | `"hello world".title()` |
| `swapcase()` | Swaps uppercase and lowercase | `"Hello".swapcase()` |

```python
text = "hello WORLD"

print(text.upper()) # HELLO WORLD
print(text.lower()) # hello world
print(text.capitalize()) # Hello world
print(text.title()) # Hello World
print(text.swapcase()) # HELLO world
```

### Searching Methods

| Method | Purpose |
|---|---|
| `find()` | Returns the first index of a substring, or `-1` if not found |
| `rfind()` | Returns the last index of a substring, or `-1` if not found |
| `index()` | Returns the first index; raises `ValueError` if not found |
| `rindex()` | Returns the last index; raises `ValueError` if not found |
| `count()` | Counts occurrences of a substring |

```python
text = "Python Programming"

print(text.find("P"))       # 0
print(text.rfind("m"))      # 13
print(text.index("gram"))  # 10
print(text.count("m"))      # 2
```

### Checking Methods

These methods return `True` or `False`.

| Method | Purpose |
|---|---|
| `startswith()` | Checks whether a string starts with given text |
| `endswith()` | Checks whether a string ends with given text |
| `isalpha()` | Checks whether all characters are alphabetic |
| `isdigit()` | Checks whether all characters are digits |
| `isnumeric()` | Checks whether all characters are numeric |
| `islower()` | Checks whether all cased characters are lowercase |
| `isupper()` | Checks whether all cased characters are uppercase |
| `istitle()` | Checks whether the string follows title case |

```python
print("Python".startswith("Py"))  # True
print("Python".endswith("on"))    # True

print("Python".isalpha())         # True
print("12345".isdigit())          # True
print("12345".isnumeric())        # True

print("hello".islower())          # True
print("HELLO".isupper())          # True
print("Hello World".istitle())    # True
```

### Removing Whitespace and Characters

| Method | Purpose |
|---|---|
| `strip()` | Removes characters from both ends |
| `lstrip()` | Removes characters from the left |
| `rstrip()` | Removes characters from the right |

```python
text = "   Hello World   "

print(text.strip())
print(text.lstrip())
print(text.rstrip())

# Removing specific characters
text = "***Python***"

print(text.strip("*"))
```

### Replacing and Splitting

| Method | Purpose |
|---|---|
| `replace()` | Replaces a substring |
| `split()` | Splits a string into a list |

```python
text = "Python is easy"

# Replace
print(text.replace("easy", "powerful"))

# Split
print(text.split())

# Split using separator
print("Java,Python,JavaScript".split(","))
```

### Joining Strings

- `join()` combines multiple strings using a separator.

```python
words = ["Python", "is", "easy"]

print(" ".join(words))
# Python is easy

print("-".join(words))
# Python-is-easy
```

### Other Useful Methods

| Method | Purpose |
|---|---|
| `len()` | Returns the number of characters |
| `removeprefix()` | Removes a prefix if present |
| `removesuffix()` | Removes a suffix if present |

```python
text = "Python"

print(len(text))                   # 6
print("unhappy".removeprefix("un"))  # happy
print("file.txt".removesuffix(".txt"))  # file
```

---

## Escape Characters

- Escape characters are used to represent special characters inside strings.
- They start with a backslash (`\`).

| Escape Character | Meaning |
|---|---|
| `\n` | New line |
| `\t` | Tab |
| `\\` | Backslash |
| `\'` | Single quote |
| `\"` | Double quote |
| `\r` | Carriage return |
| `\b` | Backspace |

```python
print("Hello\nWorld")

print("Hello\tWorld")

print("It's Python")

print("This is a backslash: \\")
```

---

## Iterating Through a String

- A string is iterable, so we can access its characters one by one.

```python
text = "Python"

# Using for loop
for character in text:
    print(character)

# Using range and indexing
for index in range(len(text)):
    print(text[index])
```

---

## String Comparison

- Strings are compared lexicographically using Unicode code points.
- Comparison is case-sensitive.

```python
print("Python" == "Python")  # True
print("Python" == "python")  # False

print("apple" < "banana")    # True
print("cat" > "apple")       # True
```

### Case-Insensitive Comparison

```python
first = "Python"
second = "PYTHON"

print(first.lower() == second.lower())  # True
```
---

## 🔁 Quick Revision

| Topic | Remember |
|---|---|
| String | Sequence of characters |
| Immutable | Cannot be changed after creation |
| Indexing | Access individual characters |
| Slicing | Extract part of a string |
| `+` | Concatenation |
| `*` | Repetition |
| `in` | Membership check |
| `find()` | Search and return index or `-1` |
| `replace()` | Replace substring |
| `split()` | String to list |
| `join()` | Combine strings |
| `strip()` | Remove characters from both ends |
| `upper()` | Convert to uppercase |
| `lower()` | Convert to lowercase |
| `len()` | Return string length |
| `format()` | Format strings |
| `f-string` | Insert variables into strings |
