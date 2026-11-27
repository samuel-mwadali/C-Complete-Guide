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
---
# **C Recursion**
## Recursion
Recursion is the technique of making a function call itself. This technique provides a way to break complicated problems down into simple problems which are easier to solve.<br>Recursion may be a bit difficult to understand. The best way to figure out how it works is to experiment with it
## Recursion Example
Adding two numbers together is easy to do, but adding a range of numbers is more complicated. In the following example, recursion is used to add a range of numbers together by breaking it down into the simple task of adding two numbers. <br> **Example** <br> Use recursion to add all numbers from 1 to 10
```c
#include <stdio.h>
int sum(int k);
int main(){
    int result = sum(10);
    printf("%d", result);
    return 0;
}
int sum(int k){
    if (k > 0){
        return k + sum(k-1);
    } else {
        return 0;
        }
}
```
**Example Explained** <br> When the sum() function is called, it adds parameter k to the sum of all numbers smaller than k and returns the result. When k becomes 0, the function just returns 0. Since the function does not call itself when k is 0, the programs stops there and returns the result.
## Halting Condition
Just as loops can run into the problem of infinite looping, recursive functions can run into the problem of infinite recursion is when the function never stops calling itsefl.<br>Every recursive function should have a halting condition, which is the condition where the function stops calling itsef. In the previous example, the halting condition is when the parameter k becomes 0.<br>**Countdown Example** <Br> Use recursion to count down from 5:
```c
#include <stdio.h>
void countdown(int n);
int main(){
    countdown(5);
    return 0;
}
void countdown(int n){
    if (n > 0){
        printf("%d ", n);
        countdown(n - 1);
        }
}
```
```text
5 4 3 2 1
```
The function calls itself with n - 1 until n becomes 0
## Calculate Factorial with Recursion
This example uses a recursive function to calculate the factorial of 5:
```c
#include <stdio.h>
int factorial(int n);
int main(){
    printf("Factorial of 5 is %d", factorial(5));
    return 0;
}
int factorial(int n){
    if (n > 1){
        return n * factorial(n - 1);
    } else {
            return 1;
    }
}
```
```text
Factorial of 5 is 120
```
**Factorial** means multiplying a number by every number below it, down to 1. For example, the factorial of 5 is: 5 x 4 x 3 x 2 x 1 = 120. By definition, 0! is also 1.
# **Function Pointer**
## Function Pointer
A function pointer is like a normal pointer, but instead of pointing to a variable, it points to a function.<br>This means it stores the address of a function, allowing you to call that function using the pointer.<br>Function pointers are useful when you want to decide which function to run while program is running, or when you want to pass a function as an argument to another function.<br>Think of it like saving a phone number - the pointer knows where the function lives in memory, so you can "cal" it later.
## Function Pointer Example
Let's start with a complete example. Below it, you will learn about each part. <br> **Example**<br> A pointer to a function that adds two numbers:
```c
#include <stdio.h>
int add(int a, int b){
    return a + b;
}
int main(){
    int (*ptr)(int, int) = add;
    int result = ptr(5, 3);
    printf("Result: %d", result);
    return 0;
}
```
```text
Result: 8
```
Here:
- ptr is a pointer to the function add()
- ptr(5, 3) calls the functin using the pointer

This works exactly the same as calling add(5, 3) <br>
**Note:** A function name itself points to start of its code in memory. That means a function name already acts like a pointer!Declaring a function pointer just gives you a variable that can hold that address - so you can change it or pass it around.
## Declaring a Function Pointer
The general syntax for declaring a function pointer is 
```c
returnType (*pointerName)(parameterType1, parameterType2, ... );
```
This means ptr is a pointer (*ptr) to a function that takes two int values (int, int) and returns an int.<br>The parentheses around *ptr are important. Without them, int *ptr(int, int); would declare a function that returns a pointer, not a pointer to a function.
## Assigning a Function to a Pointer
You can assign a function to a pointer in two ways:
```c
ptr = add;
ptr = &add;
```
Both are the same, because the function's name already represents its address in memory.
## Calling a Function through a pointer
Once the pointer is assigned, you call the function in two ways:
```c
ptr(5, 3)
(*ptr)(5, 3)
```
Both are valid and do the same thing.
## Passing a Function as an Argument
You can pass a function pointer to another function. The function that is passed is called a **callback function.**
It allows a function to call another function thay you provide as input.<br> **Example** <br> Passing a function pointer to another function
```c
#include <stdio.h>
void greetingMorning(){printf("Good morning!\n");}
void greetingEvening(){printf("Good evening!\n");}
void greet(void (*func)()){
    func();
}
int main(){
    greet(greetingMorning);
    greet(greetingEvening);
    return 0;
}
```
```text
Good morning!
Good evening!
```
Here, greet() takes another function as a parameter and calls it. This way, the same function can do different things, depending on which function you give it.<br>The parameter void (*func)() is a pointer to a function that no parameters and returns nothing (void).
## Function Pointer Array
You can also store several function pointers in an array, so you can choose which function to run while the program is running.<br>This example runs three different functions using an array of function pointers:
```c
#include <stdio.h>
void add(){printf("Add\n");}
void subtract(){printf("Subtract\n");}
void multiply(){printf("Multiply\n");}
int main(){
    void (*operations[3])()= {add, subtract, multiply};
    for (int i = 0; i < 3; i++){
        operations[i]();
    }
    return 0;
}
```
```text
Add
Subtract
Multiply
```
**Operations** is an array of 3 pointers to functions that take no parameters and return nothing.<br>This is often used for simple menus, command lists, or calculators - anywhere you want to call different functions based on user input.<br> **Example** <br> A simple calculator using an array of function pointers:
```c
#include <stdio.h>
void add(int a, int b) {printf("Result: %d\n", a + b);}
void subtract(int a, int b){printf("Result: %d\n", a - b);}
void multiply(int a, int b){printf("Result: %d\n", a * b);}
int main(){
    int choice, x = 10, y = 5;
    void (*operations[3])(int, int) = {add, subtract, multiply};
    printf("x = %d, y = %d\n\n", x, y);
    printf("Choose an operation:\n");
    printf("0: Add\n1: Subtract\n2: Multiply\n");
    scanf("%d", &choice);
    if (choice >= 0 && choice < 3){
        operations[choice](x, y);
    } else {
        printf("Invalid choice!\n");
    }
    return 0;
}
```
In this program:
- All three math functions(add(), subtract(), and muliply()) are stored in an array.
- The user picks which one to run by entering a number
- The correct function is then called using the pointer array.

