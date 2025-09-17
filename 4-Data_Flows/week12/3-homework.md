# JavaScript Async Operations Homework

### Exercise 1: Simulating Latency with Callbacks
**Learning Goals:** Synchronous Execution, Latency, Callbacks

**Task:**
1.  Create a function called `waitForMessage` that takes two arguments:
    *   `message` (a string)
    *   `callback` (a function)
2.  Inside `waitForMessage`, use `setTimeout` to simulate a network latency of **2 seconds**.
3.  After the 2-second delay, the `setTimeout` should invoke the `callback` function and pass the `message` to it as an argument.
4.  **Write the execution order:** Call your `waitForMessage` function with a message of your choice and a callback function that simply `console.log`s the received message.
5.  **Crucial Part:** Add a `console.log('This is synchronous')` statement *immediately after* you call `waitForMessage`.

**What to Observe:**
*   Run your code. Notice the order of the console logs. This demonstrates that the `waitForMessage` function is **non-blocking**; the synchronous code continues to execute without waiting for the timeout to complete.

```javascript
// Your code for Exercise 1 here
function waitForMessage(message, callback) {
  // Use setTimeout to simulate 2-second latency
}

// Call the function and observe the output order
waitForMessage("Hello, Callback!", function(receivedMessage) {
  console.log(receivedMessage);
});
console.log("This is synchronous");
```

---

### Exercise 2: From Callbacks to Promises and .then()
**Learning Goals:** Promises, Using .then(), Error Handling

**Task:**
1.  **Refactor** the `waitForMessage` function from Exercise 1. Create a new function called `waitForMessagePromise`.
2.  This function should take only one argument, `message`, and return a **new Promise**.
3.  Inside the Promise executor function, use the same `setTimeout` to simulate a 2-second latency.
4.  After 2 seconds, the Promise should **resolve** with the `message`.
5.  **Call the function:** Use the `.then()` method on the returned Promise to `console.log` the resolved message. Add a `.catch()` block to handle any potential errors (even though this simple example likely won't have any).
6.  Keep the `console.log('This is synchronous')` statement after your function call.

**What to Observe:**
*   The output order should be the same as Exercise 1, but the implementation is now using the more manageable Promise pattern instead of a nested callback.

```javascript
// Your code for Exercise 2 here
function waitForMessagePromise(message) {
  return new Promise((resolve, reject) => {
    // Simulate latency and resolve the promise with the message
  });
}

// Call the function and handle the Promise with .then()
waitForMessagePromise("Hello, Promise!")
  .then((receivedMessage) => {
    console.log(receivedMessage);
  })
  .catch((error) => {
    console.error("Something went wrong:", error);
  });
console.log("This is synchronous");
```

---

### Exercise 3: Real API Call with Async/Await and fetch()
**Learning Goals:** Async/Await, Using .fetch()

**Task:**
1.  Use the `fetch()` API to make a GET request to the free JSONPlaceholder API: `https://jsonplaceholder.typicode.com/posts/1`
2.  Create an **async function** named `getPost`.
3.  Inside this function, use `await` to wait for the `fetch()` call to complete and get the response.
4.  Use `await` again on the `response.json()` method to parse the JSON data from the response.
5.  `console.log` the parsed data. It should be an object representing a blog post.
6.  **Call your async function** `getPost`.
7.  Add a `console.log('This happens after calling getPost')` statement *immediately after* you call `getPost()`.

**What to Observe:**
*   The string `'This happens after calling getPost'` will appear *before* the blog post data. This is because `getPost` is an async function and runs in the background, allowing the synchronous code to continue immediately.
*   Open your browser's DevTools "Network" tab to see the actual HTTP request and the latency involved.

```javascript
// Your code for Exercise 3 here
async function getPost() {
  try {
    // 1. Use fetch() with await to get a response
    // 2. Use .json() with await to parse the response
    // 3. Console.log the final data
  } catch (error) {
    console.error("Failed to fetch post:", error);
  }
}

// Call the async function
getPost();
console.log('This happens after calling getPost');
```

## How to Submit
1.  Create a single JavaScript file (e.g., `async-homework.js`) and complete all three exercises within it.
2.  Comment your code clearly.
3.  Run your code to ensure it works and the output is as expected.
4.  Submit your `.js` file through the designated platform (e.g., GitHub, learning management system).

# Additional exercises

Of course. Here are two additional beginner-level exercises that build on the core concepts, presented without sub-goals or starter code.

---

### Exercise 4: User Profile Fetcher

Create an async function called `getUserProfile`. This function should fetch user data from the API endpoint `https://jsonplaceholder.typicode.com/users/1`. Once the data is retrieved, your function should extract and return only the user's `name`, `email`, and `city` from the `address` object. Be sure to handle any potential errors. Finally, call your function and use `.then()` and `.catch()` to log the extracted information or the error message.

---

### Exercise 5: Sequential Message Logger

Write a function called `logMessagesSequentially`. It should use `async/await` to perform the following actions in order, with a 1-second delay between each log:
1.  Immediately log "Start".
2.  Wait 1 second, then log "First message".
3.  Wait 1 second, then log "Second message".
4.  Wait 1 second, then log "End".

The entire sequence should take 3 seconds to complete, and the messages must appear in the exact order specified.
