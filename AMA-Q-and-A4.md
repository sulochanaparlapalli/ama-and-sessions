## 1. What is the `pass` statement in Python?

The `pass` statement is a **null (empty) statement** in Python. It does nothing when executed and is used as a placeholder where Python syntax requires a statement.

### Example

```python
def greet():
    pass

class Student:
    pass

if True:
    pass
```

---

## 2. What are the different types of functions in JavaScript?

JavaScript provides several ways to define functions. Each type has a specific use case.


### 1. Function Declaration (Named Function)

A function declared using the `function` keyword. It is **hoisted**, meaning it can be called before its definition.

### Example

```javascript
greet();

function greet() {
    console.log("Hello, World!");
}
```

**Use Case:** General-purpose reusable functions.

---

### 2. Function Expression

A function assigned to a variable. It is **not hoisted** like function declarations.

### Example

```javascript
const greet = function () {
    console.log("Hello!");
};

greet();
```

**Use Case:** When functions need to be stored in variables or passed as arguments.

---

### 3. Arrow Function (ES6)

A shorter syntax introduced in ES6. It does **not** have its own `this`, `arguments`, or `super`.

### Example

```javascript
const add = (a, b) => a + b;

console.log(add(5, 3));
```

**Use Case:** Callback functions, array methods, and concise code.

---

### 4. Anonymous Function

A function without a name, often used as a callback.

### Example

```javascript
setTimeout(function () {
    console.log("Executed after 2 seconds");
}, 2000);
```

**Use Case:** One-time operations and callbacks.

---

### 5. Immediately Invoked Function Expression (IIFE)

A function that executes immediately after it is defined.

### Example

```javascript
(function () {
    console.log("IIFE Executed");
})();
```

**Use Case:** Creating a private scope and avoiding global variable pollution.

---

### 6. Callback Function

A function passed as an argument to another function.

### Example

```javascript
function greet(name, callback) {
    console.log("Hello " + name);
    callback();
}

function bye() {
    console.log("Goodbye!");
}

greet("John", bye);
```

**Use Case:** Asynchronous programming, event handling, and array methods.

---

### 7. Higher-Order Function

A function that accepts another function as an argument or returns a function.

### Example

```javascript
const numbers = [1, 2, 3, 4];

const squares = numbers.map(function (num) {
    return num * num;
});

console.log(squares);
```

**Use Case:** Functional programming (`map`, `filter`, `reduce`).

---

### 8. Generator Function

A special function that can pause and resume execution using the `yield` keyword.

### Example

```javascript
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = numbers();

console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
```

**Use Case:** Lazy evaluation and custom iterators.

---

### 9. Async Function

Used for asynchronous programming with `async` and `await`.

### Example

```javascript
async function fetchData() {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
}
```

**Use Case:** Handling promises in a clean and readable way.

---

## 3. What happens if we don't pass a dependency array in `useEffect()`?

If no dependency array is provided, the `useEffect()` hook runs **after every render** of the component.

### Example

```jsx
useEffect(() => {
    console.log("Runs after every render");
});
```

### When it runs

- Initial render 
- Every state update 
- Every prop update 


---

## 4. Difference between Props and State in React

| Props | State |
|--------|-------|
| Passed from parent component | Managed inside the component |
| Read-only | Can be updated |
| Immutable | Mutable |
| Used to pass data | Used to store changing data |
| Controlled by parent | Controlled by component itself |

### Props Example

```jsx
function Welcome(props) {
    return <h1>Hello {props.name}</h1>;
}
```

---

### State Example

```jsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>
    Increment
</button>
```

---

## 5. What are Serializers in Django REST Framework?

A **Serializer** converts complex Python objects (like Django models) into JSON and converts JSON back into Python objects.

It acts as a bridge between Django models and API responses.

### Example

```python
from rest_framework import serializers
from .models import Student

class StudentSerializer(serializers.ModelSerializer):
    class Meta:
        model = Student
        fields = "__all__"
```

### Types of Serializers

- Serializer
- ModelSerializer
- HyperlinkedModelSerializer

---

## 6. Difference between Docker Image and Docker Container

| Docker Image | Docker Container |
|--------------|------------------|
| Blueprint/template | Running instance of an image |
| Read-only | Read-write |
| Cannot execute by itself | Executes applications |
| Created using Dockerfile | Created from an image |
| Multiple containers can use one image | Each container has its own state |

### Example

Build image:

```bash
docker build -t myapp .
```

Run container:

```bash
docker run myapp
```

### Simple Analogy

- Image → Recipe
- Container → Cooked food

---

## 7. Difference between DELETE and TRUNCATE in SQL

| DELETE | TRUNCATE |
|---------|----------|
| Removes selected rows | Removes all rows |
| Can use WHERE clause | Cannot use WHERE |
| Slower | Faster |
| Logged row by row | Minimal logging |
| Can rollback (inside transaction) | Depends on DBMS |
| Does not reset identity | Resets identity in many DBMSs |

### DELETE Example

```sql
DELETE FROM Employees
WHERE id = 5;
```

---

### TRUNCATE Example

```sql
TRUNCATE TABLE Employees;
```

---

## 8. What is a CSRF Token?

### Answer

**CSRF (Cross-Site Request Forgery)** is a security attack where an attacker tricks a logged-in user into performing unwanted actions on a website.

A **CSRF token** is a unique, secret value generated by the server and included with forms or requests. The server verifies this token before processing the request.
It prevents attackers from submitting forged requests on behalf of authenticated users.

### Django Example

```html
<form method="POST">
    {% csrf_token %}
    <button type="submit">Submit</button>
</form>
```

### How it works

1. User logs in.
2. Server generates a CSRF token.
3. Token is included in forms or request headers.
4. User submits the request.
5. Server validates the token.
6. If valid, the request is processed; otherwise, it is rejected.

