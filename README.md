# Git


## Install (Debian/Ubuntu)
Updates your Ubuntu system
```bash
sudo apt-get update
sudo apt-get upgrade
```
Install git for the latest stable version for your release of Debian/Ubuntu
```bash
# sudo apt-get install git
```
## Common Git Commands
**git init** turns a directory into an empty Git repository. This is the first step in creating a repository. After running git init, adding and committing files/directories is possible.
```bash
$ git init
```
**git add** adds files in the to the staging area for Git. There are a few different ways to use git add, by adding entire directories, specific files, or all unstaged files.
```bash
$ git add FileName.txt
```
```bash
# adds all files at once in a repository.
$ git add .
```

**git commit** saves changes made to files in a local repository.
It’s best practice to include a message with each commit explaining the changes made in a commit. Adding a commit message helps to find a particular change or understanding the changes.
```bash
$ git commit -m "commit message"
```
**git status** will return the current working branch. If a file is in the staging area, but not committed, it shows with git status. 
```bash
$ git status
```
**git log** shows the chronological commit history for a repository.
```bash
$ git log FileName.txt
```
When you run this command you get an output like this:
```bash
commit 15f4b6c44b3c8344caasdac9e4be13246e21sadw
Author: Robert Jones <robertj@gmail.com>
Date: Mon Oct 1 12:56:29 2016 -0600
```
**git checkout**
**git show FileName.txt**
**git diff**
**git resset**
git reset [hash] --hard
**git log --stat**
**git branch**
**git fetch + gitmerge = git pull**

## git config
The git config command changes the configuration options in your Git installation.
Two important settings are user.name and user.email. These values set what email address and name commits will be from on a local computer.
```bash
$ git config --global user.name "Brenda M"
$ git config --global user.email "email@email.com"
```

## Working Directory, Staging Area, and Repository<br><br>
<img src="https://user-images.githubusercontent.com/26840321/125209930-0dbb8e80-e262-11eb-838d-ee8b252bc8c2.png" alt="alt text" width="60%" height="auto"><br><br>
**Working Directory**
This simply refers to the current state of files and folders inside your file system. At this point, Git doesn’t track these files.

**Staging Area**
Before saving any file to a repository, you have to place it in a staging area. It’s like a temporary location for your files and folders before commit. You can easily add or remove files from a staging area. 

**Repository**
A repository holds your actual committed files. Git stores all this information inside a hidden folder called .git. When you commit something, whatever is inside your staging area is permanently saved in a repository.

## How Git Flow Works
<br><br><img src="https://github.com/brendamrdz/week1-course2-git-github/blob/main/images/git-workflow.png?raw=true" alt="alt text" width="60%" height="auto"><br><br>
Instead of a single master branch, it is better to use two or more branches to record the history of the project. The master branch stores the official release history, the develop branch serves as an integration branch for features. It’s also convenient to tag all commits in the master branch with a version number.

## Git reset vs Git rm
### git rm
  This command helps us to delete files from Git without removing their history from the versioning system.
  This means that if we need to recover the file we just need to "time travel" and retrieve the last commit before deleting the file in question.
  #### Flags
  - **git rm --cached** Removes the files from the staging area and the next commit but keeps them on our hard drive.
  
  - **git rm --force** Removes the files from Git and from the hard disk. Git will always save everything, so we can access the log of the existence of the files (we must use advanced commands)
### git reset
  This command helps us to go back in time. But not like git checkout which lets us go, look, walk and come back. With git reset we go back to the past without the possibility to go back to the future.
  #### Flags
  - **git reset --soft** We erase all history and Git logs but save the changes we have in staging, so we can apply the latest updates to a new commit.
  - **git reset --hard** Deletes everything, absolutely everything.
 - **git reset head** This is the command to remove files from the staging area. Not to delete them or anything, just so that the latest changes to these files are not sent to the last commit unless we change our mind.

  ## Connecting to GitHub with SSH
  
Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit.
  <br><br><img src="https://github.com/brendamrdz/week1-course2-git-github/blob/main/images/github-ssh.JPG?raw=true" alt="alt text" width="60%" height="auto"><br><br>
Check the complete documentation in the following [link](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

## Github branches managment
**git show-branch --all**
**gitk**
### Set Github repository permissions
repository settings -> Collaborations -> Add user's public email or user name
