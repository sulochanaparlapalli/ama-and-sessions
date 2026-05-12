# Python Basics: Data Types, Operators, and Control Flow

Python is a high-level, interpreted, and easy-to-learn programming language created by €entity⃂["people","Guido van Rossum","Python creator"]⃁. It is widely used in web development, data analysis, automation, artificial intelligence, and scientific computing.

## Why Learn Python?

* Simple and readable syntax
* Large standard library
* Cross-platform support
* Popular in industry and academia
* Great for beginners and professionals

Python emphasizes code readability and allows developers to write programs with fewer lines of code compared to many other languages.

---

This README explains Python basics including variables, data types, operators, type checking, type conversion, and control flow statements with simple examples and outputs.

---

# What is Python?

Python is a high-level, interpreted, and easy-to-learn programming language created by Guido van Rossum. It is widely used in web development, automation, data analysis, artificial intelligence, and scientific computing.

---

# What is a Variable?

A variable is a name used to store data in memory.

```python
name = "Sulochana"
age = 22
```

In the above example:

* `name` and `age` are variables.
* `"Sulochana"` and `22` are values.

---

# What is a Data Type?

A data type specifies the kind of value a variable can store, such as numbers, text, or collections.

```python
name = "Sulochana"   # str
age = 22              # int
price = 99.99         # float
```

---

# Why Data Types Matter

Data types determine:

* What kind of values can be stored
* What operations can be performed
* How memory is managed

---

---

# 1. Data Types in Python

Python data types are classified into the following categories:

| Category       | Data Types                      |
| -------------- | ------------------------------- |
| Numeric Types  | `int`, `float`, `complex`       |
| Sequence Types | `str`, `list`, `tuple`, `range` |
| Set Types      | `set`, `frozenset`              |
| Mapping Type   | `dict`                          |
| Boolean Type   | `bool`                          |
| None Type      | `NoneType`                      |

---

# 2. Numeric Types

## Integer (`int`)

**Purpose:** Stores whole numbers.

```python
age = 25
print(age)
print(type(age))
```

**Output**

```python
25
<class 'int'>
```

**Characteristics**

* Whole numbers only
* Positive, negative, or zero
* Immutable

---

## Float (`float`)

**Purpose:** Stores decimal numbers.

```python
price = 99.99
print(price)
print(type(price))
```

**Output**

```python
99.99
<class 'float'>
```

**Characteristics**

* Contains decimal point
* Immutable

---

## Complex (`complex`)

**Purpose:** Stores numbers with real and imaginary parts.

```python
num = 2 + 3j
print(num)
print(type(num))
```

**Output**

```python
(2+3j)
<class 'complex'>
```

**Characteristics**

* Uses `j` for imaginary part
* Immutable

---

# 3. Sequence Types

## String (`str`)

**Purpose:** Stores text.

```python
name = "Sulochana"
print(name)
print(type(name))
```

**Output**

```python
Sulochana
<class 'str'>
```

**Characteristics**

* Written inside quotes
* Immutable
* Ordered sequence of characters

---

## List (`list`)

**Purpose:** Stores multiple values in one variable.

```python
fruits = ["apple", "banana", "mango"]
print(fruits)
print(type(fruits))
```

**Output**

```python
['apple', 'banana', 'mango']
<class 'list'>
```

**Characteristics**

* Ordered
* Mutable
* Allows duplicates

---

## Tuple (`tuple`)

**Purpose:** Stores multiple values that cannot be changed.

```python
colors = ("red", "green", "blue")
print(colors)
print(type(colors))
```

**Output**

```python
('red', 'green', 'blue')
<class 'tuple'>
```

**Characteristics**

* Ordered
* Immutable
* Allows duplicates

---

## Range (`range`)

**Purpose:** Generates a sequence of numbers.

```python
numbers = range(5)
print(list(numbers))
print(type(numbers))
```

**Output**

```python
[0, 1, 2, 3, 4]
<class 'range'>
```