This is a simple example of how function pointer arrays make programs more flexible and reusable.
## Function Pointer vs Normal Function
| Norml Function | Function Pointer |
| --- | ---|
| Called directly by its name | Called using a pointer |
| The function is decided before the programs runs | You can choose which to call while the program is running |
| Good for simple code | Good for flexible and reusable code |

## Summary
- A function pointer stores the address of a function.
- You can declare, assign, and call functions through it.
- It allows passing functions as arguments to other functions
- Useful for callbacks, menus, and flexible program design.

# **C Callback Functions**
## Callback Function
A callback function is a function that is passed as an argument to another function.<br>The receiving function can then call it back(run it) whenever it needs to.<br>This is a powerful way to make your code flexible and reusable - you can decide which function should run, without changing the main logic.<br>In C, callback function are usually implemented using function pointers.
## Simple Callback Example
Here's a basic example that shows how one function can "call back" another.<br> **Example** <br> Passing a function as an argument to another function
```c
#include <stdio.h>
void sayHello(){
    printf("Hello from the callback!\n");
}
void runCallback(void (*callback)()){
    printf("Before calling the callback ... \n");
    callback();
    printf("After calling the callback.\n");
}

int main(){
    runCallback(sayHello);
    return 0;
}
```
```text
Before calling the callback ...
Hello from the callback!
After calling the callback.
```
In this example:
- sayHello() is a normal function that prints a meassage.
- runCallback() receives a function pointer as a parameter.
- When runCallback(sayHello) runs, it calls sayHello() inside itself.

**Note:** The word "callback" comes from the fact that one function "call back" another that was given to it earlier.
## Callback with Parameters
You can also pass functions that take parameters - just make sure the function pointer type matches: <br> **Example** <br> Passing a function with parameters as a callback.
```c
#include <stdio.h>
void addNumbers(int a, int b){
    printf("The sum is: %d\n", a + b);
}
void calculate(void (*callback)(int, int), int x, int y){
    callback(x, y);
}
int main(){
    calculate(addNumbers, 5, 3);
    return 0;
}
```
```text
The sum is: 8
```
Here, calculate() receives a function and two numbers, then calls the function (in this case, addNumbers()) with those numbers as arguments.<br>The parameter void (*callback)(int, int) is a pointer to a function that takes two int values and returns nothing.
## Mulitple Callbacks
You can use callbacks to let a function behave differently depending on which function you pass in. This is common in code that sorts or filters data.<br> **Example** <br> Using different callback to perform different actions:
```c
#include <stdio.h>
void greetMorning(){
    printf("Good morning!\n");
}
void greetEvening(){
    printf("Good evening!\n");
}
void greet(void (*callback)()){
    callback();
}
int main(){
    greet(greetMorning);
    greet(greetEvening);
    return 0;
}
```
```text
Good morning!
Good evening!
```
Depending on which function is passed, the program produces different output - without changing greet() itself.
## Real-Life Example: Using Callbacks in qsort()
Many C standard library functions use callbacks. For example, the qsort() function in <stdlib.h> uses callback to compare elements while sorting.<br> You provide the comparison function, and qsort() calls it as needed. This will sort the elements.
```c
#include <stdio.h>
#include <stdlib.h>
int compare(const void *a, const void *b){
    int x = *(int*)a; // the first number
    int y = *(int*)b; // the second number
    return x - y; // negative: x comes first, positive: y comes first
}
int main(){
    int numbers[] = {5, 2, 9, 1, 7};
    int size = sizeof(numbers) / sizeof(numbers[0]);
    qsort(numbers, size, sizeof(int), compare);
    for (int i = 0; i < size; i++){
            printf("%d", numbers[i]);
    }
    return 0;
}
```
```text
12579
```
Here, compare() is the callback function used by qsort() to decide how to order the numbers.<br> qsort() can sort any kind of data, so it gives your function two general pointers (const void*).(int*)a tells C that a points to an int, and the * in front gets that int.
## Summary
- A callback function is a function passed as an argument to another function.
- It allows one function to call another without knowing its name in advance.
- Callbacks make code more flexible and reusable.
- They are used in the C Standard Library (like qsort())