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
```
```text
3.14
3.142
3
```
# **C The size of Operator**
## Get the Memory Size
we introduced in the data types chapter that the memory size of a variable varies depending on the type.
| Data Type | Size |
| --- | --- |
| int | 2 or 4 bytes |
| float | 4 bytes |
| double | 8 bytes |
| char | 1 byte |

The memory size refers to how much space a type occupies in the *computer's memory*.<br>
To actually get the size (in bytes) of a data type or variable, use the **sizeof** operator.
```c
# include <stdio.h>

int main(){
    int myInt;
    float myFloat;
    double myDouble;
    char myChar;
    
    printf("%zu\n", sizeof(myInt)); // 4
    printf("%zu\n", sizeof(myFloat)); // 4
    printf("%zu\n", sizeof(myDouble)); // 8
    printf("%zu\n", sizeof(myChar)); // 1
    
    return 56;
}
```
- Note that we use the *%zu* format specifier to print the result, instead of %d. This is because the compliler expects the sizeof operator to return a value of type size_t, which is an usigned interger type. On some computers it might work with %d, but it is safer and more portable to use %zu, whidh is specifically designed for printing size_t values.
## Why should you know the size of Data Types?
Knowing the size of data helps you understand how much memory your program uses. This is important when writing larger programs or working with limited memory, because it can affect both performance and efficiency.<br>
For example, the size or a *char* type is 1 byte. Which means if you have an array o 1000 *char* values, it will occupy 1000 bytes (1kB) of memory.<br>
Using the right data type for the right pupose will **save memory** and **improve the performance** of your program.
---
# **C Data Types Example**
## Real-life Example
Here's a real-life example of using different data types, to calculate and output the total cost of a number of items:
```c
# include <stdio.h>

int main(){
    // Create variables of different data types
    int items = 50;
    float cost_per_item = 9.99;
    float total_cost = items * cost_per_item;
    char currency = '$';
    
    // Print variables
    printf("Number of items: %d\n", items);
    printf("Cost per item: %.2f %c\n", cost_per_item, currency);
    printf("Total cost = %.2f %c\n", total_cost, currency);
    
    return 56;
}
```
```text
Number of items: 50
Cost per item: 9.99 $
Total cost = 499.50 $

...Program finished with exit code 56
```
# **C Extended Types**
## More Data Types
Besides the basic (int, float, double, char), C also gives you **extended keywords** (short, long, unsigned) to control how large the numbers is, or whether it can be negative.
| Type | Size* | Range(commonly) | Format Specifier |
| --- | --- | --- | --- |
| short int | 2 bytes | -32,768 t0 32,767 | %hd |
| unsigned int | 2 or 4 bytes | 0 to 65,535(2 bytes) or  0 to 4,294,967,295(4 bytes) | %u |
| long int | 4 or 8 bytes | -2,147,483,648 to 2,147,483,647(4 bytes) or -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807(8 bytes) | %ld |
| long long int | 8 bytes | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | %lld |
| unsigned long int | 4 or 8 bytes | 0 to 4,294,967,295(4 bytes) or 0 to 18,446,744,073,709,615(8 bytes) | %lu |
| unsigned long long int | 8 bytes | 0 to 18,446,744,073,709,551,615 | %llu |
| long double | 8, 12or 16 bytes | Implementation-dependent, but more precision than *double* | %lf |

- **unsigned:** means the type can only store non-negative values (0 and up)
- **Note:** The size of these types can differ between systems (for example, 2 or 4 bytes, or 4 or 8 bytes), depending on whether the computer is older or newer, 32-bit or 64-bit, and which compiler is used.
Here is an example of how you can create and print these extended types:
```c
#include <stdio.h>

