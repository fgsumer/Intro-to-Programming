*   **Variables**
    *   [Code Inspiration](#variables-code-inspiration)
    *   [Exercises](#variables-exercises)
*   **Declarations and Statements**
    *   [Code Inspiration](#declarations-and-statements-code-inspiration)
    *   [Exercises](#declarations-and-statements-exercises)
*   **Functions**
    *   [Code Inspiration](#functions-code-inspiration)
    *   [Exercises](#functions-exercises)
*   **Scripts**
    *   [Code Inspiration](#scripts-code-inspiration)
    *   [Exercises](#scripts-exercises)
*   **Logging**
    *   [Code Inspiration](#logging-code-inspiration)
    *   [Exercises](#logging-exercises)
*   **Errors**
    *   [Code Inspiration](#errors-code-inspiration)
    *   [Exercises](#errors-exercises)
*   **Percentages**
    *   [Code Inspiration](#percentages-code-inspiration)
    *   [Exercises](#percentages-exercises)
*   **Defining Functions**
    *   [Code Inspiration](#defining-functions-code-inspiration)
    *   [Exercises](#defining-functions-exercises)
*   **Playing Computer**
    *   [Code Inspiration](#playing-computer-code-inspiration)
    *   [Exercises](#playing-computer-exercises)
*   **Scope**
    *   [Code Inspiration](#scope-code-inspiration)
    *   [Exercises](#scope-exercises)
*   **Return**
    *   [Code Inspiration](#return-code-inspiration)
    *   [Exercises](#return-exercises)
*   **Reuse**
    *   [Code Inspiration](#reuse-code-inspiration)
    *   [Exercises](#reuse-exercises)
*   **Parameters**
    *   [Code Inspiration](#parameters-code-inspiration)
    *   [Exercises](#parameters-exercises)
*   **Solving Problems with Functions**
    *   [Code Inspiration](#solving-problems-with-functions-code-inspiration)
    *   [Exercises](#solving-problems-with-functions-exercises)

---

## Practice Sections

### Variables
<a name="variables-code-inspiration"></a>
#### Code Inspiration
1.  **Storing a username:**
    ```javascript
    let userName = "Alice";
    console.log("Hello, " + userName);
    ```
2.  **Storing a changing score:**
    ```javascript
    let gameScore = 0;
    gameScore = gameScore + 10; // Score is now 10
    console.log("Your score is: " + gameScore);
    ```
3.  **Storing a constant value (PI):**
    ```javascript
    const PI = 3.14159;
    let radius = 5;
    let circumference = 2 * PI * radius;
    console.log(circumference);
    ```

<a name="variables-exercises"></a>
#### Exercises
1.  **Declare a variable:** Declare a variable called `favoriteFood` and assign your favorite food to it.
    ```javascript
    // Your code here
    ```
2.  **Update a variable:** You have a variable `count` with a value of 5. Write code to increase its value by 1.
    ```javascript
    let count = 5;
    // Your code here
    console.log(count); // Should print 6
    ```
3.  **Use `const` correctly:** Fix the error in the code below.
    ```javascript
    const birthYear = 1990;
    birthYear = 1991; // This line causes an error
    console.log(birthYear);
    ```

### Declarations and Statements
<a name="declarations-and-statements-code-inspiration"></a>
#### Code Inspiration
1.  **A simple statement:**
    ```javascript
    console.log("This is a statement. It performs an action.");
    ```
2.  **A declaration and multiple statements:**
    ```javascript
    let message; // Declaration statement
    message = "Hello"; // Assignment statement
    console.log(message); // Action statement
    ```
3.  **Multiple statements in sequence:**
    ```javascript
    let a = 5;
    let b = 10;
    let sum = a + b;
    console.log("The sum is: " + sum);
    ```

<a name="declarations-and-statements-exercises"></a>
#### Exercises
1.  **Write a sequence:** Write three statements that declare a variable `price`, assign it the value `19.99`, and then log it to the console.
    ```javascript
    // Your code here
    ```
2.  **Identify the error:** Why will this code block not run? Fix it.
    ```javascript
    let greeting = "Hi there"
    console.log(greeting)
    ```
3.  **Complete the sequence:** Complete the code to calculate the area of a rectangle (area = length * width).
    ```javascript
    let length = 8;
    let width = 3;
    // Your code here
    console.log(area); // Should print 24
    ```

### Functions
<a name="functions-code-inspiration"></a>
#### Code Inspiration
1.  **Calling a built-in function:**
    ```javascript
    let text = "hello world";
    let upperCaseText = text.toUpperCase(); // .toUpperCase() is a function
    console.log(upperCaseText); // "HELLO WORLD"
    ```
2.  **Calling the `prompt` function:**
    ```javascript
    let userInput = prompt("What is your name?"); // prompt() shows a dialog box
    console.log("You entered: " + userInput);
    ```
3.  **Calling the `Math.random` function:**
    ```javascript
    let randomNumber = Math.random(); // Generates a number between 0 and 1
    console.log("Your random number is: " + randomNumber);
    ```

<a name="functions-exercises"></a>
#### Exercises
1.  **Use a string function:** Use the `.length` function on the string `"JavaScript"` and log the result.
    ```javascript
    let language = "JavaScript";
    // Your code here
    ```
2.  **Round a number:** Use the `Math.round()` function to round the number `7.8` to the nearest integer and log it.
    ```javascript
    let number = 7.8;
    // Your code here
    ```
3.  **Get a substring:** Use the `prompt()` function to ask the user for their full name, then use the string's `.substring()` function to log only the first 5 characters.
    ```javascript
    // Your code here
    ```

### Scripts
<a name="scripts-code-inspiration"></a>
#### Code Inspiration
1.  **A simple script in an HTML file:**
    ```html
    <!DOCTYPE html>
    <html>
    <body>
        <h1>My Page</h1>
        <script>
            // This is a script tag
            document.write("<p>This paragraph was added by JavaScript!</p>");
        </script>
    </body>
    </html>
    ```
2.  **Linking an external script file (`myScript.js`):**
    ```html
    <!-- In your HTML file -->
    <script src="myScript.js"></script>
    ```
    ```javascript
    // Inside myScript.js
    alert("This script is loaded from an external file!");
    ```
3.  **A script that runs when the page loads:**
    ```html
    <script>
        console.log("The page has finished loading!");
    </script>
    ```

<a name="scripts-exercises"></a>
#### Exercises
1.  **Create an external script:** Create a file named `greeting.js`. In it, write code that logs "Hello from an external file!" to the console. Then, write the HTML tag to link this script.
    ```html
    <!-- Your HTML tag here -->
    ```
    ```javascript
    // Content of greeting.js
    // Your code here
    ```
2.  **Order of execution:** What will be the order of the logs? First, second, or third?
    ```html
    <script>
        console.log("First");
    </script>
    <h1>A Heading</h1>
    <script>
        console.log("Second");
    </script>
    ```
3.  **Fix the script source:** The following script tag isn't working. The file is named `app.js`. Correct the tag.
    ```html
    <script source="application.js"></script>
    ```

### Logging
<a name="logging-code-inspiration"></a>
#### Code Inspiration
1.  **Logging multiple values:**
    ```javascript
    let name = "Bob";
    let age = 25;
    console.log("User:", name, "Age:", age);
    ```
2.  **Using different console methods:**
    ```javascript
    console.log("This is a standard log.");
    console.warn("This is a warning!");
    console.error("This is an error message!");
    ```
3.  **Logging within loops:**
    ```javascript
    for (let i = 0; i < 3; i++) {
        console.log("Loop iteration number:", i);
    }
    ```

<a name="logging-exercises"></a>
#### Exercises
1.  **Log multiple variables:** You have two variables, `product` ("Coffee") and `price` (4.99). Use a single `console.log` to print: "The price of Coffee is $4.99".
    ```javascript
    let product = "Coffee";
    let price = 4.99;
    // Your code here
    ```
2.  **Use appropriate logging:** You want to inform a developer that a function they are using will be removed soon. Use the correct console method to log a warning message.
    ```javascript
    // Your code here
    ```
3.  **Template literal logging:** Use a template literal (backticks `` ` ``) to log the same message as exercise 1.
    ```javascript
    let product = "Coffee";
    let price = 4.99;
    // Your code here using `...${}...`
    ```

### Errors
<a name="errors-code-inspiration"></a>
#### Code Inspiration
1.  **A ReferenceError:**
    ```javascript
    console.log(variableThatDoesntExist); // ReferenceError: ... is not defined
    ```
2.  **A SyntaxError:**
    ```javascript
    let my variable = 10; // SyntaxError: Unexpected identifier
    ```
3.  **A TypeError:**
    ```javascript
    let myNumber = 42;
    myNumber.toUpperCase(); // TypeError: myNumber.toUpperCase is not a function
    ```

<a name="errors-exercises"></a>
#### Exercises
1.  **Predict the error:** What type of error will the following code produce?
    ```javascript
    const constantValue = 100;
    constantValue = 200;
    console.log(constantValue);
    ```
2.  **Find the syntax error:** There is a syntax error in this code. Find and fix it.
    ```javascript
    let firstNumber = 10
    let secondNumber = 20
    console.log firstNumber + secondNumber;
    ```
3.  **Catch a logical error:** The code runs without throwing an error, but it gives the wrong result. Find and fix the logical error.
    ```javascript
    function calculateTotal(price, quantity) {
        return price + quantity; // Should be price * quantity
    }
    let total = calculateTotal(5, 3);
    console.log(total); // Logs 8, but should log 15
    ```

### Percentages
<a name="percentages-code-inspiration"></a>
#### Code Inspiration
1.  **Calculate a percentage:**
    ```javascript
    let total = 200;
    let percentage = 15;
    let result = (percentage / 100) * total;
    console.log(percentage + "% of " + total + " is " + result); // 15% of 200 is 30
    ```
2.  **Calculate a tip:**
    ```javascript
    let billAmount = 50;
    let tipPercentage = 18;
    let tipAmount = (tipPercentage / 100) * billAmount;
    console.log("Tip: $" + tipAmount.toFixed(2));
    ```
3.  **Find the percentage:**
    ```javascript
    let obtained = 45;
    let totalMarks = 60;
    let percentageScore = (obtained / totalMarks) * 100;
    console.log("You scored " + percentageScore + "%");
    ```

<a name="percentages-exercises"></a>
#### Exercises
1.  **Calculate a discount:** An item costs `$80`. It is on sale for `25%` off. Calculate and log the discount amount and the final sale price.
    ```javascript
    let originalPrice = 80;
    let discountPercent = 25;
    // Your code here
    ```
2.  **Calculate a score:** You answered `17` questions correctly out of `20`. Calculate and log your percentage score.
    ```javascript
    let correctAnswers = 17;
    let totalQuestions = 20;
    // Your code here
    ```
3.  **Reverse a percentage:** You know that `30` is `60%` of a number. What is the original number? Calculate it.
    ```javascript
    let part = 30;
    let percent = 60;
    // Your code here (Hint: original number = (part / percent) * 100)
    ```

### Defining Functions
<a name="defining-functions-code-inspiration"></a>
#### Code Inspiration
1.  **A simple function:**
    ```javascript
    function sayHello() {
        console.log("Hello!");
    }
    // To run it:
    sayHello();
    ```
2.  **A function with a local variable:**
    ```javascript
    function getCurrentYear() {
        const now = new Date();
        const year = now.getFullYear();
        return year;
    }
    console.log(getCurrentYear());
    ```
3.  **A function that calls another function:**
    ```javascript
    function greet() {
        return "Hi!";
    }

    function loudGreet() {
        let greeting = greet(); // Calling the greet function
        return greeting.toUpperCase() + "!!!";
    }
    console.log(loudGreet()); // "HI!!!"
    ```

<a name="defining-functions-exercises"></a>
#### Exercises
1.  **Define a function:** Define a function named `printSmiley` that logs a smiley face to the console (e.g., `:)`). Then call the function.
    ```javascript
    // Your code here
    ```
2.  **Define a `getGreeting` function:** Define a function that **returns** the string "Good morning!".
    ```javascript
    // Your code here

    let message = getGreeting(); // message should be "Good morning!"
    console.log(message);
    ```
3.  **What's wrong?** The function below is supposed to log a message but doesn't. Why? Fix it.
    ```javascript
    function logMessage {
        console.log("This is a message");
    }
    ```

### Playing Computer
<a name="playing-computer-code-inspiration"></a>
#### Code Inspiration
1.  **Trace variable values:**
    ```javascript
    let a = 1;
    let b = a + 2; // a=1, b=3
    a = 5;         // a=5, b=3
    let c = a + b; // a=5, b=3, c=8
    console.log(c); // 8
    ```
2.  **Trace a function call:**
    ```javascript
    function double(x) {
        let result = x * 2;
        return result;
    }

    let input = 4;
    let output = double(input); // output becomes 8
    console.log(output);
    ```
3.  **Trace a loop:**
    ```javascript
    let total = 0;
    for (let i = 1; i <= 3; i++) {
        total = total + i;
        console.log("i:", i, "total:", total);
    }
    // i:1 total:1
    // i:2 total:3
    // i:3 total:6
    ```

<a name="playing-computer-exercises"></a>
#### Exercises
1.  **Trace the code:** What is the final value of `x`?
    ```javascript
    let x = 10;
    x = x - 2;
    x = x + 5;
    x = x * 2;
    console.log(x); // What is logged?
    ```
2.  **Trace the function:** What is logged to the console when this code runs?
    ```javascript
    function addFive(num) {
        return num + 5;
    }

    let initial = 3;
    let updated = addFive(initial);
    console.log(initial, updated);
    ```
3.  **Trace the conditionals:** What is the final value of `message`?
    ```javascript
    let time = 14;
    let message = "Hi";

    if (time < 12) {
        message = "Good morning";
    } else {
        message = "Good day";
    }

    if (time > 18) {
        message = "Good evening";
    }
    console.log(message); // What is logged?
    ```

### Scope
<a name="scope-code-inspiration"></a>
#### Code Inspiration
1.  **Global vs. Local Scope:**
    ```javascript
    let globalVar = "I'm global"; // Global scope

    function myFunction() {
        let localVar = "I'm local"; // Local scope
        console.log(globalVar); // Works!
        console.log(localVar);  // Works!
    }

    myFunction();
    console.log(globalVar); // Works!
    console.log(localVar);  // ReferenceError!
    ```
2.  **Block Scope with `let`/`const`:**
    ```javascript
    if (true) {
        let blockScoped = "I'm inside a block";
        console.log(blockScoped); // Works
    }
    console.log(blockScoped); // ReferenceError
    ```
3.  **No Block Scope with `var` (historical behavior):**
    ```javascript
    if (true) {
        var functionScoped = "I'm var";
    }
    console.log(functionScoped); // Works! (This is why let/const are preferred)
    ```

<a name="scope-exercises"></a>
#### Exercises
1.  **Predict the output:** What will be logged? Will there be an error?
    ```javascript
    let bird = "Robin";

    function identifyBird() {
        let bird = "Sparrow";
        console.log(bird);
    }

    identifyBird();
    console.log(bird);
    ```
2.  **Find the scope error:** The code below has an error. Fix it by adjusting the variable scope.
    ```javascript
    function createCounter() {
        let count = 0;
    }
    createCounter();
    count = count + 1; // We want to update the count here, but it causes an error.
    console.log(count);
    ```
3.  **Predict the error:** Why does line 5 cause an error?
    ```javascript
    let temperature = 72;

    if (temperature > 70) {
        let jacketNeeded = false;
    }

    console.log(jacketNeeded); // ReferenceError
    ```

### Return
<a name="return-code-inspiration"></a>
#### Code Inspiration
1.  **Returning a value:**
    ```javascript
    function getPi() {
        return 3.14159;
    }
    let circleArea = getPi() * 5 * 5;
    console.log(circleArea);
    ```
2.  **Returning early:**
    ```javascript
    function isAdult(age) {
        if (age < 18) {
            return false;
        }
        return true; // This only runs if the 'if' condition was false
    }
    console.log(isAdult(20)); // true
    ```
3.  **A function without a return:**
    ```javascript
    function justLog() {
        console.log("I don't return anything.");
    }
    let result = justLog();
    console.log(result); // undefined
    ```

<a name="return-exercises"></a>
#### Exercises
1.  **Fix the return:** The function is meant to return the squared number, but it doesn't. Fix it.
    ```javascript
    function square(number) {
        number * number;
    }
    let result = square(5);
    console.log(result); // Should be 25, but is undefined.
    ```
2.  **Write a `multiply` function:** Write a function that takes two parameters and returns their product.
    ```javascript
    // Your code here

    console.log(multiply(3, 7)); // Should log 21
    ```
3.  **Return a string:** Write a function `getDescription` that returns the string "This is a practice function.".
    ```javascript
    // Your code here

    let desc = getDescription();
    console.log(desc);
    ```

### Reuse
<a name="reuse-code-inspiration"></a>
#### Code Inspiration
1.  **Reusing a function:**
    ```javascript
    function getSquare(number) {
        return number * number;
    }

    let aSquared = getSquare(5); // 25
    let bSquared = getSquare(12); // 144
    let sumOfSquares = aSquared + bSquared; // 169
    console.log(sumOfSquares);
    ```
2.  **Reusing a variable:**
    ```javascript
    let companyName = "Awesome Corp";
    let header = "Welcome to " + companyName;
    let footer = "© 2023 " + companyName;
    console.log(header);
    console.log(footer);
    ```
3.  **Reusing a calculation:**
    ```javascript
    let base = 10;
    let height = 5;
    let area = (base * height) / 2; // Area of triangle

    // Reuse the base and height for a perimeter calculation (assuming right triangle)
    let hypotenuse = Math.sqrt(base * base + height * height);
    let perimeter = base + height + hypotenuse;
    console.log(area, perimeter);
    ```

<a name="reuse-exercises"></a>
#### Exercises
1.  **Reuse a function:** Use the `getSquare` function from the inspiration above to calculate the square of `9` and log it.
    ```javascript
    // Assume getSquare is already defined
    // Your code here
    ```
2.  **Reuse a value:** You have a variable `taxRate = 0.08`. Use it to calculate the tax for two items: one costing `$10` and one costing `$25`. Log both results.
    ```javascript
    let taxRate = 0.08;
    let item1 = 10;
    let item2 = 25;
    // Your code here
    ```
3.  **Avoid repetition:** The code below repeats the same calculation. Refactor it to reuse the calculation by storing it in a variable.
    ```javascript
    let score = 95;
    let maxScore = 100;

    console.log("Your percentage is: " + (score / maxScore) * 100 + "%");
    console.log("You needed " + (maxScore - score) + " more points for a perfect score.");
    // Hint: Create a variable for (score / maxScore)
    ```

### Parameters
<a name="parameters-code-inspiration"></a>
#### Code Inspiration
1.  **Multiple parameters:**
    ```javascript
    function createIntroduction(name, age, city) {
        return `Hello, I'm ${name}, I'm ${age} years old, and I'm from ${city}.`;
    }
    let intro = createIntroduction("Maria", 28, "Madrid");
    console.log(intro);
    ```
2.  **Parameters as inputs for calculations:**
    ```javascript
    function calculateArea(width, height) {
        return width * height;
    }
    let roomArea = calculateArea(10, 12); // 120
    let posterArea = calculateArea(2, 3);  // 6
    console.log(roomArea, posterArea);
    ```
3.  **Order of parameters matters:**
    ```javascript
    function divide(dividend, divisor) {
        return dividend / divisor;
    }
    let result1 = divide(10, 2); // 5
    let result2 = divide(2, 10); // 0.2
    console.log(result1, result2);
    ```

<a name="parameters-exercises"></a>
#### Exercises
1.  **Write a `sayHelloTo` function:** Write a function that takes one parameter `name` and logs "Hello, [name]!".
    ```javascript
    // Your code here

    sayHelloTo("Alice"); // Should log "Hello, Alice!"
    ```
2.  **Calculate with parameters:** Write a function `calculateTip` that takes two parameters: `billAmount` and `tipPercentage`. It should return the tip amount.
    ```javascript
    // Your code here

    let tip = calculateTip(50, 15);
    console.log(tip); // Should log 7.5
    ```
3.  **Fix the parameter order:** The function call is giving the wrong result because the parameters are in the wrong order. Fix the function call without changing the function itself.
    ```javascript
    function greetPerson(greeting, name) {
        return greeting + ", " + name + "!";
    }

    // Fix this line:
    let message = greetPerson("Sarah", "Good morning");
    console.log(message); // Should be "Good morning, Sarah!"
    ```

### Solving Problems with Functions
<a name="solving-problems-with-functions-code-inspiration"></a>
#### Code Inspiration
1.  **A function for a single, clear task:**
    ```javascript
    function isEven(number) {
        return number % 2 === 0;
    }
    console.log(isEven(4)); // true
    console.log(isEven(7)); // false
    ```
2.  **Combining smaller functions:**
    ```javascript
    function getSquare(number) {
        return number * number;
    }
    function getHypotenuse(a, b) {
        let aSquared = getSquare(a);
        let bSquared = getSquare(b);
        return Math.sqrt(aSquared + bSquared);
    }
    console.log(getHypotenuse(3, 4)); // 5
    ```
3.  **A function to validate input:**
    ```javascript
    function isValidEmail(email) {
        // A very simple check
        return email.includes("@") && email.includes(".");
    }
    let userEmail = "user@example.com";
    console.log(isValidEmail(userEmail)); // true
    ```

<a name="solving-problems-with-functions-exercises"></a>
#### Exercises
1.  **Write an `isOdd` function:** Write a function that takes a number and returns `true` if it's odd.
    ```javascript
    // Your code here

    console.log(isOdd(3)); // true
    console.log(isOdd(4)); // false
    ```
2.  **Write a `getCircleArea` function:** Write a function that takes a `radius` parameter and returns the area of the circle (Area = π * r²). You can use `Math.PI` for π.
    ```javascript
    // Your code here

    console.log(getCircleArea(5)); // Should log ~78.54
    ```
3.  **Build a `getCelsius` function:** Write a function that converts Fahrenheit to Celsius. The formula is: `C = (F - 32) * 5/9`.
    ```javascript
    // Your code here

    console.log(getCelsius(32));  // Should log 0
    console.log(getCelsius(86));  // Should log 30
    ```

---

## External Resources

1.  [MDN Web Docs: JavaScript First Steps](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps)
2.  [JavaScript.info: The Modern JavaScript Tutorial](https://javascript.info/)
3.  [W3Schools: JavaScript Tutorial](https://www.w3schools.com/js/)