**Characteristics**

* Used in loops
* Immutable

---

# 4. Set Types

## Set (`set`)

**Purpose:** Stores unique values.

```python
numbers = {1, 2, 2, 3}
print(numbers)
print(type(numbers))
```

**Output**

```python
{1, 2, 3}
<class 'set'>
```

**Characteristics**

* Unordered
* Mutable
* No duplicates

---

## Frozenset (`frozenset`)

**Purpose:** Immutable version of set.

```python
nums = frozenset([1, 2, 3])
print(nums)
print(type(nums))
```

**Output**

```python
frozenset({1, 2, 3})
<class 'frozenset'>
```

**Characteristics**

* Unordered
* Immutable
* No duplicates

---

# 5. Mapping Type

## Dictionary (`dict`)

**Purpose:** Stores data in key-value pairs.

```python
student = {"name": "Sulochana", "age": 22}
print(student)
print(type(student))
```

**Output**

```python
{'name': 'Sulochana', 'age': 22}
<class 'dict'>
```

**Characteristics**

* Mutable
* Keys are unique
* Fast lookup by key

---

# 6. Boolean Type

## Boolean (`bool`)

**Purpose:** Represents logical values.

```python
is_student = True
print(is_student)
print(type(is_student))
```

**Output**

```python
True
<class 'bool'>
```

**Characteristics**

* Only two values: `True` and `False`
* Used in conditions

---

# 7. None Type

## NoneType

**Purpose:** Represents absence of a value.

```python
value = None
print(value)
print(type(value))
```

**Output**

```python
None
<class 'NoneType'>
```

**Characteristics**

* Means "no value"
* Common as default value

---

# 8. Type Checking

## `type()`

**Purpose:** Returns the exact type of a variable.

```python
x = 10
print(type(x))
```

**Output**

```python
<class 'int'>
```

---

## `isinstance()`

**Purpose:** Checks whether a variable belongs to a specific type.

```python
x = 10
print(isinstance(x, int))
```

**Output**

```python
True
```

---

# 9. Type Conversion

Type conversion means converting a value from one data type to another.

There are two types of type conversion:

## 1. Implicit Type Conversion

**Definition:** Python automatically converts one data type to another when needed.

```python
x = 5       # int
y = 2.5     # float
result = x + y

print(result)
print(type(result))
```

**Output**

```python
7.5
<class 'float'> 
```

---

## 2. Explicit Type Conversion (Type Casting)

**Definition:** The programmer manually converts a value using built-in functions.

```python
num = "100"
converted = int(num)

print(converted)
print(type(converted))
```

**Output**

```python
100
<class 'int'> 
```

---

## Common Type Conversion Functions

| Function  | Purpose                |
| --------- | ---------------------- |
| `int()`   | Converts to integer    |
| `float()` | Converts to float      |
| `str()`   | Converts to string     |
| `list()`  | Converts to list       |
| `tuple()` | Converts to tuple      |
| `set()`   | Converts to set        |
| `dict()`  | Converts to dictionary |
| `bool()`  | Converts to boolean    |

---

# 10. Operators in Python

## Arithmetic Operators

**Purpose:** Perform mathematical calculations.

| Operator | Meaning        | Example  | Result |
| -------- | -------------- | -------- | ------ |
| `+`      | Addition       | `5 + 2`  | `7`    |
| `-`      | Subtraction    | `5 - 2`  | `3`    |
| `*`      | Multiplication | `5 * 2`  | `10`   |
| `/`      | Division       | `5 / 2`  | `2.5`  |
| `//`     | Floor Division | `5 // 2` | `2`    |
| `%`      | Modulus        | `5 % 2`  | `1`    |
| `**`     | Exponent       | `5 ** 2` | `25`   |

---

## Comparison Operators

**Purpose:** Compare two values and return `True` or `False`.

