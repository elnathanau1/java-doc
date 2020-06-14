# Intro to Programming

## Table of Contents
- [Intro to Programming](#intro-to-programming)
  * [Table of Contents](#table-of-contents)
  * [Tools/Setup:](#tools-setup-)
    + [Tools to install](#tools-to-install)
    + [Git](#git)
      - [Basic Terms](#basic-terms)
      - [Git Commands](#git-commands)
      - [Git Cheatsheet](#git-cheatsheet)
- [Java](#java)
  * [Variables, Data Types, and Math Operators](#variables--data-types--and-math-operators)
    + [Variables](#variables)
  * [Types](#types)
    + [Primitive Types](#primitive-types)
    + [String](#string)
  * [Operators](#operators)
    + [Arithmetic](#arithmetic)
    + [Increment and Decrement](#increment-and-decrement)
    + [Assignment](#assignment)
    + [Comparison](#comparison)
    + [Logical](#logical)
    + [Additional Resources](#additional-resources)
- [Glossary](#glossary)
- [Additional Resources](#additional-resources-1)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


## Tools/Setup:

### Tools to install
- [IntelliJ](https://www.jetbrains.com/idea/)

 We will be using IntelliJ as our IDE. This will allow us to write and run code, in addition to extra features like connecting to Git, dependency management, and shortcuts.

- [Git Bash](https://git-scm.com/downloads)

 This is only necessary for Windows users. This provides us a Terminal that has git installed, which allows us to use git commands. Also, this terminal is similar to the UNIX shells found on Mac and Linux.

- [Java](https://adoptopenjdk.net/)

 There are many versions of free Java available, so take your pick. Most of the code we will be writing is not dependant on the Java version, but I'd probably choose either Java 8 or 11.

### Git
---

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

## Types
---

Java is a statically typed language, which means the developer must explicitly state the type of a variable when it is declared. 

Look at the example above. The word `int` before `myVar` is declaring the type of data that variable will hold. In this case it is a **int** type so it can hold an integer/whole number.

```java
int myVar = 100;
myVar = "this is a string";
```

The above code will fail when you try to build/compile it. This is because a variable of type `int` can only ever hold whole numbers and "this is a string" is definitely not a whole number.

### Primitive Types

Primitive types are the most basic types in Java.

Some features of primitives are:
- If not explicity provided a variable will have a default value assigned to it.
- starts with a lower case letter

There are 8 total but **int**, **double**, and **boolean** are the most commonly used. 

**int**: Whole Numbers between -2,147,483,648 and 2,147,483,647

**double**: Decimal numbers like `0.5` or `3.14`

**boolean**: `true` or `false`

Slightly less commonly used but good to know:

**char**: a single text character like `C` or `a`. Unlike strings (defined below), these are defined using single quotes `'<char>'`


### String

**String** is a non-primitive type that represents text. For example `"this is a string"` is a String.
 Unlike primitives, the word String is capitialized and will **not** have a default value. To declare a string you need to wrap the value in double quotes `"`.

```java
String sampleText = "This is my favorite string!";
```

---
More about data types can be found here:
- https://www.w3schools.com/java/java_data_types.asp
- https://www.tutorialspoint.com/java/java_variable_types.htm

## Operators
---

Operators are used in Java, and most programming languages, to perform different types of operations on variables. A simple example of an operation is addition:

```java
int donuts = 10 + 10

```

### Arithmetic

Arithmetic operators are used to do math in Java.

| Symbol | Name | Description | Example | Example value |
| ------ | ---- | ----------- | ------- | --- |
| + | Add       | Adds two values                 | `2 + 2` | `4` |
| - | Subtract  | Subtracts a value from another  | `2 - 0` | `2` |
| * | Multiply  | Multiply two values             | `2 * 3` | `6` |
| / | Divide    | Divides a value from another    | `2 / 2` | `1` |
| % | Modulo    | Find the division remainder     | `2 % 2` | `0` |

---
Note: when dividing integers, any decimal created is dropped. For example:
```java
int a = 3;
int b = 2;
int c = a / b;
```
`c` will hold `1` instead of `1.5`, because it is an integer.

### Increment and Decrement

There are special operators to add one or subtract one from any value, they are `++` and `--` respectively. In the following example, `x` becomes `2`

```java
int x = 1++
```

### Assignment

The main assignment operator in java is an equal sign `=`. This operator allows you to set a variable with a given value.

```java
int donuts = 50
```

The `=` here sets the value of `donuts` to `50`.

There are also other kinds of assignment operators in Java that allow you to manipulate data at the same time as assignment.

```java
int donuts = 50
donuts -= 40
```

In this example we are saying `donuts = 50 - 40` and the final value becomes `10`.

### Comparison

There are times when you would like to compare two values instad of manipulating values. For this Java has Comparison operators. The result of using a comparison operator is a boolean - either `true` or `false`. All of the examples below equate to `true`.

| Symbol | Name | Example | Example value |
| ------ | ---- | ------- | --- |
| ==  | Equal to                  | 1 == 1 | true |
| !=  | Not equal                 | 1 != 2 | true |
| >   | Greater than              | 1 > 0  | true |
| <   | Less than                 | 1 < 2  | true |
| >=  | Greater than or equal to  | 1 >= 1 | true |
| <=  | Less than or equal to     | 1 <= 1 | true |

### Logical

Logical operators are used to determine logic of comparisons and values. Like comparison operators, the result of a logical operator is a boolean. All of the examples below equate to `true`.

| Symbol  | Name | Example | Example value | 
| ------  | ---- | ------- | --- |
| &&      | And  | 1 < 2 && 2 < 3 | true |
| ||      | Or   | 1 < 2 || 2 > 3 | true | 
| !       | Not  | !(1 > 2 && 2 > 3)| true |


### Additional Resources

- https://www.w3schools.com/java/java_operators.asp
- https://www.tutorialspoint.com/java/java_basic_operators.htm


# Glossary
Term | Definition | Example | Notes
--- | --- | --- | ---
version control| system that records changes to a file or set of files over time so that you can recall specific versions later | If you write bad code and want to revert back to a old working version, version control allows you to do that |


# Additional Resources
---

- [CodingBat](https://codingbat.com/java)

 Extra practice writing Java methods.
 
 # Credits
 - Lot of this was taken from Target's internal Java resources.
 
 
