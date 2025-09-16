# Index

1. [Gathering Requirements](#gathering-requirements)
2. [Reacting](#reacting)
3. [Step-through-prep Workshop](#step-through-prep-workshop)
4. [Breaking Down the Problem](#breaking-down-the-problem)
5. [Identifying State](#identifying-state)
6. [Refactoring to State+Render](#refactoring-to-state+render)
7. [Introducing New State](#introducing-new-state)
8. [Rendering Based on State](#rendering-based-on-state)
9. [Capturing Events](#capturing-events)
10. [Re-rendering](#re-rendering)
11. [Actually Re-rendering](#actually-re-rendering)

---

## Gathering Requirements <a name="gathering-requirements"></a>

Before writing any code, we need to understand what we're building. This is called "gathering requirements."

**Pedagogical Approach**: Use worked examples (based on cognitive load theory) and connect to real-world scenarios (situated learning).

```javascript
// Example: Let's plan a simple counter app
// Requirements:
// 1. Display a number starting at 0
// 2. Have a button to increase the number
// 3. Have a button to decrease the number
// 4. The number should never go below 0
```

**Exercise**: Think of a simple app you use daily (like a calculator or todo list). Write down 3-5 requirements for it.

## Reacting <a name="reacting"></a>

Reacting means how our program responds to user interactions or other events.

**Pedagogical Approach**: Use analogies (conceptual blending) to relate programming concepts to everyday experiences.

```javascript
// Think of your program as a vending machine:
// 1. You press a button (event)
// 2. The machine processes your selection (handler function)
// 3. You get your snack (output)

// Basic structure of reaction in code:
element.addEventListener('eventType', function() {
  // What happens when the event occurs
});
```

## Step-through-prep Workshop <a name="step-through-prep-workshop"></a>

Let's practice tracing code execution line by line - this is called "stepping through" code.

**Pedagogical Approach**: Use scaffolding by starting with simple examples and gradually increasing complexity.

```javascript
// Let's step through this code together:
let count = 0;

function increment() {
  count = count + 1;
  console.log(count);
}

increment(); // What happens here?
increment(); // And here?
```

**Exercise**: Step through this code on paper. What is the final value of count?
```javascript
let count = 5;

function changeCount() {
  count = count - 2;
  count = count * 3;
}

changeCount();
console.log(count);
```

## Breaking Down the Problem <a name="breaking-down-the-problem"></a>

Large problems become manageable when broken into smaller pieces (decomposition).

**Pedagogical Approach**: Use pattern recognition and chunking to help students see common structures.

```javascript
// Instead of: "Build a calculator"
// Break it down:
// 1. Create number buttons (0-9)
// 2. Create operation buttons (+, -, *, /)
// 3. Create display area
// 4. Make buttons update display
// 5. Make = button calculate result
// 6. Add clear button

// Each of these can be implemented separately
```

## Identifying State <a name="identifying-state"></a>

State is the current "memory" of your application - all the values that can change.

**Pedagogical Approach**: Use contrasting cases to help students distinguish between what changes (state) and what doesn't.

```javascript
// For our counter app:
// State: the current count value

// For a login form:
// State: username, password, isLoggedIn

// For a todo app:
// State: list of todos, current input text

let appState = {
  count: 0,
  // other state properties would go here
};
```

## Refactoring to State+Render <a name="refactoring-to-state+render"></a>

Refactoring means improving code structure without changing its behavior.

**Pedagogical Approach**: Use comparative examples to show before/after improvements.

```javascript
// BEFORE: Mixed logic
let count = 0;
document.getElementById('count').textContent = count;

document.getElementById('increment').addEventListener('click', function() {
  count++;
  document.getElementById('count').textContent = count;
});

// AFTER: Separate state and render
let state = { count: 0 };

function render() {
  document.getElementById('count').textContent = state.count;
}

document.getElementById('increment').addEventListener('click', function() {
  state.count++;
  render(); // Update UI to match state
});
```

## Introducing New State <a name="introducing-new-state"></a>

As apps grow, we often need to add more state variables.

**Pedagogical Approach**: Use worked examples with gradual complexity increases.

```javascript
// Let's add a maximum limit to our counter
let state = {
  count: 0,
  maxCount: 10 // New state!
};

function render() {
  document.getElementById('count').textContent = state.count;
  // Disable button if max reached
  document.getElementById('increment').disabled = state.count >= state.maxCount;
}
```

## Rendering Based on State <a name="rendering-based-on-state"></a>

Our UI should always reflect the current state.

**Pedagogical Approach**: Use visualization to connect code to screen output.

```javascript
function render() {
  // Show current count
  document.getElementById('count').textContent = state.count;
  
  // Show/hide elements based on state
  if (state.count === 0) {
    document.getElementById('decrement').style.visibility = 'hidden';
  } else {
    document.getElementById('decrement').style.visibility = 'visible';
  }
  
  // Change color based on value
  if (state.count > 5) {
    document.getElementById('count').style.color = 'red';
  } else {
    document.getElementById('count').style.color = 'black';
  }
}
```

## Capturing Events <a name="capturing-events"></a>

Events are user interactions we want to respond to.

**Pedagogical Approach**: Use multiple representations (code + diagrams) to explain event flow.

```javascript
// Common events: click, input, change, submit, keydown, keyup

// Capture button click
document.getElementById('increment').addEventListener('click', function() {
  state.count++;
  render();
});

// Capture keyboard input
document.getElementById('text-input').addEventListener('input', function(event) {
  state.inputText = event.target.value;
  render();
});

// Capture form submission
document.getElementById('my-form').addEventListener('submit', function(event) {
  event.preventDefault(); // Stop page reload
  // Process form data
});
```

## Re-rendering <a name="re-rendering"></a>

Re-rendering means updating the UI to match the current state.

**Pedagogical Approach**: Use the concept of a "single source of truth" to explain why we re-render.

```javascript
// Our render function updates the UI to match state
function render() {
  // Update all elements that depend on state
  document.getElementById('count').textContent = state.count;
  document.getElementById('message').textContent = 
    state.count > 5 ? "That's a big number!" : "Keep counting!";
}

// We call render after ANY state change
function increment() {
  state.count++;
  render(); // UI updates to match new state
}

function reset() {
  state.count = 0;
  render(); // UI updates to match new state
}
```

## Actually Re-rendering <a name="actually-re-rendering"></a>

In real applications, we need efficient re-rendering strategies.

**Pedagogical Approach**: Explain the virtual DOM concept at a high level before diving into libraries.

```javascript
// Simple re-rendering approach (for learning):
function render() {
  // This replaces the entire content of a container
  document.getElementById('app').innerHTML = `
    <div>
      <h1>Count: ${state.count}</h1>
      <button onclick="increment()">+</button>
      <button onclick="decrement()">-</button>
    </div>
  `;
}

// More advanced approach (what frameworks do):
// 1. They create a virtual representation of UI
// 2. When state changes, they create a new virtual UI
// 3. They compare new virtual UI with previous one
// 4. They update only the parts that changed

// Simple implementation concept:
let previousHTML = '';

function efficientRender() {
  const currentHTML = `
    <div>
      <h1>Count: ${state.count}</h1>
      <button onclick="increment()">+</button>
    </div>
  `;
  
  if (currentHTML !== previousHTML) {
    document.getElementById('app').innerHTML = currentHTML;
    previousHTML = currentHTML;
  }
}
```

## Summary

We've covered the fundamental concepts of building interactive JavaScript applications using scientifically-proven teaching methods:

1. **Worked examples** with gradual complexity increases
2. **Decomposition** of large problems into manageable parts
3. **Visualizations** and analogies to connect concepts
4. **Pattern recognition** to identify common structures
5. **Scaffolding** to build knowledge step by step

Remember that learning programming is a process. Practice each concept, build small projects, and don't hesitate to revisit topics as needed.

**Next Steps**: Try building a small application using these concepts, like a todo list, calculator, or simple game.



