# JavaScript Homework: Interactive Character Counter

## Exercises

### Exercise 1: Setup and Basic Functionality

**Goal:** Create the core function that calculates and displays the remaining characters.

1.  **HTML Setup:** Create a basic HTML file with:
    *   A `<textarea>` or `<input type="text">` for user input. Give it an `id`.
    *   A `<div>` or `<span>` element with an `id` (e.g., `charCounter`) to display the message like "Characters left: 50".
2.  **Define the Limit:** In your JavaScript, create a constant variable `MAX_CHARS` and set it to 50.
3.  **Query the DOM:** Use `document.getElementById()` or `document.querySelector()` to get references to your input and counter elements. Store them in variables.
4.  **Create the Update Function:** Write a function named `updateCounter()` that:
    *   Gets the current length of the text in the input field.
    *   Calculates the remaining characters: `remaining = MAX_CHARS - currentLength`.
    *   Updates the text content of your counter element to show the remaining characters.
5.  **Add Event Listener:** Attach an `'input'` event listener to the text input. This event fires every time the user types or deletes anything. Make it call your `updateCounter` function.

**Check Your Progress:** At this point, typing in the box should immediately update the counter.

---

### Exercise 2: Adding Visual Feedback and Refactoring

**Goal:** Enhance the user interface and improve your code structure.

1.  **Add Visual Warning:** Modify your `updateCounter()` function to change the color of the counter text when the user is接近ing the limit.
    *   Example: Turn the counter **red** when there are 10 or fewer characters left.
    *   *Hint:* Use the `element.style.color` property (e.g., `counterElement.style.color = 'red'`).
2.  **Disable Input (Optional Challenge):** Prevent the user from typing any more characters once the limit is exceeded.
    *   *Hint:* In your `updateCounter` function, if `remaining` is less than 0, you can trim the input value back down to `MAX_CHARS` using `.slice(0, MAX_CHARS)`.
3.  **Refactor Your Code:** Now that your function does more, make sure your code is clean and readable.
    *   Give your variables clear, descriptive names (e.g., `messageElement` instead of `div1`).
    *   Add a comment above your `updateCounter` function explaining what it does.

**Check Your Progress:** The counter should now turn red when you get close to the limit. The input should stop accepting new characters after the limit is reached.

---

### Exercise 3 (Bonus): Debouncing with a Timer

**Goal:** Use a timer to improve performance for a more complex, hypothetical scenario.

Imagine the `updateCounter()` function wasn't just updating a number but was doing a very heavy calculation (like checking a word against a dictionary on every keystroke). We wouldn't want to run it on *every* `'input'` event as that would be inefficient.

1.  **Refactor the Event Listener:** Remove the call to `updateCounter()` from the event listener.
2.  **Implement a Debounce Timer:** Inside the event listener, use `setTimeout` to wait for 500 milliseconds (half a second) before calling `updateCounter()`.
3.  **Store the Timer ID:** Store the timer's ID in a variable (e.g., `let timeoutId;` declared outside the event listener).
4.  **Reset the Timer:** Every time a new `'input'` event fires, check if `timeoutId` exists. If it does, clear the previous timer using `clearTimeout(timeoutId)` *before* setting a new one. This ensures `updateCounter` only runs *after* the user has stopped typing for 500ms.

**Final Check:** The functionality will *look* the same, but under the hood, it's using a timer to control how often the main function runs. This is a common advanced technique called "debouncing."

## How to Submit

1.  Create a new repository on GitHub named `js-character-counter`.
2.  Push your HTML, CSS, and JavaScript files to the repository.
3.  Ensure your code is well-commented to explain your logic.
4.  Submit the link to your GitHub repository.

---
# Additional Exercises

## Exercise 1: Live Form Validator

Create a simple registration form that provides live feedback as the user types. The form should have two fields: a "Username" and an "Email". Below each field, include an empty element (like a `<span>`) to display a validation message.

Your task is to write JavaScript that:
1.  Listens for user input in each field.
2.  For the Username field, check that it is not empty and is at least 5 characters long. Update the message below it to show either a success message (in green) or an error message (in red).
3.  For the Email field, check that it contains the `@` symbol. Update the message below it accordingly with a success or error message.
4.  Include a submit button. When clicked, check both validations again. If both are valid, show an alert saying "Form Submitted Successfully!". If not, prevent the alert and let the user see the error messages.

---

## Exercise 2: Countdown Timer Interface

Build a simple countdown timer that the user can control. The interface should have:
*   An `<input type="number">` field to set the timer duration in seconds.
*   A "Start" button to begin the countdown.
*   A display area (e.g., a `<h1>` tag) to show the remaining time.
*   A "Pause" button to pause the running timer.

Your task is to write JavaScript that:
1.  Allows the user to enter a number of seconds and click "Start".
2.  The display area should show the remaining time and update every second, counting down to zero.
3.  When the "Pause" button is clicked, the timer should stop counting down. Clicking "Start" again should resume from the current number.
4.  When the countdown reaches zero, the timer should stop and display an alert saying "Time's up!".

