
# 🐍 Python Arrays Cheat Sheet

Python provides two common ways to work with array-like data:

1. **List (`list`)** – A dynamic, built-in sequence that can store different data types.
2. **Array (`array` module)** – A typed array that stores elements of the same data type.

---

#  📋 Python Lists (Dynamic Arrays)

A list is a built-in Python data structure that stores multiple elements in an ordered, mutable sequence.

### Creating Lists

```python
# Empty list
numbers = []

# List of integers
numbers = [10, 20, 30, 40]

# List with different data types
data = [10, "Python", 20.5, True]

# Create a list using range()
numbers = list(range(1, 6))

# Create a list with repeated values
numbers = [0] * 5
```

### Accessing Elements

```python
numbers = [10, 20, 30, 40, 50]

# Access using positive indexing
print(numbers[0])    # 10
print(numbers[2])    # 30

# Access using negative indexing
print(numbers[-1])   # 50
print(numbers[-2])   # 40

# Get list length
print(len(numbers))
```

### Updating Elements

```python
numbers = [10, 20, 30, 40]

# Update an element
numbers[1] = 100

# Update multiple elements using slicing
numbers[1:3] = [200, 300]

print(numbers)
```

---

# ➕ Adding Elements

```python
numbers = [10, 20, 30]

# Add element at the end
numbers.append(40)

# Insert element at a specific index
numbers.insert(1, 15)

# Add multiple elements
numbers.extend([50, 60])

print(numbers)
```

---

# ➖ Removing Elements

```python
numbers = [10, 20, 30, 40, 50]

# Remove element by value (first occurrence)
numbers.remove(30)

# Remove element by index
numbers.pop(1)

# Remove last element
numbers.pop()

# Delete element using del
del numbers[0]

# Delete a range of elements
del numbers[0:2]

# Remove all elements
numbers.clear()
```

### Difference Between remove(), pop(), and del

| Operation | Description |
|---|---|
| `remove(value)` | Removes the first matching value |
| `pop(index)` | Removes and returns an element at an index |
| `pop()` | Removes and returns the last element |
| `del` | Deletes an element or a slice |
| `clear()` | Removes all elements |

---

#  🔎 Searching Elements

```python
numbers = [10, 20, 30, 20, 40]

# Check whether an element exists
print(20 in numbers)

# Check whether an element does not exist
print(50 not in numbers)

# Find the index of an element
print(numbers.index(30))

# Count occurrences of an element
print(numbers.count(20))
```

---

# 🔀 Sorting and Reversing

```python
numbers = [40, 10, 30, 20]

# Sort in ascending order (modifies original list)
numbers.sort()

# Sort in descending order
numbers.sort(reverse=True)

# Return a new sorted list
sorted_numbers = sorted(numbers)

# Reverse the original list
numbers.reverse()

# Reverse using slicing (creates a new list)
reversed_numbers = numbers[::-1]
```

### Sorting Strings

```python
names = ["Pawan", "Amit", "Rahul"]

# Alphabetical order
names.sort()

# Reverse alphabetical order
names.sort(reverse=True)

# Sort without considering case
names.sort(key=str.lower)
```

---

# ✂️ Slicing and Copying

Slicing allows you to access a portion of a list.

Syntax:

```python
list[start:stop:step]
```

```python
numbers = [10, 20, 30, 40, 50, 60]

# First three elements
print(numbers[0:3])

# Elements from index 2 onwards
print(numbers[2:])

# Elements until index 4 (excluded)
print(numbers[:4])

# Every second element
print(numbers[::2])

# Reverse the list
print(numbers[::-1])

# Copy using slicing
copy_numbers = numbers[:]

# Copy using copy()
copy_numbers = numbers.copy()
```

### Shallow Copy vs Direct Assignment

```python
numbers = [10, 20, 30]

# Direct assignment creates another reference
new_numbers = numbers

# Both variables refer to the same list
new_numbers.append(40)

print(numbers)      # [10, 20, 30, 40]

# Create a shallow copy
copy_numbers = numbers.copy()

copy_numbers.append(50)

print(numbers)      # Original remains unchanged
```

---

#  🔁 Iterating Over Lists

```python
numbers = [10, 20, 30, 40]

# Using for loop
for number in numbers:
    print(number)

# Using range()
for index in range(len(numbers)):
    print(numbers[index])

# Using enumerate()
for index, number in enumerate(numbers):
    print(index, number)

# Iterate with index starting from 1
for index, number in enumerate(numbers, start=1):
    print(index, number)
```

### List Comprehension

A concise way to create a new list.

```python
numbers = [1, 2, 3, 4, 5]

# Create squares
squares = [number * number for number in numbers]

# Filter even numbers
even_numbers = [number for number in numbers if number % 2 == 0]

# Conditional expression
result = ["Even" if number % 2 == 0 else "Odd" for number in numbers]
```

---

#  🧮 Common List Operations

```python
numbers = [10, 20, 30, 40]

# Length
len(numbers)

# Minimum value
min(numbers)

# Maximum value
max(numbers)

# Sum of elements
sum(numbers)

# Concatenate lists
combined = [10, 20] + [30, 40]

# Repeat a list
repeated = [1, 2] * 3

# Check membership
20 in numbers

# Compare lists
[10, 20] == [10, 20]
```

---

#  🔢 Nested Lists (2D Arrays)

A nested list contains other lists and can represent a matrix or a two-dimensional array.

### Creating a 2D List

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

### Accessing Elements

```python
# First row
print(matrix[0])

# First row, second column
print(matrix[0][1])

# Third row, third column
print(matrix[2][2])
```

