## Initialize a git repository

### Create a folder

```powershell
mkdir hello-world
```

### Change directory into the folder created

```powershell
cd hello-world
```

### git init

```powershell
git init
```

This will initialize a local repository. The .git folder is a special folder tracked by the git utility to track changes made and state of the repo.

## First Commit

### Add a file called [README.](http://README.md)md and add content

### Check status of git repo

```powershell
git status
```

Here we can see that there is a new file that is currently untracked by git. You may make more changes to this new file.

### Get ready with your changes by staging it

```powershell
git add .
```

The dot represents the current folder and will add all the untracked changes in that folder to the staging area.

### Check the git status again

you can see that there are list of files which are ready to be committed.

### Commit

```powershell
git commit -m "my first commit"
```

Committing the changes will add the changes to the branch of the local repository. 
