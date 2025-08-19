## 🤝 Interacting with computers

#### Learning objectives

- [x] Define a computer

Modern computers are complicated: it would be too difficult and time-consuming to list all the components that make up a modern computer. So to build our mental model, we will use this simple definition of a computer:

A `computer` is a device used to store and perform operations on data.

## 🏷️ Variables

In programming we often want to reuse our work. Consider the string: "Hello there"

Suppose we want to create different greetings for different people, like: "Hello there, Alicia" "Hello there, Barny"

We can use a variable to store this string and reuse it. How can we create a variable?

🏷️ Variable <br> A variable is a label for a piece of data. We assign a piece of data to a label and then refer back to this label, in place of the data.

We can create a variable in our program by writing a variable declaration.

🧶 Declaration <br> A declaration is an instruction that binds an identifier to a value. , like this:
```js
const greeting = "Hello there";
```

Break down the different syntactic elements of this variable declaration:

`const` is a keyword used to indicate we’re creating a variable. <br> `greeting` is the identifier - it can be used to refer to a variable after it has been declared.<br> `=` is the assignment operator. It means assign to the label greeting the value of the expression on the right hand side. <br> `"Hello there"` - this is the expression whose value we’re assigning to the label greeting.

### Try it yourself

Type this variable declaration into the REPL:
```js
const greeting = "Hello there";
```

Now refer to the label greeting in the REPL:
```js
`${greeting}, Alicia`
```

Our greeting variable is stored in memory. We can reuse it to build more expressions:
```js
`${greeting}, Barny`
```

We just used backticks to create a template literal.
```js
`A template literal places ${expressions} inside strings;
```

With template literals, we can insert expressions into strings to produce new strings. Any time we want to reference a variable inside a template literal we use a dollar sign $ and a set of curly braces {}. We can put any expression (e.g. a variable name) inside the curly braces. The value that expression evaluates to is then placed inside the string.

When an operation uses an expression, that expression is immediately evaluated, and how it was written is forgotten about. That means that the greetAlicia variable is the same in all three of these cases:
```js
const greetAlicia = "Hello there, Alicia";
```

📝string literal
In this example, we don’t use a variable or a template to create a string. Instead we write a string "Hello there, Alicia".

A sequence of characters enclosed in quotation marks is called a string literal. "Hello there, Alicia" is a string literal.

Similarly, 10 is a number literal.

```js
const name = "Alicia";
const greetAlicia = `Hello there, ${name}`;
```

```js
const greeting = "Hello there";
const name = "Alicia";
const greetAlicia = `${greeting}, ${name}`;
```
The greetAlicia variable doesn’t remember whether you used variables to make it or not - in all three cases, greetAlicia contains the string "Hello there, Alicia". Once a value is made, it doesn’t matter how it was made.

## 💬 Declarations and statements

A variable declaration is an example of a declaration. It has the effect of creating a variable.
```js
let versionNumber = "2.0.0"; // declaration
versionNumber = "2.0.1"; // statement
```
The code above has one variable declaration and one statement.

The first line is a declaration - creating a variable versionNumber with a value of "2.0.0".
The second line is a statement - reassignment (Reassignment means changing the value associated with an identifier.) of the value of versionNumber to "2.0.1".

In this example, we’ve used the let keyword to declare a new variable. The let keyword allows us to create new variables like the const keyword.

However, we can reassign the value of a variable that is declared with the let keyword.

If we’d used const to declare versionNumber, we wouldn’t be allowed to reassign it a new value.

In JavaScript, we build up programs by combining declarations and statements.

## 🪄 Functions

Now, instead of adding or multiplying numbers, we’ll consider `10.3`.

🤔 “What is the nearest whole number to `10.3`?”

The process of finding the nearest whole number to a decimal number is called `rounding`. So we could rephrase our question as:

🤔 “What does the number 10.3 round to?”

♻️ Reusing instructions
There is no operator for rounding the number 10.3 in JavaScript. But we will want to round numbers again and again. We should use a function (A function is a reusable set of instructions.)

`Math.round` is a function. Because a function is a reusable set of instructions, Math.round rounds any number.

Functions usually take inputs and then apply their set of instructions to the inputs to produce an output.


