
# 🐍 Python OOP Cheat Sheet

## What is OOP?

- OOP stands for Object-Oriented Programming.
- It is a programming approach based on classes and objects.
- It helps organize code into reusable and manageable structures.

### Benefits of OOP

1. Code reusability
2. Code organization
3. Abstraction
4. Data management through encapsulation
5. Flexibility through polymorphism

---

##  Class and Object

### Class

- A class is like a blueprint or template.
- It defines state (attributes) and behavior (methods).

### Object

- An object is an instance of a class.
- Each object can have its own data.

```python
class Employee:

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display_details(self):
        print(self.name, self.salary)


# Creating objects
employee1 = Employee("Pawan", 50000)
employee2 = Employee("Amit", 60000)

employee1.display_details()
employee2.display_details()
```

---

##  Constructor (`__init__`)

- `__init__()` is used to initialize object attributes.
- Python automatically calls it when an object is created.
- Technically, `__new__()` creates the object, and `__init__()` initializes it.

### Example

```python
class Employee:

    def __init__(self, name, age):
        self.name = name
        self.age = age


employee = Employee("Pawan", 25)
```

### Default Values in Constructor

```python
class Employee:

    def __init__(self, name="Unknown", age=0):
        self.name = name
        self.age = age


employee = Employee()
```

---

##  The `self` Keyword

- `self` refers to the current object.
- It is used to access instance attributes and methods.
- It is the first parameter of an instance method.
- `self` is not a Python keyword; it is a naming convention.

```python
class Employee:

    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)


employee = Employee("Pawan")
employee.display()
```

---

# Four Pillars of OOP

##  Encapsulation

- Encapsulation means bundling data (attributes) and methods together inside a class.
- It also allows us to control how an object's data is accessed or modified.

### Public Members

- Accessible from anywhere.

```python
class Employee:

    def __init__(self):
        self.name = "Pawan"


employee = Employee()
print(employee.name)
```

### Protected Members

- A single underscore (`_`) indicates that a member is intended for internal use.
- It is a convention, not a strict access restriction.

```python
class Employee:

    def __init__(self):
        self._salary = 50000


employee = Employee()
print(employee._salary)
```

### Private Members

- A double underscore (`__`) triggers name mangling.
- Python internally renames `__salary` to `_Employee__salary`.
- It helps prevent accidental access and naming conflicts, but does not provide strict privacy.

```python
class Employee:

    def __init__(self):
        self.__salary = 50000


employee = Employee()

# Access using the mangled name
print(employee._Employee__salary)

# Modification is also possible
employee._Employee__salary = 60000
```

### Getters and Setters

- Getters are used to retrieve attribute values.
- Setters are used to modify attribute values.
- They allow us to apply validation before modifying data.

```python
class Employee:

    def __init__(self, salary):
        self.__salary = salary

    def get_salary(self):
        return self.__salary

    def set_salary(self, salary):
        if salary > 0:
            self.__salary = salary
        else:
            print("Invalid salary")


employee = Employee(50000)

print(employee.get_salary())

employee.set_salary(60000)

print(employee.get_salary())
```

---

## Inheritance

- Inheritance allows one class to reuse the attributes and methods of another class.
- The existing class is called the parent or base class.
- The new class is called the child or derived class.

### Single Inheritance

One child class inherits from one parent class.

```python
class Animal:

    def eat(self):
        print("Animal is eating")


class Dog(Animal):

    def bark(self):
        print("Dog is barking")


dog = Dog()

dog.eat()
dog.bark()
```

### Multilevel Inheritance

A class inherits from a child class, forming an inheritance chain.

```python
class Animal:

    def eat(self):
        print("Eating")


class Dog(Animal):

    def bark(self):
        print("Barking")


class Puppy(Dog):

    def weep(self):
        print("Weeping")


puppy = Puppy()

puppy.eat()
puppy.bark()
puppy.weep()
```

### Multiple Inheritance

A child class inherits from more than one parent class.

```python
class Father:

    def father_method(self):
        print("Father method")


class Mother:

    def mother_method(self):
        print("Mother method")


class Child(Father, Mother):
    pass


child = Child()

child.father_method()
child.mother_method()
```

### Hierarchical Inheritance

Multiple child classes inherit from the same parent class.

