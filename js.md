# JavaScript Interview Questions & Answers

## 1. What is a Callback?

A callback is a function passed as an argument to another function and executed later.

```js
function greet(name, callback) {
  console.log("Hello " + name);
  callback();
}

function done() {
  console.log("Task completed");
}

greet("User", done);
```

---

## 2. What is Spread Operator?

The spread operator (...) expands elements of an array or object.

```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2);
```

---

## 3. What is Strict Mode?

Strict mode helps write safer JavaScript by catching errors.

```js
"use strict";

function strictFunction() {
  x = 10; // ReferenceError: x is not defined
}
```

---

## 4. How to Export File in JavaScript? 

```js
// file.js
export const name = "S";

export function greet() {
  console.log("Hello");
}
```

```js
import { name, greet } from "./file.js";
```

---

## 5. What is Short Circuit Evaluation?

Logical operators stop execution early.

```js
console.log(true && "Hello"); // Hello
console.log(false || "World"); // World
```

Used for default values and condition checks.

---

## 6. Name Some DOM Selectors
 
- getElementById()
- getElementsByClassName()
- getElementsByTagName()
- querySelector()
- querySelectorAll()

---

## 7. What is a Closure?

A closure is a function that remembers variables from its outer scope.

```js
function outer() {
  const message = "Hello";
  return function inner() {
    console.log(message);
  };
}

const closure = outer();
closure(); // Hello
```

---

## 8. Difference Between setTimeout and setInterval.

- `setTimeout` executes a function once after a specified delay.
- `setInterval` executes a function repeatedly at a specified interval.

```js
setTimeout(() => {
  console.log("Hello");
}, 1000);

setInterval(() => {
  console.log("Hello");
}, 1000);
```

---

## 9. What is Memoization?

Memoization is an optimization technique that stores function results to avoid repeated calculations.

---

## 10. What are Event Listeners?

Event listeners detect user actions like click, input, etc.

```js
button.addEventListener("click", () => {
  console.log("Clicked!");
});
```

---

## 11. What is Event Handling?

Event handling is the process of responding to user interactions.

```js
function handleClick() {
  alert("Button clicked");
}
```

---

## 12. Convert String to Integer

```js
const num = parseInt("123");
console.log(num); // 123
const num1 = Number("123");
console.log(num1); // 123
```

---

## 13. What is alert() Method?

Displays a popup message.

```js
alert("Hello");
```

## 14. concat two arrays into third without using concat or + operator

```js
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [...arr1, ...arr2];
console.log(arr3); // [1, 2, 3, 4, 5, 6]
```

---

## 15. What is the difference between let and var?
- `let` is block-scoped and can be reassigned.
- `var` is function-scoped and can be reassigned.
- `let` is not hoisted, while `var` is hoisted.
- `let` has block scope, while `var` has function scope.
