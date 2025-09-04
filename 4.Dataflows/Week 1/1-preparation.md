# 📑 Index

- [How the Internet Works](#how-the-internet-works)
- [Technical Writing 101](#technical-writing-101)
- [Rendering Data as UI](#rendering-data-as-ui)
- [Now Showing](#now-showing)
- [Step-through-prep Workshop](#step-through-prep-workshop)
- [Rendering One Card](#rendering-one-card)
- [Composing Elements](#composing-elements)
- [Creating Elements with Functions](#creating-elements-with-functions)
- [Creating Elements with `<template>`](#creating-elements-with-template)
- [Reusable Components](#reusable-components)
- [One-to-One Mappings](#one-to-one-mappings)
- [Using `map`](#using-map)
- [Applying `map`](#applying-map)

---

## How the Internet Works

**Objective:** Understand how your browser, servers, and JavaScript connect.  

1. **The journey of a website**  
   - You type `example.com` → browser asks a **server** → server sends back HTML, CSS, JavaScript.  
   - Browser **renders** the page → JavaScript makes it interactive.  

2. **Key concepts:**  
   - Client (you) ↔ Server (computer elsewhere)  
   - HTTP request/response cycle  
   - Files (HTML, CSS, JS) working together  

📝 **Checkpoint:** Explain to a friend in one sentence what happens when they type a URL in their browser.

---

## Technical Writing 101

**Objective:** Learn how to clearly communicate code and concepts.  

- Write **step-by-step instructions**.  
- Use **plain language** first, then **technical terms**.  
- Add **comments in code** to explain why, not just what.  

Example:  

```js
// BAD: just repeats the code
let x = 10; // set x to 10

// GOOD: explains why
let x = 10; // starting point for our counter
````

📝 **Try it yourself:** Take a code snippet and add helpful comments.

---

## Rendering Data as UI

**Objective:** Connect JavaScript data to what users see.

We often start with **data**:

```js
const movies = ["Shrek", "Finding Nemo", "Toy Story"];
```

We want to **render** it into HTML:

```html
<ul>
  <li>Shrek</li>
  <li>Finding Nemo</li>
  <li>Toy Story</li>
</ul>
```

JavaScript can build this UI dynamically.

📝 **Checkpoint:** Why is it useful to render from data instead of writing HTML manually?

---

## Now Showing

We’ll build a small **movie list app**.
At first: a static list. Later: interactive, reusable, dynamic.

Example project preview:

```
Now Showing 🎬
- Shrek
- Finding Nemo
- Toy Story
```

---

## Step-through-prep Workshop

**Objective:** Learn to break problems into **steps** before coding.

1. Write down **inputs** (movies array).
2. Define **outputs** (HTML list).
3. Plan steps:

   * Loop through movies
   * Create an `<li>` for each
   * Add it to the page

📝 **Checkpoint:** Break down the recipe for making a sandwich into "input → steps → output". (Practice abstraction!)

---

## Rendering One Card

**Objective:** Render one item visually.

```html
<div class="card">
  <h2>Shrek</h2>
</div>
```

JavaScript version:

```js
const movie = "Shrek";
const card = `<div class="card"><h2>${movie}</h2></div>`;
document.body.innerHTML = card;
```

📝 **Try it yourself:** Change `"Shrek"` to your favorite movie.

---

## Composing Elements

**Objective:** Combine multiple elements into bigger UI.

```js
const title = `<h1>Now Showing</h1>`;
const movieCard = `<div class="card"><h2>Shrek</h2></div>`;
document.body.innerHTML = title + movieCard;
```

This is the first step toward **composition**.

---

## Creating Elements with Functions

**Objective:** Use functions to avoid repetition.

```js
function createCard(movie) {
  return `<div class="card"><h2>${movie}</h2></div>`;
}

document.body.innerHTML = createCard("Shrek");
```

📝 **Try it yourself:** Call `createCard` with 3 different movies.

---

## Creating Elements with `<template>`

**Objective:** Use HTML `<template>` for reusable patterns.

```html
<template id="card-template">
  <div class="card"><h2></h2></div>
</template>
```

JavaScript:

```js
const template = document.getElementById("card-template");
const clone = template.content.cloneNode(true);
clone.querySelector("h2").textContent = "Shrek";
document.body.appendChild(clone);
```

---

## Reusable Components

Functions + templates = **components**.
They are the building blocks of modern frameworks (React, Vue, etc.).

📝 **Checkpoint:** Why do you think reusability saves time in coding?

---

## One-to-One Mappings

**Objective:** Map one piece of data to one piece of UI.

Example: each movie → one `<li>`

```js
const movies = ["Shrek", "Finding Nemo", "Toy Story"];
const items = movies.map(movie => `<li>${movie}</li>`);
document.body.innerHTML = `<ul>${items.join("")}</ul>`;
```

---

## Using `map`

* `map` transforms arrays into new arrays.
* Works perfectly for **UI rendering**.

Example:

```js
[1, 2, 3].map(n => n * 2); // [2, 4, 6]
```

📝 **Checkpoint:** What would `[1, 2, 3].map(n => n + 1)` return?

---

## Applying `map`

**Final Project:** Render a movie list with cards.

```js
const movies = ["Shrek", "Finding Nemo", "Toy Story"];

function createCard(movie) {
  return `<div class="card"><h2>${movie}</h2></div>`;
}

const cards = movies.map(createCard).join("");
document.body.innerHTML = `<h1>Now Showing</h1>${cards}`;
```

✅ You’ve built a **mini JavaScript app**!



