## Welcome to your journey into programming with JavaScript!

## 📖 Index

* [Define a Computer](#define-a-computer)
* [Interface](#interface)
* [Terminal](#terminal)
* [Data](#data)
* [REPL](#repl)
* [Prep Dir](#prep-dir)
* [Variables](#variables)
* [Declarations and Statements](#declarations-and-statements)
* [Functions](#functions)
* [Scripts](#scripts)
* [Logging](#logging)
* [Errors](#errors)
* [Percentages](#percentages)
* [Defining Functions](#defining-functions)
* [Playing Computer](#playing-computer)
* [Scope](#scope)
* [Return](#return)
* [Reuse](#reuse)
* [Parameters](#parameters)
* [Solving Problems with Functions ](#solving-problems-with-functions-)

---

## Define a Computer

A **computer** is a machine that:

1. Takes **input** (keyboard, mouse, sensors).
2. Processes it (using logic + memory).
3. Produces **output** (screen, sound, files).

👉 **Reflection**: Can you think of three devices that are computers but don’t look like one?

---

## Interface

An **interface** is how humans and computers communicate.

* Graphical: windows, buttons, icons.
* Textual: command line or terminal.

👉 **Try this**: Open your computer’s calculator. That’s a graphical interface!

---

## Terminal

The **terminal** is a text interface where you type commands.
It’s powerful because you can:

* Navigate files
* Run programs
* Automate tasks

👉 **Challenge**: Open your terminal. Type `pwd` (Linux/Mac) or `cd` (Windows PowerShell) to see “where you are.”

---

## Data

**Data** = information computers store and process. Examples:

* Numbers: `42`
* Text (strings): `"Hello"`
* Boolean: `true`, `false`

👉 **Quick Recall**: Which of these is NOT data?
`"cat"`, `99`, `open door`, `false`

---

## REPL

**REPL** = *Read–Eval–Print–Loop*.
It lets you run JavaScript interactively.

* Try it in your terminal:

```bash
node
```

Now type:

```js
2 + 2
```

👉 **Activity**: Experiment with `*`, `/`, `-` until you find something surprising.

---

## Prep Dir

Create a dedicated project folder:

```bash
mkdir js-beginner
cd js-beginner
```

This is your coding playground 🎡

---

## Variables

Variables store data:

```js
let name = "Sam";
let age = 25;
```

Think of them as *labeled boxes*.

👉 **Mini-Quiz**: What’s in the box after this?

```js
let x = 10;
x = x + 5;
```

---

## Declarations and Statements

* **Declaration**: introducing something (`let x;`).
* **Statement**: a full instruction (`let x = 10;`).

👉 **Play computer**: Predict what this does:

```js
let y;
y = 7;
y = y + 3;
```

---

## Functions

Functions = reusable chunks of code.

```js
function greet() {
  console.log("Hello!");
}
```

👉 **Task**: Write a function that says your name.

---

## Scripts

Instead of REPL, save code in a file:
`hello.js`

```js
console.log("Hello from file!");
```

Run it:

```bash
node hello.js
```

---

## Logging

We “log” to see what’s happening.

```js
console.log("Debugging here!");
```

👉 **Experiment**: Log a number, a string, and a math operation.

---

## Errors

Errors are feedback, not failure.
Example:

```js
consle.log("typo!");
```

👉 **Exercise**: Introduce an error on purpose and fix it.

---

## Percentages

Let’s apply math:

```js
let score = 45;
let total = 50;
let percentage = (score / total) * 100;
console.log(percentage);
```

👉 **Try**: Change `score` and `total` and predict the output.

---

## Defining Functions

Functions can take inputs (parameters):

```js
function greet(name) {
  console.log("Hello, " + name);
}
greet("Alex");
```

---

## Playing Computer

**Playing computer** = stepping through code manually.

👉 **Activity**: Pretend you are the computer:

```js
let a = 2;
let b = 3;
a = a + b;
b = a * 2;
```

Track values of `a` and `b`.

---

## Scope

Variables live in different “scopes.”

```js
function test() {
  let inside = "secret";
}
console.log(inside); // ❌ Error
```

👉 **Reflect**: Why does the error happen?

---

## Return

Functions can **return** values:

```js
function add(x, y) {
  return x + y;
}
let result = add(5, 10);
console.log(result);
```

---

## Reuse

Once defined, functions can be reused many times.
👉 Write a function `double(x)` and call it with 3 different values.

---

## Parameters

Parameters make functions flexible:

```js
function area(width, height) {
  return width * height;
}
console.log(area(5, 10));
```

---

## Solving Problems with Functions 📼

🎥 Practice session:

1. Write a function that converts minutes to seconds.
2. Write a function that calculates the average of three numbers.
3. Write a function that tells if a number is even.

👉 **Tip**: Work in pairs, explain your code aloud. Teaching strengthens memory!

---

✅ Congratulations — you’ve covered the foundation of programming with JavaScript!
