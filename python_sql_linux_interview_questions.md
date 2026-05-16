# Python, SQL, PostgreSQL, and Linux Interview Questions with Answers

## 1. How do you add content to a file in Linux?

To add content to an existing file without overwriting it, use the `>>` operator.

### Syntax
```bash
echo "Hello World" >> file.txt
```

### Example
```bash
echo "This is a new line" >> notes.txt
```

### Explanation
- `>` → Overwrites the file.
- `>>` → Appends content to the file.

---

## 2. What is the Staging Area in Git?

The **Staging Area** (also called the **Index**) is an intermediate area where changes are prepared before committing them to the Git repository.

### Workflow
Working Directory → Staging Area → Repository

### Commands
```bash
git add file.py
git commit -m "msg"
```

### Use
It allows you to select exactly which changes should be included in the next commit.

---

## 3. Which libraries are used for Unit Testing in Python?

Popular Python unit testing libraries include:

1. `unittest` – Built-in testing framework.
2. `pytest` – Most popular and easy to use.
3. `nose2` – Successor to nose.
4. `doctest` – Tests embedded in docstrings.

### Example using `unittest`
```python
import unittest

def add(a, b):
    return a + b

class TestAdd(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)

unittest.main()
```

---

## 4. Difference Between TRUNCATE, DROP, and DELETE. Where Can We Apply ROLLBACK?

| Command | Removes | WHERE Clause | Structure Removed | Rollback Possible |
|--------|---------|--------------|------------------|------------------|
| DELETE | Selected rows | Yes | No | Yes |
| TRUNCATE | All rows | No | No | Yes in PostgreSQL if inside a transaction |
| DROP | Entire table/database | No | Yes | Yes in PostgreSQL if inside a transaction |

### Example
```sql
DELETE FROM employees WHERE id = 10;
TRUNCATE TABLE employees;
DROP TABLE employees;
```

---

## 5. What is a Lambda Function in Python?

A **lambda function** is an anonymous one-line function.

### Syntax
```python
lambda arguments: expression
```

### Example
```python
square = lambda x: x * x
print(square(5))   # 25
```

### Use
Used for short functions, especially with `map()`, `filter()`, and `sorted()`.

---

## 6. How Can We Achieve Encapsulation in Python?

Encapsulation means restricting direct access to data and exposing it through methods.

### Example
```python
class Employee:
    def __init__(self):
        self.__salary = 50000

    def get_salary(self):
        return self.__salary

e = Employee()
print(e.get_salary())
```

---

## 7. What is the `self` Parameter in a Python Class?

`self` refers to the current object of the class.

### Example
```python
class Student:
    def __init__(self, name):
        self.name = name

s = Student("John")
print(s.name)
```

---

## 8. Which Command is Used to Show All Tables in PostgreSQL?

In the `psql` terminal:

```sql
\dt
```

### Additional Commands
```sql
\dt+
\d table_name
```

---

## 9. Difference Between Modules and Packages in Python

| Module | Package |
|------|------|
| A single `.py` file | A directory containing multiple modules |
| Contains functions/classes | Organizes related modules |
| Example: `math.py` | Example: `numpy`, `pandas` |

---

## 10. Different File Modes in Python

| Mode | Description |
|------|------|
| `r` | Read only |
| `w` | Write (overwrite) |
| `a` | Append |
| `x` | Create new file |
| `r+` | Read and write |
| `w+` | Write and read |
| `a+` | Append and read |
| `rb` | Read binary |
| `wb` | Write binary |

---

## 11. What are PEP 8 Naming Conventions?

| Item | Convention | Example |
|------|------|------|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentRecord` |
| Constant | `UPPER_CASE` | `MAX_SIZE` |
| Module | `lowercase.py` | `utils.py` |
| Private variable | `_single_leading_underscore` | `_temp` |

---

## 12. Can We Use a Tuple as a Key in a Dictionary?

Yes, if all elements inside the tuple are hashable (immutable).

### Example
```python
d = {(1, 2): "point"}
print(d[(1, 2)])
```

### Invalid Example
```python
# Error because list is mutable
d = {([1, 2], 3): "value"}
```

---

## 13. Difference Between Heap and Stack Memory

| Stack Memory | Heap Memory |
|------|------|
| Stores function calls and local references | Stores actual objects |
| Automatically managed | Managed by Python's memory manager and garbage collector |
| Faster access | Slightly slower |
| LIFO structure | Dynamic allocation |

---

## 14. What is the Role of `try`, `except`, `else`, and `finally` in Python?

```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Error")
else:
    print("No exception occurred")
finally:
    print("Always executes")
```

### Purpose
- `try` → Code that may raise an exception.
- `except` → Handles the exception.
- `else` → Runs if no exception occurs.
- `finally` → Runs whether an exception occurs or not.

---

## 15. How Can We Reverse a String in Python?

### Method 1: Slicing
```python
s = "python"
print(s[::-1])   # nohtyp
```

### Method 2: `reversed()`
```python
s = "python"
print(''.join(reversed(s)))
```

### Method 3: Loop
```python
s = "python"
rev = ""
for ch in s:
    rev = ch + rev
print(rev)
```
