# 📑 Index

1. [Ordinal Numbers](#ordinal-numbers)
2. [Testing Frameworks](#testing-frameworks)
3. [Starting a Project](#starting-a-project)
4. [Using Packages](#using-packages)
5. [Installing Jest](#installing-jest)
6. [Jest's API](#jests-api)
7. [First Test Case](#first-test-case)
8. [Interpreting Feedback](#interpreting-feedback)
9. [Generalising Further](#generalising-further)
10. [Anonymous Functions](#anonymous-functions)
11. [Arrow Functions](#arrow-functions)
12. [Solving Problems While Testing](#solving-problems-while-testing)

---

## 1. Ordinal Numbers

**Concept:** Numbers like 1st, 2nd, 3rd are called *ordinal numbers*. We’ll write a function to convert a number into its ordinal form.

```javascript
function toOrdinal(n) {
  if (n === 1) return "1st";
  if (n === 2) return "2nd";
  if (n === 3) return "3rd";
  return n + "th";
}

console.log(toOrdinal(1)); // "1st"
console.log(toOrdinal(4)); // "4th"
```

👉 **Exercise:** Extend this function so it works correctly for 11th, 12th, and 13th.

---

## 2. Testing Frameworks

**Concept:** Instead of checking outputs manually, developers use **testing frameworks**.

* They automate testing.
* They help prevent errors when code grows.

Popular frameworks: **Jest (JavaScript)**, **Pytest (Python)**, **JUnit (Java)**.

---

## 3. Starting a Project

1. Create a new folder:

   ```bash
   mkdir my-first-project && cd my-first-project
   ```
2. Initialize Node.js:

   ```bash
   npm init -y
   ```

This creates a `package.json` file, your project’s **blueprint**.

---

## 4. Using Packages

**Packages** are reusable pieces of code.
Example: lodash, express, jest.

👉 Install a package:

```bash
npm install lodash
```

Now you can use it:

```javascript
const _ = require("lodash");

console.log(_.capitalize("hello world")); // "Hello world"
```

---

## 5. Installing Jest

Jest is a **testing framework** for JavaScript.

```bash
npm install --save-dev jest
```

Update `package.json`:

```json
"scripts": {
  "test": "jest"
}
```

---

## 6. Jest's API

Key functions:

* `test(name, fn)` → defines a test.
* `expect(value)` → creates an expectation.
* `.toBe(expected)` → compares values.

---

## 7. First Test Case

Create `ordinal.test.js`:

```javascript
const toOrdinal = require("./ordinal");

test("converts 1 to 1st", () => {
  expect(toOrdinal(1)).toBe("1st");
});
```

Run:

```bash
npm test
```

---

## 8. Interpreting Feedback

Example Jest output:

```
FAIL  ./ordinal.test.js
  ✕ converts 1 to 1st (5ms)

Expected: "1st"
Received: "1th"
```

👉 This tells us exactly what went wrong.

---

## 9. Generalising Further

Instead of writing many `if` statements, we can generalise:

```javascript
function toOrdinal(n) {
  const s = ["th", "st", "nd", "rd"];
  const v = n % 100;
  return n + (s[(v - 20) % 10] || s[v] || s[0]);
}
```

---

## 10. Anonymous Functions

Functions without a name:

```javascript
setTimeout(function() {
  console.log("Hello after 2 seconds");
}, 2000);
```

---

## 11. Arrow Functions

Shorter way to write functions:

```javascript
setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);
```

👉 Try rewriting your `toOrdinal` function as an arrow function.

---

## 12. Solving Problems While Testing

Tests act as a **safety net**:

1. Write a failing test first (**Red**).
2. Fix the code (**Green**).
3. Refactor for clarity (**Refactor**).

This is called **Test-Driven Development (TDD)**.

---

✅ Congratulations! You now:

* Understand functions and testing.
* Know how to start projects.
* Can write, test, and improve code systematically.



