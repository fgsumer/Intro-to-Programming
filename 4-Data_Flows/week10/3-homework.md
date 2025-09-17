# JavaScript Homework: Building a Movie Card Gallery

---

## Exercise 1: The Blueprint - Planning and the `<template>` (Step-through-prep)

**Goal:** Plan your data structure and create a static HTML template for a single movie card. This is the "blueprint" for your dynamic content.

**Instructions:**

1.  **Data Structure:** Define a sample movie object in a new `scripts/data.js` file. This object will represent the structure of your data.
    ```javascript
    // scripts/data.js
    const sampleMovie = {
        title: "The Shawshank Redemption",
        year: 1994,
        director: "Frank Darabont",
        genre: "Drama",
        rating: 9.3,
        posterUrl: "https://via.placeholder.com/300x450/2c3e50/ffffff?text=Shawshank+Redemption", // Use a placeholder image
        description: "Two imprisoned men bond over a number of years, finding solace and eventual redemption through acts of common decency."
    };
    ```

2.  **HTML Template:** In your `index.html`, create a `<template>` element with the ID `movie-card-template`. This template should use the properties from your `sampleMovie` object to structure the card. Use semantic HTML tags where appropriate (e.g., `<article>`, `<img>`, `<h2>`).
    ```html
    <!-- index.html -->
    <template id="movie-card-template">
        <article class="movie-card">
            <img class="movie-poster" src="" alt="Movie poster for ">
            <div class="movie-info">
                <h2 class="movie-title"></h2>
                <p class="movie-year"></p>
                <p class="movie-director">Directed by <span></span></p>
                <p class="movie-genre"></p>
                <p class="movie-rating">Rating: <span></span>/10</p>
                <p class="movie-description"></p>
            </div>
        </article>
    </template>
    ```

**What you're practicing:** `Creating Elements with <template>`, `Step-through-prep Workshop` (planning your component structure based on your data).

---

## Exercise 2: The Factory - Creating a Reusable Component Function

**Goal:** Write a function that takes a movie object, clones the `<template>`, injects the movie data into it, and returns a fully-built DOM element. This is your "component factory."

**Instructions:**

1.  **Component Function:** In a new `scripts/component.js` file, create a function called `createMovieCardComponent(movie)`.
2.  **Clone the Template:** Inside the function, use `document.getElementById()` to get your template and clone its content.
3.  **Populate with Data:** For each property in the `movie` object, find the corresponding element inside the cloned template and set its `textContent` or `src` attribute.
4.  **Return the Component:** Finally, return the cloned and populated DOM element.

    ```javascript
    // scripts/component.js
    function createMovieCardComponent(movie) {
        // 1. Get the template element and clone its content
        const template = document.getElementById('movie-card-template');
        const card = template.content.cloneNode(true).firstElementChild;

        // 2. Find elements inside the cloned card
        const posterImg = card.querySelector('.movie-poster');
        const titleElement = card.querySelector('.movie-title');
        const yearElement = card.querySelector('.movie-year');
        // ... find other elements (director, genre, etc.)

        // 3. Populate the elements with data from the movie object
        posterImg.src = movie.posterUrl;
        posterImg.alt = `Movie poster for ${movie.title}`;
        titleElement.textContent = movie.title;
        yearElement.textContent = movie.year;
        // ... populate other elements

        // 4. Return the fully built card
        return card;
    }
    ```

**What you're practicing:** `Rendering One Card`, `Creating Elements with Functions`, `Reusable Components`, `Composing Elements`.

---

## Exercise 3: The Gallery - Rendering a List with `.map()`

**Goal:** Use an array of movie data and the `.map()` method to render a full gallery of movie cards onto the webpage.

**Instructions:**

1.  **Import Data:** In your main `scripts/app.js` file, import your array of movies. You can start by creating a simple array with 3-4 movie objects based on your `sampleMovie` structure.
    ```javascript
    // scripts/app.js
    import { movieData } from './data.js'; // Assume you've exported an array

    // Or define it directly here:
    const movies = [
        { /* movie 1 data */ },
        { /* movie 2 data */ },
        { /* movie 3 data */ }
    ];
    ```

2.  **Target the Container:** Find the DOM element (e.g., a `<div id="movie-gallery">`) in your HTML where you want to render the cards.
    ```javascript
    const galleryContainer = document.getElementById('movie-gallery');
    ```

3.  **Map and Render:** Use the `.map()` method on your `movies` array.
    *   **Map:** Transform each `movie` object in the array into a DOM element by passing it to your `createMovieCardComponent(movie)` function.
    *   **Append:** Take the resulting array of DOM elements and append them to the `galleryContainer`. (Hint: You might need to use a loop or `append(...array)` because `.map()` returns an array).

    ```javascript
    function renderMovieGallery(moviesList, container) {
        // Use .map() to create an array of DOM elements
        const movieCards = moviesList.map(movie => createMovieCardComponent(movie));

        // Clear the container first (good practice) and append all new cards
        container.innerHTML = ''; // Clear previous content
        container.append(...movieCards); // Spread the array into append
    }

    // Call the function to render the gallery!
    renderMovieGallery(movies, galleryContainer);
    ```

**What you're practicing:** `Rendering Data as UI`, `Now Showing` (the final result), `One-to-One Mappings`, `Using map`, `Applying map`.

---

## Bonus Challenge

*   **Styling:** Make your gallery responsive using CSS Flexbox or Grid so the cards rearrange based on screen size.
*   **Filtering:** Add a button that, when clicked, filters the gallery to only show movies with a rating above 8.0. (Hint: use `.filter()` before you `.map()`).
*   **Interactive Cards:** Add a "Read More" button to each card that toggles the visibility of the full `movie.description`.

Good luck! Remember to break down each exercise into smaller steps and test frequently.```

# Additional Exercises

Of course! Here are two new, self-contained JavaScript exercises for beginners, written in Markdown for GitHub.

---

## Exercise 1: The To-Do List Builder

**Objective:** Create a simple application that allows a user to add items to a to-do list.

**Your Tasks:**

1.  Create an HTML file with:
    *   A text `<input>` field for the new to-do item.
    *   An `<button>` labeled "Add" that users can click.
    *   An empty `<ul>` element that will serve as the container for the list.

2.  Write JavaScript code that does the following:
    *   Listens for a "click" event on the "Add" button.
    *   When clicked, it takes the current text from the input field.
    *   Creates a new `<li>` element and sets its text content to the value from the input.
    *   Appends the new `<li>` element to the `<ul>` list in the DOM.
    *   Clears the text input field after adding the item.

**Key Concepts to Use:** Selecting DOM elements, event listeners, reading input values, creating new elements, and appending elements to the DOM.

---

## Exercise 2: The Lightbulb Toggle

**Objective:** Build a classic lightbulb toggle simulator where clicking the bulb turns it on and off.

**Your Tasks:**

1.  Create an HTML file with:
    *   An `<img>` tag for the lightbulb. Use these two images for the states:
        *   Off: `https://via.placeholder.com/150/666666/000000?text=Lightbulb+Off`
        *   On: `https://via.placeholder.com/150/ffff66/000000?text=Lightbulb+On`
    *   Start with the "off" image as the `src`.

2.  Write JavaScript code that does the following:
    *   Selects the `<img>` element.
    *   Adds a "click" event listener to the image.
    *   When the image is clicked, the code checks the current `src` attribute of the image.
    *   If the bulb is off, it changes the `src` to the "on" image. If the bulb is on, it changes the `src` back to the "off" image.

**Key Concepts to Use:** Selecting DOM elements, event listeners, and manipulating element attributes (like `src`).