### Updating Elements

```python
matrix[0][1] = 100
```

### Iterating Through a 2D List

```python
for row in matrix:
    for element in row:
        print(element, end=" ")
    print()
```

### Creating a Matrix Dynamically

```python
# 3 rows and 4 columns initialized with zeros
rows = 3
columns = 4

matrix = [[0 for column in range(columns)] for row in range(rows)]
```

**Important:** Avoid using `[[0] * columns] * rows` when you need independent rows. It repeats references to the same inner list.

---

# ⚙️ Built-in Array Module

Python provides the `array` module for creating typed arrays.

Unlike lists, arrays from this module store elements of a single specified type.

### Importing the Module

```python
import array
```

### Creating Arrays

```python
import array

# Integer array
numbers = array.array('i', [10, 20, 30, 40])

# Floating-point array
prices = array.array('f', [10.5, 20.5, 30.5])

# Double-precision floating-point array
values = array.array('d', [1.5, 2.5, 3.5])

print(numbers)
```

### Common Type Codes

| Type Code | C Type | Description |
|---|---|---|
| `b` | signed char | Signed integer |
| `B` | unsigned char | Unsigned integer |
| `i` | signed int | Signed integer |
| `I` | unsigned int | Unsigned integer |
| `l` | signed long | Signed long integer |
| `f` | float | Single-precision float |
| `d` | double | Double-precision float |

The exact size of some integer type codes can depend on the platform. Check `itemsize` when storage size matters.

### Accessing and Updating Elements

```python
import array

numbers = array.array('i', [10, 20, 30, 40])

# Access elements
print(numbers[0])
print(numbers[-1])

# Update an element
numbers[1] = 100

# Get array length
print(len(numbers))
```

### Adding Elements

```python
import array

numbers = array.array('i', [10, 20, 30])

# Add one element
numbers.append(40)

# Insert at a specific index
numbers.insert(1, 15)

# Extend with another iterable
numbers.extend([50, 60])
```

### Removing Elements

```python
import array

numbers = array.array('i', [10, 20, 30, 40])

# Remove first occurrence of a value
numbers.remove(30)

# Remove and return element at index
numbers.pop(1)

# Remove last element
numbers.pop()

# Delete using del
del numbers[0]
```

### Searching and Counting

```python
import array

numbers = array.array('i', [10, 20, 30, 20])

# Find index
print(numbers.index(30))

# Count occurrences
print(numbers.count(20))

# Check membership
print(20 in numbers)
```

### Sorting and Reversing

The `array` module does not provide a `sort()` method like lists.

```python
import array

numbers = array.array('i', [40, 10, 30, 20])

# Sort by converting to a list and back
numbers = array.array('i', sorted(numbers))

# Reverse in place
numbers.reverse()
```

### Other Useful Array Operations

```python
import array

numbers = array.array('i', [10, 20, 30])

# Get type code
print(numbers.typecode)

# Get size of each element in bytes
print(numbers.itemsize)

# Convert array to list
number_list = numbers.tolist()

# Convert list to array
new_array = array.array('i', number_list)

# Copy array
copy_array = array.array(numbers.typecode, numbers)
```

---

#  ⚖️ List vs Array Module

| Feature | List | `array.array` |
|---|---|---|
| Built-in | Yes | Yes, through module |
| Data types | Different types allowed | Same specified type |
| Dynamic size | Yes | Yes |
| Indexing | Yes | Yes |
| Slicing | Yes | Yes |
| Append | Yes | Yes |
| Insert | Yes | Yes |
| Remove | Yes | Yes |
| Sort method | Yes | No |
| Type restriction | No | Yes |
| Numerical operations | Basic built-ins | Basic built-ins |
| Typical use | General-purpose data | Compact typed numeric data |

### When to Use What?

**Use a List when:**
- Working with general-purpose data.
- Storing different data types.
- Frequently adding and removing elements.
- Building everyday Python applications.

**Use `array.array` when:**
- Storing many values of the same basic numeric type.
- You want more compact typed storage than a list of Python objects.
- You don't need NumPy's advanced numerical operations.

**Use NumPy arrays when:**
- Performing mathematical and scientific computations.
- Working with large numerical datasets.
- Performing matrix operations and vectorized calculations.

---

#  ⏱️ Time Complexity of Common Operations

For Python lists, typical time complexities are:

| Operation | Time Complexity |
|---|---|
| Access by index | O(1) |
| Update by index | O(1) |
| Append | O(1) amortized |
| Pop last element | O(1) |
| Insert at beginning | O(n) |
| Insert at middle | O(n) |
| Remove by value | O(n) |
| Search by value | O(n) |
| Count occurrences | O(n) |
| Sort | O(n log n) |
| Reverse | O(n) |
| Slice of k elements | O(k) |

---

# 📋 Quick Revision

| Method | Description |
|---|---|
| `append(x)` | Add element at the end |
| `extend(iterable)` | Add multiple elements |
| `insert(i, x)` | Insert at an index |
| `remove(x)` | Remove first occurrence |
| `pop(i)` | Remove and return element |
| `clear()` | Remove all elements |
| `index(x)` | Find element index |
| `count(x)` | Count occurrences |
| `sort()` | Sort list in place |
| `reverse()` | Reverse in place |
| `copy()` | Create shallow copy |
| `len(arr)` | Get number of elements |
| `min(arr)` | Get minimum value |
| `max(arr)` | Get maximum value |
| `sum(arr)` | Calculate sum |
| `sorted(arr)` | Return a new sorted list |
| `enumerate(arr)` | Iterate with index and value |

