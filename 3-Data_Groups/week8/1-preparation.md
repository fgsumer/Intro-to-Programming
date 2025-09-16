# 📑 Index

1. [Ordered Data](#ordered-data)
2. [Key-Value Pairs](#key-value-pairs)
3. [Accessing Properties](#accessing-properties)
4. [Query Strings](#query-strings)
5. [Step-Through-Prep Workshop](#step-through-prep-workshop)
6. [No Parameters](#no-parameters)
7. [Parsing a Single Key-Value Pair](#parsing-a-single-key-value-pair)
8. [\[ \] Access with Variables](#--access-with-variables)
9. [Parsing Multiple Params](#parsing-multiple-params)
10. [Solving Problems with Objects](#solving-problems-with-objects)
11. [Conflict Resolution](#conflict-resolution)

---

## 1. Ordered Data

**Concept**: Ordered data is stored in **arrays**. Each element has an index (position).

```js
const fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // apple
```

✅ **Practice**: Create an array of your 3 favorite movies. Log the second one.

---

## 2. Key-Value Pairs

**Concept**: Objects store information using **keys** (like labels) and **values** (the data).

```js
const user = {
  name: "Alice",
  age: 25
};
console.log(user.name); // Alice
```

✅ **Practice**: Create an object for a car with `brand` and `year`.

---

## 3. Accessing Properties

**Concept**: You can use **dot notation** or **bracket notation**.

```js
const book = { title: "1984", author: "Orwell" };
console.log(book.title); // 1984
console.log(book["author"]); // Orwell
```

✅ **Practice**: Add a `pages` property and log it both ways.

---

## 4. Query Strings

**Concept**: Query strings pass data in URLs.

Example: `https://site.com?name=Alice&age=25`

```js
const url = "https://site.com?name=Alice&age=25";
```

✅ **Practice**: Identify the keys and values.

---

## 5. Step-Through-Prep Workshop

**Goal**: Learn to debug step-by-step.

```js
let numbers = [1, 2, 3];
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}
```

🧠 **Think Aloud**: Predict what will print **before** running it.

---

## 6. No Parameters

**Concept**: A function without parameters always does the same thing.

```js
function greet() {
  console.log("Hello!");
}
greet();
```

✅ **Practice**: Write a function that always logs `Welcome!`

---

## 7. Parsing a Single Key-Value Pair

**Concept**: Extract one key-value from a query string.

```js
const query = "?name=Alice";
const value = query.split("=")[1];
console.log(value); // Alice
```

✅ **Practice**: Change `name` to `color` and parse it.

---

## 8. \[ ] Access with Variables

**Concept**: Bracket notation allows variable keys.

```js
const user = { name: "Alice", age: 25 };
let key = "age";
console.log(user[key]); // 25
```

✅ **Practice**: Change the variable to access another property.

---

## 9. Parsing Multiple Params

**Concept**: Split multiple key-value pairs.

```js
const query = "?name=Alice&age=25";
const params = new URLSearchParams(query);
console.log(params.get("name")); // Alice
console.log(params.get("age")); // 25
```

✅ **Practice**: Add a third parameter (`city`) and parse it.

---

## 10. Solving Problems with Objects

**Concept**: Use objects to organize and solve real tasks.

```js
const inventory = {
  apples: 10,
  bananas: 5
};

function buy(item) {
  inventory[item]--;
}

buy("apples");
console.log(inventory);
```

✅ **Practice**: Add a new fruit and update its quantity.

---

## 11. Conflict Resolution

**Concept**: When two variables or functions have the same name, the later one overrides the first.

```js
let message = "Hello";
let message = "Hi"; // ❌ Error: redeclaration not allowed
```

✅ **Practice**: Try renaming variables to avoid conflicts.

---

## 🎯 Wrap-Up

* Arrays = ordered data.
* Objects = key-value storage.
* Dot & bracket notation to access data.
* Query strings = data in URLs.
* Debug by predicting outputs.
* Functions can have parameters or none.
* Objects help solve real-world problems.

📝 **Final Reflection**: Write 3 things you learned today and 1 thing you’re curious about.



