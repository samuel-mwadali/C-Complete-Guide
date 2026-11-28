# **C Memory Management**
Memory management is the process of handling how much memory a program uses through different operations
## Memory in C
Understanding how memory works in C is important. When you create a basic variable, C will automatically reserve space for that variable. An int variable for example, will typically occupy 4 bytes of memory, while a double variable will occupy 8 bytes of memory.<br> You can use the size of operator to find the size of different types.
```c
#include <stdio.h>

int main(){
    int myInt;
    float myFloat;
    double myDouble;
    char myChar;

    printf("%zu\n", sizeof(myInt)); // 4 bytes
    printf("%zu\n", sizeof(myFloat)); // 4 bytes
    printf("%zu\n", sizeof(myDouble)); // 8 bytes
    printf("%zu\n", sizeof(myChar)); // 1 bytes
    return 0;
}
```
```text
4
4
8
1 
```
## Why is it important to know?
If you create a program that occupies too much, or unnecessary memory, it can result in slow and poor performance.<br>In C, you have to manage memory yourself. It is a complicated task, but is also quite powerful when used correctly. Properly managing the computer memory is optimizes the performance of hte program, so it is useful that you know how to release memory when it is no longer required and only use as little as necessary for the task.<br>In previous chapters you learned about memory addresses and pointers.Both have an importance when it comes to memory management, since it is possible to work directly with memory through pointers.<br>But be careful, pointers must be handled with care, since it is possible to damage data stored in other memory addresses.
## Memory Management
Memory management is the process of handling how much memory a program uses through allocation, reallocation and deallocation (often reffered to as "freeing"). We will introduce each of these topics in the following chapters.<br>These are the steps when you work with dynamic memory:

| steps | |
| --- | --- |
| 1.Allocate **malloc() / calloc()** |
| 2.Access **ptr[0] = 12** -> | -> 3.Reallocate **realloc()** |
| 4.Free **free()** | |
---
# **Allocate Memory**
The process of reserving memory is called allocation. The way to allocate memory depends on the type of memory.<br>C has two types of memory: Static memory and dynamic memory
## Static Memory
Static memory is memory where the size is decided before the program runs. Allocation of static memory is also known as compile time memory allocation.<br>C automatically reserves memory for the variables you create. The size is decided when th program is compiled, and it cannot change while the program runs.<br>For example, if you create an integer array of 20 students, C will reserve space for 20 elements which is typically 80 bytes of memory(20 * 4)
```c
#include <stdio.h>

int main(){
    int students[20];
    printf("%zu bytes", sizeof(students));
    return 0;
}
```
```text
80 bytes
```
But when the course starts, it turns out only 12 students are attending. Then you have wasted the space of 8 unused elements.<br>Since you are not able to change the size of the array, you are left with unnecessary reserved memory. Note that the program will still run, and it is not damaged in any way. But if your program contains a lot of this kind of code, it may run slower thant it optimally could.<br>If you want better control of allocated memory, take a look at Dynamic Memory below.
## Dynamic memory
Dynamic memory is memory that is allocated after the program start running. Allocation of dynamic memory can also be referred to as *runtime memory allocation*. <br>
Unlike with static memory, you have full control over how much memory is being used at any time. You can write code to determine how much memory you need and allocate<br>Dynamic memory does not belong to a variable, it can only be accessed with pointers.<br>To allocate dyanamic memory, you can use the malloc() or calloc() functions. It is necessary to include the <stdlib.h> header to use them. The malloc() and calloc() functions allocate some memory and return a pointer to its address.
```c
int *ptr1 = malloc(size);
int *ptr2 = calloc(amount, size);
```
The malloc() function has one parameter, size which specifies how much memory to allocate measured in bytes.<br>The calloc() function has two parameters:

- amount - Specifies the amount of items to allocate
- size - Specifies the size of each item measured in bytes

**Note:** The data in the memory allocated by allocated by malloc() is unpredictable. To avoid unexpected values, make sure to write something into the memory before reading it.<br>Unlike malloc(), the calloc() function writes zeroes into all the allocated memory.However, this makes calloc() slightly less efficient.<br>The best way to allocate the right amount of memory for a data type is to use the sizeof operator
```c
int *ptr, *ptr;
ptr1 = malloc(sizeof(*ptr1));
ptr2 = calloc(1, sizeof(*ptr2));
```
Be careful: sizeof(*ptr1) tells C to measure the size of the data at the address. If you forget the * and write sizeof(ptr1) instead, it will measure the size of the pointer itself, which is the (usually) 8 bytes that are needed to store a memory address.<br>
Note: The sizeof operator cannot measure how much dynamic memory is allocated. When measuring dynamic memory, it only tells you the size of the data type of the memory. For example, if you reserve space for 5 float values, the sizeof operator will return 4, which is the number of bytes needed for a single float value.<br>
Let's use dynamic memory to improve the students example above.<br>As noted previously, we cannot use sizeof to measure how much memory was allocated, we have to calculate that by multiplying the amount of items by the size of the data type.
```c
int * students;
int numStudents = 12;
students = calloc(numStudents, sizeof(*students));
printf("%zu", numStudents * sizeof(*students));
```
## Notes
When working with dynamic memory allocation, you should also check for errors and free memory at end of the program. You will learn more about this in the next chapters.
## Stack Memory
For completeness, it is worth mentioning stack memory. Stack memory is reserved for variables that declared inside functions (like the students array in main() ). Just like static memory, its size is decided before the program runs, and C handles it automatically, you do not need to allocate or free it yourself.<br>When a function is called, stack memory is allocated for the variables in the function. When the function returns the stack memory is freed.<br>It is good to be aware of stack memory to be able to handle the memory usage of nested function calls and recursion. Recursion that repeats itself too many times may take up too much stack memory. When that happens it is called a stack overflow.
