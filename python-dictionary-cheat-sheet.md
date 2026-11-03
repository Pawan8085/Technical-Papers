
# 🐍 Python Dictionary Cheat Sheet

##  What is a Dictionary?

- A dictionary is a built-in Python data structure that stores data in **key-value pairs**.
- Each key must be unique and immutable (hashable).
- Values can be of any data type.
- Dictionaries are mutable, meaning we can add, update, and delete elements.
- Dictionaries maintain insertion order (Python 3.7+).

### Example

```python
student = {
    "name": "Pawan",
    "age": 25,
    "course": "Python"
}
```

Here:
- `"name"`, `"age"`, and `"course"` are keys.
- `"Pawan"`, `25`, and `"Python"` are values.

---

##  Creating a Dictionary

```python
# Empty dictionary
student = {}

# Dictionary with values
student = {
    "name": "Pawan",
    "age": 25
}

# Using dict()
student = dict(name="Pawan", age=25)

# Using dict.fromkeys()
keys = ["name", "age", "course"]
student = dict.fromkeys(keys, None)

# Nested dictionary
students = {
    1: {"name": "Pawan", "age": 25},
    2: {"name": "Amit", "age": 24}
}
```

---

##  Accessing Values

```python
student = {
    "name": "Pawan",
    "age": 25,
    "course": "Python"
}

# Access using key
print(student["name"])

# Access using get()
print(student.get("age"))

# Access missing key with a default value
print(student.get("city", "Not Found"))
```

**Difference between `[]` and `get()`:**

```python
student = {"name": "Pawan"}

# Raises KeyError if key does not exist
print(student["age"])

# Returns None if key does not exist
print(student.get("age"))

# Returns default value if key does not exist
print(student.get("age", 0))
```

---

##  Adding and Updating Elements

```python
student = {
    "name": "Pawan",
    "age": 25
}

# Add a new key-value pair
student["course"] = "Python"

# Update an existing value
student["age"] = 26

# Add or update multiple key-value pairs
student.update({
    "city": "Bangalore",
    "course": "Java"
})

print(student)
```

---

## Removing Elements

```python
student = {
    "name": "Pawan",
    "age": 25,
    "course": "Python"
}

# Remove a specific key and return its value
student.pop("age")

# Remove and return the last inserted key-value pair
student.popitem()

# Delete a specific key
del student["course"]

# Remove all elements
student.clear()
```

---

##  Checking Whether a Key Exists

```python
student = {
    "name": "Pawan",
    "age": 25
}

# Check if key exists
print("name" in student)

# Check if key does not exist
print("city" not in student)

# Check whether a value exists
print("Pawan" in student.values())
```

**Note:** The `in` operator checks keys by default, not values.

---

## Iterating Over a Dictionary

```python
student = {
    "name": "Pawan",
    "age": 25,
    "course": "Python"
}

# Iterate over keys
for key in student:
    print(key)

# Iterate over keys explicitly
for key in student.keys():
    print(key)

# Iterate over values
for value in student.values():
    print(value)

# Iterate over key-value pairs
for key, value in student.items():
    print(key, value)
```

### Using enumerate()

```python
student = {
    "name": "Pawan",
    "age": 25
}

for index, (key, value) in enumerate(student.items()):
    print(index, key, value)
```

---

##  Dictionary Comprehension

A concise way to create dictionaries.

```python
numbers = [1, 2, 3, 4, 5]

# Create dictionary of number and its square
squares = {
    number: number * number
    for number in numbers
}

# Dictionary with condition
even_numbers = {
    number: number * number
    for number in numbers
    if number % 2 == 0
}

# Convert two lists into a dictionary
names = ["Pawan", "Amit", "Rahul"]
ages = [25, 24, 26]

students = {
    names[index]: ages[index]
    for index in range(len(names))
}
```

---

##  Nested Dictionaries

A dictionary can contain another dictionary as its value.

```python
students = {
    1: {
        "name": "Pawan",
        "age": 25
    },
    2: {
        "name": "Amit",
        "age": 24
    }
}

# Access nested values
print(students[1]["name"])

# Update nested values
students[1]["age"] = 26

# Add a new nested key
students[1]["course"] = "Java"

# Iterate over nested dictionary
for student_id, details in students.items():
    print(student_id)

    for key, value in details.items():
        print(key, value)
```

