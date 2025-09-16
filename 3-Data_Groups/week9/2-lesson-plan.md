* [Implementing a Character Limit](#implementing-a-character-limit)
  * [Code Inspiration](#code-inspiration-implementing-a-character-limit)
  * [Exercises](#exercises-implementing-a-character-limit)
* [The DOM](#the-dom)
  * [Code Inspiration](#code-inspiration-the-dom)
  * [Exercises](#exercises-the-dom)
* [Querying the DOM](#querying-the-dom)
  * [Code Inspiration](#code-inspiration-querying-the-dom)
  * [Exercises](#exercises-querying-the-dom)
* [Calculating the Remaining Characters](#calculating-the-remaining-characters)
  * [Code Inspiration](#code-inspiration-calculating-the-remaining-characters)
  * [Exercises](#exercises-calculating-the-remaining-characters)
* [Timers](#timers)
  * [Code Inspiration](#code-inspiration-timers)
  * [Exercises](#exercises-timers)
* [DOM Events](#dom-events)
  * [Code Inspiration](#code-inspiration-dom-events)
  * [Exercises](#exercises-dom-events)
* [Reacting to Events](#reacting-to-events)
  * [Code Inspiration](#code-inspiration-reacting-to-events)
  * [Exercises](#exercises-reacting-to-events)
* [Refactor](#refactor)
  * [Code Inspiration](#code-inspiration-refactor)
  * [Exercises](#exercises-refactor)

---

## Implementing a Character Limit

### Code Inspiration: Implementing a Character Limit
```javascript
// Example 1: Basic character limit implementation
function enforceCharacterLimit(text, maxLength) {
  if (text.length > maxLength) {
    return text.substring(0, maxLength);
  }
  return text;
}

// Example 2: Character limit with visual feedback
function updateCharacterCounter(inputElement, counterElement, maxLength) {
  const currentLength = inputElement.value.length;
  counterElement.textContent = `${currentLength}/${maxLength}`;
  
  if (currentLength > maxLength) {
    counterElement.style.color = 'red';
  } else {
    counterElement.style.color = 'black';
  }
}
```

### Exercises: Implementing a Character Limit
```javascript
// Exercise 1: Implement a function that truncates text if it exceeds the limit
function truncateText(text, maxLength) {
  // Your code here
}

// Exercise 2: Create a function that validates if text is within the limit
function isWithinLimit(text, maxLength) {
  // Your code here
}
```

---

## The DOM

### Code Inspiration: The DOM
```javascript
// Example 1: Understanding the DOM structure
console.log(document.documentElement); // The root element
console.log(document.head); // The head element
console.log(document.body); // The body element

// Example 2: Creating and adding elements to the DOM
const newParagraph = document.createElement('p');
newParagraph.textContent = 'This is a new paragraph';
document.body.appendChild(newParagraph);
```

### Exercises: The DOM
```javascript
// Exercise 1: Create a new div element with the class "container"
function createContainer() {
  // Your code here
}

// Exercise 2: Add a new list item to an existing unordered list
function addListItem(listId, itemText) {
  // Your code here
}
```

---

## Querying the DOM

### Code Inspiration: Querying the DOM
```javascript
// Example 1: Selecting elements by ID
const headerElement = document.getElementById('header');

// Example 2: Selecting elements by class name
const buttons = document.getElementsByClassName('btn');

// Example 3: Using querySelector for more specific selections
const firstButton = document.querySelector('.btn-primary');
const allButtons = document.querySelectorAll('.btn');
```

### Exercises: Querying the DOM
```javascript
// Exercise 1: Select all elements with the class "highlight"
function getHighlightedElements() {
  // Your code here
}

// Exercise 2: Select the first element with the attribute data-type="special"
function getSpecialElement() {
  // Your code here
}
```

---

## Calculating the Remaining Characters

### Code Inspiration: Calculating the Remaining Characters
```javascript
// Example 1: Simple remaining characters calculation
function getRemainingChars(text, maxLength) {
  return maxLength - text.length;
}

// Example 2: Calculating with different character weights (emoji-safe)
function getRemainingCharsUnicode(text, maxLength) {
  // Using Array.from to handle emojis and special characters correctly
  return maxLength - Array.from(text).length;
}
```

### Exercises: Calculating the Remaining Characters
```javascript
// Exercise 1: Calculate remaining characters with a minimum threshold
function getRemainingWithThreshold(text, maxLength, threshold) {
  // Your code here
}

// Exercise 2: Create a function that returns a warning when characters are running low
function getCharacterWarning(text, maxLength, warningAt) {
  // Your code here
}
```

---

## Timers

### Code Inspiration: Timers
```javascript
// Example 1: Using setTimeout for delayed execution
setTimeout(() => {
  console.log('This message appears after 2 seconds');
}, 2000);

// Example 2: Using setInterval for repeated execution
let counter = 0;
const intervalId = setInterval(() => {
  counter++;
  console.log(`Counter: ${counter}`);
  if (counter >= 5) {
    clearInterval(intervalId);
  }
}, 1000);
```

### Exercises: Timers
```javascript
// Exercise 1: Create a countdown timer that logs numbers from 10 to 0
function startCountdown() {
  // Your code here
}

// Exercise 2: Implement a function that executes a callback after a delay
function executeAfterDelay(callback, delay) {
  // Your code here
}
```

---

## DOM Events

### Code Inspiration: DOM Events
```javascript
// Example 1: Adding a click event listener
const button = document.getElementById('myButton');
button.addEventListener('click', function(event) {
  console.log('Button clicked!', event);
});

// Example 2: Handling form submission
const form = document.getElementById('myForm');
form.addEventListener('submit', function(event) {
  event.preventDefault(); // Prevent form from submitting
  console.log('Form submitted!');
});
```

### Exercises: DOM Events
```javascript
// Exercise 1: Add a double-click event listener to an element
function addDoubleClickListener(elementId, callback) {
  // Your code here
}

// Exercise 2: Create a function that prevents the default action of a right-click
function preventRightClick(elementId) {
  // Your code here
}
```

---

## Reacting to Events

### Code Inspiration: Reacting to Events
```javascript
// Example 1: Reacting to keyboard events
const input = document.getElementById('myInput');
input.addEventListener('keyup', function(event) {
  console.log(`Key pressed: ${event.key}`);
});

// Example 2: Reacting to mouse movement
document.addEventListener('mousemove', function(event) {
  console.log(`Mouse position: X=${event.clientX}, Y=${event.clientY}`);
});
```

### Exercises: Reacting to Events
```javascript
// Exercise 1: Create a function that changes background color on mouseover
function addHoverEffect(elementId, color) {
  // Your code here
}

// Exercise 2: Implement a key logger that ignores certain keys
function createKeyLogger(inputId, ignoredKeys = []) {
  // Your code here
}
```

---

## Refactor

### Code Inspiration: Refactor
```javascript
// Before refactoring: Repetitive code
function updateCharacterCount() {
  const text = document.getElementById('textInput').value;
  const count = text.length;
  document.getElementById('charCount').textContent = count;
  
  if (count > 100) {
    document.getElementById('charCount').style.color = 'red';
  } else {
    document.getElementById('charCount').style.color = 'black';
  }
}

// After refactoring: More modular and reusable
function updateCharacterCountRefactored(inputId, counterId, maxLength) {
  const text = document.getElementById(inputId).value;
  const count = text.length;
  const counterElement = document.getElementById(counterId);
  
  counterElement.textContent = count;
  counterElement.style.color = count > maxLength ? 'red' : 'black';
}
```

### Exercises: Refactor
```javascript
// Exercise 1: Refactor this repetitive code
function setupInputListeners() {
  document.getElementById('input1').addEventListener('input', function() {
    document.getElementById('counter1').textContent = this.value.length;
  });
  
  document.getElementById('input2').addEventListener('input', function() {
    document.getElementById('counter2').textContent = this.value.length;
  });
  
  document.getElementById('input3').addEventListener('input', function() {
    document.getElementById('counter3').textContent = this.value.length;
  });
}

// Exercise 2: Refactor this function to be more readable and maintainable
function processUserData(users) {
  let result = [];
  for (let i = 0; i < users.length; i++) {
    if (users[i].age >= 18 && users[i].isActive) {
      result.push({
        name: users[i].name.toUpperCase(),
        age: users[i].age,
        id: users[i].id * 2
      });
    }
  }
  return result;
}
```

---

## External Resources

1. [MDN Web Docs: JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Comprehensive JavaScript documentation
2. [JavaScript.info: Document](https://javascript.info/document) - Detailed guide on working with the DOM
3. [W3Schools: JavaScript Events](https://www.w3schools.com/js/js_events.asp) - Tutorial on JavaScript events with examples