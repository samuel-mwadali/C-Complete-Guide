Documenting my journey learning C from scratch - complete with notes, code snippets and progress tracking.
---
# ** Learn C**
C is a general-purpose programming language that has been widely used for over 50 years.<br>C is very powerful; it has been used to develop operating systems, databases, applications, etc.
## what to learn
This guide, step by step, with codes along the way.
- How C programs are structured
- Variables, data types, and operators
- If statements, loops, and arrays
- Functions and how to reuse code
- Pointers and memory
- Structure to organize related data
- Reading from and writing files
- Organizing programs and build real-life projects
---
# **C introduction**
## What is C?
C is a general-purpose programming language created by Dennis Ritchie at Bell Labs in 1972.<br>It is popular because it is fast, widely supported, and helps you understand how programs work "under the hood".<br>The main reason for its popularity is because it is a fundamental language in the field of computer science.<br>C is closely connected to UNIX, because much of was written in C.
## What is C used for?
C is often used to create programs that need to run fast and work closely with the computer.
- Operating systems, such as parts of Windows, Linux and MacOS
- Programs inside devices like cars, TVs and home electronics
- Software that needs to be fasat, including databases and system tools.
- Game engines and programs that handle graphics
- Core libraries that other programming language rely on.
## Why learn C?
- It is one of the most widely used programming languages.
- If you know C, you will have no problem learning other popular programming languages such as Java, Python, C++, C#, etc as the syntax is simalar?
- It helps you understand memory, performance, and how computers handle data
- C is very versatile; it can be used in both applications and technologies
## Difference between C and C++
- C++ was developed as an extension of C, and the syntax is often similar
- C is mainly a procedural language (you build programs with functions)
- C++ supports classes and objects (often used for object-oriented programming)
---
# **Get Started**
## Install C
If you want to run C programs on your own computer, you need two things:
- A text editor to write C code
- A compiler to turn the C code into a program the computer can run
The compiler reads your C code and translates it into machine code.<br>There are many editors and comoilers availble. To make things easier, most people use an IDE, which includes both.<br> Which setup shoud you use? It depends on your computer.
| You have | Use |
| --- | --- |
| Any device | You are in right place |
| Windows | Code::Blocks |
| Mac | Xcode command Line Tools. Open the Terminal and type *xcode- select --install* |
| Linux | GCC. it is often already installed. Type gcc --version in the terminal to check |

