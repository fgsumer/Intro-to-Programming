- [Arrays](#arrays)
  - [Code Inspiration](#arrays-code-inspiration)
  - [Exercises](#arrays-exercises)
- [Summation](#summation)
  - [Code Inspiration](#summation-code-inspiration)
  - [Exercises](#summation-exercises)
- [Iteration](#iteration)
  - [Code Inspiration](#iteration-code-inspiration)
  - [Exercises](#iteration-exercises)
- [References](#references)
  - [Code Inspiration](#references-code-inspiration)
  - [Exercises](#references-exercises)
- [Mutation](#mutation)
  - [Code Inspiration](#mutation-code-inspiration)
  - [Exercises](#mutation-exercises)
- [Side-effects](#side-effects)
  - [Code Inspiration](#side-effects-code-inspiration)
  - [Exercises](#side-effects-exercises)
- [Solving Problems with Arrays](#solving-problems-with-arrays)
  - [Code Inspiration](#solving-problems-code-inspiration)
  - [Exercises](#solving-problems-exercises)

---

## Arrays

### Arrays Code Inspiration

**Example 1: Basic Array Operations**
```javascript
// Creating and accessing arrays
let fruits = ["apple", "banana", "orange"];
console.log(fruits[0]); // "apple"
console.log(fruits.length); // 3

// Adding and removing elements
fruits.push("grape"); // Adds to the end
console.log(fruits); // ["apple", "banana", "orange", "grape"]

let lastFruit = fruits.pop(); // Removes from the end
console.log(lastFruit); // "grape"
```

**Example 2: Array Methods**
```javascript
// Common array methods
let numbers = [1, 2, 3, 4, 5];

// Map - creates a new array
let doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

// Filter - creates a new array with filtered elements
let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

### Arrays Exercises

**Exercise 1: Complete the array operations**
```javascript
// TODO: Create an array called colors with "red", "green", and "blue"
let colors = 

// TODO: Add "yellow" to the end of the array

// TODO: Remove the first element and store it in a variable called firstColor

// TODO: Log the updated array and the removed color
console.log("Array:", colors);
console.log("Removed color:", firstColor);
```

**Exercise 2: Complete the array transformations**
```javascript
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// TODO: Use filter to create a new array with only numbers greater than 5
let largeNumbers = 

// TODO: Use map to create a new array where each number is squared
let squaredNumbers = 

// TODO: Log both new arrays
console.log("Numbers > 5:", largeNumbers);
console.log("Squared numbers:", squaredNumbers);
```

---

## Summation

### Summation Code Inspiration

**Example 1: Basic Summation**
```javascript
// Summing numbers with a loop
let numbers = [1, 2, 3, 4, 5];
let sum = 0;

for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}

console.log(sum); // 15
```

**Example 2: Using reduce method**
```javascript
// Summing with reduce
let numbers = [10, 20, 30, 40];
let total = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(total); // 100
```

### Summation Exercises

**Exercise 1: Complete the summation function**
```javascript
function sumArray(arr) {
  // TODO: Complete this function to return the sum of all numbers in the array
  let total = 0;
  
  return total;
}

// Test your function
console.log(sumArray([1, 2, 3, 4])); // Should output 10
console.log(sumArray([10, 20, 30])); // Should output 60
```

**Exercise 2: Complete the conditional summation**
```javascript
function sumEvenNumbers(arr) {
  // TODO: Sum only the even numbers in the array
  let sum = 0;
  
  return sum;
}

// Test your function
console.log(sumEvenNumbers([1, 2, 3, 4, 5, 6])); // Should output 12 (2+4+6)
console.log(sumEvenNumbers([10, 15, 20, 25])); // Should output 30 (10+20)
```

---

## Iteration

### Iteration Code Inspiration

**Example 1: Different ways to iterate**
```javascript
let fruits = ["apple", "banana", "cherry"];

// For loop
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

// For...of loop
for (let fruit of fruits) {
  console.log(fruit);
}

// forEach method
fruits.forEach(function(fruit) {
  console.log(fruit);
});
```

**Example 2: Iterating with index**
```javascript
let colors = ["red", "green", "blue"];

// Using for loop with index
for (let i = 0; i < colors.length; i++) {
  console.log(`Color at index ${i} is ${colors[i]}`);
}

// Using forEach with index parameter
colors.forEach(function(color, index) {
  console.log(`Color at index ${index} is ${color}`);
});
```

### Iteration Exercises

**Exercise 1: Complete the iteration**
```javascript
let animals = ["cat", "dog", "bird", "fish"];

// TODO: Use a for loop to print each animal in uppercase
for () {
  
}

// TODO: Use forEach to print each animal with its index
// Example: "0: CAT", "1: DOG", etc.
animals.forEach();
```

**Exercise 2: Complete the array transformation with iteration**
```javascript
let numbers = [1, 2, 3, 4, 5];
let doubledNumbers = [];

// TODO: Use a for loop to double each number and push to doubledNumbers


console.log("Original:", numbers);
console.log("Doubled:", doubledNumbers);
```

---

## References

### References Code Inspiration

**Example 1: Reference vs Value**
```javascript
// Primitive types are copied by value
let a = 5;
let b = a; // b gets the value of a
b = 10;
console.log(a); // 5 (unchanged)

// Objects are copied by reference
let arr1 = [1, 2, 3];
let arr2 = arr1; // arr2 references the same array as arr1
arr2.push(4);
console.log(arr1); // [1, 2, 3, 4] (changed!)
```

**Example 2: Creating independent copies**
```javascript
let original = [1, 2, 3];

// These all reference the same array
let referenceCopy = original;

// These create new independent arrays
let sliceCopy = original.slice();
let spreadCopy = [...original];

referenceCopy.push(4);
console.log(original); // [1, 2, 3, 4] (changed)

sliceCopy.push(5);
console.log(original); // [1, 2, 3, 4] (unchanged)
```

### References Exercises

**Exercise 1: Predict and fix reference issues**
```javascript
let originalArray = [1, 2, 3];
let referenceCopy = originalArray;
let realCopy = // TODO: Create a real copy of originalArray

referenceCopy.push(4);
realCopy.push(5);

console.log("Original:", originalArray); 
// What will this output? How can we fix it to keep originalArray unchanged?
```

**Exercise 2: Complete the function to avoid reference issues**
```javascript
function addElementWithoutModifyingOriginal(arr, element) {
  // TODO: Complete this function
  // It should return a new array with the element added
  // without modifying the original array
}

let original = [1, 2, 3];
let newArray = addElementWithoutModifyingOriginal(original, 4);

console.log("Original:", original); // Should be [1, 2, 3]
console.log("New array:", newArray); // Should be [1, 2, 3, 4]
```

---

## Mutation

### Mutation Code Inspiration

**Example 1: Mutating vs Non-mutating methods**
```javascript
let numbers = [1, 2, 3, 4, 5];

// Mutating methods (change the original array)
numbers.push(6); // Adds to end
numbers.pop(); // Removes from end
numbers.shift(); // Removes from beginning
numbers.unshift(0); // Adds to beginning
numbers.reverse(); // Reverses the array
numbers.sort(); // Sorts the array
numbers.splice(1, 2); // Removes elements

// Non-mutating methods (return new array)
let doubled = numbers.map(n => n * 2);
let filtered = numbers.filter(n => n > 2);
let sliced = numbers.slice(1, 3);
let concatenated = numbers.concat([6, 7, 8]);
```

**Example 2: Working with mutation intentionally**
```javascript
// Sometimes we want to mutate
let shoppingCart = ["apples", "bananas", "milk"];

// Mutating operations
shoppingCart.push("bread"); // Add item
shoppingCart.splice(1, 1); // Remove bananas

console.log(shoppingCart); // ["apples", "milk", "bread"]

// Other times we want to avoid mutation
function addToCart(cart, item) {
  // Return new array instead of mutating
  return [...cart, item];
}

let newCart = addToCart(shoppingCart, "eggs");
console.log(shoppingCart); // Unchanged
console.log(newCart); // New array with eggs
```

### Mutation Exercises

**Exercise 1: Identify and fix mutating operations**
```javascript
function processData(data) {
  // TODO: Fix this function to avoid mutating the input array
  data.sort();
  data.reverse();
  return data;
}

let originalData = [3, 1, 4, 1, 5, 9];
let processedData = processData(originalData);

console.log("Original:", originalData); // Should remain [3, 1, 4, 1, 5, 9]
console.log("Processed:", processedData); // Should be [9, 5, 4, 3, 1, 1]
```

**Exercise 2: Complete the function using non-mutating approaches**
```javascript
function transformArray(arr) {
  // TODO: Transform the array without mutating the original
  // 1. Remove the first element
  // 2. Add "start" to the beginning
  // 3. Add "end" to the end
  // Return the new array
}

let original = [1, 2, 3, 4];
let transformed = transformArray(original);

console.log("Original:", original); // Should be [1, 2, 3, 4]
console.log("Transformed:", transformed); // Should be ["start", 2, 3, 4, "end"]
```

---

## Side-effects

### Side-effects Code Inspiration

**Example 1: Functions with side effects**
```javascript
let counter = 0;

// Function with side effect (modifies external state)
function incrementWithSideEffect() {
  counter++;
  return counter;
}

// Function without side effect (pure function)
function incrementPure(number) {
  return number + 1;
}

console.log(incrementWithSideEffect()); // 1, but also changed counter
console.log(counter); // 1

console.log(incrementPure(5)); // 6, no external changes
```

**Example 2: Avoiding side effects in array processing**
```javascript
let globalArray = [1, 2, 3];

// Function with side effect (modifies external array)
function processWithSideEffect() {
  globalArray.push(4); // Side effect!
  return globalArray.length;
}

// Function without side effects
function processPure(arr) {
  let newArray = [...arr, 4]; // No modification of input
  return newArray.length;
}

console.log(processWithSideEffect()); // 4, but changed globalArray
console.log(globalArray); // [1, 2, 3, 4]

console.log(processPure([1, 2, 3])); // 4, no external changes
console.log(globalArray); // [1, 2, 3, 4] (unchanged by processPure)
```

### Side-effects Exercises

**Exercise 1: Identify and remove side effects**
```javascript
let total = 0;

function calculateTotalWithSideEffect(prices) {
  // TODO: Fix this function to avoid side effects
  total = prices.reduce((sum, price) => sum + price, 0);
  return total;
}

let prices = [10, 20, 30];
let result = calculateTotalWithSideEffect(prices);

// The function should calculate the total without modifying external state
console.log("Result:", result); // Should be 60
console.log("Global total:", total); // Should remain 0 (unchanged)
```

**Exercise 2: Create a pure function**
```javascript
// TODO: Convert this function to a pure function without side effects
function updateProfile(user, newData) {
  user.name = newData.name;
  user.age = newData.age;
  return user;
}

// Test case
let originalUser = { name: "John", age: 30 };
let updatedUser = updateProfile(originalUser, { name: "Jane", age: 25 });

console.log("Original user:", originalUser); // Should be unchanged
console.log("Updated user:", updatedUser); // Should be { name: "Jane", age: 25 }
```

---

## Solving Problems with Arrays

### Solving Problems Code Inspiration

**Example 1: Finding unique values**
```javascript
function getUniqueValues(arr) {
  // Multiple approaches:
  
  // Using Set (modern approach)
  return [...new Set(arr)];
  
  // Using filter (traditional approach)
  return arr.filter((value, index, self) => {
    return self.indexOf(value) === index;
  });
}

let duplicates = [1, 2, 2, 3, 4, 4, 5];
let unique = getUniqueValues(duplicates);
console.log(unique); // [1, 2, 3, 4, 5]
```

**Example 2: Grouping items**
```javascript
function groupByCategory(products) {
  return products.reduce((groups, product) => {
    const category = product.category;
    if (!groups[category]) {
      groups[category] = [];
    }
    groups[category].push(product);
    return groups;
  }, {});
}

let products = [
  { name: "Apple", category: "fruits" },
  { name: "Carrot", category: "vegetables" },
  { name: "Banana", category: "fruits" },
  { name: "Broccoli", category: "vegetables" }
];

console.log(groupByCategory(products));
// {
//   fruits: [{name: "Apple", category: "fruits"}, {name: "Banana", category: "fruits"}],
//   vegetables: [{name: "Carrot", category: "vegetables"}, {name: "Broccoli", category: "vegetables"}]
// }
```

### Solving Problems Exercises

**Exercise 1: Complete the array problem solution**
```javascript
function findCommonElements(arr1, arr2) {
  // TODO: Return a new array containing elements that appear in both arrays
  // Example: findCommonElements([1, 2, 3], [2, 3, 4]) should return [2, 3]
}

// Test your function
console.log(findCommonElements([1, 2, 3, 4], [3, 4, 5, 6])); // Should output [3, 4]
console.log(findCommonElements(["a", "b", "c"], ["b", "c", "d"])); // Should output ["b", "c"]
```

**Exercise 2: Complete the data transformation**
```javascript
function transformStudentData(students) {
  // TODO: Transform the student data
  // Return an array of objects with:
  // - fullName: concatenation of firstName and lastName
  // - averageGrade: average of the grades array
}

let students = [
  { firstName: "John", lastName: "Doe", grades: [90, 85, 92] },
  { firstName: "Jane", lastName: "Smith", grades: [88, 95, 78] }
];

let transformedData = transformStudentData(students);
console.log(transformedData);
// Should output:
// [
//   { fullName: "John Doe", averageGrade: 89 },
//   { fullName: "Jane Smith", averageGrade: 87 }
// ]
```

---

## Additional Resources

1. [MDN Web Docs - JavaScript Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) - Comprehensive guide to JavaScript arrays
2. [JavaScript.info - Arrays](https://javascript.info/array) - Detailed tutorial on arrays and methods
3. [freeCodeCamp - JavaScript Array Handbook](https://www.freecodecamp.org/news/the-javascript-array-handbook/) - Practical guide to array operations
