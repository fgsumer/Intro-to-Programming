# JavaScript Practice Lesson: DOM Manipulation and Components

## Topics to Practice

* [Rendering Data as UI](#rendering-data-as-ui)
  * [Code Inspiration](#rendering-data-code-inspiration)
  * [Exercises](#rendering-data-exercises)
* [Composing Elements](#composing-elements)
  * [Code Inspiration](#composing-elements-code-inspiration)
  * [Exercises](#composing-elements-exercises)
* [Creating Elements with Functions](#creating-elements-with-functions)
  * [Code Inspiration](#functions-code-inspiration)
  * [Exercises](#functions-exercises)
* [Creating Elements with `<template>`](#creating-elements-with-template)
  * [Code Inspiration](#template-code-inspiration)
  * [Exercises](#template-exercises)
* [Reusable Components](#reusable-components)
  * [Code Inspiration](#components-code-inspiration)
  * [Exercises](#components-exercises)
* [One-to-One Mappings](#one-to-one-mappings)
  * [Code Inspiration](#mappings-code-inspiration)
  * [Exercises](#mappings-exercises)
* [Using `map`](#using-map)
  * [Code Inspiration](#using-map-code-inspiration)
  * [Exercises](#using-map-exercises)
* [Applying `map`](#applying-map)
  * [Code Inspiration](#applying-map-code-inspiration)
  * [Exercises](#applying-map-exercises)

---

## Rendering Data as UI

### <a id="rendering-data-code-inspiration"></a>Code Inspiration

**Example 1: Displaying User Information**
```javascript
const user = {
  name: "Alice",
  age: 28,
  occupation: "Developer"
};

function renderUserInfo(userData) {
  const userInfoElement = document.getElementById('user-info');
  userInfoElement.innerHTML = `
    <h2>${userData.name}</h2>
    <p>Age: ${userData.age}</p>
    <p>Occupation: ${userData.occupation}</p>
  `;
}

renderUserInfo(user);
```

**Example 2: Displaying Product Details**
```javascript
const product = {
  title: "JavaScript Book",
  price: 29.99,
  inStock: true
};

function renderProduct(productData) {
  const productElement = document.createElement('div');
  productElement.className = 'product';
  productElement.innerHTML = `
    <h3>${productData.title}</h3>
    <p>Price: $${productData.price}</p>
    <p>Status: ${productData.inStock ? 'In Stock' : 'Out of Stock'}</p>
  `;
  document.body.appendChild(productElement);
}

renderProduct(product);
```

### <a id="rendering-data-exercises"></a>Exercises

**Exercise 1: Display Movie Information**
```javascript
const movie = {
  title: "Inception",
  director: "Christopher Nolan",
  year: 2010,
  rating: 8.8
};

// TODO: Complete this function to display the movie information
function displayMovie(movieData) {
  const movieElement = document.getElementById('movie-container');
  // Your code here
}

displayMovie(movie);
```

**Exercise 2: Create a Weather Widget**
```javascript
const weatherData = {
  city: "New York",
  temperature: 72,
  condition: "Sunny",
  humidity: 45
};

// TODO: Create a function to display weather information
function createWeatherWidget(weather) {
  // Your code here
}

createWeatherWidget(weatherData);
```

---

## Composing Elements

### <a id="composing-elements-code-inspiration"></a>Code Inspiration

**Example 1: Building a Card Component**
```javascript
function createCard(title, content) {
  const card = document.createElement('div');
  card.className = 'card';
  
  const cardTitle = document.createElement('h3');
  cardTitle.textContent = title;
  
  const cardContent = document.createElement('p');
  cardContent.textContent = content;
  
  card.appendChild(cardTitle);
  card.appendChild(cardContent);
  
  return card;
}

// Usage
const card = createCard("Welcome", "This is a sample card component");
document.body.appendChild(card);
```

**Example 2: Creating a Navigation Bar**
```javascript
function createNavBar(items) {
  const nav = document.createElement('nav');
  const ul = document.createElement('ul');
  
  items.forEach(item => {
    const li = document.createElement('li');
    const a = document.createElement('a');
    a.href = item.link;
    a.textContent = item.text;
    li.appendChild(a);
    ul.appendChild(li);
  });
  
  nav.appendChild(ul);
  return nav;
}

// Usage
const navItems = [
  { text: "Home", link: "#home" },
  { text: "About", link: "#about" },
  { text: "Contact", link: "#contact" }
];

const navbar = createNavBar(navItems);
document.body.prepend(navbar);
```

### <a id="composing-elements-exercises"></a>Exercises

**Exercise 1: Build a Profile Component**
```javascript
// TODO: Create a function that builds a user profile component
function createProfile(user) {
  // Your code here
}

const user = {
  name: "John Doe",
  bio: "Frontend developer passionate about JavaScript",
  avatar: "https://example.com/avatar.jpg"
};

const profile = createProfile(user);
document.getElementById('profile-section').appendChild(profile);
```

**Exercise 2: Create a Notification Banner**
```javascript
// TODO: Create a function that generates a notification banner
function createNotification(message, type = "info") {
  // Your code here
}

// Example usage:
// createNotification("Your changes have been saved", "success");
// createNotification("Error: Could not connect to server", "error");
```

---

## Creating Elements with Functions

### <a id="functions-code-inspiration"></a>Code Inspiration

**Example 1: Button Factory Function**
```javascript
function createButton(text, onClick, variant = "primary") {
  const button = document.createElement('button');
  button.textContent = text;
  button.className = `btn btn-${variant}`;
  button.addEventListener('click', onClick);
  return button;
}

// Usage
const myButton = createButton("Click me", () => {
  alert("Button clicked!");
}, "secondary");

document.body.appendChild(myButton);
```

**Example 2: Input Field Generator**
```javascript
function createInputField(type, placeholder, id, value = "") {
  const input = document.createElement('input');
  input.type = type;
  input.placeholder = placeholder;
  input.id = id;
  input.value = value;
  return input;
}

// Usage
const emailInput = createInputField("email", "Enter your email", "email-field");
document.body.appendChild(emailInput);
```

### <a id="functions-exercises"></a>Exercises

**Exercise 1: Create a Labeled Input Function**
```javascript
// TODO: Create a function that generates an input with a label
function createLabeledInput(labelText, inputType, inputId) {
  // Your code here
}

// Example usage:
// const nameInput = createLabeledInput("Name", "text", "name-input");
// document.body.appendChild(nameInput);
```

**Exercise 2: Build a Modal Dialog Function**
```javascript
// TODO: Create a function that generates a modal dialog
function createModal(title, content) {
  // Your code here
}

// Example usage:
// const modal = createModal("Warning", "Are you sure you want to delete this item?");
// document.body.appendChild(modal);
```

---

## Creating Elements with `<template>`

### <a id="template-code-inspiration"></a>Code Inspiration

**Example 1: Using Template for Product Cards**
```html
<template id="product-template">
  <div class="product-card">
    <h3 class="product-title"></h3>
    <p class="product-price"></p>
    <button class="add-to-cart">Add to Cart</button>
  </div>
</template>

<script>
function createProductFromTemplate(product) {
  const template = document.getElementById('product-template');
  const clone = template.content.cloneNode(true);
  
  clone.querySelector('.product-title').textContent = product.name;
  clone.querySelector('.product-price').textContent = `$${product.price}`;
  
  return clone;
}

// Usage
const product = { name: "JavaScript Book", price: 29.99 };
const productElement = createProductFromTemplate(product);
document.body.appendChild(productElement);
</script>
```

**Example 2: Template for User List Items**
```html
<template id="user-item-template">
  <li class="user-item">
    <span class="user-name"></span>
    <span class="user-email"></span>
  </li>
</template>

<script>
function createUserListItem(user) {
  const template = document.getElementById('user-item-template');
  const clone = template.content.cloneNode(true);
  
  clone.querySelector('.user-name').textContent = user.name;
  clone.querySelector('.user-email').textContent = user.email;
  
  return clone;
}

// Usage
const user = { name: "Alice", email: "alice@example.com" };
const userItem = createUserListItem(user);
document.getElementById('user-list').appendChild(userItem);
</script>
```

### <a id="template-exercises"></a>Exercises

**Exercise 1: Create a Message Template**
```html
<template id="message-template">
  <!-- TODO: Define a template for a message element -->
</template>

<script>
// TODO: Complete this function to use the template
function createMessage(content, type = "info") {
  // Your code here
}

// Example usage:
// const message = createMessage("This is a success message", "success");
// document.body.appendChild(message);
</script>
```

**Exercise 2: Build a Task Item from Template**
```html
<template id="task-template">
  <!-- TODO: Define a template for a task item -->
</template>

<script>
// TODO: Complete this function to create task items from the template
function createTaskItem(task) {
  // Your code here
}

// Example usage:
// const task = { title: "Learn JavaScript", completed: false };
// const taskElement = createTaskItem(task);
// document.getElementById('task-list').appendChild(taskElement);
</script>
```

---

## Reusable Components

### <a id="components-code-inspiration"></a>Code Inspiration

**Example 1: Counter Component**
```javascript
function createCounter(initialValue = 0) {
  const container = document.createElement('div');
  container.className = 'counter';
  
  const valueDisplay = document.createElement('span');
  valueDisplay.textContent = initialValue;
  valueDisplay.className = 'counter-value';
  
  const incrementBtn = document.createElement('button');
  incrementBtn.textContent = '+';
  incrementBtn.addEventListener('click', () => {
    valueDisplay.textContent = parseInt(valueDisplay.textContent) + 1;
  });
  
  const decrementBtn = document.createElement('button');
  decrementBtn.textContent = '-';
  decrementBtn.addEventListener('click', () => {
    valueDisplay.textContent = parseInt(valueDisplay.textContent) - 1;
  });
  
  container.appendChild(decrementBtn);
  container.appendChild(valueDisplay);
  container.appendChild(incrementBtn);
  
  return container;
}

// Usage
const counter = createCounter(5);
document.body.appendChild(counter);
```

**Example 2: Toggle Switch Component**
```javascript
function createToggleSwitch(initialState = false, onChange) {
  const container = document.createElement('label');
  container.className = 'switch';
  
  const input = document.createElement('input');
  input.type = 'checkbox';
  input.checked = initialState;
  
  const slider = document.createElement('span');
  slider.className = 'slider';
  
  input.addEventListener('change', () => {
    if (onChange) onChange(input.checked);
  });
  
  container.appendChild(input);
  container.appendChild(slider);
  
  return container;
}

// Usage
const toggle = createToggleSwitch(false, (isOn) => {
  console.log('Toggle is now:', isOn);
});
document.body.appendChild(toggle);
```

### <a id="components-exercises"></a>Exercises

**Exercise 1: Create a Rating Component**
```javascript
// TODO: Create a reusable rating component (1-5 stars)
function createRatingComponent(initialRating = 0, onRatingChange) {
  // Your code here
}

// Example usage:
// const rating = createRatingComponent(3, (newRating) => {
//   console.log(`Rating changed to: ${newRating}`);
// });
// document.body.appendChild(rating);
```

**Exercise 2: Build a Tab Component**
```javascript
// TODO: Create a reusable tab component
function createTabComponent(tabs) {
  // Your code here
}

// Example usage:
// const tabs = [
//   { title: "Tab 1", content: "Content for tab 1" },
//   { title: "Tab 2", content: "Content for tab 2" },
//   { title: "Tab 3", content: "Content for tab 3" }
// ];
// const tabComponent = createTabComponent(tabs);
// document.body.appendChild(tabComponent);
```

---

## One-to-One Mappings

### <a id="mappings-code-inspiration"></a>Code Inspiration

**Example 1: Mapping Users to List Items**
```javascript
const users = [
  { id: 1, name: "Alice", email: "alice@example.com" },
  { id: 2, name: "Bob", email: "bob@example.com" },
  { id: 3, name: "Charlie", email: "charlie@example.com" }
];

function renderUserList(usersArray) {
  const userList = document.getElementById('user-list');
  userList.innerHTML = ''; // Clear existing content
  
  usersArray.forEach(user => {
    const listItem = document.createElement('li');
    listItem.textContent = `${user.name} (${user.email})`;
    listItem.dataset.userId = user.id;
    userList.appendChild(listItem);
  });
}

renderUserList(users);
```

**Example 2: Mapping Products to Cards**
```javascript
const products = [
  { id: 101, name: "Laptop", price: 999.99 },
  { id: 102, name: "Mouse", price: 25.50 },
  { id: 103, name: "Keyboard", price: 75.00 }
];

function renderProductGrid(productsArray) {
  const productGrid = document.getElementById('product-grid');
  productGrid.innerHTML = ''; // Clear existing content
  
  productsArray.forEach(product => {
    const productCard = document.createElement('div');
    productCard.className = 'product-card';
    productCard.innerHTML = `
      <h3>${product.name}</h3>
      <p>Price: $${product.price.toFixed(2)}</p>
      <button data-product-id="${product.id}">Add to Cart</button>
    `;
    productGrid.appendChild(productCard);
  });
}

renderProductGrid(products);
```

### <a id="mappings-exercises"></a>Exercises

**Exercise 1: Map Tasks to Task Elements**
```javascript
const tasks = [
  { id: 1, title: "Learn JavaScript", completed: false },
  { id: 2, title: "Build a project", completed: true },
  { id: 3, title: "Deploy to GitHub", completed: false }
];

// TODO: Complete this function to map tasks to DOM elements
function renderTaskList(tasksArray) {
  const taskList = document.getElementById('task-list');
  taskList.innerHTML = '';
  
  // Your code here
}

renderTaskList(tasks);
```

**Exercise 2: Map Colors to Color Swatches**
```javascript
const colors = ["#ff0000", "#00ff00", "#0000ff", "#ffff00", "#ff00ff"];

// TODO: Create a function that maps color values to color swatch elements
function renderColorPalette(colorsArray) {
  const palette = document.getElementById('color-palette');
  palette.innerHTML = '';
  
  // Your code here
}

renderColorPalette(colors);
```

---

## Using `map`

### <a id="using-map-code-inspiration"></a>Code Inspiration

**Example 1: Transforming Arrays with Map**
```javascript
const numbers = [1, 2, 3, 4, 5];

// Double each number
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

// Convert numbers to strings
const numberStrings = numbers.map(num => `Number: ${num}`);
console.log(numberStrings); // ["Number: 1", "Number: 2", ...]

// Create HTML elements from data
const numberElements = numbers.map(num => {
  const element = document.createElement('div');
  element.textContent = num;
  element.className = 'number';
  return element;
});

// Append all elements to the document
numberElements.forEach(element => document.body.appendChild(element));
```

**Example 2: Extracting Properties with Map**
```javascript
const users = [
  { id: 1, name: "Alice", age: 28 },
  { id: 2, name: "Bob", age: 32 },
  { id: 3, name: "Charlie", age: 25 }
];

// Extract just the names
const names = users.map(user => user.name);
console.log(names); // ["Alice", "Bob", "Charlie"]

// Extract names with ages
const nameWithAge = users.map(user => `${user.name} (${user.age})`);
console.log(nameWithAge); // ["Alice (28)", "Bob (32)", "Charlie (25)"]

// Create user cards
const userCards = users.map(user => {
  const card = document.createElement('div');
  card.className = 'user-card';
  card.innerHTML = `
    <h3>${user.name}</h3>
    <p>Age: ${user.age}</p>
  `;
  return card;
});

// Add all cards to a container
const container = document.getElementById('user-container');
userCards.forEach(card => container.appendChild(card));
```

### <a id="using-map-exercises"></a>Exercises

**Exercise 1: Transform Product Data**
```javascript
const products = [
  { id: 1, name: "Laptop", price: 999.99 },
  { id: 2, name: "Phone", price: 699.99 },
  { id: 3, name: "Tablet", price: 399.99 }
];

// TODO: Use map to create an array of product names
const productNames = // Your code here
console.log(productNames);

// TODO: Use map to create an array of formatted price strings
const priceStrings = // Your code here
console.log(priceStrings);
```

**Exercise 2: Create Elements from Data**
```javascript
const books = [
  { title: "JavaScript: The Good Parts", author: "Douglas Crockford" },
  { title: "Eloquent JavaScript", author: "Marijn Haverbeke" },
  { title: "You Don't Know JS", author: "Kyle Simpson" }
];

// TODO: Use map to create an array of book elements
const bookElements = // Your code here

// TODO: Append all book elements to the book-list container
const bookList = document.getElementById('book-list');
// Your code here
```

---

## Applying `map`

### <a id="applying-map-code-inspiration"></a>Code Inspiration

**Example 1: Creating a Dynamic Select Dropdown**
```javascript
const countries = [
  { code: "us", name: "United States" },
  { code: "ca", name: "Canada" },
  { code: "uk", name: "United Kingdom" },
  { code: "au", name: "Australia" }
];

function createCountryDropdown(countriesArray) {
  const select = document.createElement('select');
  select.id = 'country-select';
  
  // Create options using map
  const options = countriesArray.map(country => {
    const option = document.createElement('option');
    option.value = country.code;
    option.textContent = country.name;
    return option;
  });
  
  // Add options to select
  options.forEach(option => select.appendChild(option));
  
  return select;
}

// Usage
const countryDropdown = createCountryDropdown(countries);
document.body.appendChild(countryDropdown);
```

**Example 2: Generating a Table from Data**
```javascript
const students = [
  { id: 1, name: "Alice", grade: "A" },
  { id: 2, name: "Bob", grade: "B" },
  { id: 3, name: "Charlie", grade: "C" }
];

function createStudentTable(studentsArray) {
  const table = document.createElement('table');
  table.innerHTML = `
    <thead>
      <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Grade</th>
      </tr>
    </thead>
    <tbody></tbody>
  `;
  
  const tbody = table.querySelector('tbody');
  
  // Create table rows using map
  const rows = studentsArray.map(student => {
    const row = document.createElement('tr');
    row.innerHTML = `
      <td>${student.id}</td>
      <td>${student.name}</td>
      <td>${student.grade}</td>
    `;
    return row;
  });
  
  // Add rows to table
  rows.forEach(row => tbody.appendChild(row));
  
  return table;
}

// Usage
const studentTable = createStudentTable(students);
document.body.appendChild(studentTable);
```

### <a id="applying-map-exercises"></a>Exercises

**Exercise 1: Create a Navigation Menu**
```javascript
const menuItems = [
  { text: "Home", url: "/home" },
  { text: "About", url: "/about" },
  { text: "Services", url: "/services" },
  { text: "Contact", url: "/contact" }
];

// TODO: Use map to create a navigation menu from the menuItems array
function createNavigationMenu(items) {
  const nav = document.createElement('nav');
  const ul = document.createElement('ul');
  
  // Your code here
  
  nav.appendChild(ul);
  return nav;
}

const navMenu = createNavigationMenu(menuItems);
document.body.appendChild(navMenu);
```

**Exercise 2: Generate a Product Gallery**
```javascript
const galleryProducts = [
  { id: 1, name: "Product 1", image: "product1.jpg", price: 19.99 },
  { id: 2, name: "Product 2", image: "product2.jpg", price: 29.99 },
  { id: 3, name: "Product 3", image: "product3.jpg", price: 39.99 }
];

// TODO: Use map to create a product gallery
function createProductGallery(products) {
  const gallery = document.createElement('div');
  gallery.className = 'product-gallery';
  
  // Your code here
  
  return gallery;
}

const productGallery = createProductGallery(galleryProducts);
document.body.appendChild(productGallery);
```

---

## Additional Resources

1. [MDN Web Docs: Document Object Model (DOM)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) - Comprehensive guide to working with the DOM
2. [JavaScript.info: Document](https://javascript.info/document) - Detailed tutorial on document manipulation
3. [W3Schools: JavaScript HTML DOM](https://www.w3schools.com/js/js_htmldom.asp) - Interactive tutorials and examples for DOM manipulation
