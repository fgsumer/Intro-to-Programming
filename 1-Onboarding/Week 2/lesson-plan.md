# Week 2 
## Topic 1 : Group discussion: Working with others 
We’re all here to learn and grow. Our goals are to become self-sufficient - able to do our own work, and get help when we need it.

We’re part of a community. We help each other, but we’re also each trying to learn for ourselves.

Below are a number of scenarios. Have a group discussion about each scenario. What do you think is good and bad about how people are working? What should they do differently? Why?

Spend 5 minutes ⏱ on each scenario.

1. Working together in a group on a piece of coursework
Amira, Babak, and Charlie are on a call together talking through how to approach a problem.

    They each write their own code on their own laptops, but Babak doesn’t think he could solve it on his own. If he deleted his code, and tried to solve it again after the call, he isn’t confident he would be successful. But he’s really eager to complete the sprint and move on to the next topic.

<details>
<summary> Facilitation hints </summary>

- Understanding is more important than speed.
- Deleting and re-trying exercises is a good test of understanding.
- Working together is good, but everyone needs to leave with understanding.
</details>


2. Watching someone solve Codewars exercises
Amira, Babak, and Charlie have a call every week where they watch Charlie solve Codewars exercises.
This is good practice for Charlie. And Amira and Babak find it useful to see how Charlie solves the problems.

<details>
<summary> Facilitation hints </summary>

 - Working together is good.
 - Seeing how other people solve problems can be interesting.
 - Taking turns is better than always being in the same roles.
 - Everyone can learn from each other.
</details>

3. Asking ChatGPT to solve a problem and copy+pasting the answer. 
    
    Dara is trying to do a piece of coursework, but isn’t sure what code to write. They ask ChatGPT to solve the problem, and copy+paste the solution into a pull request.

    Dara is pretty sure they understand the code, but isn’t sure they could write it again from scratch if they needed to.

<details>
<summary> Facilitation hints </summary>

- Deleting and re-trying exercises is a good test of understanding.
- Submitting copy+pasted code is a waste of volunteer time - people spend time reviewing it.
- No one will hire you just to copy+paste from ChatGPT. You need understanding.
- The point of coursework isn’t for you to complete it, it’s for you to learn by doing it, even if that’s a struggle and takes time.

</details>

## Topic 2 : Consolidating Git
### Learning Objectives

- [ ] Save local changes to a repository in VSCode
- [ ] Stage local changes
- [ ] Commit changes to a local branch
- [ ] Define “pushing”
- [ ] Push local changes onto a remote repository


## A. Exploring GitHub repositories
### Recap activity 🕹️ 
### Pair work 

Visit the following repository on GitHub: https://github.com/HackYourFutureBelgium/demo-repo

Answer the following questions:

a) How many commits are there in the demo-repo project?

b) Who committed on Oct 31, 2020?

c) What changes did illictonion make in the commit titled “Revert changes accidentally pushed in the past”?

d) How many files were added in the first commit? What were the names of the files?

e) What is the hash for the first commit in the history?

f) What is Claire Bickley’s favourite food?

### Group discussion
A coach will need to facilitate this section.
A coach can facilitate this group discussion by going through the questions above and asking pairs for their feedback. If pairs are unsure / not quite accurate then spend a small amount of time addressing misconceptions. 

## B. Creating a fork, cloning a repository and creating a branch
### Recap activity 🕹️ 
### Pair work 

1. __On one person’s computer__, fork this repo: On one person’s computer, fork this repo: https://github.com/CodeYourFuture/cyf-demo-repo
2. Double-check the URL of your forked repo. How can you tell the fork was successfully created?
3. Before continuing, try answering the following:

    `❓ What is the difference between a fork and a clone?`
    
    Remember to check your answer before continuing.

4. Clone your fork of `demo-repo` to your local machine
5. Open this local repository using VSCode.
6. Use `pwd` in your terminal to check you’re in the right place.
7. create a local branch called `week-2-workshop`


## C. Committing and pushing
### Activity - Figure it out  🕹️ 
### Pair work 

1. Make a change to a file

    a) Open up your local repo `demo-repo` in VSCode.
    
    b) Go to the Explorer section of VSCode.
    
    c) Find `file.txt` and edit the file with the answer to the questions.
    
    d) Remember to save the changes to `file.txt`.

