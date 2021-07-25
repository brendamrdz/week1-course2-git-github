# Git
## General info
### What is Version Control?
Version control is the method used for incrementing, tracking, and recording changes in documents or files that occur over time in a systematic manner. Versioning organizes the history of changes in a logical order, and allows for review or version rollbacks if needed.

#### Version Control System
Version control is a system that allows the software team to manage changes to the source code over time. This software tool makes it easier for developers to collaborate on different projects separating their tasks through branches. It also gives the possibility to turn back to earlier versions for comparing and fixing the mistakes if needed.
##### Benefits of version control systems:
- **Long-term change history**<br>
The changes made by developers, including the creating, modification, and deletion of files over the years, can be seen in history. It will allow going back to the previous version for analyzing bugs and fixing problems.<br>

- **Branching and merging**<br>
Branching helps work in an independent manner and not interfere with each other’s work. Merging brings the works together and allows seeing if there are conflicts between those works.<br>

- **Traceability**<br>
Ability to trace each change and connect it to project management and bug tracking software, as well as to annotate each change with a message describing the purpose of the change.<br>
## What is Git?
It is a free and open-source version control system used to handle small to very large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development. Linus Torvalds created Git in 2005 for the development of the Linux kernel. 
 
### Git scenario:
- Every developer has an entire copy of the code on their local systems
- Any changes made to the source code can be tracked by others
- There is regular communication between the developers
<img src="https://user-images.githubusercontent.com/26840321/126888848-3c68a08b-9adc-4970-9b42-6ba0f7094fb4.png" alt="alt text" width="60%" height="auto"><br><br>

## What is GitHub?
GitHub is a Git repository hosting service that provides a web-based graphical interface. It is the world’s largest coding community. Putting a code or a project into GitHub brings it increased, widespread exposure. Programmers can find source codes in many different languages and use the command-line interface, Git, to make and keep track of any changes.

GitHub helps every team member work together on a project from any location while facilitating collaboration. You can also review previous versions created at an earlier point in time.
<br><br><img src="https://user-images.githubusercontent.com/26840321/126890071-b53cf1e0-88c5-434a-b5bf-a87e057a6e67.png" alt="alt text" width="20%" height="auto"><br><br>


## Git Workflow<br><br>
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
**git checkout** To start working in a different branch, use git checkout to switch branches.

**git diff** command shows the differences between the files in two commits or between your current repository and a previous commit. 
```bash
$ git diff [id old version] [id new version]
```

**git branch**
```bash
# Create a new branch
$ git branch <branch_name>

# List all remote or local branches
$ git branch -a

# Delete a branch
$ git branch -d <branch_name>
```
**git pull**
To get the latest version of a repository run git pull. This pulls the changes from the remote repository to the local computer.It is a combination of git fetch which fetches the recent commits in the local repository and git merge, which will merge the branch from a remote to a local branch.

**git push** command is used to transfer or push the commit, which is made on a local branch in your computer to a remote repository like GitHub. The command used for pushing to GitHub is given below.
```bash
git push 'remote_name' 'branch_name'
```

**gitk** git graphical interface
## git config
The git config command changes the configuration options in your Git installation.
Two important settings are user.name and user.email. These values set what email address and name commits will be from on a local computer.
```bash
$ git config --global user.name "Brenda M"
$ git config --global user.email "email@email.com"
```

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

## git merge
The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.
Whether branches are created for testing, bug fixes, or other reasons, merging commits changes to another location. 
<br><br><img src="https://user-images.githubusercontent.com/26840321/125213307-80833480-e277-11eb-8d45-a27386cfd255.png" alt="alt text" width="40%" height="auto"><br><br>
Merge the master branch into the feature branch using the checkout and merge commands.

```bash
$ git checkout feature
$ git merge master
```

  ## Connecting to GitHub with SSH
  
Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit.
  <br><br><img src="https://github.com/brendamrdz/week1-course2-git-github/blob/main/images/github-ssh.JPG?raw=true" alt="alt text" width="60%" height="auto"><br><br>
Check the official documentation in the following [link](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)
### Set Github repository permissions
repository settings -> Collaborations -> Add user's public email or user name

## GitHub fork
A GitHub fork is a copy of a repository (repo) that sits in your account rather than the account from which you forked the data from. Once you have forked a repo, you own your forked copy. This means that you can edit the contents of your forked repository without impacting the parent repo.

## References
https://www.w3docs.com/learn-git/version-control-system.html


