
# 🏗️ SOLID Principles in Python

## What is SOLID?

- SOLID is a set of five object-oriented design principles.
- These principles help us write maintainable, flexible, reusable, and loosely coupled code.
- They make it easier to extend applications without unnecessarily modifying existing code.

### SOLID stands for

| Letter | Principle | Meaning |
|---|---|---|
| S | Single Responsibility Principle | A class should have one responsibility. |
| O | Open/Closed Principle | Open for extension, closed for modification. |
| L | Liskov Substitution Principle | Child classes should be replaceable with their parent classes. |
| I | Interface Segregation Principle | Prefer smaller, specific interfaces. |
| D | Dependency Inversion Principle | Depend on abstractions, not concrete implementations. |

---

## 1. Single Responsibility Principle (SRP)

**Definition:**

"A class should have only one reason to change."

- Every class should have a single responsibility or job.
- A class should not handle multiple unrelated responsibilities.

### ❌ Problem: One class doing multiple jobs

```python
class Staff:

    def cook_food(self, dish):
        print(f"Cooking {dish}...")

    def take_order(self, table, dish):
        print(f"Table {table} ordered {dish}")

    def serve_food(self, table, dish):
        print(f"Serving {dish} to table {table}")
```

Here, the `Staff` class handles three different responsibilities:

1. Cooking food
2. Taking orders
3. Serving food

If any of these responsibilities changes, we need to modify the same class.

### ✅ Solution: Separate responsibilities

```python
class Chef:

    def cook_food(self, dish):
        print(f"Chef is cooking {dish}...")
        return dish


class Waiter:

    def take_order(self, table, dish):
        print(f"Waiter took order: {dish} from table {table}")

    def serve_order(self, table, dish):
        print(f"Waiter is serving {dish} to table {table}")


# Usage
chef = Chef()
waiter = Waiter()

dish = "Tofu bhurji"
table = 6

waiter.take_order(table, dish)

prepared_dish = chef.cook_food(dish)

waiter.serve_order(table, prepared_dish)
```

**Why does this follow SRP?**

- `Chef` is responsible for cooking.
- `Waiter` is responsible for taking orders and serving food.
- Each class has a clearly defined responsibility.

---

## 2. Open/Closed Principle (OCP)

**Definition:**

"Software entities should be open for extension but closed for modification."

- We should be able to add new functionality without unnecessarily modifying existing code.
- This helps reduce the chances of breaking existing functionality.

### ❌ Problem: Modifying existing code for every new discount

```python
class DiscountCalculator:

    def calculate(self, customer_type, amount):

        if customer_type == "regular":
            return amount * 0.05

        elif customer_type == "premium":
            return amount * 0.10

        elif customer_type == "vip":
            return amount * 0.20
```

Suppose we want to add a `student` discount.

We need to modify the existing `DiscountCalculator` and add another condition.

As the number of discount types increases, this class becomes difficult to maintain.

### ✅ Solution: Use inheritance and polymorphism

```python
from abc import ABC, abstractmethod


# Base class
class Discount(ABC):

    @abstractmethod
    def calculate(self, amount):
        pass


class RegularDiscount(Discount):

    def calculate(self, amount):
        return amount * 0.05


class PremiumDiscount(Discount):

    def calculate(self, amount):
        return amount * 0.10


class VipDiscount(Discount):

    def calculate(self, amount):
        return amount * 0.20


# Adding a new student discount
class StudentDiscount(Discount):

    def calculate(self, amount):
        return amount * 0.15


class DiscountCalculator:

    def calculate(self, discount, amount):
        return discount.calculate(amount)


# Usage
student_discount = StudentDiscount()

discount_calculator = DiscountCalculator()

discount = discount_calculator.calculate(student_discount, 1000)

print(discount)  # 150.0
```

**Why does this follow OCP?**

- Existing discount classes do not need modification.
- We can introduce new discount types by creating new classes.
- `DiscountCalculator` works with different discount implementations through the common interface.

---

## 3. Liskov Substitution Principle (LSP)

**Definition:**

"Objects of a child class should be replaceable with objects of their parent class without breaking the program."

- Child classes should correctly support the behavior expected from their parent class.
- A child class should not introduce behavior that violates the expectations of the parent class.

### ❌ Problem: Penguin cannot fly

```python
class Bird:

    def fly(self):
        print("Flying high...")


# Sparrow can fly
class Sparrow(Bird):
    pass


# Penguin cannot fly
class Penguin(Bird):

    def fly(self):
        raise Exception("Penguin can't fly!")


def make_bird_fly(bird):
    bird.fly()


# Usage
make_bird_fly(Sparrow())  # Works
make_bird_fly(Penguin())  # Raises an exception
```

**Problem:**

- `Sparrow` can correctly use the inherited `fly()` method.
- `Penguin` cannot fly, but it inherits the `fly()` method.
- Replacing a `Bird` with a `Penguin` breaks the expected behavior.

### ✅ Solution: Create separate base classes

```python
class Bird:

    def eat(self):
        print("Eating...")


class FlyingBird(Bird):

    def fly(self):
        print("Flying high...")


class Sparrow(FlyingBird):
    pass


class Penguin(Bird):

    def swim(self):
        print("Swimming...")


def make_bird_fly(bird: FlyingBird):
    bird.fly()


# Usage
make_bird_fly(Sparrow())  # Works

penguin = Penguin()
penguin.eat()
penguin.swim()

# make_bird_fly(penguin)  # Incorrect: Penguin is not a FlyingBird
```