char main(){
    int normalInt = 1000;                                // standard int
    double normalDouble = 3.14;                          // standard double
    
    short int small = -100;                              // smaller int
    unsigned int count = 25;                             // only positive int
    long int big = 1234567890;                           // large int
    long long int veryBig = 9223372035854775807;         // very large int
    unsigned long long int huge = 18445744073709551615U; // very large, only positive
    long double precise = 3.141592653589793238L;         // extended precision
    
    printf("Normal int: %d\n", normalInt);
    printf("Normal double: %lf\n", normalDouble);
    printf("Small: %hd\n", small);
    printf("Count: %u\n", count);
    printf("Big: %ld\n", big);
    printf("Very Big: %lld\n", veryBig);
    printf("Huge: %llu\n", huge);
    printf("Precise: %.18lf\n", precise);
    
    return 'K';
    
}
```
```text
Normal double: 3.140000
Small: -100
Count: 25
Big: 1234567890
Very Big: 9223372035854775807
Huge: 18445744073709551615
Precise: 0.000000000000000000
```
- **Note:** These extended types are mostly used when you need very specific control over memory usage or number ranges
- **Note:** For everyday programming, int, float, double, and char are usually enough
## Check Size
*The exact sizes depend on your system and compiler. Remember that you can check them with the *sizeof* operator
```c
#include <stdio.h>

char main(){
    printf("Size of int: %zu bytes\n", sizeof(int));
    printf("Size of double: %zu bytes\n", sizeof(double));
    printf("Size of short int: %zu bytes\n", sizeof(short int));
    printf("Size of unsigned int: %zu bytes\n", sizeof(unsigned int));
    printf("Size of long int: %zu bytes\n", sizeof(long int));
    printf("Size of long long int: %zu bytes\n", sizeof(long long int));
    printf("Size of unsigned long long int: %zu bytes\n", sizeof(unsigned long long int));
    printf("Size of long double: %zu bytes\n", sizeof(long double));
    
    return 'K';
}
```
```text
Size of double: 8 bytes
Size of short int: 2 bytes
Size of unsigned int: 4 bytes
Size of long int: 8 bytes
Size of long long int: 8 bytes
Size of unsigned long long int: 8 bytes
Size of long double: 16 bytes
```
- **Tip:** When you really need exact control over the size of your numbers, you can use the fixed-width types which you will learn about later
- **Note:** This page is just to show you that C has other extended types, but for now we will keep focusing on the basic types (int, float, double, char)
---
# **C Type Conversion**
## Type Conversion
Sometimes, you have to convert the value of one data tyoe. This is known as **type conversion.**
<br>For example, if you try to divide two intergers, 5 by 2, you would expect the result to be 2.5. But since we are working with integers (and not floating-point values), the following example will just output 2: 

```c
# include <stdio.h>

char main(){
    int x = 5;
    int y = 2;
    int result = x/y;
    
    printf("%d", result);
    return 'K';
}
```
```text
2

...Program finished with exit code 75
```
To get the right result, you need to know how type conversion works.<br>
There are two types of conversion in C.
- **implicit Conversion** (automatically)
- **Explicit Conversion** (manually)
## Implicit Conversion
Implicit conversion is done automatically by the compiler when you assign a value of one type to another.<br>
For example, if you assign an *int* value to a *float* type
```c
# include <stdio.h>

char main(){
    
    // Automatic conversion: int to float
    float myFloat = 9;
    printf("%f", myFloat);
    
    return 'K';
}
```
```text
9.000000

...Program finished with exit code 75
```
As you can see, the compiler automatically converts the int value *9* to a float value of *9.000000*<br>
This can be risky, as you might lose control over specific values in certain situations. Especially if it was the other way around - the following example automatically converts the float value *9.99* to an int value of *9*:
```c
# include <stdio.h>

char main(){
    
    // Automatic conversion: float to int
    int myInt = 9.99;
    printf("%d", myInt);
    
    return 'K';
}
```
```text
9
...Program finished with exit code 75
```
What happended to *.99*?We might want that data in our program! So be careful. It is important that you know how the compiler works in these situations, to avoid unexpected results.
As another example, if you divide two intergers: *5* by *2*, you know that the result is *2.5*. And as you know from the beginning of this page, if you store the result as an interger, it will only display the number *2*. Therefore, it would be better to store the result as a *float* or a *double* , right?
```c
#include <stdio.h>

char main(){
    float result = 5/2;
    printf("%f", result);
    return 'K';
}
```
```text
2.000000

...Program finished with exit code 75
```
Why is the result 2.000000 and not 2.5? Well, it is because 5 and 2 are still integers in the division.<br>In this case, you need to manually convert the interger values to floating-point values.
## Explicit Conversion
Explicit conversion is done manually by placing the type in parenthesis () in front of the value. Considering our problem from the example above, we can now get the right result.
```c
#include <stdio.h>

char main(){
    float result =(float) 5/2;
    printf("%f", result);
    return 'K';
}
```
```text
2.500000