| Operator | Example  | Result  |
| -------- | -------- | ------- |
| `==`     | `5 == 5` | `True`  |
| `!=`     | `5 != 3` | `True`  |
| `>`      | `5 > 3`  | `True`  |
| `<`      | `5 < 3`  | `False` |
| `>=`     | `5 >= 5` | `True`  |
| `<=`     | `5 <= 3` | `False` |

---

## Logical Operators

**Purpose:** Combine conditions.

| Operator | Example          | Result  |
| -------- | ---------------- | ------- |
| `and`    | `True and False` | `False` |
| `or`     | `True or False`  | `True`  |
| `not`    | `not True`       | `False` |

---

## Assignment Operators

**Purpose:** Assign and update values.

| Operator | Example         | Result |
| -------- | --------------- | ------ |
| `=`      | `x = 5`         | `5`    |
| `+=`     | `x = 5; x += 2` | `7`    |
| `-=`     | `x = 5; x -= 2` | `3`    |
| `*=`     | `x = 5; x *= 2` | `10`   |
| `/=`     | `x = 5; x /= 2` | `2.5`  |

---

## Membership Operators

**Purpose:** Check whether a value exists in a sequence.

| Operator | Example              | Result |
| -------- | -------------------- | ------ |
| `in`     | `'a' in 'apple'`     | `True` |
| `not in` | `'z' not in 'apple'` | `True` |

---

## Identity Operators

**Purpose:** Check whether two variables refer to the same object.

| Operator | Example                        | Result |
| -------- | ------------------------------ | ------ |
| `is`     | `a = b = [1]; a is b`          | `True` |
| `is not` | `a = [1]; b = [1]; a is not b` | `True` |

---

# 11. Control Flow Statements

Control flow decides how the program executes.

---

## `if`

**Purpose:** Executes code when condition is true.

```python
age = 18

if age >= 18:
    print("Eligible to vote")
```

**Output**

```python
Eligible to vote
```

---

## `if-else`

**Purpose:** Chooses between two blocks of code.

```python
num = 7

if num % 2 == 0:
    print("Even")
else:
    print("Odd")
```

**Output**

```python
Odd
```

---

## `if-elif-else`

**Purpose:** Checks multiple conditions.

```python
marks = 85

if marks >= 90:
    print("A+")
elif marks >= 75:
    print("A")
else:
    print("B")
```

**Output**

```python
A
```

---

## Nested `if`

**Purpose:** Uses one `if` statement inside another.

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Allowed")
```

**Output**

```python
Allowed
```

---

## Ternary Operator

**Purpose:** Write a simple `if-else` statement in one line.

```python
age = 20
result = "Adult" if age >= 18 else "Minor"
print(result)
```

**Output**

```python
Adult
```

---

# 12. Loops

## `for`

**Purpose:** Repeats code for each item in a sequence.

```python
for i in range(3):
    print(i)
```

**Output**

```python
0
1
2
```

---

## `while`

**Purpose:** Repeats code while condition is true.

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

**Output**

```python
1
2
3
```

---

# 13. Loop Control Statements

## `break`

**Purpose:** Stops the loop immediately.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

**Output**

```python
0
1
2
```

---

## `continue`

**Purpose:** Skips the current iteration.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

**Output**

```python
0
1
3
4
```

---

## `pass`

**Purpose:** Placeholder that does nothing.

```python
if True:
    pass

print("Done")
```

**Output**

```python
Done
```

---

# Summary

* **Data Types:** `int`, `float`, `complex`, `str`, `list`, `tuple`, `range`, `set`, `frozenset`, `dict`, `bool`, `NoneType`
* **Type Checking:** `type()`, `isinstance()`
* **Type Conversion:** `int()`, `float()`, `str()`, `list()`, `tuple()`, `set()`
* **Operators:** Arithmetic, Comparison, Logical, Assignment, Membership, Identity
* **Control Flow:** `if`, `if-else`, `if-elif-else`, Nested `if`
* **Loops:** `for`, `while`
* **Loop Controls:** `break`, `continue`, `pass`
