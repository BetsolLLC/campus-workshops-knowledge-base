
## What is Version Control?
Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. So ideally, we can place any file in the computer on version control.

Here’s Why:

A Version Control System (VCS) allows you to revert files back to a previous state, revert the entire project back to a previous state, review changes made over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more. Using a VCS also means that if you screw things up or lose files, you can generally recover easily.

## What is Git?

Git is a version-control system for tracking changes in computer files and coordinating work on those files among multiple people. Git is a Distributed Version Control System. So Git does not necessarily rely on a central server to store all the versions of a project’s files. Instead, every user “clones” a copy of a repository (a collection of files) and has the full history of the project on their own hard drive. This clone has all of the metadata of the original while the original itself is stored on a self-hosted server or a third-party hosting service like GitHub.

## Difference between Git and GitHub


Git and GitHub are two different things. Git is the version control system, while GitHub is a service for hosting Git repos that helps people collaborate on writing software. 

## Understanding Sections of a Git Project


What is a Repository?
A repository a.k.a. repo is nothing but a collection of source code.

![WorkFlow of Git](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)

A Git project will have the following main sections:
1.	The Git directory is where Git stores everything it needs to accurately track the project. This includes metadata and an object database which includes compressed versions of the project files.

2.	The working directory is where a user makes local changes to a project. The working directory pulls the project’s files from the Git directory’s object database and places them on the user’s local machine.
If you consider a file in your Working Directory, it can be in three possible state.
•	It can be staged. This means the files with the updated changes are marked to be committed to the local repository but not yet committed.
•	It can be modified. This means the files with the updated changes are not yet stored in the local repository.
•	It can be committed. This means that the changes you made to your file are safely stored in the local repository.


3.	 The staging area is a file (also called the “index”, “stage”, or “cache”) that stores information about what will go into your next commit. A commit is when you tell Git to save these staged changes. Git takes a snapshot of the files as they are and permanently stores that snapshot in the Git directory.

## How to push a repository to GitHub
I will divide this section into steps to help you understand the process more clearly.

