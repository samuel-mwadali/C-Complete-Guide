Documenting my journey learning C from scratch - complete with notes, code snippets and progress tracking.
---
# **Learn C**
C is a general-purpose programming language that has been widely used for over 50 years.<br>C is very powerful; it has been used to develop operating systems, databases, applications, etc.
## What to learn
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
- A compiler to turn the C code into a program the computer can run<br>
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
# **C Variables**
## Variables
Variables are containers for storing data values, like numbers and characters.<br>
You can think of a variable as a named box where you keep a value that can be used later.<br>
In C, variables must have a specific **type**, which tells the program what kind of data the variable can store.
- **int** - stores whole numbers(intergers), such as *123* or *-123*
- **float** - stores numbers with decimals, such as *19.99* or *-19.99*
- **char** - stores a single character, such as 'a' or 'B'. Characters are surrounded by single quotes
## Declaring (creating) Variables
To create a variable, you must specify the type and give the variable a **name.**
You can also assign a value at the same time.
```text
Syntax
type variableName = value;
```
Where type is one of the C data types (such as *int*), and variableName is the name you choose (for example x or myNum)
The equal sign = is used to assign a value to the variable.<br>
So, to create a variable that should store a number.
```c
/*Create a variable named myNum of type int and assign the value 15*/
int myNum = 15;
```
you can also declare a variable first and assign a value later.
```c
// Declare a variable
int myNum;

// Assign a value later
myNum = 15;
```
- *Tip*- Variable names should be meaningful, so your code is easier to understand.
## Output Variables
You learned from the output chapter that you can print text using printf() function
```c
printf("Hello World!");
```
In many other programming languages (like python, Java, and C++), you would normally use a **print function** to display the value of a variable. However, this is not possible in C.
```c
int myNum = 15;
printf(myNum); // This will cause an error
```
- To print variables in C, you must use something called **format specifiers.**
- Don't worry - this will be explained clearly in the next chapter.
---
# **C Format Specifiers**
## Format specifiers
Format specifiers are used together with the printf() function to print variables.<br>
You can think of a format specifier as a **placeholder** that tells C what kind of value will be printed.<br>
A format specifier always starts with a percentage sign % , followed by a letter.<br>
For example, to output the value of an *int* variable, use the format specifier %d surrounded by double quotes(" "), inside the **printf()** function
```c
int myNum = 15;
printf("%d", myNum); // Output 15
```
- *How it works:* %d tells C to expect an interger value, and *myNum* provides that value.
Different data types use different format specifiers.
```c
// Create variables
int myNum = 15; // Interger (whole number)
float myFloatNum = 5.99; // Floating point number
char myLetter = 'D'; // Character

// print variables
printf("%d\n", myNum);
printf("%f\n", myFloatNum);
printf("%c\n", myLetter);
```
To combine both text and a variable, separate them with a comma inside the *printf()* function
```c
int myNum = 15;
printf("My favorite number is: %d", myNum);
```
To print different types in a single printf() function, you can use the following
```c
int myNum = 15;
char myLetter = 'D';
printf("My number is %d and my letter is %c", myNum, myLetter);
```
Run the simulation below to see how *printf()* fills in each placeholder, from left to right.
```c
int myNum = 15;
char myLetter = 'D';
printf("My number is %d and my letter is %c", myNum, myLetter);
```
- *printf()* prints the text inside text inside the double quotes, from left to right
- *Tip:* Each format specifier must match the correct type of value. You will learn more about data types later in this tutorial.
## Print values without variables
You can also print values directly without storing them in variables, as long as you use the correct format specifier.
```c
printf("My favorite number is: %d", 15);
printf("My favorite number is: %c", 'D');
```
---
# **C Variable Values**
## Change Variable Values
If you assign a new value to an existing of variable, the new value will replace the old one:
```c
int myNum = 15; // myNum is 15
myNum = 10; // Now myNum is 10
```
- *Note:* This is normal and expected. Variables are meant to change while a program runs.
You can also assign the value of one variable to another.
```c
int myNum = 15;
int myOtherNum = 23;
// Assign the value of myOtherNum (23) to myNum
myNum = myOtherNum;
// myNum is now 23 (was 15)
printf("%d", myNum);
```
you can even copy values into variables that were declared earlier without a value.
```c
// Create a variable and assign a value
int myNum = 15;

// Declare a variable without assigning a value
int myOtherNum;

// Copy the value from myNum
myOtherNum = myNum;

// myOtherNum is now 15
printf("%d", myOtherNum);
```
## Add Variables Together
You can use mathematical operators to work with variables. For example, to add one variable to another, use the + operator.
```c
int x = 5;
int y = 6;
int sum = x + y;
printf("%d", sum);
```
You can also update a variable using its current value
```c
int x = 5;
int x + 1;
printf("%d", x);
```
- *Tip:* Writing x = x + 1 means "take the current value of x and add 1 to it."
**Note:** You will learn much more about operators in later chapter
## Swap two variables
A common task in programming is to swap the values of two variables.
To do this, you need a third variable that holds one of the values for a moment. It works like swapping the drinks in two glasses: You need an empty third glass to do it.
```c
int a = 5;
int b = 10;
int temp;
// Swap the values of a and b
temp = a; // glass a to an empty glass
a = b; // glass b to an empty glass a
b = temp // empty glass temp to glas empty glass b
printf("a is %d, b is %d", a, b);
```
**Why do we need temp?** if you only write a = b; and then b = a; both variables end up as 10, the first line replaces the 5 in a, so it is lost before b can get it
# **C Declare Multiple Variables**
## Declare multiple Variables
To declare more than one variable of the same type, use a comma-separated list.
```c
int x = 5, y = 6, z = 50;
printf("%d", x + y + z);
```
- *Note:*  All variables must be of the same type. You cannot mix types in the same declaration.
You can also assign the same value to multiple variables at once:
```c
int x, y, z;
x = y = z = 50;
printf("%d", x + y + z);
```
- *Be careful: int x, y, z = 50; does not give all three variables the value 50. Only z gets it. x and y are declared, but they have no value yet.
- *Tip:* Declared multiple variables on one line is convenient, but declaring them on separate lines can make your code easier to read.
---
# **C Variable Names**
## C Variable Names
All C variables must be identified with unique names.
These unique names are called identifiers.
Identifiers can be short names (like x and y) or more descriptive names(age, sum, totalVolume).
-*Note:* It is recommended to use descriptive names in order to create understandable and maintainabe code:
```c
// Good variable name
int minutesPerHour = 60;

// OK, but not so easy to understand what m  actually is 
int m = 60;
```
The general rules for naming variables are:
- Names can contain letters, digits and underscores
- Names must begin with a letter or an underscore (_)
- Names are case-sensitive (myVar and myvar are different variables)
- Names cannot contain whitespaces or special characters like !, #, %, etc
- Reserved words (such as int) cannot be used as names
## Valid and Invalid Names
Here are some examples to help you remember the rules:
- Valid: age, _count, totalSum
- Invalid: 1age(starts with a number), my-age(contains - ), int(reserved word)
Naming style: Many C programmers use camelCase (like totalScore) or underscores (like total_score). Choose one style and use it consistently.
# **C Variables - Examples**
## Real-life Example
Often in our examples, we simplify variable names to match their data type (myint or myNum for *int* types, myChar for *char* types, and so on). This is done to avoid confusion.<br>
In real programs, variables often represent real-world data.
The following example stores information about a college student.
```c
// Student data
int studentID = 15;
int studentAge = 23;
float studentFee = 75.25;
char studentGrade = 'B';

// Print variables
printf("Student ID: %d\n", studentID);
printf("Student age: %d\n", studentAge);
printf("Student fee: %f\n", studentFee);
printf("Student grade: %c\n", studentGrade);
```
- **Notice:** Each variable stores a different type of information, but they are all used together in one program.
- *Tip:* %f prints six decimals by default, so studentFee is printed as 75.250000.
## Calculate the Area of a Rectangle
Variables are often used to store values, perform calculations, and then show the result. In this example, we calculate the area of a rectangle:
```c
// Create variables
int length = 4;
int width = 6;
int area;

// Calculate the area
area = length * width;

// Print the result
printf("Length is: %d\n", length);
printf("Width is: %d\n", width);
printf("Area of the rectangle is: %d", area);
```
- *Tip:* Calculations are usually done first, and the result is stored in a variable before being printed.
---
# **C Data Types**
## Data Types
A variable in C must be a specified data type, and you must use a format specifier inside the printf() function to display it.
```c
// Create variable
int myNum = 5; // Interger (whole number)
float myFloatNum = 5.99; // Floating point number
char myLetter = 'D'; // Character

// Print variables
printf("%d\n", myNum);
printf("%f\n", myFloatNum);
printf("%c\n", myLetter);
```
--
## Basic Data Types
The data type specifies the size and type of information the variable will store.
| Data type | Size | Description | Example |
| --- | --- | --- | --- |
| int | 2 or 4 bytes | Store whole numbers, without decimals | 1 |
| float | 4 bytes | Stores fractional numbers, containing one or more decimals. Sufficient 6-7 decimal digits. | 1.99 |
| double | 8 bytes | Stores fractional numbers, containing one or more decimals. Sufficient for storing 15 decimal digits. | 1.99 |
| char | 1 byte | Store a single character/letter/number, or ASCII values | 'A' |
## Basic Format Specifiers
There are different format specifiers for each data type. Here are some of them.
| Format specifier | Data Type |
| --- | --- |
| %d or %i | int | 
| %f or %F | float |
| %lf | double |
| %c | char |
| $s | strings |
- *Note:* It is important that you use the correct format specifier for the specified data type. If not, the program may produce errors or even crash.
# **C Character Data Types**
## The char Type
The *char* data type is used to store a single character.<br>
The character must be surrounded by single quotes, like 'A' or 'c', and we use the %c format specifier to print it
```c
char myGrade = 'A';
printf("%c", myGrade);
```
Alternatively,if you are familiar with ASCII (a standard that gives each character a number), you can use ASCII values to display certain characters. Note that thse values are not surrounded by quotes(' '), as they are numbers.
```c
char a = 65, b = 66, c = 67;
printf("%c\n", a);
printf("%c\n", b);
printf("%c", c);
```
## Character are stored as numbers
Inside the computer, every character is stored as a number. For example, 'A' is stored as 65.
if you print a char with %d instead of %c, you see the number
```c
char myLetter = 'A';

printf("%c\n", myLetter);  // A
printf("%d\n", myLetter);  // 65
```
## Notes on Characters
If you try to store more than a single character, it will only print the last character.
```c
char myText = 'Hello';
printf("%c", myText);
```
- *Note:* Don't use the *char* type for storing multiple characters, as it may produce errors.
To store multiple characters(or whole words), use strings (which you will learn more about in later chapter);
```c
char myText[] = "Hello";
printf("%s", myText);
```
- For now, just know that we use strings for storing multiple characters/text and the char type for single characters.
---
# **C Numeric Data Types**
## Numeric Types
Use *int* when you need to store a whole number without decimals, like 34 or 3999 and *float* or *double* when you need a floating point number (with decimals), like 9.99 03 3.14515
**int**
```c
int myNum = 1000;
printf("%d", myNum);
```
**float**
```c
float myNum = 5.75;
printf("%f", myNum);
```
```c
double myNum = 19.99;
printf("%lf", myNum);
```
**float ** vs **double**
- The precision of a floating point value tells how many digits it can store correctly, counting the digits both before and after decimal point. The precision of **float** is about six or seven digits, while **double** variables have a precision of about 15 digits. Therefore, it is often safer to use **double** for most calculations - but note that it takes up twice as much memory as **float** (8 bytes or 4 bytes)
Here you can see the difference. The number **1234567.89** has 9 digits, which is too many for a **float**
```c
float myFloat = 1234567.89;
double myDouble = 1234567.89;
printf("%f\n", myFloat);
printf("%lf", myDouble);
```
```text
1234567.875000
1234567.890000
```
The **float** could not store the number exactly, so the last digits are wrong. The **double** stores it correctly.
## Scientific Numbers
In C, you can write very large or very small floating point numbers using scientific notation.<br>This is done using the letter *e* (or E ), which stands for "times 10 to the power of".<br>For example, *35e3* means 35 * 10^3 = 350000.<br>
This is useful for writing numbers in a shorter way. Especiaally when working with scientific values or large-scale data.
```c
# include <stdio.h>

int main(){
    float f1 = 35e3;
    double d1 = 12E4;
    
    printf("%f\n", f1);
    printf("%lf\n", d1);
    return 0;
}
```
---
# **C Decimal Precision**
## Set decimal precision
You have probably already noticed that if you print a floating point number, the output will show many digits after the decimal point.
```c
# include <stdio.h>

int main(){
    float myFloatNum = 3.4;
    double myDoubleNum = 10.99;
    
    printf("%f\n", myFloatNum);
    printf("%lf\n", myDoubleNum);
    
}
```
```text
3.400000
10.990000
```
If you want to remove the extra zeros (set decimal precision), you can use a dot(.) followed by a number that specifies how many digits that should be shown after the decimal point.
```c
# include <stdio.h>

int main(){
    
    float myFloatNum = 3.5;
    
    printf("%f\n", myFloatNum); // default will show 6 digits after the decimal point
    printf("%.1f\n", myFloatNum);  //only show 1 digit
    printf("%.2f\n", myFloatNum);  //only show 2 digits
    printf("%.3f\n", myFloatNum);  //only show 3 digits
    printf("%.4f\n", myFloatNum);  //only show 4 digits
    return 5;
}
```
```text
3.500000
3.5
3.50
3.500
3.5000

...Program finished with exit code 5
```
## Rounding
When you set the precision, **printf()** does not just cut off the extra digits. It *rounds* the number to the nearest value.
```c
# include <stdio.h>

int main(){
    float myNum = 3.14159;
    
    printf("%.2f\n", myNum); // 3.14
    printf("%.3f\n", myNum); // 3.142
    printf("%.0f", myNum); // 3
    
    return 0;
}
```text
3.14
3.142
3
```