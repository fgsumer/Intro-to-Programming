- [1. Ordinal Numbers](#1-ordinal-numbers)
  - [Code Inspiration](#ordinal-numbers-code-inspiration)
  - [Exercises](#ordinal-numbers-exercises)
- [2. Testing Frameworks](#2-testing-frameworks)
  - [Code Inspiration](#testing-frameworks-code-inspiration)
  - [Exercises](#testing-frameworks-exercises)
- [3. Starting a Project](#3-starting-a-project)
  - [Code Inspiration](#starting-a-project-code-inspiration)
  - [Exercises](#starting-a-project-exercises)
- [4. Using Packages](#4-using-packages)
  - [Code Inspiration](#using-packages-code-inspiration)
  - [Exercises](#using-packages-exercises)
- [5. Installing Jest](#5-installing-jest)
  - [Code Inspiration](#installing-jest-code-inspiration)
  - [Exercises](#installing-jest-exercises)
- [6. Jest's API](#6-jests-api)
  - [Code Inspiration](#jests-api-code-inspiration)
  - [Exercises](#jests-api-exercises)
- [7. First Test Case](#7-first-test-case)
  - [Code Inspiration](#first-test-case-code-inspiration)
  - [Exercises](#first-test-case-exercises)
- [8. Anonymous Functions](#8-anonymous-functions)
  - [Code Inspiration](#anonymous-functions-code-inspiration)
  - [Exercises](#anonymous-functions-exercises)
- [9. Arrow Functions](#9-arrow-functions)
  - [Code Inspiration](#arrow-functions-code-inspiration)
  - [Exercises](#arrow-functions-exercises)
- [10. Solving Problems While Testing](#10-solving-problems-while-testing)
  - [Code Inspiration](#solving-problems-while-testing-code-inspiration)
  - [Exercises](#solving-problems-while-testing-exercises)

---

## 1. Ordinal Numbers

### Ordinal Numbers Code Inspiration

1. **Basic ordinal number converter**
```javascript
function getOrdinal(n) {
  // Converts a number to its ordinal form (1st, 2nd, 3rd, etc.)
  const s = ["th", "st", "nd", "rd"];
  const v = n % 100;
  return n + (s[(v - 20) % 10] || s[v] || s[0]);
}
```

2. **Date formatting with ordinals**
```javascript
function formatDateWithOrdinal(day, month, year) {
  // Returns a date string with ordinal day (e.g., "January 1st, 2023")
  const months = ["January", "February", "March", "April", "May", "June",
                 "July", "August", "September", "October", "November", "December"];
  return `${months[month-1]} ${getOrdinal(day)}, ${year}`;
}
```

3. **Position ranking with ordinals**
```javascript
function displayRanking(positions) {
  // Displays ranking with ordinals (1st, 2nd, 3rd place)
  return positions.map((name, index) => 
    `${getOrdinal(index + 1)} place: ${name}`
  ).join('\n');
}
```

### Ordinal Numbers Exercises

1. **Complete the ordinal function**
```javascript
function getOrdinal(n) {
  // TODO: Implement this function to return the ordinal form of a number
  // Example: 1 -> "1st", 2 -> "2nd", 3 -> "3rd", 4 -> "4th", 11 -> "11th"
}
```

2. **Create a leaderboard display**
```javascript
function createLeaderboard(players) {
  // TODO: Return an array of strings with player names and their ordinal positions
  // Example input: ["Alice", "Bob", "Charlie"]
  // Expected output: ["1st: Alice", "2nd: Bob", "3rd: Charlie"]
}
```

3. **Format anniversary dates**
```javascript
function formatAnniversary(years) {
  // TODO: Return a string with the ordinal anniversary
  // Example: 1 -> "1st anniversary", 2 -> "2nd anniversary", 3 -> "3rd anniversary"
}
```

[Back to Topics](#topics-to-practice)

---

## 2. Testing Frameworks

### Testing Frameworks Code Inspiration

1. **Basic test structure**
```javascript
// Simple test example without a framework
function test(description, testFunction) {
  try {
    testFunction();
    console.log(`✓ ${description}`);
  } catch (error) {
    console.error(`✗ ${description}: ${error.message}`);
  }
}
```

2. **Assertion function**
```javascript
function expect(actual) {
  return {
    toBe(expected) {
      if (actual !== expected) {
        throw new Error(`Expected ${expected} but got ${actual}`);
      }
    }
  };
}
```

3. **Test grouping**
```javascript
function describe(description, tests) {
  console.log(description);
  tests();
}
```

### Testing Frameworks Exercises

1. **Complete the test function**
```javascript
function test(description, testFunction) {
  // TODO: Implement a simple test function that catches errors and logs results
}
```

2. **Create an assertion library**
```javascript
function expect(actual) {
  // TODO: Return an object with methods like toBe, toEqual, etc.
  return {
    toBe(expected) {
      // TODO: Implement this method
    }
  };
}
```

3. **Write tests for a math utility**
```javascript
// TODO: Write tests for this function using your test framework
function add(a, b) {
  return a + b;
}
```

[Back to Topics](#topics-to-practice)

---

## 3. Starting a Project

### Starting a Project Code Inspiration

1. **Project structure example**
```
my-project/
├── package.json
├── src/
│   └── index.js
├── tests/
│   └── index.test.js
└── README.md
```

2. **Package.json basics**
```json
{
  "name": "my-javascript-project",
  "version": "1.0.0",
  "description": "A simple JavaScript project",
  "main": "src/index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  }
}
```

3. **Basic module export**
```javascript
// src/utils.js
function greet(name) {
  return `Hello, ${name}!`;
}

module.exports = { greet };
```

### Starting a Project Exercises

1. **Create a project structure**
```bash
# TODO: Create the following directory structure for a new project
# my-app/
# ├── package.json
# ├── src/
# │   └── index.js
# └── tests/
#     └── index.test.js
```

2. **Initialize a package.json**
```bash
# TODO: Run the command to create a package.json file with default values
```

3. **Create and export a module**
```javascript
// TODO: Create a math.js file that exports add, subtract, multiply, and divide functions
```

[Back to Topics](#topics-to-practice)

---

## 4. Using Packages

### Using Packages Code Inspiration

1. **Importing and using a package**
```javascript
// Using the lodash package
const _ = require('lodash');

const numbers = [1, 2, 3, 4, 5];
const doubled = _.map(numbers, n => n * 2);
```

2. **Package version management**
```json
{
  "dependencies": {
    "lodash": "^4.17.21"
  },
  "devDependencies": {
    "jest": "^27.0.0"
  }
}
```

3. **Using multiple packages**
```javascript
const moment = require('moment');
const axios = require('axios');

// Get current date and make an API request
const today = moment().format('YYYY-MM-DD');
axios.get(`https://api.example.com/data?date=${today}`);
```

### Using Packages Exercises

1. **Install and use a package**
```bash
# TODO: Install the chalk package and use it in a script to print colored text
```

2. **Add dependencies to package.json**
```json
{
  // TODO: Add lodash and moment as dependencies
  "dependencies": {
  }
}
```

3. **Create a script using multiple packages**
```javascript
// TODO: Create a script that uses both moment and axios to fetch data for today's date
```

[Back to Topics](#topics-to-practice)

---

## 5. Installing Jest

### Installing Jest Code Inspiration

1. **Install Jest as a dev dependency**
```bash
npm install --save-dev jest
```

2. **Add test script to package.json**
```json
{
  "scripts": {
    "test": "jest"
  }
}
```

3. **Run tests with Jest**
```bash
npm test
```

### Installing Jest Exercises

1. **Install Jest in your project**
```bash
# TODO: Install Jest as a development dependency
```

2. **Configure test script**
```json
{
  "scripts": {
    // TODO: Add a test script that runs Jest
  }
}
```

3. **Run your first test**
```bash
# TODO: Execute the test command to verify Jest is working
```

[Back to Topics](#topics-to-practice)

---

## 6. Jest's API

### Jest's API Code Inspiration

1. **Basic test with expect**
```javascript
test('adds 1 + 2 to equal 3', () => {
  expect(1 + 2).toBe(3);
});
```

2. **Testing arrays and objects**
```javascript
test('array containing', () => {
  expect(['apple', 'banana']).toContain('apple');
});

test('object matching', () => {
  expect({a: 1, b: 2}).toEqual({a: 1, b: 2});
});
```

3. **Testing async code**
```javascript
test('async test', async () => {
  const result = await fetchData();
  expect(result).toBeDefined();
});
```

### Jest's API Exercises

1. **Write a basic test**
```javascript
// TODO: Write a test that checks if 5 + 5 equals 10 using Jest's expect and toBe
```

2. **Test array operations**
```javascript
// TODO: Write a test that verifies an array contains a specific value
```

3. **Test object equality**
```javascript
// TODO: Write a test that checks if two objects have the same properties and values
```

[Back to Topics](#topics-to-practice)

---

## 7. First Test Case

### First Test Case Code Inspiration

1. **Testing a simple function**
```javascript
// function.js
function multiply(a, b) {
  return a * b;
}

// function.test.js
const { multiply } = require('./function');

test('multiplies 2 * 3 to equal 6', () => {
  expect(multiply(2, 3)).toBe(6);
});
```

2. **Testing edge cases**
```javascript
test('multiplies by zero', () => {
  expect(multiply(5, 0)).toBe(0);
  expect(multiply(0, 5)).toBe(0);
});
```

3. **Testing with different values**
```javascript
test('multiplies negative numbers', () => {
  expect(multiply(-2, 3)).toBe(-6);
  expect(multiply(2, -3)).toBe(-6);
  expect(multiply(-2, -3)).toBe(6);
});
```

### First Test Case Exercises

1. **Create and test a function**
```javascript
// TODO: Create a divide function and write tests for it
function divide(a, b) {
  // TODO: Implement this function
}
```

2. **Test error cases**
```javascript
// TODO: Write tests that verify divide throws an error when dividing by zero
```

3. **Test multiple scenarios**
```javascript
// TODO: Write tests for the divide function with various inputs including decimals
```

[Back to Topics](#topics-to-practice)

---

## 8. Anonymous Functions

### Anonymous Functions Code Inspiration

1. **Function as a parameter**
```javascript
// Using anonymous function with setTimeout
setTimeout(function() {
  console.log('This runs after 1 second');
}, 1000);
```

2. **Array methods with anonymous functions**
```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(function(n) {
  return n * 2;
});
```

3. **Immediately Invoked Function Expression (IIFE)**
```javascript
(function() {
  console.log('This runs immediately');
})();
```

### Anonymous Functions Exercises

1. **Use anonymous function with array method**
```javascript
const numbers = [1, 2, 3, 4, 5];
// TODO: Use an anonymous function with filter to get even numbers
```

2. **Create an IIFE**
```javascript
// TODO: Create an IIFE that calculates and logs the square of 5
```

3. **Pass anonymous function to setTimeout**
```javascript
// TODO: Use setTimeout with an anonymous function to log a message after 2 seconds
```

[Back to Topics](#topics-to-practice)

---

## 9. Arrow Functions

### Arrow Functions Code Inspiration

1. **Basic arrow function**
```javascript
const add = (a, b) => {
  return a + b;
};

// Implicit return
const multiply = (a, b) => a * b;
```

2. **Arrow functions with array methods**
```javascript
const numbers = [1, 2, 3, 4, 5];
const squared = numbers.map(n => n * n);
```

3. **Arrow functions and 'this'**
```javascript
function Timer() {
  this.seconds = 0;
  setInterval(() => {
    this.seconds++;
    console.log(this.seconds);
  }, 1000);
}
```

### Arrow Functions Exercises

1. **Convert function to arrow function**
```javascript
// TODO: Convert this function to an arrow function
function greet(name) {
  return "Hello, " + name + "!";
}
```

2. **Use arrow function with array method**
```javascript
const numbers = [1, 2, 3, 4, 5];
// TODO: Use an arrow function with reduce to sum all numbers
```

3. **Create arrow functions with implicit return**
```javascript
// TODO: Create arrow functions with implicit return for:
// 1. Doubling a number
// 2. Checking if a number is even
```

[Back to Topics](#topics-to-practice)

---

## 10. Solving Problems While Testing

### Solving Problems While Testing Code Inspiration

1. **Test-driven development example**
```javascript
// First write the test
test('capitalize function capitalizes first letter', () => {
  expect(capitalize('hello')).toBe('Hello');
});

// Then implement the function
function capitalize(str) {
  return str.charAt(0).toUpperCase() + str.slice(1);
}
```

2. **Debugging with tests**
```javascript
// When a test fails, use the error message to fix the implementation
test('add function handles string numbers', () => {
  // This test might fail initially, helping us improve our function
  expect(add('2', '3')).toBe(5);
});
```

3. **Refactoring with confidence**
```javascript
// After implementing tests, we can refactor knowing our tests will catch errors
function oldComplexFunction() { /* complex code */ }

// Refactor to:
function newCleanFunction() { /* clean code */ }

// Tests ensure both functions behave the same way
```

### Solving Problems While Testing Exercises

1. **Practice TDD with a new function**
```javascript
// TODO: First write a test for a reverseString function, then implement it
```

2. **Fix a bug using tests**
```javascript
// This function has a bug - use tests to identify and fix it
function subtract(a, b) {
  return a + b; // Oops, this should be a - b
}

// TODO: Write tests that reveal the bug, then fix the function
```

3. **Refactor with test coverage**
```javascript
// TODO: Write tests for this function, then refactor it to be more readable
function processData(data) {
  let result = 0;
  for (let i = 0; i < data.length; i++) {
    if (data[i] > 5) {
      result += data[i] * 2;
    }
  }
  return result;
}
```

[Back to Topics](#topics-to-practice)

---

## Additional Resources

1. [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide) - Comprehensive JavaScript documentation
2. [Jest Documentation](https://jestjs.io/docs/getting-started) - Official Jest testing framework guide
3. [JavaScript Testing Best Practices](https://github.com/goldbergyoni/javascript-testing-best-practices) - Extensive testing guidelines and examples

[Back to Topics](#topics-to-practice)
