# JavaScript & Web Development Interview Questions

## 1. What is Inversion of Control (IoC) in JavaScript?

### Answer
Inversion of Control means giving control of part of your program to another function or framework.

In callbacks, you pass a function to another function and trust it to execute your callback.

```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 1000);
}

fetchData((data) => {
  console.log(data);
});
```

Here, `fetchData()` controls when your callback runs.

---

## 2. What is Callback Hell?

### Answer
Callback Hell occurs when multiple nested callbacks make code difficult to read and maintain.

```js
getUser(function(user) {
  getOrders(user.id, function(orders) {
    getPayment(orders[0], function(payment) {
      console.log(payment);
    });
  });
});
```

### Problems
- Hard to read
- Difficult to debug
- Difficult to maintain

### Solution
Use Promises and Async/Await.

---

## 3. What are Function Annotations in Python?

### Answer
Function annotations specify expected data types for parameters and return values.

```python
def add(a: int, b: int) -> int:
    return a + b
```

- `a: int` → parameter should be integer
- `b: int` → parameter should be integer
- `-> int` → function returns integer

Annotations improve code readability and help type checkers.

---

## 4. What are Some Promise Methods?

### Promise.all()

Waits for all promises to succeed.

```js
Promise.all([p1, p2, p3]);
```

### Promise.allSettled()

Waits for all promises regardless of success or failure.

```js
Promise.allSettled([p1, p2, p3]);
```

### Promise.race()

Returns the first settled promise.

```js
Promise.race([p1, p2]);
```

### Promise.any()

Returns the first successful promise.

```js
Promise.any([p1, p2]);
```

---

## 5. Which Has Higher Priority: Microtask Queue or Callback Queue?

### Answer

Microtask Queue has higher priority.

### Execution Order

1. Call Stack
2. Microtask Queue
3. Callback (Macrotask) Queue

```js
console.log("Start");

setTimeout(() => console.log("Timer"), 0);

Promise.resolve().then(() => {
  console.log("Promise");
});

console.log("End");
```

### Output

```txt
Start
End
Promise
Timer
```

---

## 6. What is Currying?

### Answer

Currying converts a function with multiple arguments into a series of functions that take one argument at a time.

```js
function add(a) {
  return function(b) {
    return a + b;
  };
}

console.log(add(5)(3)); // 8
```

### Benefits

- Code reusability
- Functional programming
- Partial application

---

## 7. What Types of Data Can an API Return?

### Answer

Common API response formats:

### JSON

```json
{
  "name": "John",
  "age": 25
}
```

### XML

```xml
<user>
  <name>John</name>
</user>
```

### HTML

```html
<h1>Hello</h1>
```

### Plain Text

```txt
Success
```

### Images

- PNG
- JPG
- GIF
- SVG

### Files

- PDF
- CSV
- XLSX

---

## 8. Some Commonly Used Events in JavaScript

### Mouse Events

```js
click
dblclick
mouseover
mouseout
```

### Keyboard Events

```js
keydown
keyup
keypress
```

### Form Events

```js
submit
change
input
focus
blur
```

### Window Events

```js
load
resize
scroll
```

### Example

```js
button.addEventListener("click", () => {
  console.log("Button clicked");
});
```

---

## 9. Difference Between Promise.all() and Promise.allSettled()

| Feature | Promise.all() | Promise.allSettled() |
|----------|-------------|-------------------|
| Waits for all promises | Yes | Yes |
| Fails if one fails | Yes | No |
| Returns status of each promise | No | Yes |
| Rejects immediately | Yes | No |

### Example

```js
Promise.all([p1, p2]);
```

If one promise fails, the entire promise rejects.

```js
Promise.allSettled([p1, p2]);
```

Returns:

```js
[
  { status: "fulfilled", value: 10 },
  { status: "rejected", reason: "Error" }
]
```

---

## 10. Difference Between Primitive and Non-Primitive Data Types

| Primitive | Non-Primitive |
|------------|--------------|
| Stored by value | Stored by reference |
| Immutable | Mutable |
| Single value | Collection of values |

### Primitive Types

```js
String
Number
Boolean
Null
Undefined
BigInt
Symbol
```

### Non-Primitive Types

```js
Object
Array
Function
```

### Example

```js
let a = 10;
let b = a;

b = 20;

console.log(a); // 10
```

---

## 11. What is Authorization in API Headers?

### Answer

Authorization is used to verify that a user has permission to access a resource.

### Example

```http
Authorization: Bearer eyJhbGciOi...
```

### Common Types

- Bearer Token
- JWT Token
- API Key
- Basic Authentication

Authorization helps secure APIs and restrict access to authorized users.

---

## 12. What is the delete Operator in JavaScript?

### Answer

The `delete` operator removes a property from an object.

```js
const user = {
  name: "John",
  age: 25
};

delete user.age;

console.log(user);
```

### Output

```js
{
  name: "John"
}
```

### Note

- Deletes object properties
- Does not delete variables declared using `let`, `const`, or `var`

---

## 13. How Browser Rendering Works?

### Step 1: Parse HTML

Creates the DOM Tree.

### Step 2: Parse CSS

Creates the CSSOM Tree.

### Step 3: Create Render Tree

Combines DOM and CSSOM.

### Step 4: Layout

Calculates position and size of elements.

### Step 5: Paint

Draws elements on the screen.

### Step 6: Composite

Combines layers and displays the final page.

### Flow

```txt
HTML → DOM
CSS → CSSOM
DOM + CSSOM
      ↓
 Render Tree
      ↓
   Layout
      ↓
    Paint
      ↓
  Composite
```

---

## 14. What is JSON Format?

### Answer

JSON (JavaScript Object Notation) is a lightweight text-based format used to exchange data between systems.

### Example

```json
{
  "name": "John",
  "age": 25,
  "city": "Hyderabad"
}
```

### Rules

- Data is stored as key-value pairs.
- Keys must be enclosed in double quotes.
- Supports objects, arrays, strings, numbers, booleans, and null.

### Convert Object to JSON

```js
JSON.stringify(obj);
```

### Convert JSON to Object

```js
JSON.parse(jsonData);
```

**JSON is a lightweight text-based data format used for exchanging data between a client and a server.**