**Why does this follow LSP?**

- `Sparrow` inherits from `FlyingBird` and supports flying.
- `Penguin` inherits from `Bird` and supports eating and swimming.
- We no longer force every bird to implement flying.

---

## 4. Interface Segregation Principle (ISP)

**Definition:**

"No client should be forced to depend on methods it does not use."

- Avoid creating one large interface with many unrelated methods.
- Instead, divide it into smaller, specific interfaces.
- Classes should implement only the methods they actually need.

### ❌ Problem: One large interface

```python
from abc import ABC, abstractmethod
import math


class Calculator(ABC):

    @abstractmethod
    def add(self, a, b):
        pass

    @abstractmethod
    def subtract(self, a, b):
        pass

    @abstractmethod
    def power(self, a, b):
        pass

    @abstractmethod
    def square_root(self, a):
        pass


class AdvanceCalculator(Calculator):

    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def power(self, a, b):
        return a ** b

    def square_root(self, a):
        return math.sqrt(a)


# Problem: SimpleCalculator is forced to implement
# advanced methods it does not need.
class SimpleCalculator(Calculator):

    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def power(self, a, b):
        raise Exception("Simple calculator can't do power!")

    def square_root(self, a):
        raise Exception("Simple calculator can't do square root!")
```

**Problem:**

`SimpleCalculator` only needs addition and subtraction, but it is forced to implement advanced operations.

### ✅ Solution: Separate interfaces

```python
from abc import ABC, abstractmethod
import math


class BasicOperations(ABC):

    @abstractmethod
    def add(self, a, b):
        pass

    @abstractmethod
    def subtract(self, a, b):
        pass


class AdvancedOperations(ABC):

    @abstractmethod
    def power(self, a, b):
        pass

    @abstractmethod
    def square_root(self, a):
        pass


class SimpleCalculator(BasicOperations):

    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b


class AdvancedCalculator(AdvancedOperations):

    def power(self, a, b):
        return a ** b

    def square_root(self, a):
        return math.sqrt(a)


# Usage
simple_calculator = SimpleCalculator()

print(simple_calculator.add(10, 5))
print(simple_calculator.subtract(10, 5))


advanced_calculator = AdvancedCalculator()

print(advanced_calculator.power(2, 3))  # 8
print(advanced_calculator.square_root(25))  # 5.0
```

**Why does this follow ISP?**

- `SimpleCalculator` implements only basic operations.
- `AdvancedCalculator` implements only advanced operations.
- Neither class is forced to implement unnecessary methods.

---

## 5. Dependency Inversion Principle (DIP)

**Definition:**

"High-level modules should not depend on low-level modules. Both should depend on abstractions."

- High-level modules contain business logic.
- Low-level modules contain implementation details.
- Both should communicate through abstractions rather than depending directly on concrete implementations.

### ❌ Problem: Hardcoded dependency

```python
class EmailService:

    def send(self, message):
        print(f"Sending email: {message}")


class OrderService:

    def __init__(self):
        self.notifier = EmailService()  # Hardcoded dependency

    def place_order(self, item):
        print(f"Order placed for {item}")

        self.notifier.send(
            f"Your order for {item} is confirmed"
        )
```

**Problem:**

- `OrderService` is the high-level module containing business logic.
- `EmailService` is a low-level implementation detail.
- `OrderService` directly creates `EmailService`, so it is tightly coupled to email notifications.
- If we want to use SMS instead, we need to modify `OrderService`.
- Testing also becomes harder because the notification dependency is fixed.

### ✅ Solution: Depend on an abstraction

```python
from abc import ABC, abstractmethod


# Abstraction
class Notifier(ABC):

    @abstractmethod
    def send(self, message):
        pass


# Concrete implementations
class EmailService(Notifier):

    def send(self, message):
        print(f"Sending email: {message}")


class SmsService(Notifier):

    def send(self, message):
        print(f"Sending SMS: {message}")


# High-level module
class OrderService:

    def __init__(self, notifier):
        self.notifier = notifier  # Dependency injected from outside

    def place_order(self, item):
        print(f"Order placed for {item}")

        self.notifier.send(
            f"Your order for {item} is confirmed"
        )


# Usage

# Using EmailService
order_1 = OrderService(EmailService())
order_1.place_order("Macbook Air M5")


# Using SmsService
order_2 = OrderService(SmsService())
order_2.place_order("Earbuds")
```

**Why does this follow DIP?**

- `OrderService` depends on the `Notifier` abstraction rather than a specific notification service.
- `EmailService` and `SmsService` implement the same abstraction.
- We can change the notification service without modifying `OrderService`.

### What is Dependency Injection?

- Dependency Injection (DI) is a technique where an object receives its dependencies from outside instead of creating them internally.
- In the above example, `EmailService()` and `SmsService()` are injected into `OrderService` through its constructor.

---

# 🔁 SOLID Quick Revision

| Principle | Remember |
|---|---|
| SRP | One class, one responsibility |
| OCP | Extend functionality without modifying existing code |
| LSP | Child objects should replace parent objects without breaking behavior |
| ISP | Prefer smaller, specific interfaces |
| DIP | Depend on abstractions, not concrete implementations |

---
**Remember:** SOLID principles are design guidelines, not strict rules. Apply them where they improve maintainability and flexibility rather than adding unnecessary classes or interfaces to every small program.