---

##  Useful Dictionary Methods

### 1. get()

Returns the value of a specified key. Returns a default value if the key is missing.

```python
student = {"name": "Pawan", "age": 25}

print(student.get("name"))
print(student.get("city", "Unknown"))
```

### 2. keys()

Returns a view of all dictionary keys.

```python
student = {"name": "Pawan", "age": 25}

print(student.keys())
```

### 3. values()

Returns a view of all dictionary values.

```python
student = {"name": "Pawan", "age": 25}

print(student.values())
```

### 4. items()

Returns a view containing key-value pairs as tuples.

```python
student = {"name": "Pawan", "age": 25}

print(student.items())
```

### 5. update()

Adds new key-value pairs or updates existing ones.

```python
student = {"name": "Pawan", "age": 25}

student.update({
    "age": 26,
    "city": "Bangalore"
})
```

### 6. pop()

Removes the specified key and returns its value.

```python
student = {"name": "Pawan", "age": 25}

age = student.pop("age")

# Default value if key is missing
city = student.pop("city", "Unknown")
```

### 7. popitem()

Removes and returns the last inserted key-value pair.

```python
student = {"name": "Pawan", "age": 25}

item = student.popitem()
```

### 8. setdefault()

Returns the value of a key. If the key does not exist, inserts it with the default value.

```python
student = {"name": "Pawan"}

# Existing key
student.setdefault("name", "Amit")

# Missing key gets inserted
student.setdefault("age", 25)

print(student)
```

### 9. copy()

Creates a shallow copy of the dictionary.

```python
student = {"name": "Pawan", "age": 25}

new_student = student.copy()
```

### 10. clear()

Removes all key-value pairs.

```python
student = {"name": "Pawan", "age": 25}

student.clear()
```

### 11. fromkeys()

Creates a new dictionary using the given keys and a common default value.

```python
keys = ["name", "age", "city"]

student = dict.fromkeys(keys, None)

print(student)
```

---

##  Other Useful Dictionary Operations

```python
student = {
    "name": "Pawan",
    "age": 25
}

# Number of key-value pairs
print(len(student))

# Check whether dictionary is empty
print(not student)

# Create a shallow copy
new_student = student.copy()

# Merge two dictionaries (Python 3.9+)
first = {"name": "Pawan"}
second = {"age": 25}

merged = first | second

```

---

##  Dictionary vs List

| Feature | Dictionary | List |
|---|---|---|
| Data storage | Key-value pairs | Elements |
| Access | Using keys | Using indexes |
| Mutable | Yes | Yes |
| Duplicate keys | No | Not applicable |
| Duplicate values | Yes | Yes |
| Ordered | Yes | Yes |
| Search | Average O(1) by key | O(n) by value |

---

##  Dictionary Time Complexity

Average-case time complexity:

| Operation | Time Complexity |
|---|---|
| Access by key | O(1) |
| Insert key-value pair | O(1) |
| Update value | O(1) |
| Delete by key | O(1) |
| Search for a key | O(1) |
| Search for a value | O(n) |
| `get()` | O(1) |
| `setdefault()` | O(1) |
| `pop()` | O(1) |
| `popitem()` | O(1) |
| `keys()` | O(1) |
| `values()` | O(1) |
| `items()` | O(1) |
| `len()` | O(1) |
| `copy()` | O(n) |
| `clear()` | O(n) |
| `update()` | O(k) average |
| `fromkeys()` | O(n) |

**Note:**
- Dictionary operations are generally O(1) on average because dictionaries use hashing.
- In the worst case, lookup, insertion, and deletion can take O(n).
- Here, `n` is the number of dictionary entries and `k` is the number of entries being added or updated.
- Iterating over keys, values, or items takes O(n).

---

##  Quick Revision

| Method | Purpose |
|---|---|
| `get()` | Get value safely |
| `keys()` | Get all keys |
| `values()` | Get all values |
| `items()` | Get key-value pairs |
| `update()` | Add or update entries |
| `pop()` | Remove a specified key |
| `popitem()` | Remove last inserted entry |
| `setdefault()` | Get value or insert default |
| `copy()` | Create shallow copy |
| `clear()` | Remove all entries |
| `fromkeys()` | Create dictionary from keys |

