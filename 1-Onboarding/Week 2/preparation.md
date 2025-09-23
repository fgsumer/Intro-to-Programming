# Preparation
## 1. Install VSCode
#### Learning Objectives
- [ ] Download and install VSCode
- [ ] Identify the key parts of the VSCode interface


## 2. Check Git
#### Learning Objectives
- [ ] Double check Git is installed on your local machine



## 3. Create a work folder (HYF)
#### Learning Objectives
- [ ] Navigate and manipulate the file system using a terminal
- [ ] Create a named directory to store your work over the course



## 4. Version Control 
#### Learning Objectives
- [ ] Define a repository
- [ ] Define a commit
- [ ] Explain the purpose of version control software




## 5. Version History 
#### Learning Objectives
- [ ] Identify the number of commits on the main branch of a remote repository
- [ ] Identify the author, time and message of a given commit on GitHub


To share a project and its history, we can use an online platform called GitHub. GitHub is a platform where teams can store projects along with a history of their different versions. By storing projects on GitHub, multiple users can gain access to the history of a project.

`✍️ Exercise`

In this exercise, you’ll need to explore a GitHub repository You’ll need to look around and figure out where to find different files and find out information about them.

⚠️ You won’t be expected to know what the files do at this stage.

Go to the following link: https://github.com/CodeYourFuture/education-blog

It will take you to a GitHub repository called education-blog.

