# Betsol Campus Workshop 
## WHAT WILL WE BE LEARNING IN THE WORKSHOP? 
We'll build a simple To-do app and deploy the database and backend on the cloud. We'll be using Python & Flask framework to build the backend, React JS to build the frontend, PostgreSQL for the database and finally Heroku to deploy our finished database and backend on the cloud. 

### PREREQUISITES FOR THE WORKSHOP 
1. GitHub 
2. Heroku Account and Heroku CLI
3. pgadmin
4. Python 
5. NodeJS and NPM 

### INSTALLATION AND SETUP OF GIT 
1. Go to: Git [Link](git-scm.com).
2. Click on the Download option on the bottom left.
3. Start installation 
- While choosing your editor, select your preferred IDE and click next. 
- Feel Free to install any other options than the selected default options. 
4. On Installation, select Launch Git Bash option and click on Finish. 

### CONNECTING TO GITHUB AND CLONING THE APPLICATION DIRECTORY TO WORK WITH 
  Create a GitHub account 
  To be able to use GitHub, you will have to create an account first. You can do that on the website: http://github.com/ 
  1. Add Your Global Username and email of Git hub using following command: 
``` 
git config --global user.name "firstName lastName"
git config --global user.email "name@example.com" 
```
 
2. Fork the repository which you want to work on. 
   Click on the Fork button fork to copy the repository to your account. This will be essential for deployment to Heroku. 
3. Goto your account and you can find the copy of your repository.
4. Click on the code and copy the link present in it.
5. open the Git Bash
6. Cloning a Git Repo: Locate to the directory you want to clone the repo:  
```
cd D:/
mkdir To-doApp 
cd To-doApp 
```
7. Copy the link of your repository which you want to work with: 
```
git clone Pastethelinkhere 
 ```
8. use to following command to avoid ssh errors (optional)
```
git config http.sslVerify "false" 
```
9. Type the ls command to verify that you have the repository 
```
ls 
```
10. Enter the folder by typing 
```
cd campus-workshops-knowledge-base/ 
```
11. Type the ls command to verify the files inside the campus-workshops-knowledge-base folder 
```
ls 
```
12. Edit a README.md file and save it.  
```
notepad README.md 
```

**Note : If you are using git with your Github account for the first time then you can [click here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) , which details the steps to configure your git settings so that you can start pulling and pushing data to your remote repository**

### ADD AND COMMIT FILE  
When we first initialized our project, the file was not being tracked by Git. To do that, we use this command 
'''
git add . 
'''
The period or dot that comes after add means all the files that exist in the repository. If you want to add a specific file, maybe one named about.txt, you use git add about.txt 
1. Add files to the Staging Area for commit: 
```
git add . 
# Adds all the files in the local repository and stages them for commit 
##  or 
git add README.md 
# To add a specific file
```
2. Commit files in Git: The next state for a file after the staged state is the committed state. 
```
git commit -m "First commit" 
#The message in the " " is given so that the other users can read the message and see what changes you made 
```
3. The git push command pushes the changes in your local repository up to the remote repository you specified as the origin. 
```
git push -u origin master #pushes changes to origin 
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
git branch branchname 
```
- To Switch between the branches, use the following command 
```
  git checkout branchnameyouwanttoswichto   
```
**make sure that you have fork the campus-workshops-knowledge-base from BetsolLLC and clone it to your Local repository in your computer.
This Repository contains the Workshop Hands-on guide which you can use it for futher development of TO-DO App**
