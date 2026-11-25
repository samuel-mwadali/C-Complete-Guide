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
---
# **C Short Hand If Else**
## Short Hand if ... Else (Ternary Operator)
There is also a short-hand if ... else, known as the ternary operator because it uses three operands. The ternary operator returns  value; otherwise, it returns the second value. It can be used to replace multiple lines of code with a single line, and is often used to replace simple if ... else statements.
```c
variable = (condition) ?
expressionTrue : expressionFalse;
```
insted of writing
```c
#include <stdio.h>
char main(){
    int time = 16;
    if (time < 18){
        printf("Good day.");
    } else {
        printf("Good evening.");
    }
    return 'K';
}
```
```text
Good day.
```
You can simply write
```c
#include <stdio.h>
char main(){
    int time = 20;
    (time < 18) ? printf("Good day."):
    printf("Good evening.");
    return 'K';
}
```
```text
Good evening.
```
The ternary operator is most useful when you want to choose between two values. In th example, it finds the largest of two numbers.
```c
#include <stdio.h>
char main(){
    int a = 10;
    int b = 20;
    int max = (a > b) ? a : b;
    printf("The largest number is %d", max);
    return 'K';
}
```
It is completely up to you if you want to use the traditional if ... statement or the ternary operator.
---
# **C Nested If**
## Nested If
You can also place an if statement inside another if. This is called a nested if statement. A nested if lets you check for a condition only if another condition is already true.
```c
if (conditional){
    // code to run if conditional is true
    if (conditional){
        // code to run if both conditional and condition2 are true
    }
}
```
**Example**
In this example, we first check if x is greater than 10. If it is, we then check if y is greater than 20.
```c
#include <stdio.h>
char main(){
    int x = 15;
    int y = 25;
    
    if (x > 10){
        printf("x is greater than 10\n");
        
        //Nested if
        if (y > 20){
            printf("y is greater than 20\n");
        }
    }
    return 'K';
}
```
```text
x is greater than 10
y is greater than 20
```
## Real-Life Example
Nested if statements are useful when you need to test multiple conditions that depend on each other. For example, checking if a person is old enough to vote, and if they are a citizen.
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    int age = 20;
    bool isCitizen = true;
    if (age >= 18){
        printf("Old enough to vote.\n");
        
        if (isCitizen){
            printf("And you are a citizen, so you can vote!\n");
        } else {
            printf("But you must be citizen to vote.\n");
            } 
        }
        else {
            printf("Not old enough to vote.\n");
            }
    
    return 'K';
}
```
```text
Old enough to vote.
And you are a citizen, so you can vote!
```
## Notes
- You can nest as many if statements as you want, but avoid making the code too deep - it can become hard to read
- Nested if is often used together with else and else if for more complex decision making.
# **C Logical Operators in Conditions**
## Logical Operators in Conditions
You can combine or reverse conditions using logical operators. These work together with if, else, and else if to build more complex decisions.
- &&(AND) - all conditions must be true
- || (OR) - at least one conditions must be true
- ! (NOT) - reverses a condition (true -> false, false -> true)
## AND(&&)
Use AND (&&) when both conditions must be true
```c
#include <stdio.h>
char main(){
    int a = 200;
    int b = 33;
    int c = 500;
    if (a > b && c > a){
        printf("Both conditions are true\n");
    }
    return 'K';
}
```
```text
Both conditions are true
```
## OR(||)
Use OR (||) when at least one of the condtions can be true.
```c
#include <stdio.h>
char main(){
    int a = 200;
    int b = 33;
    int c = 500;
    if (a > b || a > c){
        printf("Both conditions are true\n");
    }
    return 'K';
}
```
```text
Both conditions are true
```
## NOT(!)
The NOT operator (!) reverses a condition
- if a condition is true, ! makes it false
- if a condition is false, ! makes it true
This is useful when you want to check that something in not the case:
```c
#include <stdio.h>
char main(){
    int a = 33;
    int b = 200;
    if (!(a > b)){
        printf("a is NOT greater than b\n");
    }
    return 'K';
}
```
```text
a is NOT greater than b
```
## Real-Life Example
In real programs, logical operators are often used for access control. For example, to get access to a system, there are specific requirements. You must be logged in, and then you either need to be admin, or have a high security clearance (level 1 or 2)
```c
#include <stdio.h>
#include <stdbool.h>
char main(){
    bool isLoggedIn = true;
    bool isAdmin = false;
    int securityLevel = 1; // 1 = highest

    if (isLoggedIn && (isAdmin || securityLevel <= 2)){
        printf("Access granted\n");
    } else {
        printf("Access denied\n");
    }
    return 'K';
}
// Try changing securityLevel and isAdmin to test different outcomes:
// SecurityLevel 1 = Access granted
// SecurityLevel 2 = Access granted
// SecurityLevel 3 = Access denied
// SecurityLevel 4 = Access denied
// If isAdmin = true, access is granted.
```
```text
Access denied
```
# **C If ... Else Examples**
## Real-Life Examples
This example shows how you can use if ... else to "open a door" if the user enters the correct code.
```c
#include <stdio.h>
char main(){
    int doorCode = 2340;
    if (doorCode = 2340){
        printf("Correct code.\nThe door is now open.");
    } else {
        printf("Wrong code.\nThe door remains closed.");
    return 'K';
}
}
```
```text
Correct code.
The door is now open.
```
This example shows that how you can use if ... else to find out if a number is positive or negative:
```c
#include <stdio.h>
char main(){
    int myNum = -10;
    // Is this a posive number or negative number?
    if (myNum > 0){
        printf("The value is a positve number.");
    } else if (myNum){
        printf("The value is a negative number.");
    } else {
        printf("The value is 0.");
    }
    return 'K';
}
```
```text
The value is a negative number.
```
# **C Switch**
## Switch statement
Instead of writing many if ... else statements, you can use the switch statement. The switch statements selects one of many code blocks to be executed.
```c
switch (expression){
    case x:
    // code block
    break;
    casey:
    // code block
    break;
    defalult:
    // code block
}
```
This is how it works:
- The switch expression is evaluated once
- The value of the expression is compared with the values of each case
- If there is a match, the associated block of code is executed.
- The break statement breaks out of switch block and stops the execution
- The default statement is optional, and specifies some code to run if there is no case match
The example below uses the weekday number to calculate the weekly name.
```c
#include <stdio.h>
char main(){
    int day = 4;
    switch (day){
        case 1:
            printf("Monday");
            break;
        case 2:
            printf("Tuesday");
            break;
        case 3:
            printf("Wednesday");
            break;
        case 4:
            printf("Thurday");
            break;
        case 5:
            printf("Friday");
            break;
        case 6:
            printf("Saturday");
            break;
        case 7:
            printf("Sunday");
    }
    return 'K';
}
```
```text
Thurday
```
## The break keyword
When C reaches a break keyword, it breaks out of the switch block. This will stop the execution of more code and case tessting inside the block. Without break, C does not stop at the end of the matching case. It continues to run the code in the next cases too, until it reaches a break or the end of the switch. This is called **fall-through.**
```c
#include <stdio.h>
char main(){
    int day = 2;
    switch (day){
        case 1:
            printf("Monday");
            break;
        case 2:
            printf("Tuesday");
        case 3:
            printf("Wednesday");
            break;
        case 4:
            printf("Thurday");
            break;
        case 5:
            printf("Friday");
            break;
        case 6:
            printf("Saturday");
            break;
        case 7:
            printf("Sunday");
    }
    return 'K';
}
```
```text
TuesdayWednesday
```
Here, case 2 matches, so "Tuesday" is printed. There is no break, so C continues into case 3 and also prints "Wednesday". Then it reaches a break and stops.
- *Tip:* End each case with break, unless you want the code to continue into the next case.
## The default Keyword
The default keyword specifies some code to run if there is no case match:
```c
#include <stdio.h>
char main(){
    int day = 4;
    switch (day) {
        case 6:
        printf("Today is Saturday");
        break;
        case 7:
        printf("Today is Sunday");
        break;
        default:
        printf("Looking forward to the Weekend");
    }
    return 'K';
}
```
```text
Looking forward to the Weekend
```
- *Note:* The default case is usually written last in the switch. When it is last, it does not need a break.
## Combine cases
Sometimes, several values should run the same code. Then you can write the cases after each other, and let them share one block of code.
```c
#include <stdio.h>
char main(){
    int day = 6;
    switch (day) {
        case 6:
        case 7:
        printf("Weekend");
        break;
        default:
        printf("Weekday");
    }
    return 'K';
}
```
```text
Weekend
```
Code 6 has no code of its own, so C falls through to the code under 7. The means that both 6 and 7 print "Weekend". For all values, the default code runs.
---
# **C While Loop**
## Loops
Loops can execute a block of code as long as a specified condition is true. Loops are handy because they save time, reduce errors, and they make code more readable.
## While loops
The whle loop repeats a block of code as long as a specified condition is true
```c
while (condition){
    // code block to be executed
}
```
In the example below, the code in the loop will run, over and over again, as long as a variable (i) is less than 5.
```c
#include <stdio.h>
char main(){
    int i = 0;
    while (i < 5){
        printf("%d", i);
        i++;
    }
    return 'K';
}
```
```text
01234
```
- **Note:** Do not forget to increase the variable used in the condition (i++), otherwise the loop will never end! Do you wonder why we use the letter i as a variable name? It's a counter variable and a common choice in simple loops because it's short, traditional, and stands for 'index' or 'iterator'.
## Countdown Example
You can also use a while loop to count down. This example counts from 3 to 1, and then prints "Go!" at the end.
```c
#include <stdio.h>
char main(){
    int countdown = 3;
    while (countdown > 0){
        printf("%d\t", countdown);
        countdown --;
    }
    printf("Go! \n");
    return 'K';
}
```
```text
3       2       1       Go!
```
## While Loop with False condition
In the previous examples, the condition was true at the start, so the loop ran one or more times. But if the condition is false at the beginning, the code inside the loop will never run:
```c
#include <stdio.h>
char main(){
    int i = 10;
    while (i < 5){
        printf("This will never be printed\n");
        i ++;
    }
    return 'K';
}
```
- **Note:** A while loop may never run if the condition is false from the start. In the next chapter, you will learn about the do while loop, which always runs the code at least once before checking the condition.
# **Do/While Loop**
## The Do/While Loop
The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.
```c
do{
    //code block to be executed
}
while(condition);
```
The example below uses a do/while loop. The loop will always be executed at least once, even if the condition is a false, because the code block is executed before the condition is tested.
```c
#include <stdio.h>
char main(){
    int i = 0;
    do{
        printf("%d\n", i);
        i ++;
    }
    while (i < 5);
    return 'K';
}
```
- Do not forget to increase the variable used in the condition, otherwise the loop will never end!
## Condition is False from the start
In the example above, the condition i < 5 was true at the beginning, so the loop executed multiple times. But what if the condition is false right from the start?
In the example below, the variable i starts at 10, so the condition i < 5 is false immediately - yet the do/while loop stills runs once:
```c
#include <stdio.h>
char main(){
    int i = 0;
    do{
        printf("i is %d\n", i);
        i ++;
    }
    while (i < 5);
    return 'K';
}
```
```text
i is 0
i is 1
i is 2
i is 3
i is 4
```
## Summary
The do/while loop always runs at least once, even if the condition is already false. This is different from a regular while loop, which would skip the loop entirely if the condition is false at the start.<br> This behaviour makes do/while useful when you want to ensure something happens at least once, like showing a message or asking  for user input.
## Practical Esample: User Input
This example keeps asking the user to enter a positive number. The loop stops when the user enters 0 or a negative number.
```c
#include <stdio.h>
char main(){
    int i = 0;
    do{
        printf("i is %d\n", i);
        i ++;
    }
    while (i < 5);
    return 'K';
}
```
- **Note:** You will learn about the scanf() function and user input in a later chapter.
# **C While Loop Examples**
## Real-life Examples
To demonstrate a practical example of the while loop, we have created a simple "countdown" program
```c
#include <stdio.h>
char main(){
    int countdown = 3;
    
    while (countdown > 0){
        printf("%d\n", countdown);
        countdown--;
    }
    printf("Happy New Year!!\n");
    return 'K';
}
```
In this example, we create a program that only print even numbers between 0 and 10 (inclusive).
```c
#include <stdio.h>
char main(){
    int i = 0;
    while (i <= 10){
        printf("%d\n", i);
        i += 2;
    }
    return 'K';
}
```
In this example we use a while loop to reverse some numbers.
```c
#include <stdio.h>
char main(){
    // A variable with some specific numbers
    int numbers = 12345;
    // A variable to store the reversed number
    int revNumbers = 0;
    // Reverse and reorder the numbers
    while (numbers){
        // Get the last number of 'numbers' and add it to 'revNumber'
        revNumbers = revNumbers * 10 + numbers % 10;
        // Remove the last number of 'numbers'
        numbers /= 10;
    }
    return 'K';
}
```
To demonstrate a practical example of the while loop combined with an if else statement, let's say we play a game of Yatzy:
```c
#include <stdio.h>
char main(){
    int dice = 1;
    while (dice <= 6){
            if (dice < 6){
                printf("No Yatzy\n");
            } else {
                printf("Yatzy!\n");
                }
    }
    dice = dice + 1;
    return 'K';
}
```
If the loop passes the values ranging from 1 to 5, it prints "No Yatzy". Whenever it passes the value 6, it prints "Yatzy!".
---
# **C For Loop**
## For Loop
When you know exactly how many times you want to loop through a block of code, use the for loop instead of a while loop:
```c
for (statement 1; statement 2; statement 3){
    // code block to be executed
}
```
Statement 1 is executed (one time) before the execution of the code block
Statement 2 defines the condition for executing the code block.
Statement 3 is executed (every time) after the code block has been executed
## Print Numbers
The example below will print the numbers 0 to 4:
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 0; i < 5; i++){
        printf("%d\n", i);
    }
    return 'K';
}
```
**Example**
- Statement 1 sets a variable before the loop starts: i = 0
- Statement 2 defines the condition for the loop to run: i < 5. If the condition is true, the loop will start over again, if it is false, the loop will end.
- Statement 3 increases a value each time the code block in the loop has been executed: i++
- **Tip:** In newer versions of C (C99 and later), you can also declare the variable inside the loop: for (int i = 0; i < 5; i++). Then i only exists inside the loop.
## Print Even Numbers
This example prints even values between 0 and 10
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 0; i <= 10; i = i + 2){
        printf("%d\n", i);
    }
    return 'K';
}
```
## Sum of Numbers
This example calculates the sum of numbers from 1 to 5:
```c
#include <stdio.h>
char main(){
    int sum = 0;
    int i;

    for (i = 1; i <= 5; i++){
        sum = sum + i;
    }
    printf("Sum is %d", sum);
}
```
## Countdown
This example prints a countdown from 5 to 1;
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 5; i > 0; i--){
        printf("%d\n", i);
    }
    return 0;
}
```