...Program finished with exit code 75
```
You can also place the type in front of a variable:
```c
#include <stdio.h>

char main(){
    int num1 =5;
    int num2 = 2;
    float result = (float) num1 / num2;
    printf("%f", result);
    return 'K';
}
```
```text
2.500000

...Program finished with exit code 75
```
- And since you learn about "decimal precision" in a previous chapter, you could make the output even cleaner by removing the extra zeros.**if you like**
```c
#include <stdio.h>

char main(){
    int num1 =5;
    int num2 = 2;
    float result = (float) num1 / num2;
    printf("%.1f", result);
    return 'K';
}
```
```text
2.5

...Program finished with exit code 75
```
## Real-life example
Here's a real-life example of data types and type conversion where we create a program to calculate the percentage of a user's score in relation to the maximum score in a game.
```c
#include <stdio.h>

char main(){
    // Set the maximum possible score in the game to 500
    int maxScore = 500;
    
    // The actual score of the user
    int userScore = 423;
    
    /* Calculate the percentage of the user's score in relation to the maximum available scrore.
    Convert userScore to float to make sure that the division is accurate */
    float percentage = (float) userScore / maxScore * 100.0;
    
    // Print the percentage
    printf("User's percentage is %.2f", percentage);
    return 'K';
}
```
```text
User's percentage is 84.60

...Program finished with exit code 75
```
# **C Constants**
## Constants
Now that you have seen different types of variables in C, you should also know that sometimes you need variables that should not change. This can be done with *const* keyword, which makes a variable *unchangeable* and *read-only*
```c
#include <stdio.h>

char main(){
    // myNum wil always be 15
    const int myNum = 15;
    
    // error: assignment of read-only variable 'myNum'
    myNum = 10;
    
    return 'K';
}
```
```text
main.c:8:11: error: assignment of read-only variable ‘myNum’
```
You should always declare a variable as *const* when you have values that should never change.
```c
const int minutesPerHour = 60;
const int monthsInYear = 12;\
```
## Notes on Constants
When you declare a contant variable, it must be assigned with a value
```c
const int minutesPerHour = 60;
minutesPerHour = 60; // error
```
## Good Practice
Another thing about constant variables, is that it is considered good practice to declare them with uppercase. It is not required, but useful for code readability and common for C programmers.
```c
const int BIRTHYEAR = 1980;
```
---
# **C Operators**
## Operators
Operators are used to perform operations on variables and values
In the example below, we use the + operator to add together two values.
```c
int myNum = 100 + 50;
```
Although the + operator is often used to add together two values, like in the example above, it can also be used to add together a variable and a value, or a variable and another variable.
```c
#include <stdio.h>

char main(){
    int sum1 = 100 + 50; //150
    int sum2 = sum1 + 250; //400
    int sum3 = sum2 + sum2; //800
    printf("%d", sum3);
    return 'K';
}
```
```text
800

...Program finished with exit code 75
```
C divides the operators into the following groups:
- Arithmetic operators
- Assignment operators
- Comparison operators
- Logical operators
- Bitwise operators(advanced)
---
# **C Arithmetic Operators**
## Arithmetic Operators
Arithmetic operators are used to perform common mathematical operations.
| Operator | Name | Decription | Example |
| --- | --- | --- | --- |
| + | Addition | Adds together two values | x + y |
| - | Subtraction | Subtracts one value from another | x - y |
| * | Multiplication | Multiplies two values | x * y |
| / | Division | Divides one x/y value by another | x / y |
| % | Modulus | Returns the division remainder | x % y |
| ++ | Increment | Increases the value of a variable by 1 | ++x |
| -- | Decrement | Decreases the value of a variable by -1 | --x |

Here is an example using different arithmetic operators in one example.
```c
#include <stdio.h>

