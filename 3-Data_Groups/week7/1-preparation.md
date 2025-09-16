# Index

1. [Prep Directory](#prep-directory)
2. [Creating Test Files](#creating-test-files)
3. [Grouping Data](#grouping-data)
4. [Arrays](#arrays)
5. [Calculating the Mean](#calculating-the-mean)
6. [Summation](#summation)
7. [Iteration](#iteration)
8. [Calculating the Median](#calculating-the-median)
9. [Assembling the Parts](#assembling-the-parts)
10. [References](#references)
11. [Mutation](#mutation)
12. [Side-effects](#side-effects)
13. [Implementing All the Cases](#implementing-all-the-cases)
14. [Solving Problems with Arrays](#solving-problems-with-arrays)
15. [Failing Fast](#failing-fast)

---

## Prep Directory

**Why?** Organizing code like a scientist keeps experiments clean.

```bash
mkdir js-beginners
cd js-beginners
```

Create a folder called `js-beginners`. This is your lab!

---

## Creating Test Files

Each idea will live in its own file. Example:

```bash
touch arrays.js
```

Inside `arrays.js`:

```javascript
console.log("Hello, Arrays!");
```

Run it:

```bash
node arrays.js
```

✅ *Active recall:* What command runs a JavaScript file?

---

## Grouping Data

We often need to group related values. Instead of separate variables:

```javascript
let a = 10;
let b = 20;
let c = 30;
```

We can group them:

```javascript
let numbers = [10, 20, 30];
```

---

## Arrays

An **array** is a list of items:

```javascript
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // apple
```

✅ *Try it:* Print the third fruit.

---

## Calculating the Mean

The **mean** = sum ÷ count.

```javascript
let values = [2, 4, 6, 8];
let sum = values[0] + values[1] + values[2] + values[3];
let mean = sum / values.length;
console.log(mean); // 5
```

Later, we’ll automate this.

---

## Summation

Instead of manual addition:

```javascript
let numbers = [2, 4, 6, 8];
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}
console.log(sum); // 20
```

✅ *Active recall:* What is `sum` initially?

---

## Iteration

**Iteration** = repeating steps. The `for` loop is one way:

```javascript
for (let i = 0; i < 5; i++) {
  console.log("Step", i);
}
```

---

## Calculating the Median

Median = middle value (after sorting).

```javascript
let nums = [7, 3, 1, 4];
nums.sort((a, b) => a - b); // [1, 3, 4, 7]
let middle = Math.floor(nums.length / 2);
let median = nums.length % 2 !== 0 ? nums[middle] : (nums[middle - 1] + nums[middle]) / 2;
console.log(median); // 3.5
```

---

## Assembling the Parts

Let’s combine **mean**, **sum**, and **median** into reusable functions:

```javascript
function sumArray(arr) {
  return arr.reduce((acc, val) => acc + val, 0);
}

function meanArray(arr) {
  return sumArray(arr) / arr.length;
}

function medianArray(arr) {
  let sorted = [...arr].sort((a, b) => a - b);
  let mid = Math.floor(sorted.length / 2);
  return sorted.length % 2 !== 0 ? sorted[mid] : (sorted[mid - 1] + sorted[mid]) / 2;
}

console.log(meanArray([1,2,3,4,5]));
console.log(medianArray([1,2,3,4,5]));
```

---

## References

Variables can **reference** the same array:

```javascript
let x = [1, 2, 3];
let y = x;
y.push(4);
console.log(x); // [1,2,3,4]
```

✅ *Think:* Why did `x` change?

---

## Mutation

**Mutation** = changing data in place.

```javascript
let data = [1, 2, 3];
data[0] = 99;
console.log(data); // [99,2,3]
```

Mutation can cause surprises if not careful.

---

## Side-effects

A **side-effect** is when a function changes something outside itself:

```javascript
let scores = [1,2,3];
function addScore(arr, value) {
  arr.push(value); // side-effect!
}

addScore(scores, 4);
console.log(scores); // [1,2,3,4]
```

---

## Implementing All the Cases

Let’s make a function that can:

* Return sum
* Return mean
* Return median

```javascript
function analyze(arr, type) {
  if (type === "sum") return sumArray(arr);
  if (type === "mean") return meanArray(arr);
  if (type === "median") return medianArray(arr);
  throw new Error("Unknown type");
}

console.log(analyze([2,4,6], "sum"));
```

---

## Solving Problems with Arrays

Example: find the **maximum number**.

```javascript
let arr = [5, 1, 9, 3];
let max = arr[0];
for (let i = 1; i < arr.length; i++) {
  if (arr[i] > max) {
    max = arr[i];
  }
}
console.log(max); // 9
```

✅ *Try it:* Write code to find the minimum.

---

## Failing Fast

**Fail fast** = stop when something’s wrong:

```javascript
function safeMean(arr) {
  if (!Array.isArray(arr)) throw new Error("Input must be an array");
  if (arr.length === 0) throw new Error("Array cannot be empty");
  return meanArray(arr);
}

console.log(safeMean([1,2,3])); // 2
```

This makes debugging easier.

---

# ✅ Next Steps

* Practice with your own datasets.
* Write small programs using arrays.
* Always test, fail, and learn!