# **C Nested Loops**
## Nested Loops
It is also possible to place a loop inside another loop. This is called a nested loop. The 'inner loop' will be executed one time for each iteration of the "outer loop".
```c
#include <stdio.h>
char main(){
    int i, j;
    // Outer loop
    for (i = 1; i <= 3; ++i){
        printf("Outer: %d\n", i); // Executes 2 times
        for(j = 1; j <= 3; ++j){
            printf(" inner: %d\n", j); // Executes  6 times (2 * 3)
        }
    }
    return 'K';
}
```
```text
Outer: 1
 inner: 1
 inner: 2
 inner: 3
Outer: 2
 inner: 1
 inner: 2
 inner: 3
Outer: 3
 inner: 1
 inner: 2
 inner: 3
```
## Multiplication Table Example
This example uses nested loops to print a simple multiplication table (1 to 3):
```c
#include <stdio.h>
char main(){
    int i, j;
    // Outer loop
    for (i = 1; i <= 3; ++i){
        for(j = 1; j <= 3; ++j){
            printf("%d", i * j); // Executes  6 times (2 * 3)
        }
        printf("\n");
    }
    return 'K';
}
```
```text
123
246
369
```
Nested loops are useful when working with tables, matrices or multi-dimensional data structures
# **C For Loop Examples**
## Real-Life Examples
To demonstrate a practical example of the for loop, let's create a program that counts to 100 by tens.
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 0; i <= 100; i += 10){
    printf("%d\n", i);
}
    return 'K';
}
```
```text
0
10
20
30
40
50
60
70
80
90
100
```
In this example, we create a program that only print even numbers between 0 and 10 (inclusive).
```c
#include <stdio.h>
char main(){
    int i;
    for(i = 0; i <= 10; i = i + 2){
        printf("%d\n", i);
    }
    return 'K';
}
```
```text
0
2
4
6
8
10
```
And in this example, we create a program that prints the multiplication table for a specified number:
```c
#include <stdio.h>
char main(){
    int number = 2;
    int i;
    // Print the multiplication table for the number 2
    for (i = 1; i <= 10; i++){
            printf("%d x %d = %d\n", number, i, number * i);
            }
    return 'K';
}
```
```text
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
2 x 6 = 12
2 x 7 = 14
2 x 8 = 16
2 x 9 = 18
2 x 10 = 20
```
# **C Break and Continue**
## Break
You have already seen the break statement used in an earlier chapter of this tutorial. It was used to "jump out" of a switch statement. The break statement can also be used to jump out of a loop.
This example stops the loop when i is equal to 4:
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 0; i < 0; i++){
        if (i == 4){
            break;
        }
        printf("%d\n", i);
    }
    return 'K';
}
```
```text
0
1
2
3
```
## Continue
The continue statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop. This example skips the value of 4:
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 0; i < 0; i++){
        if (i == 4){
        continue;
        }
    printf("%d\n", i);
    }
    return 'K';
}
```
```text
0
1
2
3
5
6
7
8
9
```
**Good to Remember:**
- **break** = stop the loop completely
- **continue** = skip this round, but keep looping.
## Combining Break and Continue
You can also combine break and continue
This example skips printing 2 and stops the loop at 4:
```c
#include <stdio.h>
char main(){
    int i;
    for (i = 0; i < 6; i++){
        if (i == 2){
            continue;
        }
        if (i == 4){
            break;
        }
        printf("%d\n", i);

    }
    return 'K';
}
```
```text
0
1
3
```
## Break and Continue in While Loop
You can also use break and continue in while loops
**Break Example**
```c
#include <stdio.h>
char main(){
    int i;
    while (i < 10){
        if (i == 4){
            break;
        }
        printf("%d\n", i);
        i++;
    }
    return 'K';
}
```
```text
0
1
2
3
```
**Continue Example**
```c
#include <stdio.h>
char main(){
    int i;
    while (i < 10){
        if (i == 4){
            i++;
            continue;
        }
        printf("%d\n", i);
        i++;
    }
    return 'K';
}
```
```text
0
1
2
3
5
6
7
8
9
```
## Real-Life Example
Imagine processing a list of numbers where you want to skip negative value, but stop completely if you find a zero.
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {3, -1, 7, 0, 9};
    int length = sizeof(myNumbers)/sizeof(myNumbers[0]);
    int i;

    for (i = 0; i < length; i++){
        if (myNumbers[i] < 0){
            continue;// Skip negative numbers
        }
        if (myNumbers[i] == 0){
            break; // Stop loop when zero is found
        }
        printf("%d\n", myNumbers[i]);
    }
    return 'K';
}
```
```text
3
7
```
- **Note:** Don't worry if you don't fully understand the example above. It uses an array (int myanumbers[] = {3, -1, 7, 0, 9};) to store numbers, and you will learn about arrays.
# **C Arrays**
## Arrays
Arrays are used to store multiple value in a single variable, instead of declaring separate variables for each value. To create an array, define the data type (like int) and specify the name of the array followed by square brackets[]
To insert values to it, use a comma-separated list inside curly braces, and make sure all values are of the same data type.
```c
int myNumbers[] = {25, 50, 75, 100};
```
We have now created a variable that holds an array of four integers.
## Access the Elements of an Array
To access an array element, refer to its index number. Array indexes start with 0; [0] is the first element [1] is the second element, etc. This statement accesses the value of the first element[0] in myNumbers.
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {25, 50, 75, 100};
    printf("%d", myNumbers[0]);
    return 'K';
    // Outputs 25
}
```
##  Change an Array Element
To change the value of a specific element, refer to the index number
```c
myNumbers[0] = 33;
```
**Example**
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {25, 50, 75, 100};
    myNumbers[0] = 33;
    printf("%d", myNumbers[0]);
    return 'K';
    // Outputs 33 instead of 25
}
```
## Set Array Size
Another common way to create arrays, is to specify the size of the array, and add elements later.
```c
#include <stdio.h>
char main(){
    // Declare an array of four integers:
    int myNumbers[4];
    
    // Add elements
    myNumbers[0] = 25;
    myNumbers[1] = 50;
    myNumbers[2] = 75;
    myNumbers[3] = 100;
    printf("%d", myNumbers[0]);
    return 'K';
}
```
Using this method, you should know the number of array elements in advance, in order for the program to store enough memory. You are not able to change the size of the array after creation.
## Avoid Mixing Data Types
It is important to note that all elements in an array must be of the same data type. This means you cannot mix different types of values, like integers and floating point numbers, in the same array.
```c
int myArray[] = {25, 50, 75, 3.15, 5.99};
```
In this example above, the values 3.15 and 5.99 will be truncated to 3 and 5. In some cases it might also result in an error, so it is important to always make sure that the elements in the array are of the same type.
# **C Array Size**
## Get Array Size
To get the size of an array, you can use the sizeof operator.
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {10, 25, 50, 75, 100};
    printf("%zu", sizeof(myNumbers));
    // Prints 20
    return 'K';
}
```
- **Note:** Why did the result show 20 instead of 5, when the array contains 5 elements?
It is because the sizeof operator returns the size of a type in bytes. You learned from the Data Types chapter that an int type is usually 4 bytes, so from the example above, 4 bytes x 5 elements = 20 bytes. Knowing the memory size of an array is great when you are working with larger programs that require good memory management. But what if you wanted to know how many elements the array was strong?
## Get the Number of elements
If you want to find out how many elements an array has, you can use this formula, which divides the total size the array by size of one element.
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {10, 25, 50, 75, 100};
    int length = sizeof(myNumbers) / sizeof(myNumbers[0]);
    printf("%d", length);
    // prints 5
    return 'K';
}
```
The sizeof formula works for arrays of any type and any size
```c
#include <stdio.h>
char main(){
    double myValues[] = {1.1, 2.2, 3.3};
    int length = sizeof(myValues) / sizeof(myValues[0]);
    printf("%d", length);
    // prints 3
    return 'K';
}
```
# **C Array Loop**
## Loop through an Array
You can use a for loop to go through the elements of an array by writing the size of the array by writing the size of the array in the loop condition (in this example the array has 4 elements, so we use i < 4). However, this is not ideal, since it will only work for arrays of a specified size.
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {25, 50, 75, 100};
    int i;
    for (i = 0; i < 4; i++){
        printf("%d\n", myNumbers[i]);
    }
    return 'K';
}
```
## Making Better Loops
In the previous chapter, you learned how to calculate the number of elements in an array using the sizeof formula. Now we can use that to write loops that work for arrays of any size. This is more flexible and sustainable.
```c
#include <stdio.h>
char main(){
    int myNumbers[] = {25, 50, 75, 100, 150};
    int length = sizeof(myNumbers) / sizeof(myNumbers[0]);
    int i;
    for (i = 0; i < length; i++){
        printf("%d\n", myNumbers[i]);
    }
    return 'K';
}
```
This loop will automatically work no matter how many elements the Array has!
- **Summary:** Always use the sizeof fomula when looping through arrays. It makes your loops adapt to the array size automatically.
---
# **C Arrays - Real Life Examples**
## Real-life Example
To demonstrate a practical example of using arrays, let's create a program that calculates the average of different ages.
```c
#include <stdio.h>
char main(){
    // An Array storing different ages
    int ages[] = {20, 22, 18, 35, 48, 26, 87, 70};
    float avg, sum = 0;
    int i;

    // Get the length of the array
    int length = sizeof(ages) / sizeof(ages[0]);

    // loop through the elements of the array
    for (i = 0;i < length; i++){
        sum += ages[i];
    }

    // Calculate the average by dividing the sum by the length
    avg = sum / length;

    // Print the average
    printf("The average age is: %.2f", avg);
    return 'K';
}
```
```text
The average age is: 40.75
```
And in this example, we create a program that finds the lowest age among different ages:
```c
#include <stdio.h>
char main(){
    // An array storing different ages
    int ages[] = {20, 22, 18, 35, 48, 26, 87, 70};
    int i;

    // Get the length of the array
    int length = sizeof(ages) / sizeof(ages[0]);

    // Create a variable and assign the first array element of ages to it
    int lowestAge = ages[0];

    // Loop through the elements of the ages array to find the lowest age
    for (i = 0; i < length; i++){
        if (lowestAge>ages[i]){
            lowestAge = ages[i];
        }
    }
    printf("%d", lowestAge);
    return 'K';
}
```
```text
18
```
# **C Multidimensional Arrays**
## Multidimensional arrays
In the previous chapter, you learned about arrays, which are also known as single dimension arrays. These are great, and something you will use alot while programming in C. However, if you want to store data as a tabular form, like a table with rows and columns, you need to get familiar with multidimensional arrays.<br>
A multidimensional array is basically an array of arrays. Arrays can have any number of dimensions. In this chapter, we will introduce the most common one: two-dimensional arrays (2D)
## Two-Dimensional arrrays
A 2D array is also known as a matrix (a table of rows and columns)
To create a 2D array of integers, take a look at the following example.
```c
int matrix[2][3] = {{1,4,2}, {3,6,8}};
```
The first dimension represents the number of rows[2] while the second dimension represents the number of column[3].
## Access the Elements of a 2D
To access an element of a two-dimensional array, you must specify, the index number of both the row and column. This statement accesses the value of the element in the first row(0) and third column(2) of the matrix array.
```c
#include <stdio.h>
int main(){
    int matrix[2][3] = {{1,4,2},{3,6,8}};
    printf("%d", matrix[0][2]);
    return 0;// Outputs 2
}
```
- *Remember that:* Array indexes start with 0. [0] is the first element, [1] is the second element, etc.
## Change Elements in a 2D Array
To change the value of an element, refer to the  index number of the element in each of the dimensions. The following example will change the value of the element in the first row(0) and first column (0)
```c
#include <stdio.h>
int main(){
    int matrix[2][3] = {{1,4,2},{3,6,8}};
    matrix[0][0] = 9;
    printf("%d", matrix[0][0]);
    return 0;// Now outputs 9 instead of 1
}
```
## loop through a 2D Array
To loop through a multi-dimensional array, you need one loop for each of the array's dimensions. The following example outputs all elements in the matrix array.
```c
#include <stdio.h>
int main(){
    int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};
    int i, j;
    for (i = 0; i < 2; i++){
        for (j = 0; j < 3; j++){
            printf("%d\n", matrix[i][j]);
        }
    }
    return 0;
}
```
## Three dimensional arrays
You can also declare arrays with more than two dimensions
```c
// A 3D array with 2 blocks, each with 4 rows and 3 columns
int example[2][4][3];\
```
This creates a 3D array with:
- 2 blocks (first index)
- 4 rows per block(second index)
- 3 columns per row (third index)
## When to use Multidimensional Arrays
Multidimensional arrays are useful when your data is arranged in rows and columns. like a table, grid or matrix
Each extra dimension adds another level of structure.
- **2D arrays** (like int scores[3][4]) are great for storing things like scores, game boards or spreadsheets
- **3D arrays** (like cube[2][3][4]) can represent more complex structures like a set of tables or levels in a game.
# **C Strings**
## Strings
Strings are used for storing text, characters. For example, "Hello World!" is a string of characters. Unlike many other programming languages, C does no have a String type to easily create string variables. Instead, you must use the char type and create an array of characters to make a string in C
```c
char greetings[] = "hello World!";
```
Note that you have to use double quotes("")
To output the string, you can use the printf() function together with the format specifier %s to tell c that we are now working with strings:
```c
char greetings[] = "Hello World!";
printf("%s", greetings);
```
## Accessing Strings
Since strings are actually arrays in C,you can access a string by referring to its index number inside square brackets[],
The example prints the first character (0) in greetings.
```c
char greetings[] = "Hello world!"
printf("%c", greetings[0]);
```
Note that we have to use the %c format specifier to print a single character.
## Modify Strings
To change the value of a specific character in string, refer to the index number, and use single quotes.
```c
#include <stdio.h>
int main(){
    char greetings[] = "Hello World!";
    greetings[0] ='J';
    printf("%s", greetings);
    // Outputs Jello World! instead of Hello World!
    return 0;
}
```
## Real-Life Example
Use strings to create a simple welcome message:
```c
char message[] = "Good to you,";
char fname[] = "Binary";
printf("%s %s!", message, fname);
```
---
# **C The Null Character**
## The Null Character \0
Every string in C ends with a special character.\0, known as the null character. It tells C where the string ends. You do not see it, and you do not have to write it when you create a string with double quotes, because C adds it for you. This is why the string "Hello" uses 6 characters of memory, not 5.
```c
char greetings = "Hello";
printf("%zu", sizeof(greetings));
// Outputs 6
```
## Another way of Creating Strings
In the examples above, we used a stirng literal (text inside double quotes) to create a string variable. This is the easiest way to create a string C.
```c
char greetings[] = "Hello World!";
// "Hello World!" is a string literal.
```
You should also that you can create a string with a set of characters. This example will produce the same string as the string literal above.
```c
#include <stdio.h>
int main(){
    char greetings[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
    printf("%s", greetings);
    return '0';
    // Output Hello World!
}
```
Why do we include the \0 character at the end?
When you create a string from single characters, you must add the null character yourself. C only adds it for you when you use double quotes. Without it, C does not know where the strings ends.
## Differences
The difference between the two ways of creating strings, is that the first method is easier to write, and you do not have to include \0 character, as C will do it for you. You should note that the size of both arrays is the same. They both have 13 characters (space also counts as a character by the way), including the \0 character.
```c
#include <stdio.h>
int main(){
    char greetings[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
    char greetings2[] = "Hello World!";
    printf("%zu\n", sizeof(greetings));
    printf("%zu", sizeof(greetings2));
    return '0';
}
```
# **C String and Loops**
## Loop Through a String
You can also loop through the characters of string, using a for loop.
```c
#include <stdio.h>
int main(){
    char carName[] = "Volvo";
    int i;
    for (i = 0; i < 5; ++i){
        printf("%c", carName[i]);
    }
    return '0';
}
```
Instead of writing the length of the string in the loop condition (i < 5), you can use the strLen() function. It returns the number of characters in a string, and it is part of the <string.h> header file (you will learn more about it in the String Functions.)
```c
#include <stdio.h>
#include <string.h>
int main(){
    char carName[] = "Volvo";
    int length = strlen(carName);
    int i;

    for (i = 0; i < length; ++i){
        printf("%c", carName[i]);
    }
    return '0';
}
```
- **Note:** The sizeof formula from the Array loops chapter does not work as well for strings. sizeof also conts the \0 character at the end of the string, so it gives 6 for "Volvo" instead of 5.
---
# **c Special Characters**
## String - Special Characters
Because strings must be writtten within quotes, C will misunderstand this string, and generate an error.
```c
char txt[] = "We are the so-called "Vikings" from the moth.";
```
The solution to avoid this problem, is to use the backslash escape character. The backslash (\) excape character turns special characters into string characters.
| Escape character | Result | Description |
| --- | --- | --- |
| \' | ' | Single quote |
| \" | " | Double quote |
| \\ | \ | Backslash |
The sequence \" inserts a double quote in a string:
```c
#include <stdio.h>
int main(){
    char txt[] = "We are the so-called \"Vikings\" from the north.";
    printf("%s", txt);
    return 0;
}
```
```text
We are the so-called "Vikings" from the north.
```
The sequence \' inserts a single quote in a string.
```c
#include <stdio.h>
int main(){
    char txt[] = "It\'s alright.";
    printf("%s", txt);
    return 0;
}
```
```text
It's alright.
```
- **Note:** Inside double qoutes, a single qoute also works without the backlash: "It's alright." The \' sequence is needed when you write a single quote as a *char*, inside single quotes. char qoute = '\'';
The sequence \\ inserts a single backlash in a string.

```C
#include <stdio.h>
int main(){
    char txt[] = "The character \\ is called backlash.";
    printf("%s", txt);
    return 0;
}
```
```text
The character \ is called backlash.
```
Other popular escape characters in C are:
| Escape Character | Result |
| --- | --- |
| \n | New Line |
| \t | Tab |
| \0 | Null |
---
