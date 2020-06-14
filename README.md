# Intro to Programming

## Table of Contents
- [Tools and Setup](#tools-and-setup)
  - [Tools to install](#tools-to-install)
  - [Git](#git)
    - [Basic Terms](#basic-terms)
    - [Git Commands](#git-commands)
    - [Git Cheatsheet](#git-cheatsheet)
- [Java](#java)
- [Glossary](#glossary)
- [Additional Resources](#additional-resources)

## Tools/Setup:

### Tools to install
- [IntelliJ](https://www.jetbrains.com/idea/)

 We will be using IntelliJ as our IDE. This will allow us to write and run code, in addition to extra features like connecting to Git, dependency management, and shortcuts.

- [Git Bash](https://git-scm.com/downloads)

 This is only necessary for Windows users. This provides us a Terminal that has git installed, which allows us to use git commands. Also, this terminal is similar to the UNIX shells found on Mac and Linux.

- [Java](https://adoptopenjdk.net/)

 There are many versions of free Java available, so take your pick. Most of the code we will be writing is not dependant on the Java version, but I'd probably choose either Java 8 or 11.

### Git
While not necessary in learning how to program, Git is essential in becoming a good programmer. Git is the standard for [version control](#glossary)

#### Basic Terms
- Repository (repo): location where code and projects are stored in Git.
- Commit: individual change to a file (or set of files). This is how Github keeps track of which changes were made when and by who
- Merge conflict: When two people attempt to edit the same code file. Github can try to auto resolve these, however if they are complicated, they can be resolved in IntelliJ
- Branch: A set of code changes with a unique name. The main branch in every project is called `master`. `master` is typically production-ready code, so try not to push broken code into it.
- Pull Request (PR): A request to merge the code changes from a branch into `master`.
- `.gitignore`: This is a file where you can put the names of other files/directories that you don't want Git to track changes for.


#### Git Commands
Command | What it does | Notes
--- | --- | ---
`git init` | Create empty Git repo in specified directory | 
`git clone <repo>` | Downloads a copy of a repo in specified directory |
`git status` | Lists which files have been changed or staged for commit | 
`git add <directory>` | Stages all changes in `<directory>` for next commit. `<directory>` can be replaced with <file> to just stage a single file. | `git add .` will stage all files
`git commit -m "<message>"` | Commit the staged changes, using "<message>" as commit message | Remember to use `-m "<message>"` - otherwise an in-terminal text editor will open. 
`git push` | Pushes any staged commits to current branch | 
`git pull` | Downloads any changes to the repo online | Note: This may cause merge conflicts
`git reset --hard HEAD` | Undo all local changes to repo | 
`git branch` | Lists all the branches in repo | Add `<branch>` argument to create new branch with name `<branch>`
`git checkout -b <branch>` | Create and check out new branch named `<branch>` | Drop the `-b` argument to check out an existing branch
  
#### Git Cheatsheet
These are some useful command flows for general usage:
- Flow for pushing local changes to online repo
```
git status
git add <files to be added>
git commit -m "<commit message>"
git push
```
- Undo all changes in local branch and switch to `master` branch
```
git reset --hard HEAD
git checkout master
```
- After a PR is merged to `master`:
  - check out `master`
  - pull recent changes
```
git checkout master
git pull
```
- Merge `master` branch changes into local branch - note: this may cause merge conflicts that need to be fixed in IntelliJ
```
git fetch
git merge origin/master
```

# Java
Java is a programming language that has been around since 1995 that is mainly used for backend applications. Java programs are run on the Java Virtual Machine (JVM) which allows it to be built/compiled once, regardless of the end users operating system. 

## Variables, Data Types, and Math Operators

### Variables
---

Variables are items that hold a value which we can use somewhere in our application. Variables are created or "declared" and are then assigned a value. In Java the standard is to name variables using camel case. Camel case means that the name should start with a lower case letter and any subsequent word should be capitalized. Numbers are allowed, but not as the first character of the variable.


| camel case  |  not camel case |
|---|---|
|  myVar |  MyVar |
|  var1 | myvar  |
|  apple2Oranges | 1Var  |

Declaring a variable in java looks like this:
```java
int myVar = 100;
```
This will create a variable named myVar that has a value of 100. If you want to change/reassign the value of `myVar` all you need to do is set it to a new value like so:

```java
myVar = 2;
```

`myVar` will now hold 2 instead of 100.


# Glossary
Term | Definition | Example | Notes
--- | --- | --- | ---
version control| system that records changes to a file or set of files over time so that you can recall specific versions later | If you write bad code and want to revert back to a old working version, version control allows you to do that |


# Additional Resources
- [CodingBat](https://codingbat.com/java)

 Extra practice writing Java methods.