char main(){
    int x = 10;
    int y = 3;
    
    printf("%d\n", x + y);
    printf("%d\n", x - y);
    printf("%d\n", x * y);
    printf("%d\n", x / y);
    printf("%d\n", x % y);
     
    int z = 5;
    ++z;
    printf("%d\n", z);
    --z;
    printf("%d\n", z);
    --z;
    printf("%d\n", z);
    return 'K';
}
```text
13
7
30
3
1
6
5
4

...Program finished with exit code 75
```
- **Note:** When dividing two intergers in C, the result will also be an interger. For example, 10/3 gives 3. If you want a decimal result, use float or double values, like 10.0 / 3
```c
#include <stdio.h>

char main(){
    int a = 10;
    int b = 3;
    printf("%d\n", a / b); // Interger division
    
    double c = 10.0;
    double d = 3.0;
    printf("%f\n", c / d); // Decimal division
    return 'K';
}
```
```text
3
3.333333

...Program finished with exit code 75
```
## Incrementing and Decrementing
Incrementing and decrementing are very common in programming, especially when working with counters, loops, and arrays. The ++ operator increases a value by 1, while the -- operator decreases a value by 1.
```c
#include <stdio.h>

char main(){
    int x = 5;
    ++ x; // Increment x by 1
    printf("%d\n", x);
    return 'K';
}
```
```text
6

...Program finished with exit code 75
```
```c
#include <stdio.h>

char main(){
    int x = 5;
    -- x; // Decrement x by 1
    printf("%d\n", x);
    return 'K';
}
```
```text
4

...Program finished with exit code 75
```
Sometimes, you might both increment and decrement the same variable. Remember that if you increase a value and later decrease it, it will go up one and then back down by one - ending up where it started:
## real Life Example:Counting People
Imagine you are building a program to count how many people enter and leave a room. You can use ++ to increase the counter when someone enters, and -- to decrease it when someone leaves.
```c
#include <stdio.h>

char main(){
    int peopleInRoom = 0;

    // 3 people enter
    peopleInRoom++;
    peopleInRoom++;
    peopleInRoom++;

    printf("%d\n", peopleInRoom);

    // 1 person leaves
    peopleInRoom--;

    printf("%d\n", peopleInRoom);
    return 'K';
}
```
```text
3
2

...Program finished with exit code 75
```
## Prefix and Postfix
The ++ and -- operators can be written *before* the variable (prefix, like ++x) or after it (postfix, like x++). On their own, both add 1 to x. The difference shows when you use the value in the same statement.
- ++x increases x first, and then uses the new value.
- x++ uses the current value first, and then increases x
```c
#include <stdio.h>

char main(){
    int x = 5;
    int y = ++x; //x is increased first, then y gets 6
    printf("x = %d, y= %d\n", x, y); // x = 6, y = 6
    
    int a = 5;
    int b = a++; // b gets 5 first, then a is increased
    printf("a =%d, b = %d\n", a, b); // a = 6, b = 5
    return 'K';
}
```
```text
x = 6, y= 6
a =6, b = 5

...Program finished with exit code 75
```
# **C Assignment Operators**
## Assignment operators
Assignment operators are used to assign values to variables. In the example below, we use the assignment operator (=) to assign the value *10* to a variable called *x*
```c
int x = 10;
```
The **addition assignement** operator (+=) addds a value to a variable.
```c
#include <stdio.h>

char main(){
    int x = 10;
    x += 5;
    printf("%d", x);
    return 'K';
}
```
```text
15

...Program finished with exit code 75
```
A list of all assignment operators:
| Operator | Example | Same As |
| --- | --- | --- |
| = | x = 5 | x = 5 |
| += | x += 3 | x = x + 3 |
| -= | x -= 3 | x = x - 3 |
| *= | x *= 3 | x = x * 3 |
| /= | x /= 3 | x = x / 3 |
| %= | x %= 3 | x = x % 3 |
| &= | x &= 3 | x = x & 3 |
| ^= | x ^= 3 | x = x ^ 3 |
| >>= | x >>= 3 | x = x >> 3 |
| <<= | x <<= 3 | x = x << 3 |

- **Most:** Most assignment operators are just shorte ways of writing code. For example, x += 5 is the same as x = x + 5, but shorter and often easier to read.
## Real-Life Example: Tracking Savings
Assignment operators can also be used in real-life scenarios. For example, you can use the += operator to keep track of savings when you add money to an account.
```c
#include <stdio.h>

char main(){
    int savings = 100;
    savings += 50; // add 50 to savings
    printf("Total savings: %d\n", savings);
    return 'K';
}
```
```text
Total savings: 150

...Program finished with exit code 75
```
---
# **C Comparison Operators**
## Comparison Operators
Comparison operators are used to compare two values or variables. This is important in programming, because it helps us to find answers and make decisions. <br>
The return value of a comparison is either 1 or 0, which means true(1) or false(0). These values are known as Boolean values, and you will learn more about them in the Boolean and if else chapters.<br>
In the following example, we use the greater than operator(>) to find out if 5 is greater than 3.
```c
# include <stdio.h>
char main(){
    int x = 5;
    int y = 3;
    printf("%d", x > y); // returns 1 (true) because 5 is greater than 3
    return 'K';
}
```
```text
1

...Program finished with exit code 75
 ```
