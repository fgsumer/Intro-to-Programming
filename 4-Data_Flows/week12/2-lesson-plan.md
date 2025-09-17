* [Synchronous Execution](#synchronous-execution)
  * [Code Inspiration](#synchronous-code-inspiration)
  * [Exercises](#synchronous-exercises)
* [Latency](#latency)
  * [Code Inspiration](#latency-code-inspiration)
  * [Exercises](#latency-exercises)
* [Callbacks](#callbacks)
  * [Code Inspiration](#callbacks-code-inspiration)
  * [Exercises](#callbacks-exercises)
* [Promises](#promises)
  * [Code Inspiration](#promises-code-inspiration)
  * [Exercises](#promises-exercises)
* [Using .then()](#using-then)
  * [Code Inspiration](#using-then-code-inspiration)
  * [Exercises](#using-then-exercises)
* [Async/Await](#async-await)
  * [Code Inspiration](#async-await-code-inspiration)
  * [Exercises](#async-await-exercises)
* [Using .fetch()](#using-fetch)
  * [Code Inspiration](#using-fetch-code-inspiration)
  * [Exercises](#using-fetch-exercises)

---

## Synchronous Execution

### Synchronous Code Inspiration
```javascript
// Example 1: Simple synchronous execution
console.log("Step 1");
console.log("Step 2");
console.log("Step 3");

// Example 2: Synchronous function calls
function greet(name) {
  return `Hello, ${name}!`;
}

const message = greet("Alice");
console.log(message);
```

### Synchronous Exercises
```javascript
// Exercise 1: Complete the synchronous function
function calculateArea(width, height) {
  // Your code here
}

const area = calculateArea(5, 8);
console.log(area); // Should output: 40

// Exercise 2: Fix the execution order
console.log("Starting the process...");
// Add your code here to make sure this logs after the previous line
console.log("Process completed!");
```

---

## Latency

### Latency Code Inspiration
```javascript
// Example 1: Simulating latency with setTimeout
console.log("Before latency");
setTimeout(() => {
  console.log("After 2 seconds");
}, 2000);
console.log("After latency call");

// Example 2: Multiple latency simulations
console.log("Start");
setTimeout(() => console.log("First timeout"), 1000);
setTimeout(() => console.log("Second timeout"), 500);
console.log("End");
```

### Latency Exercises
```javascript
// Exercise 1: Create a delayed greeting
function delayedGreeting(name, delay) {
  // Your code here
}

delayedGreeting("Bob", 1500); // Should log "Hello, Bob!" after 1.5 seconds

// Exercise 2: Sequence of delayed messages
console.log("Program started");
// Add your code here to log messages with different delays
```

---

## Callbacks

### Callbacks Code Inspiration
```javascript
// Example 1: Simple callback function
function processData(data, callback) {
  const processed = data.toUpperCase();
  callback(processed);
}

processData("hello", (result) => {
  console.log(result); // Outputs: HELLO
});

// Example 2: Error handling with callbacks
function divide(a, b, success, error) {
  if (b === 0) {
    error("Division by zero");
  } else {
    success(a / b);
  }
}

divide(10, 2, 
  (result) => console.log(result), 
  (err) => console.error(err)
);
```

### Callbacks Exercises
```javascript
// Exercise 1: Implement a callback function
function processArray(arr, callback) {
  // Your code here
}

processArray([1, 2, 3], (result) => {
  console.log(result); // Should output: [2, 4, 6] (doubled values)
});

// Exercise 2: Create a callback-based timer
function setTimer(duration, callback) {
  // Your code here
}

setTimer(3000, () => {
  console.log("Timer completed!");
});
```

---

## Promises

### Promises Code Inspiration
```javascript
// Example 1: Creating a simple promise
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Promise resolved!");
  }, 1000);
});

myPromise.then((message) => {
  console.log(message);
});

// Example 2: Promise with error handling
const dividePromise = (a, b) => {
  return new Promise((resolve, reject) => {
    if (b === 0) {
      reject("Division by zero");
    } else {
      resolve(a / b);
    }
  });
};

dividePromise(10, 2)
  .then(result => console.log(result))
  .catch(error => console.error(error));
```

### Promises Exercises
```javascript
// Exercise 1: Create a promise that resolves after a delay
function createDelayPromise(delay) {
  // Your code here
}

createDelayPromise(2000).then(() => {
  console.log("2 seconds have passed");
});

// Exercise 2: Convert callback function to promise
function readFileCallback(filename, callback) {
  setTimeout(() => {
    callback(`Content of ${filename}`);
  }, 1000);
}

function readFilePromise(filename) {
  // Your code here to return a promise
}

readFilePromise("test.txt").then(content => {
  console.log(content);
});
```

---

## Using .then()

### Using .then() Code Inspiration
```javascript
// Example 1: Chaining .then() methods
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

// Example 2: Multiple promise handling with .then()
const promise1 = Promise.resolve(3);
const promise2 = 42;
const promise3 = new Promise((resolve) => {
  setTimeout(resolve, 100, 'foo');
});

Promise.all([promise1, promise2, promise3])
  .then(values => {
    console.log(values); // [3, 42, "foo"]
  });
```

### Using .then() Exercises
```javascript
// Exercise 1: Chain multiple operations
function getUser() {
  return Promise.resolve({ id: 1, name: "John" });
}

function getPosts(userId) {
  return Promise.resolve([{ id: 1, title: "Post 1" }, { id: 2, title: "Post 2" }]);
}

// Use .then() chaining to get user and then their posts
// Your code here

// Exercise 2: Handle multiple promises
const fetchUser = Promise.resolve({ name: "Alice", age: 30 });
const fetchSettings = Promise.resolve({ theme: "dark", notifications: true });

// Use Promise.all() and .then() to handle both promises
// Your code here
```

---

## Async/Await

### Async/Await Code Inspiration
```javascript
// Example 1: Basic async/await usage
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();

// Example 2: Multiple async operations
async function processUserData(userId) {
  const user = await getUser(userId);
  const posts = await getPosts(userId);
  return { user, posts };
}

processUserData(1).then(data => console.log(data));
```

### Async/Await Exercises
```javascript
// Exercise 1: Convert .then() chain to async/await
function getData() {
  return fetch('https://jsonplaceholder.typicode.com/users/1')
    .then(response => response.json())
    .then(user => {
      return fetch(`https://jsonplaceholder.typicode.com/posts?userId=${user.id}`)
    })
    .then(response => response.json())
    .then(posts => {
      console.log(posts);
    });
}

// Convert the above function to use async/await
async function getDataAsync() {
  // Your code here
}

// Exercise 2: Handle errors with async/await
async function loadResource(url) {
  // Your code here with try/catch
}

loadResource('https://invalid-url.com').catch(error => {
  console.log("Handled error:", error.message);
});
```

---

## Using .fetch()

### Using .fetch() Code Inspiration
```javascript
// Example 1: Basic fetch usage
fetch('https://jsonplaceholder.typicode.com/posts')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

// Example 2: POST request with fetch
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then(response => response.json())
  .then(data => console.log(data));
```

### Using .fetch() Exercises
```javascript
// Exercise 1: Create a function to fetch user data
function fetchUser(userId) {
  // Your code here to fetch user data from JSONPlaceholder API
}

fetchUser(1).then(user => console.log(user));

// Exercise 2: Implement error handling for fetch
function safeFetch(url) {
  // Your code here to fetch with proper error handling
}

safeFetch('https://jsonplaceholder.typicode.com/invalid-endpoint')
  .then(data => console.log(data))
  .catch(error => console.error('Caught error:', error));
```

---

## External Resources

1. [MDN Web Docs: Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)
2. [JavaScript.info: Promises, async/await](https://javascript.info/async)
3. [Google Developers: JavaScript Promises](https://developers.google.com/web/fundamentals/primers/promises)
