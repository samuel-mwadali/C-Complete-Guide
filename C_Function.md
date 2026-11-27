# **C Functions**
## Functions
A function is a block of code which only runs when it is called.
You can pass data, known as parameters, into a function.
Functions are used to perform certain actions, and they are important for resuing code: Define the code once, and use it many times.
## Predefined Functions
So it turns out you already know what a function is. You have been using it the whole using it the whole time. For example, main() is a function, which is used to execute code, and printf() is function; used to output/print text to the screen.
```c
int main(){
    printf("Hello World!");
    return 0;
}
```
## Creating a function
To create you own function, specify the name of the function, followed by parentheses () and curly brackets {}

```c
void myFunction(){
    // code to be executed
}
```
## Example Explained
- myFunction() is the name of the function
- void means that the function does not have a return value. You will learn more about return values in the next chapter.
- Inside the function (the body), add code that defines what the function should do.
## Call a Function
Declared functions are not executed immmediately. They are "saved for later use", and will be executed when they are called. To call a function, write the function's name followed by two parentheses () and a semicolon ; In the following example, myFunction () is used to print a text (the action), when it is called
```c
#include <stdio.h>
// Create a function
void myFunction(){
    printf("I just got executed!");
}
int main(){
    myFunction(); // call the function
    return 0;
}
```
```text
I just got executed!
```
A function can be called multiple times
```c
#include <stdio.h>
// Create a function
void myFunction(){
    printf("I just got executed!\n");
}
int main(){
    myFunction();
    myFunction();
    myFunction();
    return 0;
}
```
```text
I just got executed!
I just got executed!
I just got executed!
```
## Calculate the Sum of Numbers
You can put almost whatever you want inside a function. The purpose of the function is to save the code, and execute it when you need it. Like in the example below, we have created a function to calculate the sum of two numbers. Whenever you are ready to execute the function (and perform the calculation), you just call it.
```c
#include <stdio.h>
// Create a function
void calculateSum(){
    int x = 5;
    int y = 10;
    int sum = x + y;
    printf("The sum of x + y is %d", sum);
}
int main(){
    calculateSum(); // call the function
    return 0;
}
```
```text
The sum of x + y is 15
```
This was just an example to demonstrate a simple function with different statements in C. The real power of a function is revealed in the next chapter, when we pass parameters to it. This allows the function to calculate the sum of any numbers, instead of being limited ot fixed values 5 and 10.
---
# **C Function Parameters**
## Parameters and Arguments
Information can be passed to functions as a parameter. Parameter act as variables inside the function. Parameters are specified after the function name, inside the parantheses. You can add as many parameters as you want, just separate them with a comma:
```c
retunType functionName(parameter1, parameter2, parameter3){
    // code to be executed
}
```
In the example below, the function takes a string of characters with name as parameter. When the function is called, we pass along a name, which is used inside the function to print "Hello" and the name of each person.
```c
#include <stdio.h>
// Create a function
void myFunction(char name[]){
    printf("Hello %s\n", name);
}
int main(){
    myFunction("Liam");
    myFunction("Jenny");
    myFunction("Anja");
    return 0;
}
```
```text
Hello Liam
Hello Jenny
Hello Anja
```
The value that is passed to the function is called an argument. So, from the example above: name is a parameter, while lian, Jenny and Anja are arguments.
## Multiple Parameters
In this example, the function takes two parameters; a string and an int
```c
#include <stdio.h>
// Create a function
void myFunction(char name[], int age){
    printf("Hello %s. Your are %d years old.\n", name, age);
}
int main(){
    myFunction("Liam", 3);
    myFunction("Jenny", 14);
    myFunction("Anja", 30);
    return 0;
}
```
```text
Hello Liam. Your are 3 years old.
Hello Jenny. Your are 14 years old.
Hello Anja. Your are 30 years old.
```
If we consider the "Calculate the Sum of Numbers" example from the previous page, we can make a more flexible program by using function parameters.
```c
#include <stdio.h>
// Create a function
void calculateSum(int x, int y){
    int sum = x + y;
    printf("The sum of %d + %d is: %d\n", x, y, sum);
}

int main(){
    calculateSum(5, 3);
    calculateSum(8, 2);
    calculateSum(15, 15);
    return 0;
}
```
```text
The sum of 5 + 3 is: 8
The sum of 8 + 2 is: 10
The sum of 15 + 15 is: 30
```
## Notes on parameters
Note that when you are working with multiple parameters, the function call must have the same number of arguments as there are parameters, and the arguments must be passed in the same order.
## Pass Arrays as Function Parameters
You can also pass arrays to a function
```c
#include <stdio.h>
// Create a function
void myFunction(int myNumbers[5]){
    for (int i = 0; i < 5; i++){
        printf("%d\n", myNumbers[i]);
    }
    }
int main(){
    int myNumbers[5] = {10, 20, 30, 40, 50};
    myFunction(myNumbers);
    return 0;
}
```
**Example Explained**
The function (myFunction) takes an array as its parameter (int myNumbers[5]), and loops through the array elements with the for loop. When the functions is called inside main(), we pass along the myNumbers array, which outputs the array elements. <br>Note that when you call the function, you only need to use the name of the array when passing it as an argument myFunction(myNumbers).However, the function parameter must be written as an array, with square brackets (int myNumbers[5]).
## Return values
The void keyword, used in the previous examples, indicates that the function should not return a value. If you want the function to return a value, you use a data type(such as int or float, etc) instead of void, and use the return keyword inside the function.
```c
#include <stdio.h>
// Create a function
int myFunction(int x){
    return 5 + x;
    }
int main(){
    printf("Result is: %d", myFunction(3));
    return 0;
}
```
```text
Result is: 8 
```
You can also strore the result in a variable
```c
#include <stdio.h>
// Create a function
int myFunction(int x, int y){
    return y + x;
    }
int main(){
    printf("Result is: %d", myFunction(3,7));
    return 0;
}
```
```text
Result is: 10 
```
If we consider the "Calculate the Sum of Numbers" example one more time, we can use return instead and strore the results in different variables. This will make the program even more flexible and easier to control.
```c
#include <stdio.h>
// Create a function
int calculateSum(int x, int y){
    return x + y;
    }
int main(){
    int result1 = calculateSum(5, 3);
    int result2 = calculateSum(8, 2);
    int result3 = calculateSum(15, 15);

    printf("Result1 is: %d\n", result1);
    printf("Result2 is: %d\n", result2);
    printf("Result3 is: %d", result3);
    return 0;
}
```
```text
Result1 is: 8
Result2 is: 10
Result3 is: 30 
```
- *Tip:* If you have many "result variable", it is better to store the results in an array.
```c
#include <stdio.h>
// Create a function
int calculateSum(int x, int y){
    return x + y;
    }
int main(){
    // Create an Array
    int resultArr[6];
    // Call the function with different arguments and store the results in the array
    resultArr[0] = calculateSum(5, 3);
    resultArr[1] = calculateSum(8, 2);
    resultArr[2] = calculateSum(15, 15);
    resultArr[3] = calculateSum(9, 1);
    resultArr[4] = calculateSum(7, 7);
    resultArr[5] = calculateSum(1, 1);

    for (int i = 0; i < 6; i++){
        printf("Result%d is = %d\n", i + 1, resultArr[i]);
    }
    return 0;
}
```
```text
Result1 is = 8
Result2 is = 10
Result3 is = 30
Result4 is = 10
Result5 is = 14
Result6 is = 2 
```
## Real-Life Example
To demostrate a practical example of using functions, lets create a program that converts a value from Fahrenheit to Celsius
```c
#include <stdio.h>
// Function to convert Fahrenheit to Celsius
float toCelsius(float fahrenheit){
    return (5.0 / 9.0) * (fahrenheit - 32.0);
}
int main(){
    // Set a fahrenheit value
    float f_value = 98.8;

    // Call the function with the fahrenheit value
    float result = toCelsius(f_value);

    // Print the fahrenheit value
    printf("Fahrenheit: %.2f\n", f_value);

    // Print the result
    printf("Convert Fahrenheit to Celsius: %.2f\n", result);
    return 0;
}
```
```text
Fahrenheit: 98.80                                                                                                       Convert Fahrenheit to Celsius: 37.11 
```
---
# **C Pass By Reference**
## Pass By Reference
In the previous chapter, you learned how to pass values to a function as parameters.<br>When you do this, the function gets a copy of the value. This is called **pass by value**. If the funtion changes the copy, the original variable does not change.
```c
#include <stdio.h>
void addTen(int x){
    x = x + 10;
    }
int main(){
    int myNum = 5;
    addTen(myNum);
    printf("%d\n", myNum);
    return 0; // Output 5
}
```
The function adds 10 to x, but x is only a copy of myNum. So myNum is still 5. This is how it works, when you call addTen(myNum), the value of myNum(5) is copied into the parameterx. x is a new variable that only exists inside the function, and it is removed when the function is finished.<br>This is not a problem. It is how C normally works, and it is often exactly what you want the function can use the value, but it cannot change your variables by accident. If the function needs to give a result back, it can use return:
```c
#include <stdio.h>
int addTen(int x){
    return x + 10;
    }
int main(){
    int myNum = 5;
    myNum = addTen(myNum);
    printf("%d\n", myNum);
    return 0; // Output 15
}
```
Use pass by reference (below) only when a function must change the original variable directly, or give back more than one result
## Pass By Reference
Sometimes you want a function to change the original variable. To do this, give the function the memory address of the variable, instead of a copy of its value. This is often called pass by reference
```c
#include <stdio.h>
void addTen(int *x){
    *x = *x + 10;
    }
int main(){
    int myNum = 5;
    addTen(&myNum);
    printf("%d\n", myNum);
    return 0; // Output 15
}
```
Compared to the pass by value example, three things are different.
- The parameter is a pointer (int *x). It stores the memory address of myNum.
- The function call uses & to pass the the memory address: addTen(&myNum)
- Inside the function, *x is myNum itself, so *x = *x + 10; changes myNum to 15<br>