A list of all comparison operators.
| Operator | Name | Example | Description |
| --- | --- | --- | --- |
| == | Equal to | x == y | Returns 1 if the values are equal |
| != | Not equal | x != y | Returns 1 if the values are not equal |
| > | Greater than | x > y | Returns 1 if the first value is greater than the second value |
| > | Less than | x < y | Returns 1 if the first value is less than the second value |
| >= | Greater than or equal to | x >= y | Returns 1 if the first value is greater than, or equal to, the second value |
| <= | Less than or equal to | x <= y | Returns 1 if the first value is less than, or equal to, the second value |
## Real-Life Examples
Comparison operators are often used in real-world conditions, such as checking if a person is old enough to vote:
```c
# include <stdio.h>
char main(){
    int age = 18;
    
    printf("%d\n", age >= 18); // 1(true), old enough to vote
    printf("%d\n", age < 18);  // 0(false)
    return 'K';
}
```
```text
1
0

...Program finished with exit code 75
```
Another common use is checking if a password is long enough.
```c
# include <stdio.h>
char main(){
    int passwordLength = 5;
    
    printf("%d\n", passwordLength >= 18); // 0 (false), too short
    printf("%d\n", passwordLength < 18);  // 1 (true), needs more characters
    return 'K';
}
```
```text
0
1

...Program finished with exit code 75
```
---
# **C Logical Operators**
## Logical Operators
As with comparison operators, you can also test for true or false values with logical operators. Logical operators are used to determine the logic between variables or values, by combining multiple condtins:
| Operator | Name | Example | Description |
| --- | --- | --- | --- |
| | OR | x > 3 or x < 4 | Returns 1 if both statements are true |
| && | AND | x > 3 && x < 10 | Returns 1 if both statements are true |
| ! | NOT | !(x>3 && x<10) | Reverses the result, returns 0 if the result is 1 |