2. View the local changes
   
   a) Locate the Source Control tab in VSCode
![VS Code](/1-Onboarding/assests/explorer%20-%20vscode.png)

    b) Go to the Changes section and click on the file you changed - this should now show the changes for the file.

    c) Try editing the file again in the Explorer tab and check to see the update is visible in the Source Control panel

3. Stage the changes

We need to tell Git which changes we want to be part of our commit. When making a commit, we can decide to not include all of our changes, but just include some of them. We choose which changes we want to include in a commit by `staging` our changes.

a) In the Source Control tab again, go to the file `file.txt` and click on the `+`.
b) View the Staged Changes area in your Source Control panel. 

4. Create the commit

Once we’ve staged our changes, then we can commit these changes. Before we do, we should make sure we’re on the correct branch. Check that you’re on the `week-2-workshop` branch.

Your VSCode window should look like this:
![VS Code](/1-Onboarding/assests/check-current-branch-week-1-workshop.png)

and not like this:
![VS Code](/1-Onboarding/assests/check-current-branch-is-main.png)


If you’re sure you’re on the right branch:

a) Enter a commit message describing briefly what you did in your commit

b) Click `Commit` to create the Git commit.



5. After you've committed your work locally, you now have a local branch called `week-2-workshop` that contains all your work. This branch exists only on your computer for now.

    Your local repository now has:
   - main (default branch)
   - `week-2-workshop` (your working branch)

    But your remote fork on GitHub still only has `main`. This means your `week-2-workshop` branch hasn't been sent __"pushed"__ to GitHub yet.

    a) Make sure your current branch is `week-2-workshop`
    
    b) In VS Code look for the option to push your branch
    
    c) Go to your GitHub fork and figure out how to check the `week-2-workshop` branch is on the remote fork.

6. In your pair, discuss the following questions/tasks:

    a) What is a commit? 

    b) Explain why we need to make commits when we’re developing a project.
    
    c) Explain why we store repositories on GitHub.
    
    d) Describe the purpose of VSCode.
    
    e) Explain the difference between Git and GitHub.
    
    f) Explain why developers use branches.
    
    g) Explain the difference between a fork and a clone.
    
    h) What does the branch name `origin/main` mean instead of just `main` ?

### Group discussion
A coach will need to facilitate this section.
A coach can facilitate this group discussion by going through the questions above and asking pairs for their feedback. If pairs are unsure / not quite accurate then spend a small amount of time addressing misconceptions. 


## Topic 3 : Mentored code review
### Learning Objectives

- [ ] Explain what a code reviewer is looking for in a PR.
- [ ] Describe elements of the GitHub code review interface.
- [ ] List ways someone writing code can make it easier to review.
  
Our learners get feedback on their work through code review. At work, colleagues review each others code to understand code, look for problems, and both share and learn better ways of doing things.
At HYF every learner should get code review on their work every week.

### 🕹️Live Code Review
The coach will review a few pull requests of learners or any other example, and talk out loud about what they’re looking for and doing.
The learner(s) will ask questions as they do.

<details>
<summary> Hints and tips </summary>

- How did you understand what the goal of the PR is? 
- Reading the title and description, looking at the coursework exercises, etc.
- The uses of the different tabs in a PR: Conversation, Commits, Files changed.
- What made a PR easy or hard to review? 
- Where unrelated files/lines changed?
- Was code consistently formatted? Did indentation help or hurt understanding?
- How did you review the code? Did you read top-to-bottom? Did you jump around into and out-of functions? Did you look at tests? 
- Did you clone the code locally and try running it?
</details>



## Topic 4 : Structuring a feedback form
#### Pair or group work 
- Start by forking [the repository](https://github.com/HackYourFutureBelgium/Challenge-Feedback-form?tab=readme-ov-file) to your own GitHub account.
- All instructions and requirements are explained in the `README.md` file. Take your time to read it thoroughly before you begin.
- Use clear and descriptive commit messages to explain what you did and why.
- Once you're done, open a pull request from your fork’s main branch back to the original repository
- Share your pull request with a colleague and ask them to review it.