This is what the memory looks like while addTen() runs:
This is exactly how scanf() works: in scanf("%d", &myNum), you give scanf() the memory address of myNum, so it can store the number that the user types there.<br>
**Note:** Arrays work this way automatically. When you pass an array to a function, the function gets the memory address of the first element, not a copy of the array. So a function can change the elements of an array, without using &.
## Swap Two Variables
In the change values chapter, you learned how to swap the values of two variables with third variables with a third variable. With pointers, you can put the swap in a function:
```c
#include <stdio.h>
void swap(int *a, int*b){
    int temp = *a;
    *a = *b;
    *b = temp;
}
int main(){
    int x = 5;
    int y = 10;
    swap(&x, &y);
    printf("x is %d, y is %d\n", x, y);
    return 0;
}
```
```text
x is 10, y is 5 
```
Without pointers, the function would only swap its own copies, and x and y would not change.
## Real-Life Example
A function can only return one value. With pointers, a function can give back more than one result. This function finds both the lowest and the highest age in an aray.
```c
void minMax(int ages[], int length, int *min, int *max){
    *min = ages[0];
    *max = ages[0];
    for (int i = 1; i < length; i++){
        if (ages[i] < *min){
            *min = ages[i];
        }
        if (ages[i] > *max){
            *max = ages[i];
        }
    }
}
int main(){
    int ages[] = {20, 22, 18, 35, 48, 26, 87, 70};
    int lowest, highest;
    minMax(ages, 8, &lowest, &highest);
    printf("Lowest age: %d\n", lowest);
    printf("Highest age: %d\n", highest);
    return 0;
}
```
```text
Lowest age: 18
Highest age: 87
```
**Example Explained**
- The function takes four parameters: the array (ages), its length(8), and two pointers(int *min) and (int *max)
- *min and *max both start with the first age in the array(20)
- The loop checks the rest of the ages. If an age is lower than *min, it becomes the new lowest age. If it is higher than *max, it becomes the new highest age.
- in main(), &lowest and &highest pass the memory addresses of two variables, so the function stores the results directly in them.
- After the function call, lowest is 18 and highest is 87
---
 # **C Variable Scope**
 ## Scope
 Now that you understand how functions work, it is important to learn how variables act inside and outside of functions.<br>In C, variables are only accessible inside the region they are created. This is called **scope**
 ## Local Scope
 A variable created inside a function belongs to the local scope of that function, and only be used inside that function.
 ```c
 #include <stdio.h>
void myFunction(){
    // Local variable that belongs to myFunction
    int x = 5;

    // Print the variable x
    printf("%d", x);
    }
int main(){
    myFunction();
    return 0;
}
```
```text
5
```
A local variable cannot be used outside the function it belongs to. If you try to access the function, an error occurs.
```c
#include <stdio.h>
void myFunction(){
    // Local variable that belongs to myFunction
    int x = 5;
    }

int main(){
    myFunction();
    // Print the variable x in the main function
    printf("%d", x);
    return 0;
}
```
**Note:** Function parameters are also local variables. They are created when the function is called, and removed when the function is finished (like the parameter x in the pass by reference)
## Block scope
A block of code is the code inside curly braces {} like the code in an if statement or a loop. A variable created inside that block.
```c
#include <stdio.h>
int main(){
    int age = 20;
    if (age >= 18){
        // message only exists inside this block
        char message[] = "You can vote!";
        printf("%s", message);
    }
    // message cannot be used here
    return 0;
}
```
*Tip:* This also goes for loops, like for (int i = 0; i < 5; i++), where the variable i only exists inside the loop.
## Global scope
A variable created outside of a function is called **globla variable** and belongs to the global scope. <br> Global variables are available from within any scope, global and local<br>
**Example** <br>
A variable created outside of a function is global and can therefore be used by any function.
```c
#include <stdio.h>
// Global variable x
int x = 5;

void myFunction(){
    // We can use x here
    printf("%d\n", x);
    }

int main(){
    myFunction();

    // We can also use x here
    printf("%d\n", x);
    return 0;
}
```
## Naming Variables
If you use the same variable name inside and outside of a function, C will treat them as two separate variables: One available in the global scope(outside the function) and one available in the local scope(inside the function )<br>**Example**<br>The function will print the local x, and then the code will print the global x
```c
#include <stdio.h>
// Global variable x
int x = 5;

void myFunction(){
    // Local variable with the same name as the global variable (x)
    int x = 22;
    printf("%d\n", x); // Refers to the local variable x
    }

int main(){
    myFunction();

    // Refers to the global variable x
    printf("%d\n", x);
    return 0;
}
```
```text
22
5
```
However, you should avoid using the same variable name for both global and local variables as it can lead to errors and confusion.<br>In general, you should be careful with global variables, since they can be accessed and modified from any function.<br> **Example** <br> Change the value of x from myFunction.
```c
#include <stdio.h>
// Global variable x
int x = 5;

void myFunction(){
    printf("%d\n", ++x); // Increment the value of x by 1 and print it
    }

int main(){
    myFunction();

    // Print the global variable x
    printf("%d\n", x);
    return 0;
    // The value of x is now 6 (no longer 5)
}
```
## Conclusion
To sum up, use local variables (with good variable names) as much as you can. This will make your code easier to maintain and better to understand. However, you may find global variables when working on existing C programs or while collaborating with others. Therefore, it is good to understand how the scope works and how to use it effectively to make sure your code is clear and functional.

