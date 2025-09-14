# Preparation
## 1. Install VSCode
#### Learning Objectives
- [ ] Download and install VSCode
- [ ] Identify the key parts of the VSCode interface

We use VS Code to write all of our code in the course. It is known as an Integrated Development Environment (IDE) and really helps you write great code.

[🔗 Download and install VSCode now](https://code.visualstudio.com/)


🎥 [Watch this short overview of Visual Studio Code](https://www.youtube.com/watch?v=B-s71n0dHUk&t=4s)

## 2. Check Git
#### Learning Objectives
- [ ] Double check Git is installed on your local machine


You will use Git continually as a developer. We will cover Git in more depth later in the course. Right now, we will just check that you have it installed.

Open up a terminal and run the command `git --version` to double check you have Git installed. If it is installed successfully, you should get a version number (which may not be exactly the same as this example, but should look similar):
```
git version 2.40.0
```
Otherwise, you will need to install it or ask for support on your Slack channel.

## 3. Create a work folder (HYF)
#### Learning Objectives
- [ ] Navigate and manipulate the file system using a terminal
- [ ] Create a named directory to store your work over the course

__📢 Important :__ Make a folder called HYF in your home directory. Store all your work for the course in this folder.

You’ll need to create a HYF folder to store your projects on the course. You can do this any way you like, but here we are using the terminal.

### How to create a folder using the terminal
1. Open a terminal on your computer.

    For each of the steps below, you’ll need to use the command line in your terminal.

    Use this [cli documentation](https://www.techrepublic.com/article/16-terminal-commands-every-user-should-know/) to remember terminal commands.

2. In your terminal, print your current working directory.
3. List the files and folders in your current working directory.

    You’ll need a place to store your work for the course.

4. Make a new directory called HYF in your home directory.
5. Change directory into the HYF directory.
6. Double check you’re in the right place by printing your current working directory.


## 4. Version Control 
#### Learning Objectives
- [ ] Define a repository
- [ ] Define a commit
- [ ] Explain the purpose of version control software


Version control, also known as source control, is the practice of tracking and managing changes to software code. Version control systems are software tools that help software teams manage changes to source code over time. Version control software keeps track of every modification to the code in a special kind of database. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members.

```
📖definition: Git is version control software that allows developers to create and manage different versions of a project.
`````

In Git, we create different versions of a project over time by creating commits.

A __commit__ is a snapshot of our project at a particular point in time. You can also think of a commit as a particular version of a project.

Commits store the following information:
  - what changed in this commit
  - who created the change
  - what time the change happened
  - what the previous commit was

A typical timeline of commits might look like this:
![Commit History](/1-Onboarding/assests/commit-history.png)

Commits also have a hash associated with them. A hash is a long string of characters used to identify a particular commit.

A typical hash will look like this: `fec6909d6de23c75e77960986a9b6a7aee7feec7` but you will often see them abbreviated to the first few characters like this: `fec6909`

## 5. Version History 
#### Learning Objectives
- [ ] Identify the number of commits on the main branch of a remote repository
- [ ] Identify the author, time and message of a given commit on GitHub


To share a project and its history, we can use an online platform called GitHub. GitHub is a platform where teams can store projects along with a history of their different versions. By storing projects on GitHub, multiple users can gain access to the history of a project.

`✍️Exercise`

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

`✍️Exercise`

Go to the following link: https://github.com/CodeYourFuture/education-blog/commits/main

Try answering the following questions:

Go to the commit that says “add test p element to index page”

Questions

- How many files were changed in this commit?
- Who created the change?
- What time did the change take place?

`✍️Exercise`

Go to the following link: https://github.com/CodeYourFuture/education-blog/commits/main and locate commit that says “remove \ and # from start of paragraph”

Questions

- How many files were changed in this commit?
- What change was made in this commit?

## 6. Inspecting a commit

#### Learning Objectives

- [ ] Given a remote repository on GitHub, identify the files and folders from any commit in a version timeline

Recall that a commit is a snapshot of our project at some point in time. Therefore, we should be able to check out a previous version of our project and look at the files and folders there. We can use the Github interface to check out the files and folders at a previous commit.

`✍️exercise`

Go back to this page https://github.com/CodeYourFuture/education-blog/commits/main

- Locate the the commit with hash `4e78b32` and then look for the icon that that says  `“Browse the repository at this point in the history”`. Explore the code at this point in the history. What differences do you notice?
- Do the same for the commit `cd981a0`

## 6. Inspecting previous versions

#### Learning Objectives

- [ ] Use a Git history to view previous versions of a project
- [ ] Find the commit that corresponds to a particular version of a project

We can view the different commits of a project on Github. This means we can see what the website looked like before, in previous versions.

`✍️exercise`
Here are some different versions of the same educational backlog.

Deployed [version A](https://git-demo-week1-version-a.netlify.app/) educational blog

Deployed [version B](https://git-demo-week1-version-b.netlify.app/) educational blog

Deployed [version C](https://git-demo-week1-version-c.netlify.app/) educational blog

Questions

- What is the difference between Version A and Version B on the index page (the page you first land on after clicking on the link)
- What is the difference between Version C and the main version of the site.
- Which commit from the education-blog repo correspond to Version C? Remember to check the git history.
- Which commit from the education-blog repo correspond to Version A?


## 7. Forking a repository

#### Learning Objectives

- [ ] Create a fork of a repository
  




## 8. Working Locally

#### Learning Objectives

- [ ] Clone a remote repository from GitHub into a local folder
- [ ] Define the terms ‘remote’ and ’local’ in the context of GitHub



## 9. Viewing files from a git clone

#### Learning Objectives

- [ ] Clone a remote repository from GitHub into a local folder
- [ ] Define the terms ‘remote’ and ’local’ in the context of GitHub



## 10. Branching

#### Learning Objectives



## 11. Wrapping up Git

#### Learning Objectives

