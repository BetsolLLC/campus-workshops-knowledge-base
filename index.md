# Betsol Campus Workshop 
## What we will cover in this workshop?
We will build a simple To-do app and deploy it on a popular cloud platform. In order to demonstrate full stack application development we will cover how to build a backend API, setup a database and build a frontend using popular languages like Python, SQL and JavaScript. To top it off we will be deploying the full application on Heroku to expose your application on the internet.

### Full Stack Technologies that you will learn
- **Flask** a light-weight Python framework will be used to build a RESTful API which will serve as the backend
- **ReactJS** as JavaScript framework will be used to build the frontend UI application
- **PostgreSQL** as a database engine managed by pgAdmin a Database Management System (DBMS).
- **Heroku** a Platform-as-a-Service cloud platform to realise our full stack application as a whole.

## Pre-requisites for the workshop 
### Cloud Accounts
1. GitHub Account [SignUp](https://github.com/signup)
2. Heroku Account [SignUp](https://signup.heroku.com/)

### Installables on your PC
4. Heroku CLI [Installation](https://devcenter.heroku.com/articles/heroku-cli)
5. pgAdmin [Download Page](https://www.pgadmin.org/download/)
6. Python 
7. NodeJS and NPM

##  Installation And Setup Of Git
1. Go to: Git [Link](git-scm.com).
2. Click on the `Downloads`
3. Click on the OS you're using. (eg. `Windows`)
4. Click on `Click here to download`
5. Find the download location
6. Start installation 
-- While choosing your editor, select your preferred IDE and click next. 
-- Feel Free to install any other options than the selected default options. 
7. On Installation, select Launch Git Bash option and click on Finish. 

**Note:** Installation steps may differ per operating system.  

## Getting started with the Workshop
### Connect to GitHub and clone the repository with reference material
1. Login to GitHub
2. Navigate to the repository with the reference material for this workshop -> [BetsolLLC/campus-workshops-knowledge-base](https://github.com/BetsolLLC/campus-workshops-knowledge-base)
3. Fork the repository using https://github.com/BetsolLLC/campus-workshops-knowledge-base 
   ,Click on the Fork button fork to copy the repository to your account. 
   ![image](https://user-images.githubusercontent.com/47311332/166196562-a6e4d5d0-6a35-42b0-9b52-0da6a5ee07d3.png)
3. Goto your account and you can find the copy of your repository and click on the campus-workshops-knowledge-base
    ![image](https://user-images.githubusercontent.com/47311332/166196241-7a3567ed-a0a7-4206-a1b4-57ae035d25f1.png)
    ![image](https://user-images.githubusercontent.com/47311332/166196306-580ec304-5ff9-42ef-b097-8586ebb8882c.png)
4. Click on the code and copy the link present in it.
    ![image](https://user-images.githubusercontent.com/47311332/166196490-b4774fb0-3125-48c0-949b-9c8896862561.png)

### About this repository [BetsolLLC/campus-workshops-knowledge-base](https://github.com/BetsolLLC/campus-workshops-knowledge-base)
**This repository contains all the relevant guides and reference material you need to complete this Workshop.**
**It is important that you have forked the `BetsolLLC/campus-workshops-knowledge-base` repository into your GitHub Account before cloning it into you PC's local repository.**


### Configure Personal Access Token
**Note : If you are using git with your Github account for the first time then you can [click here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) , which details the steps to configure your git settings so that you can start pulling and pushing data to your remote repository**

### Clone Repo locally
1. Open the Git Bash in your prefered working directory.
2. Setup your local git config to contribute with your name and email (it is important that the email matches with the email used to signup with GitHub)
```
git config --global user.name "Firstname Lastname"
git config --global user.email "your_email@youremail.com"
```
3. Create a directory called `to-do-app` and change the working directory to it
```
mkdir to-do-app 
cd to-do-app 
```
4. Using the `git clone` command clone the repository
```
git clone <copied-repo-link> 
 ```
    4.1 If you face any SSL issues in this step 4. run the following command and run step 4. again before continuing to step 5. 
    ```
    git config http.sslVerify "false" 
    ```
5. Verify that you have a folder called `campus-workshops-knowledge-base/` (You may use `ls` command on Linux, macOS and `dir` command on Windows)
6. Change directory into the folder
```
cd campus-workshops-knowledge-base/ 
```

### Add your first commit
1. Edit the `README.md` file using any text editor.
2. To check the status of your changes to the repository: 
``` 
git status 
```
3. To stage your changes to the staging area using the `git add` command
```
git add .
```
or add only the changed `README.md` 
```
git add README.md
```
4. Now, the status of the staged files can be checked again using the `git status` command.
5. Commit files in Git: The next state for a file after the staged state is the committed state. 
```
git commit -m "First commit" 
#The message in the " " is given so that the other users can read the message and see what changes you made 
```
3. The git push command pushes the changes in your local repository up to the remote repository you specified as the origin. 
```
git push -u origin main #pushes changes to origin 
```
**NOTE: Each time you make changes that you want to be reflected on GitHub, the following are the most common flow of commands:** 
```
  git add . 
  git status #Lists all new or modified files to be committed 
  git commit -m "Second commit" 
  git push -u origin master 
```  
### Using Branches  
- To check for all the branches in you project type 
```
  git branch 
```
- To create a new branch, use the following command 
```
git checkout -b branchname 
```
- To Switch between the branches, use the following command 
```
  git checkout branchnameyouwanttoswichto   
```
