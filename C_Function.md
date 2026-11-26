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