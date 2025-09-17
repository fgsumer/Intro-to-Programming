* **Comparison**
  - [Code Inspiration](#comparison-code-inspiration)
  - [Exercises](#comparison-exercises)
* **Assertions**
  - [Code Inspiration](#assertions-code-inspiration)
  - [Exercises](#assertions-exercises)
* **Interpreting errors**
  - [Code Inspiration](#interpreting-errors-code-inspiration)
  - [Exercises](#interpreting-errors-exercises)
* **Interpreting this error**
  - [Code Inspiration](#interpreting-this-error-code-inspiration)
  - [Exercises](#interpreting-this-error-exercises)
* **Reusing variable names**
  - [Code Inspiration](#reusing-variable-names-code-inspiration)
  - [Exercises](#reusing-variable-names-exercises)
* **Strategy**
  - [Code Inspiration](#strategy-code-inspiration)
  - [Exercises](#strategy-exercises)
* **Conditionality**
  - [Code Inspiration](#conditionality-code-inspiration)
  - [Exercises](#conditionality-exercises)
* **Sub-goal**
  - [Code Inspiration](#sub-goal-code-inspiration)
  - [Exercises](#sub-goal-exercises)
* **Strings**
  - [Code Inspiration](#strings-code-inspiration)
  - [Exercises](#strings-exercises)
* **Testing a sub-goal**
  - [Code Inspiration](#testing-a-sub-goal-code-inspiration)
  - [Exercises](#testing-a-sub-goal-exercises)
* **Sub-goal #2**
  - [Code Inspiration](#sub-goal-2-code-inspiration)
  - [Exercises](#sub-goal-2-exercises)
* **Refactoring repetition**
  - [Code Inspiration](#refactoring-repetition-code-inspiration)
  - [Exercises](#refactoring-repetition-exercises)
* **Identifying missing tests**
  - [Code Inspiration](#identifying-missing-tests-code-inspiration)
  - [Exercises](#identifying-missing-tests-exercises)

---

## Comparison

<a name="comparison-code-inspiration"></a>
### Code Inspiration
1. **Basic comparison examples**
```javascript
// Example 1: Equality checks
console.log(5 == '5');    // true (loose equality)
console.log(5 === '5');   // false (strict equality)

// Example 2: Inequality checks
console.log(10 != '10');  // false
console.log(10 !== '10'); // true

// Example 3: Greater/Less than
console.log(7 > 5);       // true
console.log(7 < 5);       // false
```

2. **Comparing different data types**
```javascript
// Example 1: String comparison
console.log('apple' < 'banana');  // true (lexicographical order)

// Example 2: Boolean comparison
console.log(true == 1);           // true
console.log(true === 1);          // false

// Example 3: Special cases
console.log(null == undefined);   // true
console.log(null === undefined);  // false
```

3. **Complex comparisons**
```javascript
// Example 1: Multiple comparisons
let age = 25;
console.log(age >= 18 && age <= 65);  // true

// Example 2: Using comparison with arrays
let arr1 = [1, 2, 3];
let arr2 = [1, 2, 3];
console.log(arr1 == arr2);  // false (different references)
console.log(arr1 === arr2); // false

// Example 3: Object comparison
let obj1 = {name: "John"};
let obj2 = {name: "John"};
console.log(obj1 == obj2);  // false
```

<a name="comparison-exercises"></a>
### Exercises
1. **Fix the comparisons**
```javascript
// Fix the following code to get the expected results
let a = 10;
let b = '10';

console.log(a == b);  // Expected: false
console.log(a === b); // Expected: true

// Your fixed code here:
```

2. **Write comparison expressions**
```javascript
// Write expressions that evaluate to true for the following:
// 1. Check if 'hello' is not equal to 'world' (any type of inequality)
// 2. Check if 15 is greater than 10 and less than 20
// 3. Check if a variable 'value' is strictly equal to 5 OR strictly equal to '5'

// Your code here:
```

3. **Debug comparison logic**
```javascript
// The following function should return true if the input is between 0 and 100
// but it has errors. Fix them.
function isInRange(value) {
  return value > 0 && value < 100;
}

// Test cases that should all return true:
console.log(isInRange(50));   // true
console.log(isInRange(0));    // false, but should be true?
console.log(isInRange(100));  // false, but should be true?

// Your fixed code here:
```

---

## Assertions

<a name="assertions-code-inspiration"></a>
### Code Inspiration
1. **Basic assertion examples**
```javascript
// Example 1: Simple console assertions
console.assert(5 > 3, '5 should be greater than 3');
console.assert(typeof 'hello' === 'string', 'Should be a string');

// Example 2: Function return value assertions
function add(a, b) {
  return a + b;
}
console.assert(add(2, 3) === 5, 'Add function should return sum');

// Example 3: Array content assertion
let fruits = ['apple', 'banana'];
console.assert(fruits.length === 2, 'Array should have 2 items');
```

2. **Custom assertion function**
```javascript
// Example 1: Simple assert function
function assert(condition, message) {
  if (!condition) {
    throw new Error("Assertion failed: " + message);
  }
}

// Example 2: Using the custom assert
let age = 20;
assert(age >= 18, "Person should be adult");

// Example 3: Assert with value comparison
function assertEquals(actual, expected) {
  if (actual !== expected) {
    throw new Error(`Expected ${expected}, but got ${actual}`);
  }
}
```

3. **Testing with assertions**
```javascript
// Example 1: Testing a function with multiple cases
function multiply(a, b) {
  return a * b;
}

// Test cases
console.assert(multiply(2, 3) === 6, '2 * 3 should be 6');
console.assert(multiply(0, 5) === 0, '0 * 5 should be 0');
console.assert(multiply(-2, 3) === -6, '-2 * 3 should be -6');

// Example 2: Testing array methods
let numbers = [1, 2, 3];
numbers.push(4);
console.assert(numbers.length === 4, 'Array should have 4 elements after push');
```

<a name="assertions-exercises"></a>
### Exercises
1. **Write assertions for a function**
```javascript
// Write assertions to test the following function
function getGrade(score) {
  if (score >= 90) return 'A';
  if (score >= 80) return 'B';
  if (score >= 70) return 'C';
  if (score >= 60) return 'D';
  return 'F';
}

// Your assertions here:
```

2. **Create a custom assertion function**
```javascript
// Create a function called assertType that checks if a value
// is of the expected type and throws an error if not
// Example: assertType(5, 'number') should not throw
// Example: assertType('hello', 'number') should throw

// Your code here:
```

3. **Fix the faulty assertions**
```javascript
// The following assertions are incorrect. Fix them.
let result = 10 / 2;

console.assert(result === 5, '10 divided by 2 should be 4');
console.assert(typeof result === 'int', 'Result should be an integer');
console.assert(result > 5 && result < 5, 'Result should be exactly 5');

// Your fixed assertions here:
```

---

## Interpreting errors

<a name="interpreting-errors-code-inspiration"></a>
### Code Inspiration
1. **Common error types**
```javascript
// Example 1: ReferenceError
try {
  console.log(nonExistentVariable);
} catch (error) {
  console.log('Error type:', error.name);
  console.log('Error message:', error.message);
}

// Example 2: TypeError
try {
  let nullValue = null;
  console.log(nullValue.nonExistentProperty);
} catch (error) {
  console.log('Error type:', error.name);
  console.log('Error message:', error.message);
}

// Example 3: SyntaxError (this will throw during parsing, not execution)
// Uncomment to see the error
// let if = 5; // Invalid variable name
```

2. **Reading error stack traces**
```javascript
// Example 1: Simple stack trace
function functionA() {
  functionB();
}

function functionB() {
  functionC();
}

function functionC() {
  throw new Error('Something went wrong!');
}

try {
  functionA();
} catch (error) {
  console.log('Stack trace:', error.stack);
}

// Example 2: Custom error with stack
class CustomError extends Error {
  constructor(message) {
    super(message);
    this.name = 'CustomError';
  }
}
```

3. **Handling different error types**
```javascript
// Example 1: Catching specific errors
try {
  // Code that might throw different errors
  let data = JSON.parse('invalid json');
} catch (error) {
  if (error instanceof SyntaxError) {
    console.log('JSON parsing error:', error.message);
  } else {
    console.log('Other error:', error.message);
  }
}

// Example 2: Finally block
let fileHandle;
try {
  fileHandle = openFile('example.txt');
  // Process file
} catch (error) {
  console.log('Error processing file:', error.message);
} finally {
  if (fileHandle) {
    closeFile(fileHandle);
  }
}
```

<a name="interpreting-errors-exercises"></a>
### Exercises
1. **Identify the error type**
```javascript
// For each code snippet, identify what type of error will occur and why:

// Snippet 1:
let x = 5;
x();

// Snippet 2:
console.log(y);

// Snippet 3:
let obj = {};
obj.nonExistentMethod();

// Your answers here:
```

2. **Fix error handling code**
```javascript
// The following error handling has issues. Fix them.
try {
  let data = JSON.parse('{invalid json}');
  console.log('Parsed data:', data);
} catch (error) {
  console.log('There was an error');
}

// Your fixed code here:
```

3. **Create custom error messages**
```javascript
// Write a function that safely accesses nested object properties
// and throws a custom error message if any level is undefined
function safeAccess(obj, path) {
  // Your code here
}

// Test cases:
let user = { profile: { name: 'John' } };
console.log(safeAccess(user, 'profile.name')); // Should return 'John'
console.log(safeAccess(user, 'profile.age'));  // Should throw meaningful error
```

---

## Interpreting this error

<a name="interpreting-this-error-code-inspiration"></a>
### Code Inspiration
1. **Understanding 'this' context**
```javascript
// Example 1: 'this' in global context
console.log(this); // In browser: Window, in Node.js: global

// Example 2: 'this' in object methods
let person = {
  name: 'Alice',
  greet: function() {
    console.log('Hello, ' + this.name);
  }
};
person.greet(); // Hello, Alice

// Example 3: 'this' pitfall
let greetFunction = person.greet;
greetFunction(); // Hello, undefined (or error in strict mode)
```

2. **Fixing 'this' issues**
```javascript
// Example 1: Using bind
let boundGreet = person.greet.bind(person);
boundGreet(); // Hello, Alice

// Example 2: Using call and apply
person.greet.call(person); // Hello, Alice
person.greet.apply(person); // Hello, Alice

// Example 3: Arrow functions and 'this'
let person2 = {
  name: 'Bob',
  greet: () => {
    console.log('Hello, ' + this.name);
  }
};
person2.greet(); // Hello, undefined (arrow functions don't have their own 'this')
```

3. **'this' in different contexts**
```javascript
// Example 1: 'this' in constructor functions
function Car(make, model) {
  this.make = make;
  this.model = model;
  this.display = function() {
    console.log(this.make + ' ' + this.model);
  };
}
let myCar = new Car('Toyota', 'Corolla');
myCar.display(); // Toyota Corolla

// Example 2: 'this' in event handlers
// In browser:
// button.addEventListener('click', function() {
//   console.log(this); // Refers to the button element
// });

// Example 3: 'this' with arrow functions in classes
class Person {
  constructor(name) {
    this.name = name;
  }
  
  greet() {
    setTimeout(() => {
      console.log('Hello, ' + this.name); // 'this' refers to Person instance
    }, 100);
  }
}
```

<a name="interpreting-this-error-exercises"></a>
### Exercises
1. **Predict 'this' output**
```javascript
// What will each of these log and why?
let obj = {
  value: 10,
  getValue: function() {
    return this.value;
  }
};

console.log(obj.getValue()); // 1.

let getValue = obj.getValue;
console.log(getValue());     // 2.

let boundGetValue = obj.getValue.bind(obj);
console.log(boundGetValue()); // 3.

// Your predictions here:
```

2. **Fix 'this' context issues**
```javascript
// Fix the following code so it properly logs the person's name
let person = {
  name: 'Sarah',
  tasks: ['task1', 'task2', 'task3'],
  showTasks: function() {
    this.tasks.forEach(function(task) {
      console.log(this.name + ' needs to do: ' + task);
    });
  }
};

person.showTasks(); // Currently logs "undefined needs to do: taskX"

// Your fixed code here:
```

3. **Implement with correct 'this' binding**
```javascript
// Create a counter object with methods to increment, decrement, and get value
// Make sure 'this' is properly bound in all methods
let counter = {
  value: 0,
  // Your methods here
};

// Test your implementation
counter.increment();
counter.increment();
console.log(counter.getValue()); // Should be 2
counter.decrement();
console.log(counter.getValue()); // Should be 1

// Your code here:
```

---

## Reusing variable names

<a name="reusing-variable-names-code-inspiration"></a>
### Code Inspiration
1. **Variable scope examples**
```javascript
// Example 1: Global vs local variables
let globalVar = 'I am global';

function testScope() {
  let localVar = 'I am local';
  console.log(globalVar); // Accessible
  console.log(localVar);  // Accessible
}

testScope();
console.log(globalVar); // Accessible
// console.log(localVar); // Error: localVar is not defined

// Example 2: Variable shadowing
let name = 'Global Name';

function showName() {
  let name = 'Local Name'; // Shadows the global variable
  console.log(name); // 'Local Name'
}

showName();
console.log(name); // 'Global Name'
```

2. **Block scope with let/const**
```javascript
// Example 1: Block scope
if (true) {
  let blockScoped = 'I exist only in this block';
  var functionScoped = 'I exist in the entire function';
}
// console.log(blockScoped); // Error: not defined
console.log(functionScoped); // Works

// Example 2: Loop variables
for (let i = 0; i < 3; i++) {
  setTimeout(function() {
    console.log(i); // 0, 1, 2 (each i is scoped to the loop iteration)
  }, 100);
}

for (var j = 0; j < 3; j++) {
  setTimeout(function() {
    console.log(j); // 3, 3, 3 (j is function-scoped)
  }, 100);
}
```

3. **Best practices for variable naming**
```javascript
// Example 1: Descriptive variable names
// Bad:
let t = 10;
let d = 5;

// Good:
let temperature = 10;
let distance = 5;

// Example 2: Avoiding reuse in same scope
function calculateArea(width, height) {
  // Don't reuse parameter names as local variables
  let result = width * height;
  return result;
}

// Example 3: Constants for values that shouldn't change
const TAX_RATE = 0.08;
const MAX_USERS = 100;
```

<a name="reusing-variable-names-exercises"></a>
### Exercises
1. **Identify scope issues**
```javascript
// Identify the issues with variable scope in this code:
let count = 0;

function increment() {
  count += 1;
  let message = 'Count is ' + count;
  return message;
}

if (count < 5) {
  let result = increment();
  console.log(result);
}

console.log(message); // What will happen here?

// Your analysis here:
```

2. **Refactor variable reuse**
```javascript
// Refactor this code to avoid problematic variable reuse:
function processData(data) {
  let result = [];
  
  for (let i = 0; i < data.length; i++) {
    let item = data[i];
    let result = processItem(item); // Problematic reuse
    result.push(result); // This is wrong
  }
  
  return result;
}

// Your refactored code here:
```

3. **Fix variable shadowing**
```javascript
// The following code has unintended variable shadowing. Fix it.
const DEFAULT_COLOR = 'blue';

function createButton(color) {
  let DEFAULT_COLOR = color || 'red'; // This shadows the global constant
  return {
    color: DEFAULT_COLOR,
    label: 'Submit'
  };
}

console.log(createButton('green'));
console.log('Global DEFAULT_COLOR:', DEFAULT_COLOR); // Should still be 'blue'

// Your fixed code here:
```

---

## Strategy

<a name="strategy-code-inspiration"></a>
### Code Inspiration
1. **Problem-solving strategies**
```javascript
// Example 1: Breaking down problems
// Problem: Calculate the average of an array of numbers
function calculateAverage(numbers) {
  // Strategy: Sum all numbers, then divide by count
  let sum = 0;
  for (let i = 0; i < numbers.length; i++) {
    sum += numbers[i];
  }
  return sum / numbers.length;
}

// Example 2: Using helper functions
// Problem: Check if a string is a palindrome
function isPalindrome(str) {
  // Strategy: Clean string, then compare with reverse
  let cleaned = cleanString(str);
  return cleaned === reverseString(cleaned);
}

function cleanString(str) {
  return str.toLowerCase().replace(/[^a-z0-9]/g, '');
}

function reverseString(str) {
  return str.split('').reverse().join('');
}
```

2. **Algorithm strategies**
```javascript
// Example 1: Iterative approach
function factorialIterative(n) {
  let result = 1;
  for (let i = 2; i <= n; i++) {
    result *= i;
  }
  return result;
}

// Example 2: Recursive approach
function factorialRecursive(n) {
  if (n <= 1) return 1;
  return n * factorialRecursive(n - 1);
}

// Example 3: Divide and conquer
function findMax(arr, start = 0, end = arr.length - 1) {
  if (start === end) return arr[start];
  
  let mid = Math.floor((start + end) / 2);
  let leftMax = findMax(arr, start, mid);
  let rightMax = findMax(arr, mid + 1, end);
  
  return Math.max(leftMax, rightMax);
}
```

3. **Debugging strategies**
```javascript
// Example 1: Console logging strategy
function complexCalculation(a, b, c) {
  console.log('Input:', a, b, c);
  
  let step1 = a * b;
  console.log('Step 1 (a * b):', step1);
  
  let step2 = step1 + c;
  console.log('Step 2 (step1 + c):', step2);
  
  let result = Math.sqrt(step2);
  console.log('Result (sqrt(step2)):', result);
  
  return result;
}

// Example 2: Rubber duck debugging
// Explain your code line by line to find issues:
function problematicFunction(data) {
  // First, I'm filtering the data to only include active items
  let activeItems = data.filter(item => item.isActive);
  
  // Then I'm mapping to get just the values I need
  let values = activeItems.map(item => item.value);
  
  // Now I need to sum these values
  let sum = values.reduce((total, current) => total + current, 0);
  
  // Wait, should I check if the array is empty to avoid division by zero?
  return sum / values.length;
}
```

<a name="strategy-exercises"></a>
### Exercises
1. **Develop a strategy**
```javascript
// Develop a strategy to solve this problem:
// Write a function that takes an array of integers and returns
// the second largest number. [3, 1, 5, 2, 4] should return 4.

// Describe your strategy in words first, then implement:

// Strategy description:

// Your implementation:
function secondLargest(numbers) {
  // Your code here
}
```

2. **Compare strategies**
```javascript
// Implement two different strategies to solve this problem:
// Count how many times each word appears in a string

// Strategy 1: Using an object
function countWordsStrategy1(text) {
  // Your code here
}

// Strategy 2: Using a Map
function countWordsStrategy2(text) {
  // Your code here
}

// Test both strategies with sample input
```

3. **Optimization strategy**
```javascript
// The following function works but is inefficient. 
// Develop a strategy to optimize it and implement:
function hasDuplicateValues(array) {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      if (i !== j && array[i] === array[j]) {
        return true;
      }
    }
  }
  return false;
}

// Describe your optimization strategy:

// Your optimized implementation:
function hasDuplicateValuesOptimized(array) {
  // Your code here
}
```

---

## Conditionality

<a name="conditionality-code-inspiration"></a>
### Code Inspiration
1. **Basic conditional structures**
```javascript
// Example 1: if-else statements
let temperature = 25;

if (temperature > 30) {
  console.log('It\'s hot outside');
} else if (temperature > 20) {
  console.log('It\'s warm outside');
} else {
  console.log('It\'s cold outside');
}

// Example 2: Switch statements
let day = 'Monday';
switch (day) {
  case 'Monday':
    console.log('Start of the work week');
    break;
  case 'Friday':
    console.log('Almost weekend!');
    break;
  default:
    console.log('Middle of the week');
}
```

2. **Ternary operator**
```javascript
// Example 1: Simple ternary
let age = 20;
let canVote = age >= 18 ? 'Yes' : 'No';
console.log(canVote); // Yes

// Example 2: Multiple conditions with ternary
let score = 85;
let grade = score >= 90 ? 'A' :
            score >= 80 ? 'B' :
            score >= 70 ? 'C' :
            score >= 60 ? 'D' : 'F';
console.log(grade); // B

// Example 3: Ternary for assignment
let user = {
  name: 'Alice',
  preferences: null
};
let theme = user.preferences ? user.preferences.theme : 'default';
console.log(theme); // default
```

3. **Logical operators for conditionality**
```javascript
// Example 1: Short-circuit evaluation
let config = {
  theme: null
};
let selectedTheme = config.theme || 'light'; // Uses 'light' if theme is falsy
console.log(selectedTheme); // light

// Example 2: Optional chaining with nullish coalescing
let user = {
  profile: {
    settings: {
      notifications: true
    }
  }
};
let notifications = user?.profile?.settings?.notifications ?? false;
console.log(notifications); // true

// Example 3: Guard clauses
function processUser(user) {
  // Early return if invalid user
  if (!user || !user.email) {
    return 'Invalid user';
  }
  
  // Main logic here
  return `Processing user: ${user.email}`;
}
```

<a name="conditionality-exercises"></a>
### Exercises
1. **Simplify conditional logic**
```javascript
// Simplify the following conditional logic:
function getAccessLevel(user) {
  if (user) {
    if (user.role) {
      if (user.role === 'admin') {
        return 'full';
      } else if (user.role === 'editor') {
        return 'partial';
      } else {
        return 'limited';
      }
    } else {
      return 'limited';
    }
  } else {
    return 'none';
  }
}

// Your simplified version:
function getAccessLevelSimplified(user) {
  // Your code here
}
```

2. **Convert to ternary**
```javascript
// Convert the following if-else statements to ternary expressions:
let time = 14;
let greeting;

if (time < 12) {
  greeting = 'Good morning';
} else if (time < 18) {
  greeting = 'Good afternoon';
} else {
  greeting = 'Good evening';
}

// Your ternary version:
```

3. **Fix conditional bugs**
```javascript
// The following function has conditional bugs. Identify and fix them:
function calculateDiscount(price, isMember, couponCode) {
  let discount = 0;
  
  if (isMember = true) {
    discount += 0.1;
  }
  
  if (couponCode == 'SAVE10') {
    discount += 0.1;
  } else if (couponCode == 'SAVE20') {
    discount += 0.2;
  }
  
  if (discount > 0.3) {
    discount = 0.3;
  }
  
  return price * (1 - discount);
}

// Test cases that should work:
console.log(calculateDiscount(100, true, 'SAVE10')); // Should be 80 (20% off)
console.log(calculateDiscount(100, false, 'SAVE20')); // Should be 80 (20% off)

// Your fixed code:
```

---

## Sub-goal

<a name="sub-goal-code-inspiration"></a>
### Code Inspiration
1. **Breaking problems into sub-goals**
```javascript
// Example 1: User registration process
function registerUser(userData) {
  // Sub-goal 1: Validate input
  if (!isValidUserData(userData)) {
    throw new Error('Invalid user data');
  }
  
  // Sub-goal 2: Check if user already exists
  if (userExists(userData.email)) {
    throw new Error('User already exists');
  }
  
  // Sub-goal 3: Hash password
  let hashedPassword = hashPassword(userData.password);
  
  // Sub-goal 4: Save to database
  let userId = saveUserToDatabase({
    ...userData,
    password: hashedPassword
  });
  
  // Sub-goal 5: Send welcome email
  sendWelcomeEmail(userData.email);
  
  return userId;
}

// Example 2: Data processing pipeline
function processSalesData(rawData) {
  // Sub-goal 1: Clean the data
  let cleanedData = cleanData(rawData);
  
  // Sub-goal 2: Transform data structure
  let transformedData = transformData(cleanedData);
  
  // Sub-goal 3: Calculate metrics
  let metrics = calculateMetrics(transformedData);
  
  // Sub-goal 4: Generate report
  let report = generateReport(metrics);
  
  return report;
}
```

2. **Implementing sub-goals as functions**
```javascript
// Example 1: Password validation sub-goals
function validatePassword(password) {
  return (
    hasMinimumLength(password, 8) &&
    hasUppercaseLetter(password) &&
    hasLowercaseLetter(password) &&
    hasNumber(password)
  );
}

function hasMinimumLength(str, length) {
  return str.length >= length;
}

function hasUppercaseLetter(str) {
  return /[A-Z]/.test(str);
}

function hasLowercaseLetter(str) {
  return /[a-z]/.test(str);
}

function hasNumber(str) {
  return /[0-9]/.test(str);
}

// Example 2: Shopping cart sub-goals
function calculateCartTotal(cart) {
  let subtotal = calculateSubtotal(cart.items);
  let discounts = calculateDiscounts(cart);
  let tax = calculateTax(subtotal - discounts, cart.shippingAddress);
  let shipping = calculateShipping(cart.items, cart.shippingAddress);
  
  return subtotal - discounts + tax + shipping;
}
```

3. **Testing sub-goals independently**
```javascript
// Example 1: Testing individual sub-goals
// Test hasMinimumLength function
console.assert(hasMinimumLength('password', 8) === true, 'Should meet minimum length');
console.assert(hasMinimumLength('pass', 8) === false, 'Should not meet minimum length');

// Test hasUppercaseLetter function
console.assert(hasUppercaseLetter('Password') === true, 'Should have uppercase');
console.assert(hasUppercaseLetter('password') === false, 'Should not have uppercase');

// Example 2: Integration testing
// Test the complete validatePassword function
console.assert(validatePassword('StrongPass1') === true, 'Should be valid password');
console.assert(validatePassword('weak') === false, 'Should be invalid password');
```

<a name="sub-goal-exercises"></a>
### Exercises
1. **Identify sub-goals**
```javascript
// Identify the sub-goals needed to implement this function:
function formatUserAddress(user) {
  // Takes a user object and returns a formatted address string
  // Example: "123 Main St, Apt 4B, New York, NY 10001"
  
  // List the sub-goals here:
  // 1.
  // 2.
  // 3.
  // etc.
  
  // Your implementation:
}
```

2. **Implement sub-goal functions**
```javascript
// Implement the sub-goal functions for this main function:
function analyzeText(text) {
  // Returns an object with:
  // - totalCharacters (including spaces)
  // - totalWords
  // - totalSentences
  // - mostFrequentWord
  
  // Implement these helper functions:
  // function countCharacters(text) {}
  // function countWords(text) {}
  // function countSentences(text) {}
  // function findMostFrequentWord(text) {}
  
  // Your code here:
}
```

3. **Debug sub-goal integration**
```javascript
// The following function has issues with sub-goal integration. Fix it.
function createUsername(firstName, lastName, birthYear) {
  // Sub-goal 1: Clean names
  let cleanFirst = firstName.trim().toLowerCase();
  let cleanLast = lastName.trim().toLowerCase();
  
  // Sub-goal 2: Extract last two digits of birth year
  let yearDigits = birthYear.toString().slice(0, 2);
  
  // Sub-goal 3: Combine parts
  return cleanFirst + cleanLast + yearDigits;
}

// Test case that should work:
console.log(createUsername(' John ', 'Doe', 1990)); // Should return 'johndoe90'

// Your fixed code:
```

---

## Strings

<a name="strings-code-inspiration"></a>
### Code Inspiration
1. **String manipulation basics**
```javascript
// Example 1: Basic string operations
let greeting = 'Hello, World!';
console.log(greeting.length); // 13
console.log(greeting.toUpperCase()); // HELLO, WORLD!
console.log(greeting.toLowerCase()); // hello, world!
console.log(greeting.indexOf('World')); // 7
console.log(greeting.substring(7, 12)); // World

// Example 2: String concatenation
let firstName = 'John';
let lastName = 'Doe';
let fullName = firstName + ' ' + lastName; // John Doe
let templateFullName = `${firstName} ${lastName}`; // John Doe

// Example 3: String splitting and joining
let tags = 'js,html,css';
let tagArray = tags.split(','); // ['js', 'html', 'css']
let newTags = tagArray.join(' | '); // 'js | html | css'
```

2. **Regular expressions with strings**
```javascript
// Example 1: Basic regex patterns
let text = 'The quick brown fox jumps over 12 lazy dogs.';

// Match all digits
let digits = text.match(/\d/g); // ['1', '2']

// Replace all vowels
let noVowels = text.replace(/[aeiou]/gi, '*'); // 'Th* q**ck br*wn f*x j*mps *v*r 12 l*zy d*gs.'

// Test if string contains numbers
let hasNumbers = /\d/.test(text); // true

// Example 2: Email validation
function isValidEmail(email) {
  let emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
}

console.log(isValidEmail('test@example.com')); // true
console.log(isValidEmail('invalid.email')); // false
```

3. **String template literals**
```javascript
// Example 1: Basic template literals
let name = 'Alice';
let age = 25;
console.log(`My name is ${name} and I'm ${age} years old.`);

// Example 2: Multi-line strings
let multiLine = `
  This is a
  multi-line
  string
`;
console.log(multiLine);

// Example 3: Expression evaluation
let a = 5;
let b = 10;
console.log(`The sum of ${a} and ${b} is ${a + b}.`); // The sum of 5 and 10 is 15.

// Example 4: Tagged templates
function highlight(strings, ...values) {
  return strings.reduce((result, str, i) => {
    return result + str + (values[i] ? `<mark>${values[i]}</mark>` : '');
  }, '');
}

let name2 = 'Bob';
let score = 95;
console.log(highlight`Player ${name2} scored ${score} points.`);
```

<a name="strings-exercises"></a>
### Exercises
1. **String manipulation practice**
```javascript
// Write a function that takes a string and returns:
// 1. The string reversed
// 2. The string with vowels replaced with '*'
// 3. The string in title case (first letter of each word capitalized)

function manipulateString(input) {
  // Your code here
}

// Test cases:
console.log(manipulateString('hello world')); 
// Should return something like: 
// { reversed: 'dlrow olleh', noVowels: 'h*ll* w*rld', titleCase: 'Hello World' }
```

2. **String validation**
```javascript
// Write a function that validates a password string with these rules:
// - At least 8 characters long
// - Contains at least one uppercase letter
// - Contains at least one lowercase letter  
// - Contains at least one number
// - Contains at least one special character (!@#$%^&*)

function validatePassword(password) {
  // Your code here
}

// Test cases:
console.log(validatePassword('Weak1!')); // false
console.log(validatePassword('StrongPassword123!')); // true
```

3. **String parsing**
```javascript
// Write a function that parses a query string and returns an object
// Example: "name=John&age=30&city=NewYork" should return
// { name: 'John', age: '30', city: 'NewYork' }

function parseQueryString(queryString) {
  // Your code here
}

// Test case:
console.log(parseQueryString('name=John&age=30&city=NewYork'));
```

---

## Testing a sub-goal

<a name="testing-a-sub-goal-code-inspiration"></a>
### Code Inspiration
1. **Testing individual sub-goals**
```javascript
// Example 1: Testing a string validation sub-goal
function hasMinimumLength(str, minLength) {
  return str.length >= minLength;
}

// Tests for the sub-goal
console.assert(hasMinimumLength('password', 8) === true, 
  'hasMinimumLength should return true for strings meeting minimum length');
console.assert(hasMinimumLength('pass', 8) === false, 
  'hasMinimumLength should return false for strings below minimum length');

// Example 2: Testing a calculation sub-goal  
function calculateTax(subtotal, taxRate) {
  return subtotal * taxRate;
}

// Tests for the sub-goal
console.assert(calculateTax(100, 0.08) === 8, 
  'calculateTax should correctly calculate tax amount');
console.assert(calculateTax(0, 0.08) === 0, 
  'calculateTax should return 0 for zero subtotal');
```

2. **Mocking dependencies for sub-goal testing**
```javascript
// Example 1: Testing a function with dependencies
function getUserFullName(userId, userService) {
  let user = userService.getUser(userId);
  return `${user.firstName} ${user.lastName}`;
}

// Mock userService for testing
let mockUserService = {
  getUser: function(id) {
    return { firstName: 'John', lastName: 'Doe' };
  }
};

// Test the function with mock service
console.assert(
  getUserFullName(123, mockUserService) === 'John Doe',
  'getUserFullName should return full name'
);

// Example 2: Testing API call sub-goals with mocking
function fetchUserData(userId) {
  return fetch(`/api/users/${userId}`)
    .then(response => response.json())
    .then(data => processUserData(data));
}

// Mock fetch for testing
global.fetch = jest.fn(() => 
  Promise.resolve({
    json: () => Promise.resolve({ name: 'John', age: 30 })
  })
);

// Test the function
fetchUserData(123).then(data => {
  console.assert(data.name === 'John', 'Should return user data');
});
```

3. **Edge case testing for sub-goals**
```javascript
// Example 1: Testing edge cases for a validation function
function isValidUsername(username) {
  // Username must be 3-20 characters, alphanumeric only
  let regex = /^[a-zA-Z0-9]{3,20}$/;
  return regex.test(username);
}

// Test various edge cases
console.assert(isValidUsername('abc') === true, 'Minimum length should work');
console.assert(isValidUsername('a'.repeat(20)) === true, 'Maximum length should work');
console.assert(isValidUsername('a'.repeat(21)) === false, 'Over maximum should fail');
console.assert(isValidUsername('ab') === false, 'Under minimum should fail');
console.assert(isValidUsername('test user') === false, 'Spaces should fail');
console.assert(isValidUsername('test@user') === false, 'Special chars should fail');

// Example 2: Testing number handling edge cases
function parsePercentage(value) {
  if (typeof value === 'string') {
    value = value.replace('%', '');
  }
  let num = Number(value);
  return isNaN(num) ? 0 : num / 100;
}

// Test edge cases
console.assert(parsePercentage('50%') === 0.5, 'Should parse percentage string');
console.assert(parsePercentage(50) === 0.5, 'Should parse number');
console.assert(parsePercentage('invalid') === 0, 'Should handle invalid input');
console.assert(parsePercentage('') === 0, 'Should handle empty string');
```

<a name="testing-a-sub-goal-exercises"></a>
### Exercises
1. **Write tests for sub-goals**
```javascript
// Write tests for the following sub-goal functions:
function capitalizeFirstLetter(str) {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

function getInitials(firstName, lastName) {
  return `${firstName.charAt(0)}${lastName.charAt(0)}`.toUpperCase();
}

// Your tests here:
```

2. **Test edge cases**
```javascript
// Write tests for edge cases for this function:
function divideNumbers(a, b) {
  if (b === 0) {
    throw new Error('Division by zero');
  }
  return a / b;
}

// Your tests for edge cases:
```

3. **Create test mocks**
```javascript
// The following function has a dependency. Create a mock for testing.
function getUserProfile(userId, databaseService) {
  let user = databaseService.getUser(userId);
  let preferences = databaseService.getPreferences(userId);
  
  return {
    name: user.name,
    email: user.email,
    theme: preferences.theme || 'light'
  };
}

// Create a mock databaseService and write tests for getUserProfile:

// Your mock and tests here:
```

---

## Sub-goal #2

<a name="sub-goal-2-code-inspiration"></a>
### Code Inspiration
1. **Advanced sub-goal decomposition**
```javascript
// Example 1: E-commerce checkout process
function processCheckout(order, paymentInfo, user) {
  // Sub-goal 1: Validate order completeness
  if (!isOrderValid(order)) {
    throw new Error('Invalid order');
  }
  
  // Sub-goal 2: Process payment
  let paymentResult = processPayment(order.total, paymentInfo);
  if (!paymentResult.success) {
    throw new Error('Payment failed: ' + paymentResult.message);
  }
  
  // Sub-goal 3: Update inventory
  updateInventory(order.items);
  
  // Sub-goal 4: Generate shipping label
  let shippingLabel = generateShippingLabel(order, user);
  
  // Sub-goal 5: Send confirmation
  sendOrderConfirmation(order, user, paymentResult);
  
  // Sub-goal 6: Record analytics
  recordAnalytics('purchase', order, user);
  
  return {
    success: true,
    orderId: order.id,
    shippingLabel: shippingLabel
  };
}

// Example 2: Data export pipeline
function exportUserData(userId, format) {
  // Sub-goal 1: Fetch user data
  let userData = fetchUserData(userId);
  
  // Sub-goal 2: Fetch user activity
  let userActivity = fetchUserActivity(userId);
  
  // Sub-goal 3: Transform data based on format
  let transformedData = transformData(userData, userActivity, format);
  
  // Sub-goal 4: Generate export file
  let exportFile = generateExportFile(transformedData, format);
  
  // Sub-goal 5: Store export record
  storeExportRecord(userId, format, exportFile);
  
  return exportFile;
}
```

2. **Error handling in sub-goals**
```javascript
// Example 1: Robust sub-goal with error handling
function processUserUpload(file) {
  try {
    // Sub-goal 1: Validate file
    if (!isValidFileType(file)) {
      throw new Error('Invalid file type');
    }
    
    // Sub-goal 2: Parse file content
    let content = parseFileContent(file);
    
    // Sub-goal 3: Validate data structure
    if (!isValidUserData(content)) {
      throw new Error('Invalid data structure');
    }
    
    // Sub-goal 4: Process each user
    let results = [];
    for (let userData of content.users) {
      try {
        let result = processSingleUser(userData);
        results.push({ success: true, data: result });
      } catch (userError) {
        results.push({ 
          success: false, 
          error: userError.message,
          data: userData 
        });
      }
    }
    
    // Sub-goal 5: Generate report
    let report = generateUploadReport(results);
    
    return {
      success: true,
      processed: results.filter(r => r.success).length,
      failed: results.filter(r => !r.success).length,
      report: report
    };
    
  } catch (error) {
    return {
      success: false,
      error: error.message
    };
  }
}
```

3. **Parallel sub-goal execution**
```javascript
// Example 1: Parallel API calls
async function fetchUserDashboardData(userId) {
  // Execute sub-goals in parallel
  let [userData, recentActivity, notifications, preferences] = await Promise.all([
    fetchUserData(userId),           // Sub-goal 1
    fetchRecentActivity(userId),     // Sub-goal 2  
    fetchNotifications(userId),      // Sub-goal 3
    fetchUserPreferences(userId)     // Sub-goal 4
  ]);
  
  // Sub-goal 5: Combine and transform data
  return {
    user: transformUserData(userData),
    activity: processActivity(recentActivity),
    notifications: filterNotifications(notifications),
    settings: preferences
  };
}

// Example 2: Sequential sub-goals with error handling
async function performDataMigration(source, target) {
  try {
    // Sub-goal 1: Verify connections
    await verifyConnection(source);
    await verifyConnection(target);
    
    // Sub-goal 2: Export data from source
    let data = await exportData(source);
    
    // Sub-goal 3: Transform data format
    let transformedData = transformDataForTarget(data, target);
    
    // Sub-goal 4: Import data to target
    let result = await importData(target, transformedData);
    
    // Sub-goal 5: Validate migration
    await validateMigration(source, target, result);
    
    return { success: true, stats: result.stats };
    
  } catch (error) {
    // Sub-goal 6: Handle errors and cleanup
    await cleanupFailedMigration(target);
    return { success: false, error: error.message };
  }
}
```

<a name="sub-goal-2-exercises"></a>
### Exercises
1. **Decompose complex task**
```javascript
// Decompose this complex task into sub-goals:
function generateMonthlyReport(month, year) {
  // This function should:
  // 1. Fetch sales data for the specified month/year
  // 2. Calculate total revenue, expenses, and profit
  // 3. Compare with previous month and same month last year
  // 4. Identify top-performing products
  // 5. Generate PDF report
  // 6. Email report to management
  // 7. Store report in database
  
  // List the sub-goals here:
  // 1.
  // 2.
  // 3.
  // etc.
}
```

2. **Implement error handling for sub-goals**
```javascript
// Add proper error handling to this function:
function processOrder(order) {
  let inventory = checkInventory(order.items);
  let payment = processPayment(order.total, order.paymentMethod);
  updateInventory(order.items);
  createShippingLabel(order);
  sendConfirmationEmail(order.customerEmail);
  
  return { success: true, orderId: order.id };
}

// Your implementation with error handling:
```

3. **Optimize sub-goal execution**
```javascript
// The following function executes sub-goals sequentially. 
// Identify which could run in parallel and refactor:
async function getUserProfile(userId) {
  let userInfo = await fetchUserInfo(userId);        // Sub-goal 1
  let userPosts = await fetchUserPosts(userId);      // Sub-goal 2
  let userFriends = await fetchUserFriends(userId);  // Sub-goal 3
  let userPhotos = await fetchUserPhotos(userId);    // Sub-goal 4
  
  return {
    info: userInfo,
    posts: userPosts,
    friends: userFriends,
    photos: userPhotos
  };
}

// Your optimized version:
```

---

## Refactoring repetition

<a name="refactoring-repetition-code-inspiration"></a>
### Code Inspiration
1. **Identifying code repetition**
```javascript
// Example 1: Repeated validation logic
// Before refactoring:
function processUserRegistration(userData) {
  if (!userData.email || !userData.email.includes('@')) {
    throw new Error('Invalid email');
  }
  if (!userData.password || userData.password.length < 8) {
    throw new Error('Password must be at least 8 characters');
  }
  // ... more validation
}

function updateUserProfile(userData) {
  if (!userData.email || !userData.email.includes('@')) {
    throw new Error('Invalid email');
  }
  // Different validation but same email check repeated
}

// After refactoring:
function validateEmail(email) {
  if (!email || !email.includes('@')) {
    throw new Error('Invalid email');
  }
}

function processUserRegistration(userData) {
  validateEmail(userData.email);
  // ... other validation
}

function updateUserProfile(userData) {
  validateEmail(userData.email);
  // ... other validation
}
```

2. **Extracting repeated patterns**
```javascript
// Example 1: Repeated API call pattern
// Before refactoring:
async function getUser(id) {
  try {
    let response = await fetch(`/api/users/${id}`);
    if (!response.ok) throw new Error('HTTP error');
    return await response.json();
  } catch (error) {
    console.error('Failed to fetch user:', error);
    throw error;
  }
}

async function getPosts(userId) {
  try {
    let response = await fetch(`/api/posts?userId=${userId}`);
    if (!response.ok) throw new Error('HTTP error');
    return await response.json();
  } catch (error) {
    console.error('Failed to fetch posts:', error);
    throw error;
  }
}

// After refactoring:
async function apiFetch(endpoint) {
  try {
    let response = await fetch(endpoint);
    if (!response.ok) throw new Error('HTTP error');
    return await response.json();
  } catch (error) {
    console.error(`Failed to fetch ${endpoint}:`, error);
    throw error;
  }
}

async function getUser(id) {
  return apiFetch(`/api/users/${id}`);
}

async function getPosts(userId) {
  return apiFetch(`/api/posts?userId=${userId}`);
}
```

3. **Parameterizing repeated logic**
```javascript
// Example 1: Repeated formatting logic
// Before refactoring:
function formatUserDate(date) {
  return new Date(date).toLocaleDateString('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  });
}

function formatPostDate(date) {
  return new Date(date).toLocaleDateString('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  });
}

// After refactoring:
function formatDate(date, options = {}) {
  const defaultOptions = {
    year: 'numeric',
    month: 'long', 
    day: 'numeric'
  };
  return new Date(date).toLocaleDateString('en-US', 
    { ...defaultOptions, ...options }
  );
}

function formatUserDate(date) {
  return formatDate(date);
}

function formatPostDate(date) {
  return formatDate(date, { weekday: 'long' }); // Can override defaults
}

// Example 2: Repeated calculation pattern
function calculateTotalWithTax(amount, taxRate) {
  return amount + (amount * taxRate);
}

function calculateDiscountPrice(originalPrice, discountPercent) {
  return originalPrice - (originalPrice * discountPercent);
}

// Refactor to generic calculation function:
function calculatePercentage(base, percentage, isAddition = true) {
  return isAddition 
    ? base + (base * percentage) 
    : base - (base * percentage);
}
```

<a name="refactoring-repetition-exercises"></a>
### Exercises
1. **Identify and extract repetition**
```javascript
// Identify repetition in this code and refactor:
function calculateCircleArea(radius) {
  return Math.PI * radius * radius;
}

function calculateCircleCircumference(radius) {
  return 2 * Math.PI * radius;
}

function calculateSphereVolume(radius) {
  return (4/3) * Math.PI * radius * radius * radius;
}

function calculateSphereSurfaceArea(radius) {
  return 4 * Math.PI * radius * radius;
}

// Your refactored code:
```

2. **Refactor repeated validation**
```javascript
// Refactor the repeated validation logic:
function createUser(userData) {
  if (!userData.username || userData.username.trim() === '') {
    throw new Error('Username is required');
  }
  if (userData.username.length < 3) {
    throw new Error('Username must be at least 3 characters');
  }
  if (!userData.email || !userData.email.includes('@')) {
    throw new Error('Valid email is required');
  }
  // ... more user validation
}

function updateUser(userId, userData) {
  if (!userData.username || userData.username.trim() === '') {
    throw new Error('Username is required');
  }
  if (userData.username.length < 3) {
    throw new Error('Username must be at least 3 characters');
  }
  if (!userData.email || !userData.email.includes('@')) {
    throw new Error('Valid email is required');
  }
  // ... more user validation
}

// Your refactored code:
```

3. **Create reusable utility functions**
```javascript
// Create reusable utility functions from this repeated pattern:
function displayError(message, elementId) {
  let element = document.getElementById(elementId);
  element.textContent = message;
  element.style.color = 'red';
  element.style.display = 'block';
}

function displaySuccess(message, elementId) {
  let element = document.getElementById(elementId);
  element.textContent = message;
  element.style.color = 'green';
  element.style.display = 'block';
}

function displayWarning(message, elementId) {
  let element = document.getElementById(elementId);
  element.textContent = message;
  element.style.color = 'orange';
  element.style.display = 'block';
}

// Your utility function(s):
```

---

## Identifying missing tests

<a name="identifying-missing-tests-code-inspiration"></a>
### Code Inspiration
1. **Analyzing test coverage**
```javascript
// Example 1: Function with incomplete test coverage
function calculateDiscount(price, isMember, couponCode) {
  let discount = 0;
  
  if (isMember) {
    discount += 0.1; // 10% member discount
  }
  
  if (couponCode === 'SAVE10') {
    discount += 0.1; // Additional 10% off
  } else if (couponCode === 'SAVE20') {
    discount += 0.2; // Additional 20% off
  }
  
  // Maximum discount cannot exceed 30%
  if (discount > 0.3) {
    discount = 0.3;
  }
  
  return price * (1 - discount);
}

// Existing tests might cover:
// - Regular price without membership or coupon
// - Member discount without coupon
// - Coupon discount without membership

// Missing tests might include:
// - Member with SAVE10 coupon (should get 20% off)
// - Member with SAVE20 coupon (should get 30% off, not more)
// - Non-member with SAVE20 coupon
// - Invalid coupon codes
// - Edge cases like zero price, negative price
```

2. **Boundary value analysis**
```javascript
// Example 1: Function with boundary conditions
function getTemperatureDescription(temp) {
  if (temp <= 0) {
    return 'Freezing';
  } else if (temp < 15) {
    return 'Cold';
  } else if (temp < 25) {
    return 'Warm';
  } else {
    return 'Hot';
  }
}

// Tests should cover boundary values:
// - temp = 0 (boundary between Freezing and Cold)
// - temp = 15 (boundary between Cold and Warm)  
// - temp = 25 (boundary between Warm and Hot)
// - Also values just below/above these boundaries

// Example 2: Input validation boundaries
function validateAge(age) {
  return age >= 13 && age <= 120;
}

// Important test cases:
// - age = 12 (should be invalid)
// - age = 13 (should be valid, lower boundary)
// - age = 120 (should be valid, upper boundary)
// - age = 121 (should be invalid)
// - age = 0, negative numbers, non-integers
```

3. **Edge case identification**
```javascript
// Example 1: String handling function
function truncateString(str, maxLength) {
  if (str.length <= maxLength) {
    return str;
  }
  return str.substring(0, maxLength - 3) + '...';
}

// Edge cases to test:
// - Empty string
// - String shorter than maxLength
// - String equal to maxLength
// - String longer than maxLength
// - maxLength = 0, negative numbers
// - Unicode characters, emojis
// - Very long strings

// Example 2: Array processing function
function findDuplicateNumbers(numbers) {
  let seen = new Set();
  let duplicates = new Set();
  
  for (let num of numbers) {
    if (seen.has(num)) {
      duplicates.add(num);
    }
    seen.add(num);
  }
  
  return Array.from(duplicates);
}

// Edge cases to test:
// - Empty array
// - Array with no duplicates
// - Array with one duplicate
// - Array with multiple duplicates
// - Array with negative numbers, zero
// - Array with very large numbers
// - Array with non-number values (should handle error)
```

<a name="identifying-missing-tests-exercises"></a>
### Exercises
1. **Identify missing test cases**
```javascript
// Identify missing test cases for this function:
function isPrime(number) {
  if (number <= 1) return false;
  if (number <= 3) return true;
  if (number % 2 === 0 || number % 3 === 0) return false;
  
  for (let i = 5; i * i <= number; i += 6) {
    if (number % i === 0 || number % (i + 2) === 0) return false;
  }
  
  return true;
}

// Existing tests might cover:
// - 2 (prime)
// - 3 (prime) 
// - 4 (not prime)
// - 5 (prime)

// List missing test cases:
```

2. **Create comprehensive test suite**
```javascript
// Write a comprehensive test suite for this function:
function formatPhoneNumber(phoneNumber) {
  // Remove all non-digit characters
  let cleaned = phoneNumber.replace(/\D/g, '');
  
  // Check if number has 10 digits (US format)
  if (cleaned.length === 10) {
    return `(${cleaned.substring(0, 3)}) ${cleaned.substring(3, 6)}-${cleaned.substring(6)}`;
  }
  
  // Check if number has 11 digits and starts with 1
  if (cleaned.length === 11 && cleaned[0] === '1') {
    return `+1 (${cleaned.substring(1, 4)}) ${cleaned.substring(4, 7)}-${cleaned.substring(7)}`;
  }
  
  // Return original if format doesn't match
  return phoneNumber;
}

// Your test cases:
```

3. **Find edge cases in existing code**
```javascript
// Review this function and list edge cases that should be tested:
function calculateShippingCost(orderTotal, itemsCount, destination) {
  let baseCost = 5.99;
  
  // Free shipping for orders over $50
  if (orderTotal > 50) {
    baseCost = 0;
  }
  
  // Additional cost for multiple items
  if (itemsCount > 5) {
    baseCost += (itemsCount - 5) * 0.5;
  }
  
  // International shipping surcharge
  if (destination !== 'US') {
    baseCost += 15.99;
  }
  
  return Math.max(baseCost, 0); // Ensure non-negative
}

// List edge cases to test:
```

---

## External Resources

1. [MDN Web Docs - JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Comprehensive JavaScript documentation and tutorials

2. [JavaScript.info](https://javascript.info/) - Modern JavaScript tutorial from basics to advanced topics

3. [freeCodeCamp JavaScript Curriculum](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/) - Interactive JavaScript learning with exercises