```python
class Animal:

    def eat(self):
        print("Eating")


class Dog(Animal):
    pass


class Cat(Animal):
    pass


dog = Dog()
cat = Cat()

dog.eat()
cat.eat()
```

### Hybrid Inheritance

- Hybrid inheritance is a combination of two or more types of inheritance.
- It combines different inheritance structures.

---

## Polymorphism

- Polymorphism means one interface or method name can have different behavior depending on the object.

### Method Overriding

- A child class provides its own implementation of a parent class method.
- The child class method overrides the inherited implementation.

```python
class Animal:

    def sound(self):
        print("Animal makes a sound")


class Dog(Animal):

    def sound(self):
        print("Dog barks")


class Cat(Animal):

    def sound(self):
        print("Cat meows")


animals = [Dog(), Cat()]

for animal in animals:
    animal.sound()
```

### Method Overloading

- Method overloading means defining multiple methods with the same name but different parameter lists.
- Python does not support traditional method overloading by defining multiple methods with the same name.
- We can achieve similar behavior using default arguments or variable-length arguments.

```python
class Calculator:

    def add(self, first, second=0, third=0):
        return first + second + third


calculator = Calculator()

print(calculator.add(10, 20))
print(calculator.add(10, 20, 30))
```

---

## Abstraction

- Abstraction means hiding implementation details and exposing only the required functionality.
- Python supports abstraction through the `abc` module.

### Abstract Class and Abstract Method

- An abstract class cannot be instantiated while it contains unimplemented abstract methods.
- Concrete child classes must implement inherited abstract methods before they can be instantiated.

```python
from abc import ABC, abstractmethod


class Payment(ABC):

    @abstractmethod
    def pay(self, amount):
        pass


class CreditCardPayment(Payment):

    def pay(self, amount):
        print(f"Paid {amount} using credit card")


payment = CreditCardPayment()
payment.pay(1000)
```

---

# Types of Methods

## Instance Method

- Works with instance attributes.
- Takes `self` as its first parameter.

```python
class Employee:

    def display(self):
        print("Instance method")


employee = Employee()
employee.display()
```

## Class Method

- Works with class-level data.
- Uses `@classmethod`.
- Takes `cls` as its first parameter.

```python
class Employee:

    company = "ABC Technologies"

    @classmethod
    def display_company(cls):
        print(cls.company)


Employee.display_company()
```

## Static Method

- Does not receive `self` or `cls` automatically.
- Used for utility operations related to a class.
- Uses `@staticmethod`.

```python
class Calculator:

    @staticmethod
    def add(first, second):
        return first + second


print(Calculator.add(10, 20))
```

---

# Class Variables vs Instance Variables

### Instance Variables

- Belong to individual objects.
- Each object can have a different value.
- Usually defined using `self` inside instance methods.

### Class Variables

- Shared by all instances of a class unless shadowed by an instance attribute.
- Defined directly inside the class.

```python
class Employee:

    company = "ABC Technologies"

    def __init__(self, name):
        self.name = name


employee1 = Employee("Pawan")
employee2 = Employee("Amit")

print(employee1.name)
print(employee2.name)

print(employee1.company)
print(employee2.company)
```

**Important:** Modifying a class variable through an instance assignment creates an instance attribute; it does not modify the original class variable.

```python
employee1.company = "XYZ Technologies"

print(employee1.company)  # XYZ Technologies
print(employee2.company)  # ABC Technologies
print(Employee.company)   # ABC Technologies
```

---

# The `super()` Function

- `super()` provides access to methods in the next class in the Method Resolution Order (MRO).
- It is commonly used to call inherited methods and constructors.

```python
class Animal:

    def __init__(self, name):
        self.name = name


class Dog(Animal):

    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed


dog = Dog("Tommy", "Labrador")

print(dog.name)
print(dog.breed)
```
---

# Composition

- Composition means building a class using objects of other classes.
- It represents a "has-a" relationship.
- It is an alternative to inheritance when one class needs to use another class's functionality.

```python
class Engine:

    def start(self):
        print("Engine started")


class Car:

    def __init__(self):
        self.engine = Engine()

    def start_car(self):
        self.engine.start()


car = Car()
car.start_car()
```

Here, a Car has an Engine.

---

