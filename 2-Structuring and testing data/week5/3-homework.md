# JavaScript Homework: The String Validator

## Exercise 1: Build the Core Validator Function

**Sub-Goal #1:** Create a function `isValidPassword` that validates a string based on specific rules.

**Requirements:**
The function must take a string password and return `true` only if ALL the following conditions are met. Otherwise, it returns `false`.
1.  The password must be at least 8 characters long.
2.  It must contain at least one uppercase letter (`A-Z`).
3.  It must contain at least one lowercase letter (`a-z`).
4.  It must contain at least one digit (`0-9`).

**Your Tasks:**
1.  **Strategy:** Before writing code, plan your approach. Break the problem into sub-goals (e.g., check length, then check for uppercase, etc.).
2.  **Implementation:** Write the function using a combination of `for` loops and conditional statements (`if`, `else`). **Do not use regular expressions (Regex) for this exercise.** The goal is to practice string iteration and comparison.
3.  **Reusing Variables:** Think carefully about which variables you need to declare (`let`, `const`) and if you can reuse any (e.g., a variable to track the current character).
4.  **Initial Test:** Use `console.log` to manually test your function with a few inputs (e.g., `"Password1"` should be `true`, `"password"` should be `false`).

**Hints:**
*   Use a strategy of "early return" – if you find one condition is failed, you can return `false` immediately.
*   You might use boolean flags (e.g., `hasUppercase`, `hasLowercase`) to track if you've found each required character type.

---

## Exercise 2: Testing, Debugging, and Interpreting Errors

**Sub-Goal #2:** Rigorously test your function and fix any bugs you find, including a specific `this`-related error.

**Your Tasks:**
1.  **Write Assertions:** Create a function `runTests()` that uses `console.assert()` to test `isValidPassword` against the following test cases. `console.assert(expression, message)` only logs the `message` if the `expression` is `false`.
    ```javascript
    // Should be true
    console.assert(isValidPassword("Valid1Pass") === true, "✅ 'Valid1Pass' should be valid");

    // Should be false (missing uppercase)
    console.assert(isValidPassword("invalidpassword1") === false, "❌ Password missing uppercase should be invalid");

    // Add AT LEAST 4 more assertions to test other failure cases and edge cases.
    ```
2.  **Run and Interpret Errors:** Run your tests. You will likely see error messages in the console. Read them carefully. They tell you exactly which test failed and why. Debug and fix your `isValidPassword` function until all tests pass.
3.  **Intentionally Cause a `this` Error:** Inside your `isValidPassword` function, try to use a `this` keyword (e.g., `console.log(this.length)`). Run your tests again.
4.  **Interpreting `this` Error:** Observe the new error message. What does it say about `this`? Understand that inside a standard function, `this` has a specific context, and in this case, it's likely `undefined` (in strict mode) or the global object. **Comment out or remove the `this` line once you understand the error.**

---

## Exercise 3: Refactor and Improve

**Your Tasks:**
1.  **Identify Repetition:** Look at your solution from Exercise 1. Do you see repetition? For example, are you writing similar `for` loops to check for uppercase, lowercase, and digits? This is a prime candidate for **refactoring**.
2.  **Refactor:** Create helper functions to remove repetition. For example:
    *   `function hasUppercase(str) { ... }`
    *   `function hasLowercase(str) { ... }`
    *   `function hasDigit(str) { ... }`
    Rewrite your `isValidPassword` function to use these helper functions. This makes your code more readable, modular, and easier to debug.
3.  **Identify Missing Tests:** Look at your new, refactored code.
    *   Did you remember to test a password that is exactly 8 characters long?
    *   What about an empty string (`""`)?
    *   What about a string with exactly one uppercase, one lowercase, and one digit, but also with non-alphanumeric characters (e.g., `"Passw0rd!"`)? Should it be valid or invalid based on our requirements?
    **Add new assertions to `runTests()` to cover these edge cases and any others you think are important.** A good developer proactively tries to break their own code.

## Submission Guidelines

1.  Create a single JavaScript file (e.g., `passwordValidator.js`).
2.  The file should contain:
    *   The helper functions (`hasUppercase`, etc.).
    *   The final refactored `isValidPassword` function.
    *   A comprehensive `runTests()` function with all your assertions.
3.  Call `runTests()` at the end of the file to execute your test suite.
4.  Ensure your code is clean, well-commented, and all tests pass (no assertions fail in the console).

---
# Additional Exercises

## Exercise 1: The Grocery List Manager

**Objective:** Create a simple program to manage a grocery list.

**Your Tasks:**
1.  Create an empty array to represent the grocery list.
2.  Write a function called `addItem` that takes a string (the item name) as an argument and adds it to the list.
3.  Write a function called `removeItem` that takes a string (the item name) as an argument and removes it from the list.
4.  Write a function called `printList` that prints each item on the list to the console, formatted as a numbered list (e.g., `1. Milk`).
5.  Test your functions by adding at least 3 items, printing the list, removing one item, and then printing the list again to confirm the item was removed.

---

## Exercise 2: The Number Checker

**Objective:** Write a function that analyzes a number and returns a specific message based on its value.

**Your Tasks:**
1.  Write a function named `checkNumber` that takes a single number as an argument.
2.  The function should return a different string message for each of these cases:
    *   If the number is positive and even, return "Positive and Even".
    *   If the number is positive and odd, return "Positive and Odd".
    *   If the number is negative, return "Negative".
    *   If the number is zero, return "Zero".
3.  Test your function by calling it with at least one number that triggers each of the possible return messages. Use `console.log` to display the result of each test.