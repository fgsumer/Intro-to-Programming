# JavaScript Homework: Functions & Problem Solving

### Exercise 1: The Percentage Calculator

This exercise practices basic function structure, parameters, returns, and arithmetic.

**The Problem:**
You often find yourself needing to calculate percentages in your code for things like discounts, taxes, or progress bars. Instead of writing the same logic repeatedly, you decide to create a robust function.

**Your Tasks:**

1.  Define a function named `calculatePercentage` that takes two parameters:
    * `part` (the number you want to find the percentage of)
    * `whole` (the total or reference number)
2.  The function should **return** the calculated percentage value.
3.  Include a check: if the `whole` parameter is 0, the function should **throw a new Error** with a descriptive message to prevent division by zero.
4.  **Reuse** your function to calculate the following, logging the results to the console with a descriptive message (e.g., `"25 is 50% of 50"`):
    * What is 25% of 200?
    * What percentage is 50 out of 200?
    * What percentage is 75 out of 25? (This should trigger your error check).

**Check Your Work (Play Computer):**
Before you run your code, mentally execute the function calls with the given inputs. What do you expect the outputs to be? What will happen in the third case? Write your predictions as comments in your code.

---

### Exercise 2: The Scope Detective

This exercise is designed to test and improve your understanding of variable scope and the flow of execution.

**The Problem:**
You've been given a piece of buggy code. It's supposed to take a customer's order, apply a discount, and print a receipt. However, it's throwing errors and giving incorrect results due to scope issues and incorrect statements.

**Your Tasks:**

1.  **Analyze the code below.** Run it in your mind first ("play computer") and identify all the errors related to scope, incorrect declarations, and statement placement.
2.  **Fix the code** by adjusting variable scope (`let`, `const`), moving declarations, and ensuring the function parameters are used correctly.
3.  **Add a comment** above each fix you make, explaining what the error was.

```javascript
// BUGGY CODE - FIX ME!
const discount = 0.15; // 15% discount

function createReceipt(itemName, price, quantity) {
  subtotal = price * quantity;
  let total = subtotal - subtotal * discount;

  console.log("Item: " + itemName);
  console.log("Quantity: " + quantity);
  console.log("Price per item: $" + price);
  console.log("Subtotal: $" + subtotal);
  console.log("Discount Applied: " + (discount * 100) + "%");
  console.log("Total Due: $" + total);

  return total;
}

let itemName = "Coffee";
price = 4.50;
let quantity = 3;

if (quantity > 0) {
  var totalDue = createReceipt(price, quantity, itemName);
}
console.log("Please pay: $" + totalDue);
```

---

### Exercise 3: The Reusable Budget Helper

This exercise combines everything: complex function logic, multiple parameters, reuse, and problem-solving.

**The Problem:**
You want to create a helper script to manage your monthly budget. Your script will need several functions that work together.

**Your Tasks:**

1.  **Write a function `spentPercentage`** that takes two parameters: `spent` and `budget`. It should return the percentage of the budget that has been spent. Reuse the logic from your `calculatePercentage` function in **Exercise 1**.
2.  **Write a function `getBudgetStatus`** that takes the same parameters (`spent`, `budget`). It should:
    * Call `spentPercentage` to get the value.
    * Return a different string message based on that percentage:
        * If less than 50% is spent: `"Under budget! 🎉"`
        * If between 50% and 99%: `"On track. 👍"`
        * If 100% or more: `"Over budget! ⚠️"`
3.  **Write a function `formatBudgetReport`** that takes three parameters: `category` (a string), `spent`, and `budget`. It should:
    * Call the other two functions.
    * **Return** a single, formatted string that looks like this:
      `"Food: Spent $75 of $100 (75%) - On track. 👍"`
4.  **Finally, write a script** that defines a few example budgets (e.g., for `Food`, `Transportation`, `Entertainment`). Use your `formatBudgetReport` function to generate reports for them and **log** each report to the console.

**Challenge:**
Add a new parameter to `getBudgetStatus` called `warnAt` (defaulting to 100) that allows you to customize what percentage triggers the "Over budget" warning.

---

## Submission Instructions
1.  Create a single JavaScript file (e.g., `homework.js`) for your solutions.
2.  Clearly label each exercise within the file using comments (e.g., `// Exercise 1`).
3.  Ensure your code is well-commented, especially where you explain your fixes in Exercise 2.
4.  Push your file to GitHub and submit the link.
