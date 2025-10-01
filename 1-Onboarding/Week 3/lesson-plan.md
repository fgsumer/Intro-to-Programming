# Week 3 
## Topic 1 : Interview Introductions
- [ ] Tailor an introduction to job requirements
- [ ] Describe what makes an introduction engaging or boring
- [ ] Deliver an introduction out-loud

## Interview Introductions
Before starting this workshop, you should have reviewed the interview introductions prep item.

For this workshop you need to break up into groups of 3-4 students, each with at least one volunteer. We will be trying to make some sample introductions for Jane.

Jane is a fictional person who has completed a software development programme. Jane is applying for a Junior Software Developer role with the fictional company, Software for Lawyers Ltd. You don’t need to understand all of the technical terms in these two pieces of text to complete the task.

#### Introduce Jane (Group work)
1. Individually, write an introduction for Jane to be used for her interview with Software for Lawyers Ltd. You should be aiming for it to be 1-2 minutes long which is approximately 140-300 words. 

2. In your groups, take turns reading out your introductions for Jane. Give each other feedback. Everyone in the group should give feedback about every introduction. Try to put yourselves in the shoes of the hiring manager. Does their introduction give the impression that Jane is a perfect fit? If not why not? Was the introduction easy to follow? What differences are there between your introductions? Which ones make you want to work with Jane? Why? 

3. Each group picks one version of Jane’s intro (or a “best parts mashup”) to share with the whole class.

#### Jane’s summary
Jane has recently completed the part time Super Coders Software Development programme. During this time, she was also working full-time and caring for her two children. The course teaches full stack web development and general programming concepts. It teaches HTML, CSS, JavaScript, Node.js, Express, React and PostgreSQL.

Jane is very passionate about programming. She taught herself the Python programming language before starting the course.

Her portfolio includes many full stack applications. This includes projects she has built with other students, as well as some solo projects. She’s especially proud of a project called Pin the Mood. This project stores book recommendations until the user has time to read the books. The project used React, Express, Node.js and PostgresSQL. The project team was an agile team made up of two trainees, a scrum master and a tech lead.

After leaving school seven years ago, she joined Lawyers 4U as a call handler. She has developed excellent interpersonal skills and has gained experience working under pressure.

#### The Job Description
Software for Lawyers Ltd makes case management software. Their software helps lawyers manage caseloads and track time spent. The development team is small and close knit. They are looking to add a Junior Software Developer to their team.

#### Requirements
- A university degree in a relevant subject or a software development course
- Experience with Node.js, Express and React
- A strong portfolio with solo and group projects
- Excellent interpersonal skills
- Experience developing software in an agile team
- Passionate about programming
  
#### Nice to Haves
- Experience in the legal sector
- Some knowledge of Python
- Experience working in an office-based environment


## Topic 2 : Developer Tools
- [ ] Inspect the DOM
- [ ] Identify the values of design tokens in the CSS
- [ ] Alter the values of the CSS Variables using DevTools
- [ ] Select the Grid Badge in the Elements panel
- [ ] Use the Grid Editor to change layout
- [ ] Run a Lighthouse audit
- [ ] Identify and resolve the reported issues
- [ ] Find the MDN docs links in the Styles panel
- [ ] Ask ChatGPT to explain the Devtools explanation
- [ ] Find a different API using the same code
- [ ] Inspect the Accessibility Tree and compare it to the DOM


## 2.1 Inspect the DOM
### Explore
#### In groups of no more than 3. [Set a timer for 10 minutes](https://www.google.com/search?q=timer+for+10+minutes).