Answer the following questions using the page linked to above:
- View the README.md file. What do the instructions tell you
- How many files are there inside the blogs folder?
- How many lines are there in the package.json file? 
- Find the file with the blog content you can see on the live site here [blog 1](https://git-demo-week1.netlify.app/blogs/1/)

You’ll learn more about these type of files throughout the course.

`✍️ Exercise`

Go to the following link: https://github.com/CodeYourFuture/education-blog/commits/main

Try answering the following questions:

Go to the commit that says “add test p element to index page”

Questions

- How many files were changed in this commit?
- Who created the change?
- What time did the change take place?

`✍️ Exercise`

Go to the following link: https://github.com/CodeYourFuture/education-blog/commits/main and locate commit that says “remove \ and # from start of paragraph”

Questions

- How many files were changed in this commit?
- What change was made in this commit?

## 6. Inspecting a commit

#### Learning Objectives

- [ ] Given a remote repository on GitHub, identify the files and folders from any commit in a version timeline

Recall that a commit is a snapshot of our project at some point in time. Therefore, we should be able to check out a previous version of our project and look at the files and folders there. We can use the Github interface to check out the files and folders at a previous commit.

`✍️ Exercise`

Go back to this page https://github.com/CodeYourFuture/education-blog/commits/main

- Locate the the commit with hash `4e78b32` and then look for the icon that that says  `“Browse the repository at this point in the history”`. Explore the code at this point in the history. What differences do you notice?
- Do the same for the commit `cd981a0`

## 7. Inspecting previous versions

#### Learning Objectives

- [ ] Use a Git history to view previous versions of a project
- [ ] Find the commit that corresponds to a particular version of a project

We can view the different commits of a project on Github. This means we can see what the website looked like before, in previous versions.

`✍️ Exercise`
Here are some different versions of the same educational backlog.

Deployed [version A](https://git-demo-week1-version-a.netlify.app/) educational blog

Deployed [version B](https://git-demo-week1-version-b.netlify.app/) educational blog

Deployed [version C](https://git-demo-week1-version-c.netlify.app/) educational blog

Questions

- What is the difference between Version A and Version B on the index page (the page you first land on after clicking on the link)
- What is the difference between Version C and the main version of the site.
- Which commit from the education-blog repo correspond to Version C? Remember to check the git history.
- Which commit from the education-blog repo correspond to Version A?


## 8. Forking a repository

#### Learning Objectives

- [ ] Create a fork of a repository
  
Forking a repository allows you to create your own copy of someone else’s repository. This is useful when you want to make changes to the project without affecting the original repository.

`✍️ Exercise`

- Navigate to the [octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife) repository, 
- In the top-right corner of the page, click Fork.
- By default, forks are named the same as their upstream repositories. Optionally, to further distinguish your fork, in the "Repository name" field, type a name.
- Optionally, in the "Description" field, type a description of your fork.
- Optionally, select Copy the DEFAULT branch only.
- Click Create fork.
- How can you check you successfully forked the original repository (Hint: Check the URL of your forked repository)


## 9. Working Locally

#### Learning Objectives

- [ ] Clone a remote repository from GitHub into a local folder
- [ ] Define the terms ‘remote’ and ’local’ in the context of GitHub

When you fork the Spoon-Knife repository on GitHub, you create a copy of it on your GitHub account.
This version on GitHub is called your remote repository — because it's stored on the internet, not on your computer. But just forking it doesn’t mean you have the files on your own computer yet. To get the files onto your computer, you need to clone the repository.
This creates a local copy — which means the project now lives on your machine, and you can start working on it.

🎥 Follow through the steps in the video to fork your spoon-knife repository [“How to clone a repository from GitHub to Visual Studio Code”.](https://www.youtube.com/watch?v=ILJ4dfOL7zs&t=52s)

🎗️ Reminder:
- Use the URL for your fork of the spoon-knife repo when cloning
- When selecting the location to clone your files, choose the HYF folder you created in the module prep


## 10. Viewing files from a git clone

#### Learning Objectives

- [ ] Open a cloned repository in your IDE
- [ ] Explore the repository in your IDE
- [ ] Open the Integrated Terminal in VSCode

Once you’ve got a local copy of a codebase on your local machine you can start to view the files and folders in that codebase. You can use a code editor like VSCode.

VSCode is an application that enables developers to view and edit files on their local machine.

`✍️ Exercise`

Explore VSCode
- Figure out how to open the cloned repository on your local machine in VSCode.
- Explore the repository in VSCode and use the code editor to look at the various files and folders.
- Try opening the Integrated Terminal in your VSCode window.

🤔 If you get stuck on any of these exercises, it’s a good idea to search online. For example, you could Google “opening terminal in vscode”


## 11. Branching

#### Learning Objectives
- [ ] Explain why a git repository may have multiple branches
- [ ] Describe what’s special about the branch named main
- [ ] Create a new local branch in a git repository

We can check the commits on the remote repository as before:
![Commit History](/1-Onboarding/assests/commit-history-github.png)

On the left page of the page, we see additional information:
![Commit History](/1-Onboarding/assests/main-branch-highlighted.png)

So what is `main`?

`main` is a branch.

Commits form a sequence that look like this:
![Main Branch](/1-Onboarding/assests/mainbranch.png)

🌿 What Is a Branch?

📖 Definition:
A branch is a series of commits (saved changes) that represent a specific version or direction of the project.

A branch is like a separate line of development in your project — it shows the path of changes made over time.

You can create multiple branches with different names, each used for working on different ideas or features without affecting the main project.

🎨 Example:
![Branches](/1-Onboarding/assests/branches.png)
Let’s say you’re experimenting with the design of a website:

- On one branch, you try making the website more blue.
- On another branch, you try making it more purple.

These two branches might share some of the same commits (such as the original layout), but each one also has its own unique changes added on top.

This way, you can test ideas side by side, without interfering with the main version of your site.

The main branch is often treated as a special branch - it’s where we put commits which people working on the project have agreed on. Other branches (e.g. the experimental purple branch) may have extra changes that have not been agreed on. If people working on the project agree the changes from the purple branch are good, we’ll add those changes to the main branch.

When we’re working on something new, we haven’t agreed with other people that our new thing is good yet, so we often don’t add our changes to the main branch straight away. Instead we make our own branch to experiment on.

We can start to create independent branches like this: 
![coursework branch](/1-Onboarding/assests/coursework-branch.png)
In the diagram above, we can continue to commit on the “week-1-coursework” branch without altering the history of the main branch.

`✍️ Exercise` 

Creating a local branch: Open the your spoon-knife repository in VSCode.

Using [this clip](https://youtube.com/clip/UgkxvXsnm_98Rx0NUZq25apQWA6POccRoQzw), create a new branch called `update spoon-knife` in your local repository 👉 

📋 How can you check that you’ve successfully created a branch?

## 12. Wrapping up Git

#### Learning Objectives

- [ ] Commit changes to a local git branch

Now you’ll need to create a commit.
- Try opening your clone of your Spoon-Knife repo in VSCode
- Make sure you’re on the `main` branch
- Make a new branch for your changes
- Add/update something in the README.md file
- You can use the [“How to commit changes and push them in Visual Studio Code”](https://www.youtube.com/watch?v=B8RSMBSzFuA&t=2s) video to figure out how to create a commit.



📚 Double check the learning objectives for this preparation. If there are any parts you're still struggling with, make a note and take some time to search for extra resources (videos, articles, examples) to support your learning.

Now you are ready to continue with [Coursework the week](/1-Onboarding/Week%201/homework.md)