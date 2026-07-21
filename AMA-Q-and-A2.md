## 1. What is React?

React is a **JavaScript library** used for building **interactive and reusable user interfaces (UI)**, especially for **Single Page Applications (SPAs)**.

It allows developers to create applications using **components**, making code reusable, maintainable, and easier to manage.

### Features
- Component-based architecture
- Virtual DOM for faster rendering
- Reusable UI components
- One-way data flow
- Declarative programming

**Example:**
```jsx
function App() {
  return <h1>Hello React!</h1>;
}
```

---

## 2. Who developed React?

React was developed by **Jordan Walke**, a software engineer at **Meta (formerly Facebook)**.

- First created in **2011**
- First released publicly in **2013**
- Currently maintained by **Meta** and the open-source community.

---

## 3. What is React DOM?

React DOM is a package that connects **React components** with the **browser's DOM (Document Object Model)**.

It is responsible for:
- Rendering React components into the webpage
- Updating the DOM efficiently using the Virtual DOM
- Handling UI updates automatically

**Example:**

```jsx
import ReactDOM from "react-dom/client";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```

Here:
- `createRoot()` creates the React application.
- `render()` displays the component on the webpage.

---

## 4. What is JSX?

JSX stands for **JavaScript XML**.

It is a syntax extension that allows us to write **HTML-like code inside JavaScript**.

Browsers cannot understand JSX directly. It is converted into JavaScript by **Babel** during compilation.

### Example

```jsx
const element = <h1>Hello React</h1>;
```

Behind the scenes, Babel converts it into:

```javascript
const element = React.createElement("h1", null, "Hello React");
```

### Advantages
- Easier to read
- Looks similar to HTML
- Makes UI development simpler
- Allows JavaScript expressions inside HTML

Example:

```jsx
const name = "John";

function App() {
  return <h1>Hello {name}</h1>;
}
```

---

## 5. What is a Component in React?

A component is a **reusable piece of UI**.

Instead of writing the same HTML multiple times, we create a component once and use it anywhere.

### Types of Components

#### Functional Component (Recommended)

```jsx
function Welcome() {
  return <h1>Welcome!</h1>;
}
```

#### Class Component (Older way)

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Welcome!</h1>;
  }
}
```

### Advantages
- Reusable
- Easy to maintain
- Modular
- Improves code organization

---

## 6. What are Hooks?

Hooks are special functions introduced in **React 16.8** that allow **functional components** to use React features such as state and lifecycle methods.

Before Hooks, these features were only available in class components.

### Common Hooks

| Hook | Purpose |
|------|----------|
| `useState()` | Manage state |
| `useEffect()` | Handle side effects |
| `useContext()` | Access context values |
| `useRef()` | Access DOM elements |
| `useMemo()` | Optimize expensive calculations |
| `useCallback()` | Memoize functions |
| `useReducer()` | Complex state management |

### Example

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h2>{count}</h2>
      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </>
  );
}
```

---

## 7. What are Props?

Props stands for **Properties**.

Props are used to **pass data from a parent component to a child component**.

Props are **read-only**, meaning a child component cannot modify them.

### Example

Parent Component:

```jsx
function App() {
  return <Student name="Sulochana" age={22} />;
}
```

Child Component:

```jsx
function Student(props) {
  return (
    <>
      <h2>{props.name}</h2>
      <p>{props.age}</p>
    </>
  );
}
```

Output:

```
Sulochana
22
```

### Destructuring Props

```jsx
function Student({ name, age }) {
  return (
    <>
      <h2>{name}</h2>
      <p>{age}</p>
    </>
  );
}
```

### Advantages
- Pass data between components
- Makes components reusable
- Enables dynamic UI
- Supports one-way data flow
