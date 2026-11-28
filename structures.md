# **C Structures (structs)**
## Structures
Structures (also called structs) are a way to group several related variables into one place.<br>Each variable in the structure is known as member of the strucure.<br>Unlike an array, a structure can contain many different data types (int, float, char, etc)
## Create a Structure
You can create a structure by using the struct keyword and declaring each of its members inside curly braces;
```c
struct myStructure{ // structure declaration
    int myNum; // Member (int variable)
    char myLetter; // Member (char variable)
}; // End the structure with a semi colon
```
To access the structure, you must create a variable of it.
Use the struct keyword inside the main() function, followed by name of the structure and then the name of the structure variable:<br>Create a struct variable with the name "s1":
```c
struct myStructure{
    int myNum;
    char myLetter;
};
int main(){
    struct myStructure s1;
    return 0;
}
```
## Access Structure Members
To access members of a structure, use the dot syntax (.) <br>**Example**
```c
#include <stdio.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
};
int main(){
    // Create a structure variable of myStructure called s1
    struct myStructure s1;

    // Assign values to members of s1
    s1.myNum = 13;
    s1.myLetter = 'B';

    // Print values
    printf("My number: %d\n", s1.myNum);
    printf("my letter: %c\n", s1.myLetter);
    return 0;
}
```
```text
My number: 13
my letter: B
```
Now you can easily create multiple structure variables with different values, using just one structure.<br> **Example**
```c
#include <stdio.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
};
int main(){
    // Create a structure variable of myStructure called s1
    struct myStructure s1;
    struct myStructure s2;

    // Assign values to members of s1
    s1.myNum = 13;
    s1.myLetter = 'B';

    s2.myNum = 20;
    s2.myLetter = 'C';

    // Print values
    printf("My number: %d\n", s1.myNum);
    printf("my letter: %c\n", s1.myLetter);
    printf("My number: %d\n", s2.myNum);
    printf("my letter: %c\n", s2.myLetter);
    return 0;
}
```
```text
My number: 13
my letter: B
My number: 20
my letter: C
```
## What about strings in strutures?
Remeber that strings in C are actually an array of characters, and unfortunately, you can't assign a value to an array like this:<br> **Example**
```c
#include <stdio.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
    char myString[30];
};
int main(){
    struct myStructure s1;

    // Trying to assign a value to the string
    s1.myString = "Samuel Mwadali";

    // Trying to print the value
    printf("My string: %s\n", s1.myString);
    return 0;
}
```
```text
An error will occur.
```
However, there is a solution for this! You can use the strcpy() function (from <string.h>) and assign the value to s1.myString, like this:<br> **example**
```c
#include <stdio.h>
#include <string.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
    char myString[30]; // string
};
int main(){
    struct myStructure s1;

    // Assign a value to the string using the strcpy function
    strcpy(s1.myString, "Samuel Mwadali");

    // Print the value
    printf("My string: %s\n", s1.myString);
    return 0;
}
```
```text
My string: Samuel Mwadali
```
## Simple Syntax
You can also assign values to members of a structure variable at declaration time, in a single line.<br>Just insert the values in comma-separated list inside curly braces {}. Note that you don't have to use the strcpy() function for string values with this technique.<br> **Example**
```c
#include <stdio.h>
#include <string.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
    char myString[30]; // string
};
int main(){
    // Create a structure variable and assign values to it.
    struct myStructure s1 = {13, 'B', "samuel mwadali"};

    // Print the value
    printf("%d %c %s", s1.myNum, s1.myLetter, s1.myString);
    return 0;
}
```
```text
13 B samuel mwadali
```
**Note:** The order of the inserted values must match the order of the variable types declared in the structure (13 for int, 'B' for char, etc)
## Copy Structures
You can also assign one structure to another. In the following example, the values of s1 are copied to s2:
```c
#include <stdio.h>
#include <string.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
    char myString[30]; // string
};
int main(){
    // Create a structure variable and assign values to it.
    struct myStructure s1 = {13, 'B', "samuel mwadali"};
    struct myStructure s2;
    s2 = s1;

    // Print the value
    printf("%d %c %s", s2.myNum, s2.myLetter, s2.myString);
    return 0;
}
```
```text
13 B samuel mwadali
```
## Modify Values
If you want to change/modify a value, you can use the dot syntax (.).<br>And to modify a string value, ths strcpy() function is useful again.<br> **Example**
```c
#include <stdio.h>
#include <string.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
    char myString[30];
};
int main(){
    // Create a structure variable and assign values to it.
    struct myStructure s1 = {13, 'B', "samuel mwadali"};

    // Modify values
    s1.myNum = 30;
    s1.myLetter = 'C';
    strcpy(s1.myString, "Something else");

    // Print the value
    printf("%d %c %s", s1.myNum, s1.myLetter, s1.myString);
    return 0;
}
```
```text
30 C Something else
```
Modifying values is especially useful when you copy structure values
```c
#include <stdio.h>
#include <string.h>
// Create a structure called myStructure
struct myStructure{
    int myNum;
    char myLetter;
    char myString[30];
};
int main(){
    // Create a structure variable and assign values to it.
    struct myStructure s1 = {13, 'B', "samuel mwadali"};
    struct myStructure s2;

    // Copy s1 values to s2
    s2 = s1;

    // Change s2 values
    s2.myNum = 30;
    s2.myLetter = 'C';
    strcpy(s2.myString, "Something else");

    // Print the value
    printf("%d %c %s\n", s1.myNum, s1.myLetter, s1.myString);
    printf("%d %c %s", s2.myNum, s2.myLetter, s2.myString);
    return 0;
}
```
```text
13 B samuel mwadali
30 C Something else 
```
**Ok, so, how are structures useful?**<br>Imagine you have to write a program to store different information about cars, such as brand, model, and year. What's great about structures is that you can create a single "Car template" and use it for every car you make.
## Real_Life Example
Use a structure to store different information about cars
```c
#include <stdio.h>
#include <string.h>
// Create a structure called myStructure
struct Car{
    char brand[30];
    char model[30];
    int year;
};
int main(){
    struct Car car1 = {"BMW", "X5", 1999};
    struct Car car2 = {"Ford", "Mustang", 1969};
    struct Car car3 = {"Toyota", "Corolla", 2011};

    // Print the value
    printf("%s %s %d\n", car1.brand, car1.model, car1.year);
    printf("%s %s %d\n", car2.brand, car2.model, car2.year);
    printf("%s %s %d\n", car3.brand, car3.model, car3.year);
    return 0;
}
```
```text
BMW X5 1999
Ford Mustang 1969
Toyota Corolla 2011 
```
---
# **C Nested Structures**
## Nested Structs
A structure can contain another structure as a member. This is called a **nested structure**, and it is useful when you want to group related data together in layers
```c
#include <stdio.h>
// Create a structure
struct Owner{
    char firstName[30];
    char lastName[30];
};
struct Car{
    char brand[30];
    int year;
    struct Owner owner; // Nested structure
    };
int main(){
    struct Owner owner = {"Binary", "Flores"};
    struct Car car1 = {"Ford", 2010, owner};

    // Print the value
    printf("Car: %s (%d)\n", car1.brand, car1.year);
    printf("Owner: %s %s\n", car1.owner.firstName, car1.owner.lastName);
    return 0;
}
```
```text
Car: Ford (2010)
Owner: Binary Flores
```
Here, the Car structure contains another structure (Owner) inside it. This makes it easy to organize complex data, for example, a car and its owner.<br>To access a member of the inner structure, use the dot. twice, like car1.owner.firstName
## Create the inner Structure Directly
You can also create the innner structure directly inside the curly braces, without creating a separate variable for it first
```c
#include <stdio.h>
// Create a structure
struct Owner{
    char firstName[30];
    char lastName[30];
};
struct Car{
    char brand[30];
    int year;
    struct Owner owner; // Nested structure
    };
int main(){
    struct Car car1 = {"Ford", 2010, {"Binary", "Flores"}};

    // Print the value
    printf("Car: %s (%d)\n", car1.brand, car1.year);
    printf("Owner: %s %s\n", car1.owner.firstName, car1.owner.lastName);
    return 0;
}
```
```text
Car: Ford (2010)
Owner: Binary Flores
```
---
# **C Arrays of Structs**
## Arrays of Structs
A struct groups related values, like the name and age of one student.<br>When you want to store many student, you can create an array of structs. Each element in the array is a whole struct
```c
#include <stdio.h>
// Create a structure
struct Student{
    char name[20];
    int age;
    };
int main(){
    struct Student students[3] ={
        {"Mwadali", 20},
        {"Anja", 22},
        {"Jenny", 21}
        };
    printf("%s is %d years old\n", students[0].name, students[0].age);
    return 0;
}
```
```text
Mwadali is 20 years old
```
Use the index to pick a student, and the dot (.) to pick a member. For example,<br> students[0].name is the name of the first student.
## Loop through an Array of Structs
Use a for loop to print all the students:
```c
#include <stdio.h>
// Create a structure
struct Student{
    char name[20];
    int age;
    };
int main(){
    struct Student students[3] ={
        {"Mwadali", 20},
        {"Anja", 22},
        {"Jenny", 21}
        };
    int i;
    for (i = 0; i < 3; i++){
            printf("%s is %d years old\n", students[i].name, students[i].age);
    }
    return 0;
}
```
```text
Mwadali is 20 years old
Anja is 22 years old
Jenny. is 21 years old
```
## Change values
To change a member, use the index to pick the student, and the dot to pick the member<br>In this example, we make two changes: we change the age of the first student (Mwadali) to 23; and the name of the second student (Anja) to "Samuel":
```c
#include <stdio.h>
#include <string.h>
// Create a structure
struct Student{
    char name[20];
    int age;
    };
int main(){
    struct Student students[3] ={
        {"Mwadali", 20},
        {"Anja", 22},
        {"Jenny", 21}
        };
    students[0].age = 23;
    strcpy(students[1].name, "Samuel");

    int i;
    for (i = 0; i < 3; i++){
            printf("%s is %d years old\n", students[i].name, students[i].age);
    }
    return 0;
}
```
```text
Mwadali is 23 years old
Samuel is 22 years old
Jenny is 21 years old
```
**Note:** We use = to change the age, because it is a number. For the name, we use strcpy, because you cannot use = for strings.
## Real-Life Example
Find the student with the highest grade
```c
#include <stdio.h>
// Create a structure
struct Student{
    char name[20];
    int grade;
    };
int main(){
    struct Student students[4] ={
        {"Mwadali", 92},
        {"Anja", 85},
        {"Jenny", 88},
        {"Samuel", 90}
        };

    int best = 0;
    int i;

    for (i = 0; i < 4; i++){
            if (students[i].grade > students[best].grade){
                    best = i;
            }
            printf(" Students name: %s Student grade: %d\n", students[i].name, students[i].grade);
    }
    printf("Top student: %s (%d)\n", students[best].name, students[best].grade);
    return 0;
}
```
```text
 Students name: Mwadali Student grade: 92
 Students name: Anja Student grade: 85
 Students name: Jenny Student grade: 88
 Students name: Samuel Student grade: 90
 Top student: Mwadali (92)
```
The variable best **best** stores the index of the best student so far. The loop compares each student with best one, and updates best when it finds a higher grade.
---
# **Structs and Pointers**
## Strucures and Pointers
You can use pointers with structs to make your code more efficient, especially when passing structs to functions or changing their values.<br>To use a pointer to a struct, just add the + symbol, like you would with oher data types.<br>To access its members, you must use the -> operator instead of the dot . syntax.
```c
#include <stdio.h>
// Define a struct
struct Car{
    char brand[20];
    int year;
};

int main(){
    struct Car car ={"Toyota", 2020};

    // Declare a pointer to the struct
    struct Car *ptr = &car;

    // Access members using the -> operator
    printf("Brand: %s\n", ptr->brand);
    printf("Year: %d\n", ptr->year);
    return 0;
}
```
```text
Brand: Toyota
Year: 2020 
```
ptr -> brand is a shorter way to write (*ptr).brand: it goes to the struct that ptr points to, and gets its brand member.
## Passing Struct Pointers to Functions
Just like in the Pass by reference chapter, you can pass a pointer to a struct to a function, so the function can change the original struct.
```c
#include <stdio.h>
// Define a struct
struct Car{
    char brand[30];
    int year;
};
// Function that takes a pointer to a Car struct and updates the year
void updateYear(struct Car *c){
    c->year = 2025; // Change the year
    }
int main(){
    struct Car myCar ={"Toyota", 2020};

    updateYear(&myCar); // Pass a pointer so the function can change the year

    printf("Brand: %s\n", myCar.brand);
    printf("Year: %d\n", myCar.year);
    return 0;
}
```
```text
Brand: Toyota
Year: 2025
```
## Why Use Sruct Pointers?
Using pointers with structs is helpful when:
- **You want to avoid copying large amounts of data.** Instead of copying a whole struct, you can just pass a pointer. This makes your program faster and uses less memory
- **You want to change values inside a function.** If you pass a pointer to a struct into a function, the function can change the original values.
- **You want to create struct dynamically using memory allocation.** With pointers, you can use malloc() to create structs while the program is running.

**Tip:** If you're working with big programs or many values, struct pointers can help make your code cleaner and more efficient.