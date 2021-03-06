# Intro to Programming

## Table of Contents
  * [Tools/Setup:](#tools-setup-)
    + [Tools to install](#tools-to-install)
    + [Git](#git)
      - [Basic Terms](#basic-terms)
      - [Git Commands](#git-commands)
      - [Git Cheatsheet](#git-cheatsheet)
- [Java](#java)
  * [Hello World](#hello-world)
      - [**`Application.java`**](#---applicationjava---)
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
- [Credits](#credits)
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
- Merge conflict: when two people attempt to edit the same code file. Github can try to auto resolve these, however if they are complicated, they can be resolved in IntelliJ
- Branch: a set of code changes with a unique name. The main branch in every project is called `master`. `master` is typically production-ready code, so try not to push broken code into it.
- Pull Request (PR): a request to merge the code changes from a branch into `master`.
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

## Hello World
Writing a program that outputs "Hello World" is typically what programmers do when they try to learn something new. In Java, this generally looks like the code below:

#### **`Application.java`**
```java
public class Application {
   public static void main(String[] args) {
      System.out.println("Hello World")
   }
}
```
Let's quickly dissect this line by line to get a general understanding of how to run a program.

1. `public class Application {`
    - Without going into too much detail about classes, know that every class should be in its own source file. This line defines that the `Application` class is living in this source file. Generally speaking, only one `public class <NAME> {` line will be in each `.java` file
2. `public static void main(String[] args) {`
    - There is a lot to take in here, but to start, this is just a good line to memorize as every program will have this. This is called our `main` method, and it tells Java where your code starts when you run your app. Make sure you remember the spelling and capitalization of this line - it's very important!
3. `System.out.println("Hello World")
    - This line is what outputs (or "prints") `Hello World` to the console. `System.out.println(<ANYTHING>)` is very useful in testing and debugging, especially as you first learn how to code. As you learn new material or get curious about how things within Java interact, feel free to toss it into a `System.out.println()` to see what it'll print out!
4. `}` 
    - Make sure you close your brackets and parentheses! Every `(` must have a corresponding `)` and every `{` must have a corresponding `}`. Parentheses and brackets are used to define code being a part of another chunk of code. In our `Hello World` example, the `main` method a part of the `Application` class, `System.out.println("Hello World")` is part of the `main` method, and `"Hello World"` is part of the `System.out.println()` method.
    - It may be a bit confusing when to use parentheses and when to use brackets, but don't worry! IntelliJ will let you know when you're wrong. Also, you'll get better at knowing when each is appropriate over time.

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
**Note**: when dividing integers, any decimal created is dropped. For example:
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

**Note**: Note the difference between assignment `=` and equal to `==`. This is a very common mistake that your IDE may not point out.

### Logical

Logical operators are used to determine logic of comparisons and values. Like comparison operators, the result of a logical operator is a boolean. All of the examples below equate to `true`.

| Symbol  | Name | Example | Example value | 
| ------  | ---- | ------- | --- |
| &&      | And  | 1 < 2 && 2 < 3 | true |
| \|\|      | Or   | 1 < 2 \|\| 2 > 3 | true | 
| !       | Not  | !(1 > 2 && 2 > 3)| true |

# Control Flow
Statements inside your code are usually ran from top to bottom. Control flow statements help to change the flow of execution.

Three different types of control flow statements in Java (only included commonly used ones):

- Decision making statements:  if, else, else-if
- Looping statements: for, while
- Branching statements: break, continue, return

### Decision making statements

#### if
The if statement tells your program to execute a certain section of code only if the condition is true.
```java
if (number % 2 == 0) {
  System.out.println("The number is even.");
}
```
For example, in the above, the statement is printed only if the number is divisible by 2. 

#### else
The else statement is ran when an "if" condition is false.
```java
if (number % 2 == 0) {
  System.out.println("The number is even.");
} else {
  System.out.println("The number is odd.");
}
```
In the above example, it prints that the number is even, if the number is divisible by 2, else it prints that the number is odd.

#### else-if
Sometimes we want to check a different condition after the `if` condition fails. 
```java
if (number <= 0) {
  System.out.println("Please enter a valid positive number.");
} else if (number % 2 == 0) {
  System.out.println("The number is even.");
} else {
  System.out.println("The number is odd.");
}
```
**Note**: else-if statements chained together go top down - if one condition is satisfied, the conditions after it aren't checked.

### Looping statements
#### for
The for statement loops until a particular condition is satisfied.
```java
for (initialization; termination; increment) {
    statement(s)
}
```
- The initialization expression creates the loop. It is only ran once when the loop begins.
- The termination expression stops the loop when it becomes false.
- The increment expression is ran at the end of each iteration through the loop.

```java
System.out.println("Printing numbers 1 to 10.");
for (int count = 0; count <=10 ; count++) {
    System.out.println(count);
}
```

#### while
The while loop executes a set of statements while a certain conditions is true. The while statement evaluates expression, which must return a boolean value. If the expression evaluates to true, the while statement executes the statement(s) in the while block. The while statement continues testing the expression and executing its block until the expression evaluates to false. 
```java
int count = 1;
while (count <= 10) {
  System.out.println(count);
  count++;
}                                                                                
```

### Branching statements

#### break
The break statement stops the innermost loop that it is in.

```java
for (int i=1; i<=5; i++){
  if (i==3) {
    System.out.println("Breaking the for loop.");
    break;
  }
  System.out.println("Printing " + i);
}
```

#### continue
The continue statement skips the current iteration of a loop. Note that unlike the break statement, it keeps running the loop from the next iteration instead of stopping it completely.
```java
for (int i = 0; i <10; i++) {
  if (i % 2 != 0) {
    continue;
  }
  System.out.println(i + " is even");
}
```

#### return 
The return statement exits from the current method and gives back a value. For example, the code below will print out `true`, and not `This line will never get printed` because the return statement ends the method and Java never reaches the last line.

```java
public static void main(String[] args) {
  int i = 52;
  bool even = isEven(i);
  System.out.println(even);
}
public static boolean isEven(int num) {
  if(num % 2 == 0) {
    return true;
  }
  else {
    return false;
  }
  System.out.println("This line will never get printed");
}
```

## Collections
There are many types of collections in Java, we'll only go over a few here. 

#### Arrays
Arrays are a group of like-typed variables that are referred to by a common name. Here is an example of an array of integers from 1 to 10:
```java
int[] numbers = {1,2,3,4,5,6,7,8,9,10};
```
Arrays allow us to process multiple items at the same time. Instead of writing
```java
int a = 1;
int b = 2;
int c = 3;
int d = 4;
System.out.println(a);
System.out.println(b);
System.out.println(c);
System.out.println(d);
```
we can write
```java
int[] numbers = {1,2,3,4};
for (int number : numbers) {
  System.out.println(number);
}
```
- **Note**: This is a special way of writing a for loop to iterate over a collection of items.

However, arrays are static, which means that once they are created, their size cannot change.

#### Arraylist
Arraylists help us fix this issue. Arraylists are dynamic, which means that you can add and remove objects from the list.

```java
    ArrayList<Integer> list = new ArrayList<>();
         
    list.add(1);
    list.add(2);
    list.add(3);
```

# Glossary
Term | Definition | Example | Notes
--- | --- | --- | ---
version control| system that records changes to a file or set of files over time so that you can recall specific versions later | If you write bad code and want to revert back to a old working version, version control allows you to do that |


# Additional Resources
- [CodingBat](https://codingbat.com/java)

 Extra practice writing Java methods.
 
 # Credits
 - Lot of this was taken from Target's internal Java resources. 
 - <small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>
