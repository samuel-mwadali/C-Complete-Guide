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