## install IDE
An IDE(Intergrated Development Environment) is a program that helps you write, compile, and run code.
Popular IDEs and editors inclued Code::Blocks, Visual Studio, and VS code. There are free tools that can also help you find errors in your code.<br>**Note:** Web-based IDEs can also work, but they oten have limited features.
## Quickstart
Let's create our first C file.<br>
Open Code::Blocks and go to File>New>Empty File.<br>
Write the following c code and save the file as *myfirstcoding.c* (File>Save File as):
```C
#include <stdio.h>
int main(){
    printf("Hellow World!");
    return 0;
}
```
**What just happened?** You wrote C code, the compiler turned it into a program, and the computer ran it. Basic workflow you will use throughout.
| **myfirstcoding.c** |
| --- |
| *-> compile ->* |
| **program** |
| *-> run ->* |
| **Hello World!** |
---
# **C Syntax**
## Syntax
You have already seen the following code a couple of times in the first. Let's break it down and understand what each part does:<br>
Here is what each line of the program does:
```C
#include <stdio.h>            // Makes printf() available

int main(){                   // The program starts here
    printf("Hellow World!");  // Prints Hello World! to the screen
    return 0;                 // Ends the program
}                             // The end of main()
```
## Example explained
- **line 1:** tells C to include a header file. This header lets us use input/output functions such as printf()
- **line 2:** A blank line. C ignores extra spaces and blank lines, but we use them to make the code easier to read.
- **line 3:** main() is a special function. Your program starts running here. Any code inside the curly brackets {} will be executed<br>The word int before main() means that the function gives back a whole number (an interger) when it ends. That number is the 0 in return 0.
- **line 4:** printf() is a function used to output (print) text to the screen. In our example, it prints *Hello World!*<br>
**Note:** Every C statement ends with a semicolon ;<br>
**Note:** The body of *int main()* could also be written as:
```C
int main(){printf("Hello World!");return 0;}
```
**Remember:** The compiler ignores extra spaces and new lines, but using multiple lines makes code easier to read.
- **line 5** *return 0* ends the *main()* function and sends a value back to the operating system.<br>Returning *0* usually means "everything worked."
- **line 6:** Do not forget the closing curly bracket } to end **main()** function.
---
# **C Statements**
## Statements
A **computer program** is a list of instructions that a computer follows.<br>In C, these instructions are called **statements**.<br>The following statements tells the program to print the text **Hello World!** to the screen.
```c
pritnf("Hello World!");
```
Every statement in C must end with semicolon ;
If you forget the semicolon, the compiler will show an error and the program will not run.
## Many statements
Most C programs contain more than one statement.<br>Statement are executed one by one, in the same order as they are written.
```c
pritnf("Hello World!");
printf("Have a good day!");
return 0;
```
## Example explained
This program contains three statements
- printf("Hello World!"):
- printf("Have a good day!");
- return );
The first statements runs first and prints *Hello World!*.<br>
Then the second statements runs and prints *Have a good day!*.<br>
Finally, the last statement runs and ends the program.
- **Remember: Each statement is one instruction, and it must end with a semicolon.
---
# **Output (print Text)**
## Output (Print Text)
To output values or print text in C, you can use the printf() function:
```c
#include <stdio.h>

int main(){
    printf("Hello World!");
    return 0;
}
```
## Double quotes
When you want to print text, the text must be wrapped in double quotes "".
if you forget the double quotes, an error occurs:
- **Tip:** If you see stranger error messages, check that your text starts and ends with double quotes
## Many **printf()** Functions
You can use as many **printf()** functions as you want.<br>
However, note that does not insert a new line at the end of the output.
```c
# include <stdio.h>

int main(){
    printf("Hello World!");
    printf("I am learning C.");
    printf("And it is awesome!");
    return 0;
}
```
- **Notice:** All the text appears on the same line. In the next chapter, you will learn how to add new lines to make the output easier to read.
---
# **C New Lines**
## New lines
To start a new line when printing text, you can use the \n character:
```c
# include <stdio.h>

int main() {
    printf("Hellow World!\n");
    printf("I am learning C.");
    return 0;
}
```
You can also print multiple lines using a single *printf()* function. However, this could make the code harder to read:
```c
#include <stdio.h>

int main(){
    printf("Hello World!\nI am learning C.\nAnd it is awesome!");
    return 0;
}
```
- *Tip* Two \n characters in row will create a blank line
```c
# include <stdio.h>

int main() {
    printf("Hello World!\n\n");
    printf("I am learning C.");
    return 0;
}
```
**What is \n exactly?**<br>
\n is called an escape sequence.<br>
Escape sequences start with a backslash and represent special characters that cannot be typed directly.<br>
In this case, \n tells the program to move the cursor to the beginning of the next line.<br>
Here are some other common escape sequences:
| Escape Sequence | Description |
| --- | --- |
| \t | Insert a horizontal tab |
| \\ | Insert a backslash character(\) |
| \" | Insert a double quote character |
## Fun Example: Draw a Pyramid
With few *printf()* functions and \n, you can draw pictures in the output. Pictures made of keyboard characters are called ASCII art.
```c
# include <stdio.h>

int main(){
    printf("    *\n");
    printf("   **\n");
    printf("  ***\n");
    printf(" ****\n");
    printf("*****\n");
    return 0;
}
```
---
# **Comments**
## Comments in C
Comments can be used to explain C code, and to make it more readable.<br>
It can also be used to prevent exection when testing alternative code.<br>
Comments are ignored by the compiler, so they do not affect your program's output.
## Single-line Comments
Single-line comments start with two forward slashes(//).<br>
Any text between // and the end of the line is ignored by the compiler.<br>
This example uses a single-line comment before a line of code.
```c
// This is a comment
printf("Hello World!");
```
This example uses a single-line comment at the end of of a line of code.
```c
printf("Hello World!"); // This is a comment
```
You can also use // to disable a single line of code.
```c
printf("This will run");
// printf("This will NOT run");
```
## Multi-line Comments
Multi-line comments starts with /* and end with */
Any text between /* and */ will be ignored by the compiler.
```c
/* The code below will print the words
words Hello World!
to the screen, and it is amazing */
printf("Hello World!");
```
**Single or multi-line comments?**
it is up to you which you want to use. Normally, we use // for short comments and /* */ for longer comments.<br>**Good to know:** Before c99 (release in 1999), you could only use multi-line comments in C.
## What the Compiler Sees
Comments are for people reading your code, not for the computer. They help explain what your program does, but they don't affect how it runs.<br>When you compile  your program, comments are ignored.<br>Here is a program with some helpful comments. Switch the view to see the code without them.