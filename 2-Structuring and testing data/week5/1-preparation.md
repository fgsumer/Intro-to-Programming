# 📖 Index

* [Clocks](#clocks)
* [Comparison](#comparison)
* [Assertions](#assertions)
* [Interpreting errors](#interpreting-errors)
* [Interpreting this error](#interpreting-this-error)
* [Reusing variable names](#reusing-variable-names)
* [Strategy](#strategy)
* [Conditionality](#conditionality)
* [Sub-goal](#sub-goal)
* [Strings](#strings)
* [Testing a sub-goal](#testing-a-sub-goal)
* [Sub-goal #2](#sub-goal-2)
* [Refactoring repetition](#refactoring-repetition)
* [Identifying missing tests](#identifying-missing-tests)

---

## Clocks

**Learning goal:** Understand how computers handle time.

```js
const now = new Date();
console.log(now);
```

✅ *Reflection:* What changes if you run this code again one minute later?

**Exercise:** Print the current hour and minute.

---

## Comparison

**Learning goal:** Learn how to compare values.

```js
console.log(5 > 3);   // true
console.log(5 === 5); // true
console.log(5 !== 2); // true
```

✅ *Reflection:* How does `===` differ from `==`?

**Exercise:** Check if the current hour is equal to 12.

---

## Assertions

**Learning goal:** Practice testing assumptions.

```js
console.assert(2 + 2 === 4, "Math is broken!");
```

✅ *Reflection:* Why is it helpful to assert things in code?

**Exercise:** Assert that `now.getFullYear()` equals the current year.

---

## Interpreting errors

**Learning goal:** Errors are your friends!

```js
console.log(x);
// ReferenceError: x is not defined
```

✅ *Reflection:* What does the error message tell you?

**Exercise:** Intentionally cause an error and explain it in plain English.

---

## Interpreting this error

**Learning goal:** Focus on *this specific* error.

```js
const name = "Alex";
console.log(Name);
// ReferenceError: Name is not defined
```

✅ *Reflection:* Why is JavaScript complaining?

**Exercise:** Fix the error above.

---

## Reusing variable names

**Learning goal:** Avoid overwriting accidentally.

```js
let age = 20;
age = 21; // allowed
let age = 22; // ❌ error if in same block
```

✅ *Reflection:* Why might reusing variable names cause bugs?

**Exercise:** Create a variable and try redeclaring it with `let`.

---

## Strategy

**Learning goal:** Learn problem-solving strategies.

* Break the problem into **sub-goals**.
* Write small tests.
* Fix one error at a time.

✅ *Reflection:* Why is “divide and conquer” a good coding strategy?

**Exercise:** Describe your own coding strategy in one sentence.

---

## Conditionality

**Learning goal:** Make programs react to conditions.

```js
const hour = new Date().getHours();
if (hour < 12) {
  console.log("Good morning!");
} else {
  console.log("Good afternoon!");
}
```

✅ *Reflection:* How does the output change if you test at night?

**Exercise:** Write a program that prints “Good evening!” if the time is after 6pm.

---

## Sub-goal

**Learning goal:** Tackle small pieces of a bigger problem.

Example problem: Print greeting depending on time.

* Sub-goal 1: Get current hour.
* Sub-goal 2: Compare with 12.
* Sub-goal 3: Print correct message.

✅ *Reflection:* Why are sub-goals easier than solving the whole problem at once?

---

## Strings

**Learning goal:** Work with text.

```js
const greeting = "Hello";
const name = "Sam";
console.log(greeting + ", " + name);
```

✅ *Reflection:* What’s the difference between numbers and strings?

**Exercise:** Write a string that says “Today is \[day]”.

---

## Testing a sub-goal

**Learning goal:** Test partial progress.

```js
const day = new Date().getDay();
console.log(day); // Test output
```

✅ *Reflection:* Why test before finishing the full program?

---

## Sub-goal #2

**Learning goal:** Build on earlier progress.

If sub-goal #1 works, move to the next step:

```js
if (day === 0) {
  console.log("It’s Sunday!");
}
```

✅ *Reflection:* How does completing sub-goal #1 help with #2?

---

## Refactoring repetition

**Learning goal:** Avoid writing the same code twice.

```js
// Before:
console.log("Hello Alice");
console.log("Hello Bob");

// After:
function greet(name) {
  console.log("Hello " + name);
}
greet("Alice");
greet("Bob");
```

✅ *Reflection:* Why is refactoring important?

**Exercise:** Refactor three repeated lines of code into a function.

---

## Identifying missing tests

**Learning goal:** Test more cases.

```js
function isEven(n) {
  return n % 2 === 0;
}

console.assert(isEven(2) === true);
console.assert(isEven(3) === false);
```

✅ *Reflection:* What happens if you never test `0` or negative numbers?

**Exercise:** Add at least two new tests.

---

## 🎯 Final Note

Learning JavaScript is about:

1. **Understanding concepts** (read examples).
2. **Practicing** (write and run code).
3. **Reflecting** (ask why it works or fails).

👉 Remember: Errors are not failures—they are guides!
