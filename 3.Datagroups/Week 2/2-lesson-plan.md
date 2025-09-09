# JavaScript Practice Lesson: Working with Objects and Query Strings

## Topics to Practice
- [Accessing Properties](#accessing-properties)
  - [Code Inspiration](#accessing-properties-code-inspiration)
  - [Exercises](#accessing-properties-exercises)
- [Query Strings](#query-strings)
  - [Code Inspiration](#query-strings-code-inspiration)
  - [Exercises](#query-strings-exercises)
- [No Parameters](#no-parameters)
  - [Code Inspiration](#no-parameters-code-inspiration)
  - [Exercises](#no-parameters-exercises)
- [Parsing a Single Key-Value Pair](#parsing-a-single-key-value-pair)
  - [Code Inspiration](#parsing-a-single-key-value-pair-code-inspiration)
  - [Exercises](#parsing-a-single-key-value-pair-exercises)
- [Access with Variables](#access-with-variables)
  - [Code Inspiration](#access-with-variables-code-inspiration)
  - [Exercises](#access-with-variables-exercises)
- [Parsing Multiple Params](#parsing-multiple-params)
  - [Code Inspiration](#parsing-multiple-params-code-inspiration)
  - [Exercises](#parsing-multiple-params-exercises)
- [Solving Problems with Objects](#solving-problems-with-objects)
  - [Code Inspiration](#solving-problems-with-objects-code-inspiration)
  - [Exercises](#solving-problems-with-objects-exercises)
- [Conflict Resolution](#conflict-resolution)
  - [Code Inspiration](#conflict-resolution-code-inspiration)
  - [Exercises](#conflict-resolution-exercises)

---

## Accessing Properties
<a name="accessing-properties-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Dot notation
const person = {
  name: "Alice",
  age: 30,
  profession: "developer"
};
console.log(person.name); // Output: "Alice"

// Example 2: Bracket notation
const property = "age";
console.log(person[property]); // Output: 30
```

<a name="accessing-properties-exercises"></a>
### Exercises
```javascript
// Exercise 1: Complete the function to return the title property
const book = {
  title: "JavaScript for Beginners",
  author: "John Doe",
  year: 2023
};

function getBookTitle() {
  // Your code here
}

// Exercise 2: Complete the function to return the value of the dynamic property
const car = {
  make: "Toyota",
  model: "Camry",
  year: 2020
};

function getCarProperty(propertyName) {
  // Your code here
}
```

---

## Query Strings
<a name="query-strings-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Simple query string
const queryString = "?name=John&age=25";
console.log(queryString); // Output: "?name=John&age=25"

// Example 2: Creating a query string from an object
const params = {
  search: "javascript",
  page: 1,
  sort: "newest"
};

const queryParams = new URLSearchParams(params).toString();
console.log(queryParams); // Output: "search=javascript&page=1&sort=newest"
```

<a name="query-strings-exercises"></a>
### Exercises
```javascript
// Exercise 1: Create a query string from the following object
const filters = {
  category: "books",
  priceRange: "0-50",
  inStock: true
};

function createQueryString() {
  // Your code here
}

// Exercise 2: Extract the value of 'page' from the query string
const url = "https://example.com/products?category=electronics&page=2&sort=price";

function getPageNumber() {
  // Your code here
}
```

---

## No Parameters
<a name="no-parameters-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Function with no parameters
function getCurrentDate() {
  return new Date().toDateString();
}
console.log(getCurrentDate()); // Output: Current date string

// Example 2: Object method with no parameters
const calculator = {
  value: 0,
  reset() {
    this.value = 0;
    return this.value;
  }
};
console.log(calculator.reset()); // Output: 0
```

<a name="no-parameters-exercises"></a>
### Exercises
```javascript
// Exercise 1: Create a function that returns a random number between 1-100
function getRandomNumber() {
  // Your code here
}

// Exercise 2: Complete the user object method
const user = {
  name: "Sarah",
  loginCount: 0,
  // Add a method that increments loginCount by 1
  incrementLogin() {
    // Your code here
  }
};
```

---

## Parsing a Single Key-Value Pair
<a name="parsing-a-single-key-value-pair-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Parsing from a string
const keyValueStr = "theme=dark";
const [key, value] = keyValueStr.split('=');
console.log(key); // Output: "theme"
console.log(value); // Output: "dark"

// Example 2: Creating a key-value pair
const settings = {
  fontSize: 16
};
const settingPair = `fontSize=${settings.fontSize}`;
console.log(settingPair); // Output: "fontSize=16"
```

<a name="parsing-a-single-key-value-pair-exercises"></a>
### Exercises
```javascript
// Exercise 1: Parse the key-value string into an object
const settingString = "language=JavaScript";

function parseKeyValue(str) {
  // Your code here
}

// Exercise 2: Create a key-value string from the input
function createKeyValuePair(key, value) {
  // Your code here
}
```

---

## Access with Variables
<a name="access-with-variables-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Dynamic property access
const person = {
  name: "Maria",
  age: 28,
  job: "designer"
};

const propertyToAccess = "job";
console.log(person[propertyToAccess]); // Output: "designer"

// Example 2: Using variables to set properties
const newProperty = "hobbies";
person[newProperty] = ["reading", "painting"];
console.log(person.hobbies); // Output: ["reading", "painting"]
```

<a name="access-with-variables-exercises"></a>
### Exercises
```javascript
// Exercise 1: Complete the function to access object properties dynamically
const student = {
  name: "Alex",
  grade: "A",
  subject: "Math"
};

function getProperty(obj, propName) {
  // Your code here
}

// Exercise 2: Add a new property using a variable as the key
const newKey = "attendance";
const newValue = "95%";

function addProperty(obj, key, value) {
  // Your code here
}
```

---

## Parsing Multiple Params
<a name="parsing-multiple-params-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Parsing multiple query parameters
const queryString = "?name=John&age=30&city=NewYork";
const urlParams = new URLSearchParams(queryString);

console.log(urlParams.get('name')); // Output: "John"
console.log(urlParams.get('age')); // Output: "30"
console.log(urlParams.get('city')); // Output: "NewYork"

// Example 2: Converting an object to query string
const params = {
  name: "Jane",
  age: 25,
  occupation: "developer"
};

const queryString = Object.entries(params)
  .map(([key, value]) => `${key}=${value}`)
  .join('&');
console.log(queryString); // Output: "name=Jane&age=25&occupation=developer"
```

<a name="parsing-multiple-params-exercises"></a>
### Exercises
```javascript
// Exercise 1: Parse the query string and return an object
const queryString = "?product=laptop&price=1200&inStock=true";

function parseQueryString(queryStr) {
  // Your code here
}

// Exercise 2: Convert the object to a query string (without using URLSearchParams)
const filters = {
  category: "electronics",
  minPrice: 100,
  maxPrice: 500,
  rating: 4
};

function objectToQueryString(obj) {
  // Your code here
}
```

---

## Solving Problems with Objects
<a name="solving-problems-with-objects-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Using objects to count occurrences
const fruits = ['apple', 'banana', 'apple', 'orange', 'banana', 'apple'];
const fruitCount = {};

fruits.forEach(fruit => {
  fruitCount[fruit] = (fruitCount[fruit] || 0) + 1;
});

console.log(fruitCount); // Output: {apple: 3, banana: 2, orange: 1}

// Example 2: Using objects to map values
const userRoles = {
  1: "admin",
  2: "editor",
  3: "viewer"
};

const users = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" }
];

users.forEach(user => {
  user.role = userRoles[user.id];
});
console.log(users);
```

<a name="solving-problems-with-objects-exercises"></a>
### Exercises
```javascript
// Exercise 1: Count the occurrences of each word in the array
const words = ['hello', 'world', 'hello', 'javascript', 'world', 'hello'];

function countWords(arr) {
  // Your code here
}

// Exercise 2: Transform the array of products using the priceMap
const products = [
  { id: 1, name: "Laptop" },
  { id: 2, name: "Phone" },
  { id: 3, name: "Tablet" }
];

const priceMap = {
  1: 999,
  2: 499,
  3: 299
};

function addPrices(products, prices) {
  // Your code here
}
```

---

## Conflict Resolution
<a name="conflict-resolution-code-inspiration"></a>
### Code Inspiration
```javascript
// Example 1: Resolving conflicting properties when merging objects
const defaults = {
  theme: "light",
  fontSize: 16,
  notifications: true
};

const userSettings = {
  theme: "dark",
  language: "en"
};

// Merge with user settings taking precedence
const mergedSettings = { ...defaults, ...userSettings };
console.log(mergedSettings);
// Output: {theme: "dark", fontSize: 16, notifications: true, language: "en"}

// Example 2: Custom conflict resolution
function mergeWithConflictResolution(obj1, obj2, resolveFn) {
  const result = { ...obj1 };
  for (let key in obj2) {
    if (key in result) {
      result[key] = resolveFn(result[key], obj2[key]);
    } else {
      result[key] = obj2[key];
    }
  }
  return result;
}

// Resolve by taking the larger number
const stats1 = { score: 100, level: 5 };
const stats2 = { score: 150, health: 100 };

const merged = mergeWithConflictResolution(stats1, stats2, (a, b) => Math.max(a, b));
console.log(merged); // Output: {score: 150, level: 5, health: 100}
```

<a name="conflict-resolution-exercises"></a>
### Exercises
```javascript
// Exercise 1: Merge two objects with user preferences taking precedence
const defaultPreferences = {
  theme: "light",
  language: "en",
  autoSave: true
};

const userPreferences = {
  theme: "dark",
  notifications: false
};

function mergePreferences(defaults, user) {
  // Your code here
}

// Exercise 2: Create a function that merges two objects with custom conflict resolution
// When the same key exists in both objects, concatenate the string values
const obj1 = { greeting: "Hello", name: "John" };
const obj2 = { greeting: "Hi", age: 30 };

function mergeConcatenateStrings(obj1, obj2) {
  // Your code here
}
```

---

## Additional Resources

1. [MDN Web Docs: Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects) - Comprehensive guide to JavaScript objects
2. [JavaScript.info: Objects](https://javascript.info/object) - Detailed tutorial on objects with examples
3. [URLSearchParams API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams) - Official documentation for working with query strings
