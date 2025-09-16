# JavaScript Homework: The Ordinal Number Converter

## Setup Instructions

1.  **Start a New Project**: Create a new directory for your project and initialize it as a Node.js package. Accept all the default `npm init` settings for now.
    ```bash
    mkdir ordinal-converter
    cd ordinal-converter
    npm init -y
    ```

2.  **Install Jest**: Add Jest to your project as a development dependency.
    ```bash
    npm install --save-dev jest
    ```

3.  **Configure Package.json**: Open your `package.json` file and change the `"scripts"` section to include a test script that runs Jest.
    ```json
    "scripts": {
      "test": "jest"
    }
    ```

4.  **Project Structure**: Create the following files in your project root:
    ```
    ordinal-converter/
    ├── src/
    │   └── ordinal.js
    ├── __tests__/
    │   └── ordinal.test.js
    ├── package.json
    └── README.md
    ```

## Exercise 1: Writing the Test Suite (TDD)

**Do not write the function logic first.** You will practice Test-Driven Development (TDD), where you write tests *before* you write the code.

In the file `__tests__/ordinal.test.js`:

1.  Import the function you plan to create (we will assume it's a default export from `../src/ordinal`).
2.  Use Jest's `describe` block to group your tests for the `toOrdinal` function.
3.  Write individual `test` blocks for the following cases. Use **arrow functions** for your test callbacks.
    *   Test that 1 returns '1st'
    *   Test that 2 returns '2nd'
    *   Test that 3 returns '3rd'
    *   Test that 4 returns '4th'
    *   Test that 11 returns '11th' (a key exception)
    *   Test that 12 returns '12th' (another exception)
    *   Test that 13 returns '13th' (another exception)
    *   Test that 21 returns '21st' (notice the pattern change)
    *   Test that 22 returns '22nd'
    *   Test that 23 returns '23rd'
    *   Test that 101 returns '101st'

4.  Run your test suite using `npm test`. **All tests should fail spectacularly.** This is expected and confirms your tests are set up correctly to test a function that doesn't exist yet. Take a moment to **interpret the feedback** from Jest—it will tell you it can't find the module or function.

## Exercise 2: Implementing the Logic

Now, you will create the function to make your tests pass.

In the file `src/ordinal.js`:

1.  Create and export a function called `toOrdinal` that takes a single integer argument.
2.  Implement the logic to convert the number to its ordinal string representation.
    *   **Hint:** The rules for forming ordinals are:
        *   Numbers ending in 1 (but not 11) use "st".
        *   Numbers ending in 2 (but not 12) use "nd".
        *   Numbers ending in 3 (but not 13) use "rd".
        *   All other numbers use "th", including 11, 12, and 13.
    *   You will likely need to use the modulus operator `%` to get the last digit(s) of the number to check these conditions.
3.  **Generalise Further:** Your initial implementation might only work for the first few cases. Run `npm test` frequently. Use the feedback from each failing test to refine your algorithm until it handles all the edge cases you defined in Exercise 1 (like 11, 12, 13, 21, etc.).

## Exercise 3: Refactoring and Edge Cases

Once all your tests from Exercise 1 are passing (green), it's time to improve and strengthen your code.

1.  **Refactor:** Look at your solution in `src/ordinal.js`. Can you make it more readable or efficient without breaking the tests? This is the safe step of TDD—you can change the implementation confidently because you have tests to ensure you don't break existing functionality.

2.  **Add New Tests:** Add the following **edge cases** to your `ordinal.test.js` file. Think about how your function *should* behave and write a test for it first. Then, implement the logic to make it pass.
    *   Test that the function correctly handles 0. What should `toOrdinal(0)` return? ('0th' is acceptable).
    *   Test that the function throws a `TypeError` or returns a sensible error when a non-integer (like a string or a decimal) is passed in. (Hint: Use `expect(() => { toOrdinal('abc'); }).toThrow(TypeError);`)

3.  **Final Run:** Execute `npm test` one final time. Your goal is to have a complete test suite where all tests pass.

## Submission Guidelines

1.  Push your complete project (including the `node_modules` folder) to a new GitHub repository.
2.  Ensure your repository includes:
    *   A `src/` directory with your `ordinal.js` file.
    *   A `__tests__/` directory with your `ordinal.test.js` file.
    *   Your `package.json` file with the correct Jest configuration.
3.  The GitHub repository link is your submission.

## Success Criteria

*   The project is initialized correctly with `package.json`.
*   Jest is installed as a dev dependency and configured in the `package.json` scripts.
*   The test suite in `__tests__/ordinal.test.js` is comprehensive and uses Jest's API correctly.
*   The implementation in `src/ordinal.js` correctly converts all specified integers to ordinals.
*   The code handles edge cases (0, invalid input) appropriately.
*   All tests pass when `npm test` is run.

---

# Additional Exercises

## Exercise 1: The Vowel Counter

**Objective:** Write a function that counts the number of vowels in a given string.

**Your Task:**
1.  Create a function named `countVowels`.
2.  The function should take one parameter: `text` (a string).
3.  It should return the total count of vowels (a, e, i, o, u) in the provided string. The function should count both lowercase and uppercase vowels.
4.  Test your function with different words and sentences to make sure it works.

**Example Output:**
*   `countVowels("Hello World!")` should return `3`.
*   `countVowels("JavaScript is fun")` should return `5`.

---

## Exercise 2: The Grade Assigner

**Objective:** Write a function that assigns a letter grade based on a numerical score.

**Your Task:**
1.  Create a function named `assignGrade`.
2.  The function should take one parameter: `score` (a number between 0 and 100).
3.  It should return a string representing the letter grade based on the following scale:
    *   90 and above: 'A'
    *   80 - 89: 'B'
    *   70 - 79: 'C'
    *   60 - 69: 'D'
    *   Below 60: 'F'
4.  Test your function with various scores to ensure it returns the correct grade for each range.

**Example Output:**
*   `assignGrade(95)` should return `'A'`.
*   `assignGrade(73)` should return `'C'`.
*   `assignGrade(42)` should return `'F'`.
