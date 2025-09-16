# Index

- [Introduction](#introduction)
- [Synchronous Execution](#synchronous-execution)
- [Latency](#latency)
- [Callbacks](#callbacks)
- [Promises](#promises)
- [Using .then()](#using-then)
- [Async/Await](#asyncawait)
- [Using .fetch()](#using-fetch)
- [Fetch Films Workshop](#fetch-films-workshop)
- [Step-through-prep Workshop](#step-through-prep-workshop)

## Introduction

Welcome to JavaScript Asynchronous Programming! This module will guide you through one of JavaScript's most powerful features: handling operations that take time to complete, like fetching data from the internet.

## Synchronous Execution

JavaScript normally executes code **synchronously** - line by line, in order.

```javascript
console.log("Step 1");
console.log("Step 2");
console.log("Step 3");
// Output: Step 1, Step 2, Step 3 (in order, with no delay)
```

Synchronous code is predictable but can be problematic when operations take time to complete.

## Latency

**Latency** is the delay between initiating a request and receiving a response. In web development, we frequently encounter latency when:

- Requesting data from a server
- Loading images or other media
- Querying a database

```javascript
console.log("Requesting data...");
// This would normally cause a delay if synchronous:
const data = getDataFromServer(); // Imagine this takes 2 seconds
console.log("Data received:", data);
// Problem: The entire program freezes during those 2 seconds!
```

## Callbacks

**Callbacks** are functions passed as arguments to other functions, to be executed later once an operation completes.

```javascript
// Simple callback example
function doHomework(subject, callback) {
  console.log(`Starting my ${subject} homework.`);
  setTimeout(() => {
    console.log(`Finished my ${subject} homework.`);
    callback(); // Execute the callback function
  }, 2000); // Simulate 2 seconds of work
}

function alertFinished() {
  console.log("I'm done with all homework!");
}

doHomework('math', alertFinished);
```

**Callback Hell** (Pyramid of Doom) - A common problem with nested callbacks:

```javascript
getData(function(a) {
  getMoreData(a, function(b) {
    getEvenMoreData(b, function(c) {
      getFinalData(c, function(finalData) {
        console.log(finalData);
      });
    });
  });
});
```

## Promises

**Promises** are objects that represent the eventual completion (or failure) of an asynchronous operation.

A Promise can be in one of three states:
- **Pending**: Initial state, neither fulfilled nor rejected
- **Fulfilled**: Operation completed successfully
- **Rejected**: Operation failed

```javascript
// Creating a promise
const myPromise = new Promise((resolve, reject) => {
  // Asynchronous operation here
  const success = true; // Simulate success or failure
  
  if (success) {
    resolve("Data successfully retrieved!");
  } else {
    reject("Failed to retrieve data.");
  }
});
```

## Using .then()

The `.then()` method is used with promises to handle fulfilled states.

```javascript
// Using a promise with .then()
myPromise
  .then((result) => {
    console.log(result); // "Data successfully retrieved!"
  })
  .catch((error) => {
    console.error(error); // Handle errors
  });
```

Chaining multiple promises:

```javascript
fetchData()
  .then(processData)
  .then(saveData)
  .then((result) => {
    console.log("All operations completed:", result);
  })
  .catch((error) => {
    console.error("Something went wrong:", error);
  });
```

## Async/Await

**Async/Await** is a modern syntax for working with promises that makes asynchronous code look more like synchronous code.

```javascript
// The async keyword allows us to use await inside a function
async function getData() {
  try {
    const result = await myPromise; // Pause until the promise settles
    console.log(result); // "Data successfully retrieved!"
  } catch (error) {
    console.error(error); // Handle errors
  }
}

getData();
```

Multiple async operations with await:

```javascript
async function processUserData(userId) {
  try {
    const user = await fetchUser(userId);
    const posts = await fetchUserPosts(user.id);
    const comments = await fetchPostComments(posts[0].id);
    
    return { user, posts, comments };
  } catch (error) {
    console.error("Failed to process user data:", error);
  }
}
```

## Using .fetch()

The `fetch()` API is a modern way to make HTTP requests in JavaScript.

```javascript
// Basic fetch usage
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json(); // Parse JSON data
  })
  .then(data => {
    console.log(data); // Work with the JSON data
  })
  .catch(error => {
    console.error('There was a problem:', error);
  });
```

Using fetch with async/await:

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    
    const data = await response.json();
    console.log(data);
    return data;
  } catch (error) {
    console.error('Fetch error:', error);
  }
}
```

## Fetch Films Workshop

Let's build a practical application that fetches movie data from an API.

```javascript
// HTML needed:
// <button id="fetchFilms">Get Films</button>
// <div id="filmsContainer"></div>

document.getElementById('fetchFilms').addEventListener('click', fetchFilms);

async function fetchFilms() {
  try {
    const response = await fetch('https://swapi.dev/api/films/');
    
    if (!response.ok) {
      throw new Error('Failed to fetch films');
    }
    
    const data = await response.json();
    displayFilms(data.results);
  } catch (error) {
    console.error('Error fetching films:', error);
    document.getElementById('filmsContainer').innerHTML = 
      '<p>Failed to load films. Please try again later.</p>';
  }
}

function displayFilms(films) {
  const container = document.getElementById('filmsContainer');
  container.innerHTML = ''; // Clear previous results
  
  films.forEach(film => {
    const filmElement = document.createElement('div');
    filmElement.className = 'film';
    filmElement.innerHTML = `
      <h3>${film.title}</h3>
      <p>Director: ${film.director}</p>
      <p>Release Date: ${film.release_date}</p>
      <p>${film.opening_crawl.substring(0, 100)}...</p>
    `;
    container.appendChild(filmElement);
  });
}
```

## Step-through-prep Workshop

In this workshop, we'll practice debugging and understanding asynchronous code by stepping through execution.

**Exercise 1: Predict the Output**

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Timeout callback');
}, 0);

Promise.resolve().then(() => {
  console.log('Promise resolved');
});

console.log('End');
```

**What will be the output order?**
<details>
<summary>Click to reveal answer</summary>
Start, End, Promise resolved, Timeout callback
</details>

**Exercise 2: Fix the Code**

```javascript
// This code has a bug - can you find it?
function getUserData(userId) {
  let user;
  
  fetch(`https://api.example.com/users/${userId}`)
    .then(response => response.json())
    .then(data => {
      user = data;
    });
    
  return user;
}

console.log(getUserData(123)); // Outputs: undefined
```

**Solution:**
```javascript
// Fixed version using async/await
async function getUserData(userId) {
  try {
    const response = await fetch(`https://api.example.com/users/${userId}`);
    const user = await response.json();
    return user;
  } catch (error) {
    console.error('Error fetching user:', error);
    return null;
  }
}

// Or using promises properly
function getUserData(userId) {
  return fetch(`https://api.example.com/users/${userId}`)
    .then(response => response.json())
    .catch(error => {
      console.error('Error fetching user:', error);
      return null;
    });
}

// Usage:
getUserData(123).then(user => console.log(user));
```

**Exercise 3: Sequential vs Parallel Requests**

```javascript
// Sequential requests (one after another)
async function getSequentialData() {
  const startTime = Date.now();
  
  const user = await fetch('/api/user');
  const posts = await fetch('/api/posts');
  const comments = await fetch('/api/comments');
  
  console.log(`Sequential took: ${Date.now() - startTime}ms`);
  return { user, posts, comments };
}

// Parallel requests (all at once)
async function getParallelData() {
  const startTime = Date.now();
  
  const [user, posts, comments] = await Promise.all([
    fetch('/api/user'),
    fetch('/api/posts'),
    fetch('/api/comments')
  ]);
  
  console.log(`Parallel took: ${Date.now() - startTime}ms`);
  return { user, posts, comments };
}
```

**Challenge Question:**
When would you use sequential requests instead of parallel requests?

<details>
<summary>Click to reveal answer</summary>
Use sequential requests when one request depends on data from a previous request. For example, you might need to get a user ID first before fetching that user's posts.
</details>

## Additional Resources

1. [MDN Web Docs: Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)
2. [JavaScript.info: Promises, async/await](https://javascript.info/async)
3. [Google Developers: Promises](https://developers.google.com/web/fundamentals/primers/promises)

## Practice Exercises

1. Create a weather app that fetches data from a weather API
2. Build a image gallery that loads images asynchronously
3. Implement error handling for failed API requests with retry logic
4. Create a function that makes multiple API calls and returns only when all are complete

Remember to practice regularly and experiment with different approaches to solidify your understanding of asynchronous JavaScript!



