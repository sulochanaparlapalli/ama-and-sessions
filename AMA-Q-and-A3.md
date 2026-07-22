
## 1. What is `flatMap()` in JavaScript?

`flatMap()` is an array method that first applies a function to each element using `map()`, and then flattens the result by one level.

It is equivalent to:

```javascript
array.map(callback).flat();
```

### Example

```javascript
const numbers = [1, 2, 3];

const result = numbers.flatMap(num => [num, num * 2]);

console.log(result);
```

**Output**

```javascript
[1, 2, 2, 4, 3, 6]
```

---

## 2. What is `flat()` in JavaScript arrays?

`flat()` is used to convert nested arrays into a single array.

### Syntax

```javascript
array.flat(depth)
```

- Default depth = 1

### Example 1

```javascript
const arr = [1, 2, [3, 4]];

console.log(arr.flat());
```

---

## 3. What is the difference between `undefined` and `not defined`?

### `undefined`

A variable exists but has no value assigned.

```javascript
let a;

console.log(a);
```

Output

```javascript
undefined
```

---

### `not defined`

A variable was never declared.

```javascript
console.log(b);
```

Output

```javascript
ReferenceError: b is not defined
```

---

### Difference Table

| undefined | not defined |
|------------|-------------|
| Variable is declared | Variable is not declared |
| Value is missing | Variable doesn't exist |
| No error | ReferenceError |
| Type is undefined | No type because variable doesn't exist |

---

## 4. What is the difference between `package.json` and `package-lock.json`?

### package.json

- Created by developer.
- Contains project information.
- Lists dependencies.
- Lists scripts.
- Specifies version ranges.

Example

```json
{
  "name": "react-app",
  "version": "1.0.0",
  "dependencies": {
    "react": "^19.0.0"
  }
}
```

---

### package-lock.json

- Automatically created by npm.
- Stores the exact version of every package.
- Ensures everyone installs identical dependencies.
- Improves installation speed.

Example

```json
{
  "react": {
    "version": "19.0.1"
  }
}
```

---

### Difference Table

| package.json | package-lock.json |
|---------------|-------------------|
| Created manually | Generated automatically |
| Stores dependency ranges | Stores exact versions |
| Used for project configuration | Used for reproducible installs |
| Can be edited | Usually not edited manually |

---

## 5. What is Virtual DOM (VDOM)?

The Virtual DOM is a lightweight JavaScript copy of the real DOM.

Instead of updating the browser DOM directly, React:

1. Creates a Virtual DOM.
2. Compares the new Virtual DOM with the previous one (Diffing).
3. Finds only the changed elements.
4. Updates only those changes in the real DOM.

### Flow

```
State Changes
      ↓
New Virtual DOM
      ↓
Compare with Old Virtual DOM
      ↓
Find Differences (Diffing)
      ↓
Update Only Changed Nodes
      ↓
Real DOM
```

### Benefits

- Faster updates
- Better performance
- Less DOM manipulation

---


## 6. Why is React faster than direct DOM manipulation?

React is faster because it minimizes expensive DOM operations.

### Without React

```javascript
document.getElementById("count").innerHTML = count;
```

Every update directly modifies the real DOM, which is relatively slow.

---

### With React

When state changes:

1. React creates a new Virtual DOM.
2. Compares it with the previous Virtual DOM.
3. Identifies only the changed elements.
4. Updates only those elements in the real DOM.

This process is called **Reconciliation**.

### Example

Suppose a page contains:

- Navbar
- Sidebar
- Profile
- Footer

Only the profile name changes.

**Without React**

The browser may perform unnecessary DOM work.

**With React**

Only the profile name node is updated.
