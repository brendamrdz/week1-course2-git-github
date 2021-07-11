# git


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
Instead of a single master branch, this workflow uses two branches to record the history of the project. The master branch stores the official release history, and the develop branch serves as an integration branch for features. It’s also convenient to tag all commits in the master branch with a version number.

## Git reset vs Git rm
  Git reset vs git remove
  git rm: Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones.
  Esto quiere decir que si necesitamos recuperar el archivo solo debemos "viajar en el tiempo" y recuperar el ultimo commit antes de borrar el archivo en cuestion
  Flags
  git rm --cached: Elimina los archivos del area de staging y del proximo commit pero los mantiene en nuestro disco duro.
  
  git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guardara todo, por lo que podemos acceder al registro de la existencia de los archivos (debemos usar comandos avanzados)
  Git reset
  Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. con git reset volvemos al pasado sin la posibilidad de volver al futuro.
  git reset --soft: Borramos todo el historial y los registros de Git pero  guardamos los cambios que tengamos en staging, asi podemos aplicar las ultimas actualizaciones a un nuevo commit
  
  
  git reset --hard Borra todo, abosultamente todo.
  
  IMPORTANTE
  git reset head: Este es el comando para sacar archivos del area de staging. No para borrarlos ni nada de eso, solo para que los ultimos cambios de estos archivos no se envien al ultimo commit a menos que cambiemos de opinion
  