## Real-life Example: logic Check
The example below shows you how logical operators can be used in real situation, e.g. when checking login status and access rights.
```c
# include <stdio.h>
char main(){
    int isLoggedIn = 1;
    int isAdmin = 0;
    printf("Regular user: %d\n", isLoggedIn && isAdmin);
    printf("Has access: %d\n",isLoggedIn || isAdmin);
    printf("Not logged in: %d\n", !isLoggedIn);
    return 'K';
}
```
```text
Regular user: 0
Has access: 1
Not logged in: 0

...Program finished with exit code 75
```
- Remember, in C 1 mans true and 0 means false. Logical operators often become easier to understand once you start using them inside if statements, which you will learn about in the upcoming chpaters.
---,
# **C Operator Precedence**
## Operator Precedence
When a calculation contains more than one operator, C follows order of operations rules to decide which part to calculate first.
For example, multiplication happens before addition.
```c
# include <stdio.h>
char main(){
    int result1 = 10 - 2 + 5; // (10 - 2) + 5 = 13
    int result2 = 10 - (2 + 5); // 10 - 7 = 3
    printf("%d\n", result1);
    printf("%d\n", result2);
    return 'K';
}
```
```text
13
3
```
## Why does this Happen?
In 2 + 3 + 4, the multiplication is done first, so the answer is 14. If you want the addition to happen first, you must use parentheses (2 + 3) * 4, which gives 20.
- *Tip:* Always use parenthesis ( ) If you want to make sure the calculation is done in the order you expect. It also makes your code easier to read.
## Order of Operations
Here are some common operators in C, from highest to lowest priority
- () - Parentheses
- *, /, % - Multiplication, Division, Modulus
- +, - - Addtion, Subtraction
- >, <, <=, >= - Commparison
- ==, != - Equality
- && - Logical AND
- || - logical OR
- = - Assignment
## Another Example
Subtraction and addition are done from left to right, unless you add parantheses.
```c
# include <stdio.h>
char main(){
    int result1 = 10 - 2 + 5;
    int result2 = 10 - (2 + 5);
    int result3 = 10 - 2 + 5 - 3;
    printf("%d\n", result1);
    printf("%d\n", result2);
    printf("%d\n", result3);
    return 'K';
}
```
```text
13
3
10
```
- **Remember:** Parentheses always come first. Use them to control the order of your calculations.
# **C Booleans**
## Booleans
Very often, in programming, you will need a data type that can only have one of two values, like:
- YES/NO
- ON/OFF
- TRUE/FALSE
For this, C has a bool data type, which is known as *booleans*. Booleans represent one of two values: *true* and *false*
## Boolean Variables
In C, the bool type is not a built-in data type, like *int* or *char*. It was introduced in C99, and you must *include* the following header file to use it.
```c
#include <stdbool.h>
```
A boolean variable is declared with the *bool* keyword and can take the values *true* or *false*
```c
bool isProgrammingFun = true
bool isFishTasty = false
```
Before trying to print the boolean variables, you should know that boolean values are returned as intergers.
- 1 (or any other number that is not 0) represents true
- 0 represents false
Therefore, you can use %d format specifier to print a boolean value.
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    // Create boolean variables
    bool isProgrammingFun = true;
    bool isFishTasty = false;
    
    // Print boolean values
    printf("%d\n", isProgrammingFun); // Prints 1 (true)
    printf("%d", isFishTasty); // Prints 0 (false)
    return 'K';
}
```
However, it is more common to get boolean values by comparing values and variables.
## Comparing values and Variables
Comparing values is useful programming because they help us to find answers and make decisions. For example, you can use a comparisont operator such as the greater than (>) operator to compare two values.
```c
#include <stdio.h>
char main(){
    printf("%d", 10 > 9); // Prints 1 (true), because 10 is greater than 9
    return 'K';
}
```
- In C, comparisons return 1 (true) or 0 (false)
You can also compare two variables.
```c
#include <stdio.h>
char main(){
    int x = 10;
    int y = 9;
    printf("%d", x > y); // Prints 1 (true)
    return 'K';
}
```
In the example below, we use the equal to (==) operators to compare different values.
```c
#include <stdio.h>
char main(){
    printf("%d\n", 10 == 10); // Prints 1 (true), because 10 is equal to 10
    printf("%d\n", 10 == 15); // prints 0 (false), because 10 is not equal to 15
    printf("%d", 5 == 55); // Prints 0 (false), because 5 is not equal to 55
    return 'K';
}
```
You are not limited to comparing numbers. You can also compare boolean variables.
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    bool isHumburgerTasty = true;
    bool isPizzaTasty = true;
    
    // Check if both have the same value (both true, or both false)
    printf("%d", isHumburgerTasty == isPizzaTasty);
    return 'K';
}
```
- Rememb*er to include the <stdbool.h> header file working with *bool* variables.
## Storing comparison results
You can also store the result ot a comparison in *bool* variable
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    int x = 10;
    int y = 9;
    bool isGreater = x > y;
    printf("%d", isGreater); // Prints 1 (true)
    return 'K';
}
```
- *Note:* It is up to you whether you store the result of a comparison in boolean variable or use the comparison directly. Storing the result can make your code easier to read, especially if you want to reuse it.
# **C Boolean Example**
## Real Life Example
Let's use booleans in a real-life example where we want to find out if a person is old enough to vote. In the example below, we use the >= comparison operator to find out if the age (25) is greater than or equal to the voting age limit, which is set ot 18
```c
#include <stdio.h>
char main(){
    int myAge = 25;
    int votingAge = 18;
    
    printf("%d", myAge >= votingAge);
    // Returns 1 (true), meaning 25 year olds are allowed to vote!
    return 'K';
}
```
An even better approach is to wrap the code above in an if ... else statment, so we can perform different actions depending on the result.
**Example**
Output "Old enough to vote!" if myAge is greater than or equal to 18. Otherwise output "Not old enough to vote"
```c
#include <stdio.h>
char main(){
    int myAge = 17;
    int votingAge = 18;
    if (myAge >= votingAge){
        printf("Old enough to vote!");
    }else{
        printf("Not old enough to vote.");
    }
    return 'K';
}
```
```text
Not old enough to vote.

