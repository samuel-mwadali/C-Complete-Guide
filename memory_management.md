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