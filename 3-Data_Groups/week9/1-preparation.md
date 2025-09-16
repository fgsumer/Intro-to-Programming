# 📚 Index

- [User Interfaces](#user-interfaces)
- [Implementing a Character Limit](#implementing-a-character-limit)
- [Step-through-Prep Workshop](#step-through-prep-workshop)
- [Breaking Down the Strategy](#breaking-down-the-strategy)
- [The DOM](#the-dom)
- [Querying the DOM](#querying-the-dom)
- [Calculating the Remaining Characters](#calculating-the-remaining-characters)
- [Updating the Interface](#updating-the-interface)
- [Timers](#timers)
- [DOM Events](#dom-events)
- [Reacting to Events](#reacting-to-events)
- [Check Progress](#check-progress)
- [Refactor](#refactor)

---

## User Interfaces
A **user interface (UI)** is how humans interact with software.  
In JavaScript, we often make UIs dynamic: they **respond to input, clicks, and changes**.

👉 Example: A text box that shows how many characters you can still type.

---

## Implementing a Character Limit
Imagine Twitter’s post box:  
- You type text.  
- It shows how many characters you have left.  

We’ll recreate this.

**HTML Starter Code:**
```html
<textarea id="tweetInput" maxlength="50"></textarea>
<p id="charCount">50 characters left</p>
````

---

## Step-through-Prep Workshop

Before writing JavaScript, we **plan the steps** (like a recipe).
Cognitive science shows planning reduces **cognitive load**.

1. Find the text area.
2. Find the counter.
3. Detect when text changes.
4. Update remaining characters.

---

## Breaking Down the Strategy

We’ll **divide big problems into small ones** (chunking).

* Step 1: Access the text box.
* Step 2: Access the message.
* Step 3: Calculate remaining characters.
* Step 4: Display the result.

---

## The DOM

The **Document Object Model (DOM)** represents your web page as a tree of objects.
JavaScript lets us **query** and **change** the DOM.

---

## Querying the DOM

```js
const textBox = document.getElementById("tweetInput");
const counter = document.getElementById("charCount");
```

✅ Now `textBox` and `counter` are references to real HTML elements.

---

## Calculating the Remaining Characters

```js
function updateCounter() {
  const max = 50;
  const remaining = max - textBox.value.length;
  return remaining;
}
```

---

## Updating the Interface

```js
function updateUI() {
  const remaining = updateCounter();
  counter.textContent = `${remaining} characters left`;
}
```

---

## Timers

We can run code every X milliseconds with `setInterval`.
Example: Check typing progress every half second.

```js
setInterval(updateUI, 500);
```

---

## DOM Events

A better way than timers is **events**.
Events fire exactly when something happens.

```js
textBox.addEventListener("input", updateUI);
```

Now the UI updates instantly when typing.

---

## Reacting to Events

We’ve now created a **responsive UI**:

* User types → JavaScript reacts → UI updates.

This is the **core of interactive programming**.

---

## Check Progress

📝 Quick quiz:

1. What does the DOM represent?
2. Which method finds an element by ID?
3. Why are events better than timers here?

Try answering without looking back (retrieval practice).

---

## Refactor

Good developers **refactor**: improve code without changing behavior.

Example: Combine functions into a cleaner version:

```js
const textBox = document.getElementById("tweetInput");
const counter = document.getElementById("charCount");
const max = 50;

textBox.addEventListener("input", () => {
  const remaining = max - textBox.value.length;
  counter.textContent = `${remaining} characters left`;
});
```

---

✅ Congratulations! You’ve built your **first interactive UI with JavaScript**.
Next step: experiment with different limits, styles, or even add a **warning when near the limit**.




