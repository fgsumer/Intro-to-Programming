# Week 4 
### Learning Objectives
- [ ] Predict the behavior of JavaScript expressions before running them.
- [ ] Distinguish between strings, numbers, and how they behave differently.
- [ ] Use debugging techniques (console.log, reading error messages).
- [ ] Collaborate effectively to reason through problems step-by-step.
  

You’ll work on three coding challenges in pairs or groups of 2–3 people.

Each exercise is designed to help you predict, test, and reason about how JavaScript expressions behave.

## 🧩 Exercise 1: Random Day Generator
Group setup: Pairs or small groups of max. 3 students

```js
const startDay = 1;
const endDay = 7;

const randomDay = Math.floor(Math.random() * (endDay - startDay + 1)) + startDay;

// In this program, each number between 1 and 7 represents a day of the week.
// 1 = Monday, 2 = Tuesday, ... , 7 = Sunday

console.log(`Your lucky day number is: ${randomDay}`);
```

Now, answer the following questions:

a) What does `Math.random()` return? Use [the MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) to find out.

b)What does `Math.floor()` do? Why do we need it here?

c) What does (endDay - startDay + 1) represent? Why do we add +1?

d) In your own words, what range of numbers can `randomDay` take? Try running the program multiple times — what pattern do you notice?

e) How could we modify this program to randomly pick a month (1–12) or a dice roll (1–6)?

f) What do you think will happen if you remove the 
```js
+ startDay
``` 
part?
Try it and explain your observation.

__💡 Optional Challenge:__ Use an [if](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) or [switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch) statement to print the actual name of the day (e.g. Monday, Tuesday) instead of just the number.

Example:

```js
console.log("Your lucky day is: Friday!");
``` 


## 🧩 Exercise 2: Getting the File Extension
Group setup: Pairs or small groups of max. 3 students 

```js
const fileName = 2025_project_final_version;
const extension = fileName.split(".")[1];

// The `extension` variable should store the part of the file name after the dot.
// However, this code isn't working!
```
Now, answer the following questions:
1. Before running the code — what do you think will happen? Why might this code not work?

2. Run the program in Node. What error message do you get?

3. Why does this error occur? Is it what you expected What data type is `fileName`?

4. Update the expression for extension so that it gives the correct result. (__Hint:__ Think about what type of data `.split()` works on!)

5. Try your fixed code with different examples:
```js
"document.pdf"
"photo.jpeg"
"index.html"
```
## 🧩 Exercise 3: Coding Marathon Tracker

Group setup: Pairs or small groups of max. 3 students
```js
const totalSecondsCoded = 9365; // total time spent coding in seconds

const remainingSeconds = totalSecondsCoded % 60;
const totalMinutes = (totalSecondsCoded - remainingSeconds) / 60;

const remainingMinutes = totalMinutes % 60;
const totalHours = (totalMinutes - remainingMinutes) / 60;

const codingTimeFormatted = `${totalHours}h ${remainingMinutes}m ${remainingSeconds}s`;
console.log(codingTimeFormatted);
```
Now, answer the following questions:

1. How many variable declarations are there in this program?
2. How many function calls are there? Which function(s) are called?
3. Using [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#remainder) on the modulo operator,
explain what the expression below represents.
```js
totalSecondsCoded % 60
```
4. Interpret this line:
```js
const totalMinutes = (totalSecondsCoded - remainingSeconds) / 60;
```
What is this expression doing, and why is it necessary?

5. What do you think the variable `codingTimeFormatted` represents?
Can you think of a clearer or more descriptive variable name?

6. Try experimenting with different values of totalSecondsCoded. Will this code still work for very small numbers (like 45) or very large numbers (like 100000)? Explain why or why not.

__💡 Optional Challenge :__ Modify the program so that it also shows days when the total time exceeds 24 hours.
For example:
```js
1d 2h 30m 15s
```

## 💬 Independent Study & Support Time

After completing the group exercises, you can use the remaining time to:
- Ask questions to the volunteer coaches or facilitators.
- Collaborate and help each other with blockers.
- Continue working on their own module materials or unfinished tasks.

Coaches are available during this time to provide guidance, clarify concepts, and support

## Wrap up (last 20 min.)
You are done for the day. Take a moment to reflect on what you have learned and achieved.

Stand in a circle and share:
- your name 📛
- one thing you achieved today 💪🏽 
- the task you are going to work on next 👷🏾 
- one thing you need help with 🛟 
  
Give yourselves a round of applause. Now you have earned your rest. 