### Step 1 – Create a GitHub account
To be able to use GitHub, you will have to create an account first. You can do that on the website:
[http://github.com/](http://github.com/)

### Step 2 – Fork the repository
Click on the Fork button ![fork](https://user-images.githubusercontent.com/55580805/161741123-02a2fd74-1c33-409b-8c58-8265c7fa3812.png)
to copy the repository to your account. This will be essential for deployment to heroku. 

### Step 3 – Cloning a Git Repo:
Locate to the directory you want to clone the repo: 
[https://github.com/orgs/BetsolLLC/repositories](https://github.com/orgs/BetsolLLC/repositories)

Copy the link of the repository you want and enter the following: 

![1](https://user-images.githubusercontent.com/55580805/161741917-74ace543-00f5-4310-b00f-78d41d87eb76.png)

### Step 4 – Add and commit file(s)
When we first initialized our project, the file was not being tracked by Git. To do that, we use this command git add. The period or dot that comes after add means all the files that exist in the repository. If you want to add a specific file, maybe one named about.txt, you use git add about.txt.

### Add files to the Staging Area for commit:

![1](https://user-images.githubusercontent.com/55580805/161742880-ccefb38f-cbde-48b1-96ce-e038267295e5.png)

![2](https://user-images.githubusercontent.com/55580805/161742987-c25432f1-d99e-4717-bc2d-5a1ef0efa156.png)



The next state for a file after the staged state is the committed state. 
The first part of the command git commit tells Git that all the files staged are ready to be committed so it is time to take a snapshot. The second part -m "first commit" is the commit message. -m is shorthand for message while the text inside the parenthesis is the commit message.

### Commit Changes you made to your Git Repo:
Now to commit files you added to your git repo:

![3](https://user-images.githubusercontent.com/55580805/161743180-cb292d53-c76e-4391-b567-8e71189fcea7.png)


The git push command pushes the changes in your local repository up to the remote repository you specified as the origin.

![4](https://user-images.githubusercontent.com/55580805/161743316-2419e131-5d51-4fd0-95d3-b88f4e353939.png)

### Revert back to the last committed version to the Git Repo:
Now you can choose to revert back to the last committed version by entering:

![5](https://user-images.githubusercontent.com/55580805/161743450-71f350c2-ba4c-4b07-98ad-7bafaf468234.png)

![6](https://user-images.githubusercontent.com/55580805/161743659-29ac0941-f870-4e3e-948c-d05bc7a36fdb.png)

## How to Pull a Repository in Git

To pull in Git means to clone a remote repository's current state into your computer/repository. This comes in handy when you want to work on your repo from a different computer or when you are contributing to an open-source project online.

To test this, don't worry about switching to a new computer. Just run ![7](https://user-images.githubusercontent.com/55580805/161744997-638ea600-251a-4cd7-b087-f43802ca4d44.png)   to leave the current directory and go back one step. 

To make sure those changes are reflected on my local copy of the repo:

![8](https://user-images.githubusercontent.com/55580805/161745783-168f613f-334a-48e0-8ba5-dbc511153c54.png)

Here are two more useful git commands:

![9](https://user-images.githubusercontent.com/55580805/161745854-b2a97232-19e7-4f65-b4b6-ec230cc272dc.png)

In the simplest terms, git fetch followed by a git merge equals a git pull. But then why do these exist?

When you use git pull, Git tries to automatically do your work for us. **It is context-sensitive**, so Git will merge any pulled commits into the branch you are currently working in. git pull **automatically merges the commits without letting you review them first.**

When you git fetch, Git gathers any commits from the target branch that do not exist in your current branch and **stores them in your local repository.** However, **it does not merge them with your current branch.** This is particularly useful if you need to keep your repository up to date but are working on something that might break if you update your files. To integrate the commits into your master branch, you use git merge.



## Additional Reading: 

Before we commit let’s see what files are staged:

![10](https://user-images.githubusercontent.com/55580805/161745978-b0029d08-b6a4-4491-a0e8-20ff73cdbc6e.png)

### See the Changes you made to your file:

Once you start making changes on your files and you save them, the file won’t match the last version that was committed to git. To see the changes, you just made:

![11](https://user-images.githubusercontent.com/55580805/161746124-0bca8e90-fae1-4d3b-bcc4-675c605e631b.png)

### View Commit History:

You can use the git log command to see the history of commits you made to your files:

![12](https://user-images.githubusercontent.com/55580805/161746226-40347302-df63-4a64-9044-ebbdd974c426.png)

### Uncommit Changes you just made to your Git Repo:

Now suppose you just made some error in your code or placed an unwanted file inside the repository, you can unstage the files you just added using:

![13](https://user-images.githubusercontent.com/55580805/161746356-1bb272c6-0d3c-44d6-ac8f-62746c81827b.png)


### Add a remote origin and Push:

Now each time you make changes in your files and save it, it won’t be automatically updated on GitHub. All the changes we made in the file are updated in the local repository. Now to update the changes to the master:

![14](https://user-images.githubusercontent.com/55580805/161746516-009d81e6-23e6-44a7-a84e-c2659e6c703d.png)

The git remote command lets you create, view, and delete connections to other repositories.

![15](https://user-images.githubusercontent.com/55580805/161746664-297d4469-4baa-4359-bc8e-7deda7659e78.png)

The git remote -v command lists the URLs of the remote connections you have to other repositories.


### Git Ignore:

![16](https://user-images.githubusercontent.com/55580805/161747173-cb9a8135-4ec4-4b6c-9063-61d79b1fcf1c.png)

It tells git which files (or patterns) it should ignore. It's usually used to avoid committing transient files from your working directory that aren't useful to other collaborators, such as compilation products, temporary files IDEs create, etc.

## How to Use Branches in Git

With branches, we can create a copy of a file we would like to work on without messing up the original copy. We can either merge these changes to the original copy or just let the branch remain independent. Visual representation of our repo

![17](https://user-images.githubusercontent.com/55580805/161747249-d9aa37da-9f44-4da4-9ee6-788994f740cd.png)

At this point, I want to add more tasks to the list but I am not yet sure whether I want them on my main list. So, I will create a new branch called ‘test’ to see what my list would look like with more tasks included.

### To create a new branch, run this command: 

![18](https://user-images.githubusercontent.com/55580805/161747325-e6b14336-1cb5-4e25-8a94-c89bd6b4de66.png)

‘checkout’ tells Git it is supposed to switch to a new branch. ‘-b’ tells Git to create a new branch. ‘test’ is the name of the branch to be created.


Now that we have a new branch created, this is what our repo will look like:

![19](https://user-images.githubusercontent.com/55580805/161747386-4dc35e3a-cfe0-488c-90d0-0029c9ff0676.png)

To merge the new state to the main branch, we should first stage and commit this branch.

After committing the test branch, switch back to the main branch by running this command: 

![20](https://user-images.githubusercontent.com/55580805/161747451-b79b3890-2086-4c76-90bb-dcf3186678bc.png)

At this point, you will see all the changes made in the test branch reflected on the main branch.

![21](https://user-images.githubusercontent.com/55580805/161747892-8f7f9aa0-7c8f-4e68-bb04-ff423241f161.png)

The test branch will not be pushed. It will only remain in your local repo. If you would like to push your test branch, switch to the branch using

![22](https://user-images.githubusercontent.com/55580805/161748339-322d3d1a-bb54-4e9b-adf7-f5d49f1150c6.png)

then run  ![23](https://user-images.githubusercontent.com/55580805/161748547-9bc672cf-8cad-45d2-bc3c-c48127fe559c.png)











