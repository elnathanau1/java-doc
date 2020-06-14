# Intro to Programming

## Table of Contents
- [Tools and Setup](#tools-and-setup)
  - [Tools to install](#tools-to-install)
  - [Git](#git)
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


#### Git Commands
Command | What it does | Notes
--- | --- | ---
`git init` | Create empty Git repo in specified directory | 
`git clone <repo>` | Downloads a copy of a repo in specified directory |
`git add <directory>` | Stages all changes in `<directory>` for next commit. `<directory>` can be replaced with <file> to just stage a single file. | `git add .` will stage all files
`git commit -m "<message>"` | Commit the staged changes, using "<message>" as commit message | Remember to use `-m "<message>"` - otherwise an in-terminal text editor will open. 
`git push` | Pushes any staged commits to current branch | 
`git pull` | Downloads any changes to the repo online | Note: This may cause merge conflicts
`git reset --hard HEAD` | Undo all local changes to repo | 


## Glossary
Term | Definition | Example | Notes
--- | --- | --- | ---
version control| system that records changes to a file or set of files over time so that you can recall specific versions later | If you write bad code and want to revert back to a old working version, version control allows you to do that |


## Additional Resources
- [CodingBat](https://codingbat.com/java)

 Extra practice writing Java methods.