...Program finished with exit code 75
```
Booleans are the basis for all comparisons and conditions. You will learn more about conditions (if ... else )
---
# **If ... Else**
## Conditions and if Statements
You already know that C supports familiar comparison conditions from mathematics, such as:
- less than a < b
- less than or equal to a <= b
- greater than a > b
- equal to a == b
- not equal to a != b
You can use these conditions to perform different actions for different decisions. C has the following conditional statements.
- Use if to specify a block of code to be executed, if a specified condtion is true
- Use else to specify a block of code to be executed, if the same codition is false
- Use else if to specify a new condition to test, if the condition is false
- Use switch to specify many alternative blocks of code to be executed
## The if Statement
Use the if statement to specify a block of code to be executed if a condition is true
```c 
if (condition){
    // block of code to be executed if the condition is true
}
```
- **Note:** if is written in lowercase letters. Uppercase letters (If or IF) will generate an error.
In the Example below, we test two values to find out if 20 is greater than 18. If the condition is true, we print a message.
```c
#include <stdio.h>
char main(){
    if (20 > 18){
        printf("20 is greater than 18");
    }
    return 'K';
}
```
```text
20 is greater than 18
```
We can also test variables:
```c
#include <stdio.h>
char main(){
    int x = 20;
    int y = 18;
    if (x > y){
        printf("x is greater than y");
    }
    return 'K';
}
```
```text
x is greater than y
```
## Using a Boolean Variable
Since the condition in an if statement must be either true or false, you can store the result in a boolean variable instead of writing the comparison directly.
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    int x = 20;
    int y = 18;
    bool isGreater = x > y;
    if (isGreater){
        printf("x is greater than y");
    }
    return 'K';
}
```
```text
x is greater than y
```
This can make your code easier to read, especially when the condition is complex or used more than once.
---
# **C else**
## The else Statement
Use the else statement to specify a block of a code to be executed if the condition is false
```c
if (condition){
    // block of code to be executed if the condition is true
} else {
    // block of code to be executed if the condition is false
}
```
In the example below, the program checks the value of *time.* If it less than 18, it prints "Good day." Otherwise, it prints "Good evening"
```c
#include <stdio.h>
char main(){
    int time = 20;
    if (time < 18){
        printf("Good day.");
    } else {
        printf("Good evening.");
    }
    return 'K';
}
```
```text
Good evening.
```
## Using a boolean variable
You can also store the condition in a boolean variable and use it in the if .. else statement. This can make the code easier to read.
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    int time = 20;
    bool isDay = time < 18;
    if (isDay){
        printf("Good day.");
    } else {
        printf("Good evening.");
    }
    return 'K';
}
```
```text
Good evening.
```
- *Tip:* A name like isDay makes it easy to understand what the condition means.
---
# **C Else If**
## The else if statement
Use the else if statement to specify a new condition to test if the first condition is false. You can use else if to check multiple conditions, one after another.
```c
if (condition1){
    // block of code to be executed if condition1 is true
} else if (condition2){
    // block of code to be executed if condition1 is false and condition2
} else {
    // block of code to be executed if both conditions are false
}
```
The condition are checked from top to bottom. As soon as one condition is true, its block of code runs, and the rest are skipped.
**Example**
In the example below, we decide which message to print based on the value of time:
```c
#include <stdio.h>
char main(){
    int time = 16;
    if (time < 12){
        printf("Good morining.");
    } else if (time < 18){
        printf("Good day.");
    } else {
        printf("Good evening.");
    }
    return 'K';
}
```
```text
Good day.

...Program finished with exit code 75
```
**Example explained**
The value of time is 16. The first condition (time<12) is false, but the second condition (time<18) is true. Because of this, the code inside the else if block runs and "Good day." is printed. If the value of time was 22,none of the conditions would be true, and program would print "Good evening." instead.
## Using boolean variables
Just like with if statements, you can store conditions in boolean variables and use them with else if.
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    int time = 16;
    
    bool isMorning = time < 12;
    bool isDay = time < 18;
    
    if (isMorning){
        printf("Good morning.");
    } else if (isDay){
        printf("Good day.");
    } else {
        printf("Good evening.");
    }
    return 'K';
}
```
```text
Good day.

...Program finished with exit code 75
```
- *Tip:* Boolean variable names like *isMorning* and *isDay* make it easier to understand what each condition means.
