# JavaScript Practice Lesson: State and Rendering

## Topics to Practice

* [1. Gathering Requirements](#1-gathering-requirements)
  * [Code Inspiration](#1-code-inspiration)
  * [Exercises](#1-exercises)
* [2. Identifying State](#2-identifying-state)
  * [Code Inspiration](#2-code-inspiration)
  * [Exercises](#2-exercises)
* [3. Refactoring to State+Render](#3-refactoring-to-staterender)
  * [Code Inspiration](#3-code-inspiration)
  * [Exercises](#3-exercises)
* [4. Introducing New State](#4-introducing-new-state)
  * [Code Inspiration](#4-code-inspiration)
  * [Exercises](#4-exercises)
* [5. Rendering Based on State](#5-rendering-based-on-state)
  * [Code Inspiration](#5-code-inspiration)
  * [Exercises](#5-exercises)
* [6. Capturing Events](#6-capturing-events)
  * [Code Inspiration](#6-code-inspiration)
  * [Exercises](#6-exercises)
* [7. Re-rendering](#7-re-rendering)
  * [Code Inspiration](#7-code-inspiration)
  * [Exercises](#7-exercises)
* [8. Actually Re-rendering](#8-actually-re-rendering)
  * [Code Inspiration](#8-code-inspiration)
  * [Exercises](#8-exercises)

---

## 1. Gathering Requirements
<a name="1-gathering-requirements"></a>

### Code Inspiration
<a name="1-code-inspiration"></a>

```javascript
// Example 1: Simple counter app requirements
// - We need to track a count number
// - We need buttons to increase and decrease the count
// - We need to display the current count

// Example 2: Todo list requirements
// - We need to track a list of tasks
// - We need to add new tasks
// - We need to mark tasks as complete
// - We need to display all tasks
```

### Exercises
<a name="1-exercises"></a>

```javascript
// Exercise 1: For a weather app, list the requirements
// Your code here...

// Exercise 2: For a shopping cart, list the requirements
// Your code here...
```

## 2. Identifying State
<a name="2-identifying-state"></a>

### Code Inspiration
<a name="2-code-inspiration"></a>

```javascript
// Example 1: Counter app state
const state = {
  count: 0 // The changing value we need to track
};

// Example 2: Todo app state
const state = {
  todos: [], // List of todo items
  newTodoText: '' // Current text for new todo input
};
```

### Exercises
<a name="2-exercises"></a>

```javascript
// Exercise 1: Identify state for a login form
// Your code here...

// Exercise 2: Identify state for a photo gallery
// Your code here...
```

## 3. Refactoring to State+Render
<a name="3-refactoring-to-staterender"></a>

### Code Inspiration
<a name="3-code-inspiration"></a>

```javascript
// Example 1: Before refactoring
let count = 0;

function handleIncrement() {
  count++;
  document.getElementById('count').textContent = count;
}

// After refactoring
const state = { count: 0 };

function render() {
  document.getElementById('count').textContent = state.count;
}

function handleIncrement() {
  state.count++;
  render();
}
```

### Exercises
<a name="3-exercises"></a>

```javascript
// Exercise 1: Refactor this code to use state+render pattern
let temperature = 72;

function increaseTemp() {
  temperature++;
  document.getElementById('temp').textContent = temperature + '°F';
}

// Your refactored code here...

// Exercise 2: Refactor this code to use state+render pattern
let isLoggedIn = false;

function toggleLogin() {
  isLoggedIn = !isLoggedIn;
  document.getElementById('status').textContent = 
    isLoggedIn ? 'Logged In' : 'Logged Out';
}

// Your refactored code here...
```

## 4. Introducing New State
<a name="4-introducing-new-state"></a>

### Code Inspiration
<a name="4-code-inspiration"></a>

```javascript
// Example 1: Adding error state to counter
const state = {
  count: 0,
  error: null // New state for error messages
};

// Example 2: Adding filter state to todo app
const state = {
  todos: [],
  newTodoText: '',
  filter: 'all' // New state for filtering (all, active, completed)
};
```

### Exercises
<a name="4-exercises"></a>

```javascript
// Exercise 1: Add loading state to a weather app
const state = {
  temperature: 0,
  condition: 'sunny'
  // Add loading state here
};

// Your code here...

// Exercise 2: Add theme state to an app (light/dark mode)
const state = {
  // Add theme state here
};

// Your code here...
```

## 5. Rendering Based on State
<a name="5-rendering-based-on-state"></a>

### Code Inspiration
<a name="5-code-inspiration"></a>

```javascript
// Example 1: Conditional rendering based on error state
function render() {
  document.getElementById('count').textContent = state.count;
  
  if (state.error) {
    document.getElementById('error').textContent = state.error;
    document.getElementById('error').style.display = 'block';
  } else {
    document.getElementById('error').style.display = 'none';
  }
}

// Example 2: Rendering different todo filters
function render() {
  const filteredTodos = state.todos.filter(todo => {
    if (state.filter === 'active') return !todo.completed;
    if (state.filter === 'completed') return todo.completed;
    return true; // 'all' filter
  });
  
  // Render filteredTodos
}
```

### Exercises
<a name="5-exercises"></a>

```javascript
// Exercise 1: Render different messages based on temperature state
function render() {
  // Your code here...
  // If temperature > 80, show "Hot" message
  // If temperature < 50, show "Cold" message
  // Otherwise show "Moderate" message
}

// Exercise 2: Render different UI based on login state
function render() {
  // Your code here...
  // If user is logged in, show welcome message and logout button
  // If user is logged out, show login form
}
```

## 6. Capturing Events
<a name="6-capturing-events"></a>

### Code Inspiration
<a name="6-code-inspiration"></a>

```javascript
// Example 1: Button click event
document.getElementById('increment-btn').addEventListener('click', () => {
  state.count++;
  render();
});

// Example 2: Form submission event
document.getElementById('todo-form').addEventListener('submit', (event) => {
  event.preventDefault(); // Prevent page reload
  state.todos.push({ text: state.newTodoText, completed: false });
  state.newTodoText = '';
  render();
});
```

### Exercises
<a name="6-exercises"></a>

```javascript
// Exercise 1: Capture input change event for a search box
document.getElementById('search-input').addEventListener('input', (event) => {
  // Your code here...
  // Update state with search term and re-render
});

// Exercise 2: Capture checkbox change event for a todo item
document.getElementById('todo-checkbox').addEventListener('change', (event) => {
  // Your code here...
  // Update todo completion status in state and re-render
});
```

## 7. Re-rendering
<a name="7-re-rendering"></a>

### Code Inspiration
<a name="7-code-inspiration"></a>

```javascript
// Example 1: Simple re-render function
function render() {
  document.getElementById('count').textContent = state.count;
  
  // Re-render error message conditionally
  const errorElement = document.getElementById('error');
  errorElement.textContent = state.error || '';
  errorElement.style.display = state.error ? 'block' : 'none';
}

// Example 2: Re-render todo list
function render() {
  const todoList = document.getElementById('todo-list');
  todoList.innerHTML = ''; // Clear existing content
  
  state.todos.forEach(todo => {
    const li = document.createElement('li');
    li.textContent = todo.text;
    if (todo.completed) {
      li.style.textDecoration = 'line-through';
    }
    todoList.appendChild(li);
  });
}
```

### Exercises
<a name="7-exercises"></a>

```javascript
// Exercise 1: Create a re-render function for a shopping cart
function render() {
  // Your code here...
  // Display each item in the cart
  // Calculate and display total price
}

// Exercise 2: Create a re-render function for a theme switcher
function render() {
  // Your code here...
  // Apply the current theme (light/dark) to the page
  // Update theme toggle button text
}
```

## 8. Actually Re-rendering
<a name="8-actually-re-rendering"></a>

### Code Inspiration
<a name="8-code-inspiration"></a>

```javascript
// Example 1: Complete counter app with re-rendering
const state = { count: 0, error: null };

function render() {
  document.getElementById('count').textContent = state.count;
  
  const errorElement = document.getElementById('error');
  errorElement.textContent = state.error || '';
  errorElement.style.display = state.error ? 'block' : 'none';
}

document.getElementById('increment-btn').addEventListener('click', () => {
  state.count++;
  state.error = null;
  render();
});

document.getElementById('decrement-btn').addEventListener('click', () => {
  if (state.count > 0) {
    state.count--;
    state.error = null;
  } else {
    state.error = "Count cannot be negative";
  }
  render();
});

// Initial render
render();
```

### Exercises
<a name="8-exercises"></a>

```javascript
// Exercise 1: Complete the temperature converter app
const state = {
  celsius: 0,
  fahrenheit: 32
};

function convertToFahrenheit(celsius) {
  return (celsius * 9/5) + 32;
}

function convertToCelsius(fahrenheit) {
  return (fahrenheit - 32) * 5/9;
}

function render() {
  // Your code here...
  // Display both temperature values
}

// Add event listeners and complete the implementation
// Your code here...

// Exercise 2: Complete the todo app with add and toggle functionality
const state = {
  todos: [],
  newTodoText: ''
};

function render() {
  // Your code here...
  // Render the todo list
}

// Add event listeners and complete the implementation
// Your code here...
```

## Additional Resources

1. [MDN Web Docs: State](https://developer.mozilla.org/en-US/docs/Glossary/State) - Mozilla's documentation on application state
2. [JavaScript.info: Document and Website Structure](https://javascript.info/document) - Great resource on DOM manipulation
3. [FreeCodeCamp: JavaScript DOM Manipulation](https://www.freecodecamp.org/news/javascript-dom-manipulation/) - Tutorial on working with the DOM