---
# **C Function Declaration and Definition**
## Function Declaration and Definition
You have already learned from the previous chapters that you can create and call a function in the following way:
```c
#include <stdio.h>
// Create a function
void myFunction(){
    printf("I just got executed!");
    }

int main(){
    myFunction(); // Call the function
    return 0;
}
```
```text
I just got executed!  
```
A function consists of two parts:
- **Declaration:** the function's name, return type, and parameters(if any)
- **Definition:** the body of the function (code to be executed)
```c
void myFunction(){ // declaration
    // the body of the function
    (definition)
}
```
In C, a function must be declared before it is called. That is why the function is created above **main()** in the examples so far.<br>You will often see C programs have the function declaration above main(), and function definition below main(). This makes the code better organized and easier to read:
```c
#include <stdio.h>
// Function declaration
void myFunction();

// The main function
int main(){
    myFunction(); // Call the function
    return 0;
}

// Function definition
void myFunction(){
    printf("I just got executed!");
}
```
```text
I just got executed! 
```
## What about Parameters
If we use the example from the function parameters chapter regarding parameters and return values:
```c
#include <stdio.h>
int myFunction(int x, int y){
    return x + y;
}
int main(){
    int result = myFunction(5,3);
    printf("Result is = %d", result);
    return 0;
}
```
```text
Result is = 8  
```
it is considered good practice to write it like this instead
```c
#include <stdio.h>
// Function declaration
int myFunction(int x, int y);

// The main body
int main(){
    int result = myFunction(5,3); // call the function
    printf("Result is = %d", result);
    return 0;
}
// Function definition
int myFunction(int x, int y){
    return x + y;
}
```
```text
Result is = 8 
```
## Functions Calling Other Functions
As long as you declare functions first, it is also possible to use functions to call other functions:<br> **Example** <br> Use one function to call another function.
```c
#include <stdio.h>
// Declare two functions, myFunction and myOtherFunction
void myFunction();
void myOtherFunction();

// The main body
int main(){
    myFunction(); // call myFunction (from main)
    return 0;
}
// Define myFunction
void myFunction(int x, int y){
    printf("Some text in myFunction\n");
    myOtherFunction(); // call myFunction (from myFunction)
}
// Define myOtherFunction
void myOtherFunction(){
    printf("Hey! Some text in myOtherFunction\n");
}
```
```text
Some text in myFunction
Hey! Some text in myOtherFunction 
```
---
# **C Math Function**
## Math Functions
There is also a list of math functions available, that allows you to perform mathematical tasks on numbers.<br>To use them, you must include the math.h header file in your program
```c
#include <math.h>
```
## Square Root
To find the square root of a number, use the sqrt() function
```c
#include <stdio.h>
#include <math.h>
int main(){
    printf("%f", sqrt(16));
    return 0;
}
```
```text
4.000000 
```
**Note:** The math functions return a double value, so we use %f to print the result. That is why sqrt(16) prints 4.000000 and not 4
## Round a Number
The ceil() function rounds a number upwards to the nearest integer, and the floor() function rounds a number downwards to its nearest integer, and returns the result.<br> **Example** <br>
```c
#include <stdio.h>
#include <math.h>
int main(){
    printf("%f\n", ceil(1.4));
    printf("%f\n", floor(1.4));
    return 0;
}
```
```text
2.000000
1.000000
```
## Power
The pow() function returns the value of x to the power of y(x^y)<br> **Example** <br>
```c
#include <stdio.h>
#include <math.h>
int main(){
    printf("%f\n", pow(4, 3));
    return 0;
}
```
```text
64.000000
```
# **C Inline Function**
## Inline Function
You might sometimes see the inline keyword used in other people's functions. It's not something you need to use often as a beginner, but it's good to know what it means.<br>An inline function is a small function that asks the compiler to insert its code directly where it is called, instead of jumping to it.<br>This can make short, frequently used functions a little faster, because it removes the small delay of a normal function call.<br>Let's compare a regular function with an inline function.<br> **Regular Function**
```c
int square(int x){
    return x * y;
}
```
**Inline Function**
```c
static inline int square(int x){
    return x * y;
}
```
Both functions work the same way. The difference is that the inline version suggests to the compiler to copy the function's code directly where it is used.<br> **Note:** In C, inline functions are usually written as **static inline**. The static keyword makes the function availalble only in the current file.Without it, you can get an error if the compiler decides not inline the function.
## Inline Function Example
Here is a simple example that uses an inline function
```c
#include <stdio.h>
static inline int add(int a, int b){
    return a + b;
}
int main(){
    printf("%d", add(5, 3));
    return 0;
}
```
```text
8 
```
Here, the compiler might replace add(5, 3) with code 5 + 3 directly - saving the time it would take to call a separate function.
## When Not to use inline
Inline functions are best for small, simple functiions. Avoid using them for:
- Large functions (they make your program bigger)
- Recursive functions
- Functions that are rarely called

Too many inline functions can make your program slower and larger, a problem known as code bloat.
## Inline vs Regular Function

| Regular Function | Inline Function |
| --- | --- |
| Code jumps to the function each time it's called | Code may be inserted directly where it's called |
| Slightly slower(small delay) | Can be slightly faster |
| Good for large functions | Good for small functions |

Moder compilers are good at deciding this on their own. They often inline small regular functions too, even without the inline keyword. That is why you rarely need to use it, and why we will continue to use regular functions
## Summary
- Inline functions are defined with the inline keyword, usually together with static
- They can make small, often-used functions faster
- The compiler decides whether to inline a function or not
- Mostly used for short, simple functions