- Inspect [this page](https://cyf-workshop.netlify.app/devtools/) with Devtools.
- Write down the answers to these questions:
  - What is the name of the font used on the page?
  - What is the CSS variable that holds this value? (Hint: variables start with `--`, like, `--paper`)
  - What is the brand colour value (Hint: it’s set in a variable)?
  - What is the brand colour value used for in the page?
  - What variables hold CSS length data type values?
  

- When the timer goes off, share your answers with the other groups


So we’ve seen that fonts, colors, and spacing are often stored as CSS Variables, or custom properties. This allows them to be easily changed throughout a project by simply altering one value. Let’s experiment with this.

### Experiment
- [Set a class timer for 10 minutes](https://www.google.com/search?q=timer+for+10+minutes).
- Inspect the CSS of [the page](https://cyf-workshop.netlify.app/devtools/) with Devtools.
- Find the CSS Variables (hint: variables start with `--`, for example, `--paper`)
- Try changing the values of these variables and see how it affects the page.
- Some questions to answer. (Make a prediction about what you think will happen first, and then test it)
  - What will happen when you click the value of '--finger' and press up arrow ten times?
  - What will happen when you delete the value of `--copy`
  - What will happen when you change the value of '--space' to `red`?

### Reflection
- When the timer goes off, set a new timer for 10 minutes to share your answers with the other groups.

### 2.2 Grid Inspector
Next, let’s see how the page layout is handled. Modern websites use the CSS Grid for layout and you can manipulate grids with Devtools.

### Grid Editor
- [Set a class timer for 10 minutes.](https://www.google.com/search?q=timer+for+10+minutes)
- With Devtools, locate a grid element on [the same page.](https://cyf-workshop.netlify.app/devtools/).
- Activate the [Grid Badge](https://developer.chrome.com/docs/devtools/css/grid/) in the Elements panel.
- Use the Grid Editor to try changing the layout.
- When the timer goes off, one of the students or the coach can show/explain how to do it. 

### 2.3 Lighthouse
It’s important that software works and that people can use it. Lighthouse can help you write code correctly by pointing out your errors. But even better, it can teach you to fix the errors.

### Audit
- [Set a class timer for 10 minutes.](https://www.google.com/search?q=timer+for+10+minutes)
- Run a Lighthouse audit on [the same page.](https://cyf-workshop.netlify.app/devtools/)
- Look at the results and identify the issue.
- Now, how will you fix it? Click on the error. Lighthouse explains what is wrong and provides a link to a detailed explanation on why it’s wrong, how serious it is, and how to fix it!
- If you have time, fix the error, but in any case, once the timer goes off, paste the link to the detailed explanation page into the workshop thread in Slack.
- Go straight to the next challenge, after which we will spend some time discussing what we discovered.

### Hover for more
In fact Devtools is a great teacher. In the Styles panel, hover over any CSS property to get a quick definition of that property. Click ‘Learn More’ to go straight to the MDN page for that property.

If the explanation doesn’t make sense to you, ask ChatGPT (a generative AI) to explain it further.

>⚠️Plausible Hallucinations
Remember: Generative AIs are regularly confidently wrong; it can be helpful, but never trust it over Devtools. If something doesn’t make sense, or seems confusing or maybe wrong, it’s better to ask friendly humans in Slack.

### Explore and Explain
- [Set a class timer for 10 minutes.](https://www.google.com/search?q=timer+for+10+minutes)
- Select `<main>` in the Elements panel
- Hover over the ruleset attached to main in the Styles panel.
- Copy the Devtools explanation and ask ChatGPT to explain it, like this:
<details>
<summary> Please explain this to me like I'm a beginner learning HTML and CSS.</summary>

Determine a grid item’s size and location within the grid by contributing a line, a span, or nothing (automatic) to its grid placement. Shorthand for ‘grid-row-start’, ‘grid-column-start’, ‘grid-row-end’, and ‘grid-column-end’.
</details>


### 2.4 More (For the free study time)
Inspect web pages as you use the internet. Do this all the time! What font does Youtube use? What about [CSS Tricks](https://css-tricks.com/tag/devtools/)? [Hackernews](https://news.ycombinator.com/) is still using tables - what’s wrong with this?

Try changing the style and content of some websites. Make your favourite website bright pink. Make the BBC News page tell people about something great you did. Send a screenshot of something cool you changed to your Slack channel.

There are crash courses in Devtools all over [YouTube](https://www.youtube.com/watch?v=gTVpBbFWry8) and Udemy etc. Find a useful tip and share it in your class channel.

## Topic 3 
### Google Sheets SQL Showdown: Team Quiz
Welcome, spreadsheet warriors! Today, we’ll be putting your Google Sheets SQL knowledge to the test in a team quiz.
#### Requirements
 - __Quiz Leader:__ Sample questions are provided below, but you should set your own. Anyone: trainee or volunteer can take this role. Prepare your quiz questions and answers in advance.
 - __Timekeeper:__ Keep track of time for each round to ensure the quiz runs smoothly.
 - __Assemble Your Team:__ Get into groups of 3-4. Teamwork makes the dream work!
 - __Paper & Pen:__ Prepare to write queries and discuss strategies WITHOUT using a computer.
 - __Friendly Competition:__ Complete the challenge with a positive and collaborative spirit!

### The Challenge
This workshop will be divided into rounds, each presenting a Google Sheets SQL query. The scenarios will target various SQL functionalities available in Google Sheets.

You will write your answers on paper, not on a computer. Close your laptops. 

__Round 1: Getting Data:__ Practice using SELECT statements to find and get information from a sheet.

__Round 2: Conditional Queries:__ Let’s try something harder! Use WHERE clauses and conditional statements to filter data.

__Round 3: Advanced Arena:__ Challenge yourselves. Try using multiple conditions or advanced ways to filter data.

__Bonus Round (Optional):__ Feeling confident? The quiz leader may do an extra round with an example spreadsheet. Really pushing your problem-solving abilities.

### Let the Games Begin!
Remember, effective communication, teamwork, and friendly competition are the keys to success!

### SQL Team Quiz Example Questions
#### Round 1: Data Retrieval (10 minutes)
__Scenario:__ You’re working with a Google Sheet containing product information.

1. Write a query to select all product names and prices from the ‘Products’ sheet.
2. How can you change the query to only show products with a price greater than $50?

#### Round 2: Conditional Queries (10 minutes)
__Scenario:__ The Google Sheet also has a ‘Sales’ sheet that stores information about sales.

1. Write a query to get the product name and sales amount. Filter out sales where the quantity sold is greater than 10 AND the price is less than $100.
2. Update the query to show sales where the product category is ‘Electronics’ OR the cost is over than $500.

#### Round 3: Advanced Arena (10 minutes)
__Scenario:__ We have a ‘Customers’ sheet, containing customer names and their sale history.

1. Write a query to find all customers whose names start with ‘A’ and have made a sale in the last 30 days.
2. How can you change the query to show the top 5 customers by total sale amount, in descending order?

#### Bonus Round: Real-World Scenario
__Scenario:__ The marketing team wants to identify top customers for a targeted campaign.

1. Write a query to find customers who have:
   1. Made over 3 purchases
   2. Have a total spend of over $1000
   3. Whose last buy was within the last 60 days.
   



## Topic 4 
### Know Your Computer
“Know Your Computer” focuses on how to perform regular tasks on your computer. In this workshop you will use basic Linux commands in the terminal. The goal is to reduce your fear of using the terminal. 

### Tasks
You must use the terminal and Linux commands to complete each challenge. You must not use your GUI! Hands off the mouse!

1. Create a folder called `my-shopping` inside your Documents folder
2. Create a file called `my-list.txt` inside `my-shopping` folder.
3. Write the following items to `my-list.txt` file:
   1. Tea
   2. Pasta
   3. Coffee
   4. Milk
4. Create a new folder called `my-new-shopping` inside your Documents folder.
5. Now move `my-list.txt` from your `my-shopping` folder to your `my-new-shopping` folder. Your `my-shopping` folder should be empty after this step.
6. Copy `my-list.txt` from your `my-new-shopping` folder back to your `my-shopping` folder. After this step, both folders should contain a file called `my-list.txt`.
7. Now add the following line to `my-list.txt` file that is inside `my-new-shopping` folder:
   1. Sugar 
8. Display the content of `my-list.txt` file inside `my-shopping` and the one inside `my-new-shopping`. `my-list.txt` file in `my-shopping` folder must have 4 items while the one inside `my-new-shopping` folder must have 5 items.

### Resources
To help with this here are resources you can refer to: [freecodecamp.com](https://www.freecodecamp.org/news/the-linux-commands-handbook/), [Guru99](https://www.guru99.com/linux-commands-cheat-sheet.html)


## Wrap up (last 20 min.)
You are done for the day. Take a moment to reflect on what you have learned and achieved.

Stand in a circle and share:
- your name 📛
- one thing you achieved today 💪🏽 
- the task you are going to work on next 👷🏾 
- one thing you need help with 🛟 
  
Give yourselves a round of applause. Now you have earned your rest. 
