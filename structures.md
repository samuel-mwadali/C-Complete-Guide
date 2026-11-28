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
# **C Structs and Pointers**
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

# **C Unions**
## C Unions
A union is similar to a struct in that it can store members of different data types.<br>However, there are somes differences:

- In a struct, eacn member has its own memory
- In a union, all members share the same memory, which means you can only use one of the values at a time.<br>

Most of the time, you will use structs instead of unions, as they can store and access multiple values at the same time, which is more common in everyday programs.<br>
However, unions are useful when you only need to store one of several possible types at a time, and you want to save memory.
## Declare a Union
To create a union, use the union keyword, and then create a variable from it (just like with structs);
```c
#include <stdio.h>
union myUnion{ // Union declaration
    int myNum; // Member (int)
    char myLetter; // Member (char)
    char myString[30]; // Member (char array)
    };
int main(){
    // Create a union variable with the name "u1":
    union myUnion u1;
    return 0;
}
```
## Access Union Members
And just like with structs, to access members of a union, use the dot . syntax.<br>
**Important:** Since all members share the same memory, changing one will affect the others. Only the **last assigned member** holds a valid value.
```c
#include <stdio.h>
union myUnion{ // Union declaration
    int myNum; // Member (int)
    char myLetter; // Member (char)
    char myString[30]; // Member (char array)
    };
int main(){
    // Create a union variable with the name "u1":
    union myUnion u1;

    u1.myNum = 1000;

    //Since this is the last value written to the union, myNum no longer holds 1000 - its value is now invalid
    u1.myLetter = 'A';

    printf("myNum: %d\n", u1.myNum); // This value is no longer reliable
    printf("myLetter: %c\n", u1.myLetter); // Prints 'A'
    return 0;
}
```
```text
myNum: 833
myLetter: A
```
## Size of a Union
The size of a union is usually the same as the size of its largest member.
```c
#include <stdio.h>
union myUnion{ // Union declaration
    int myNum; // Member (int)
    char myString[36]; // Member (char array)
    };
int main(){
    // Create a union variable with the name "u1":
    union myUnion u1;

    printf("Size of union: %zu bytes\n", sizeof(u1));
    return 0;
}
```
```text
Size of union: 36 bytes
```
Since the largest member is 36 bytes, the entire union will also be 36 bytes.<br>If it was a struct instead, the size would be 40 bytes.<br> myNum (4 bytes) + myString (36 bytes) = 40 bytes total
## When to Use Unions
Use unions when:

- You need to store different types in the same location
- You only use one type at a time
- Saving memory is very important
---
# **C Typedef**
## C typedef
The typedef keyword let's you create a new name (an alias) for an existing type. This can make comples declarations easier to read, and your code easier to maintain.<br>For example, instead of always writing float, we can create a new type called Temperature to make the code clearer.
```c
#include <stdio.h>
typedef float Temperature;
int main(){
    Temperature today = 25.5;
    Temperature tomorrow = 18.6;

    printf("Today: %.1f C\n", today);
    printf("Tomorrow: %.1f C\n", tomorrow);
    return 0;
}
```
```text
Today: 25.5 C
Tomorrow: 18.6 C
```
Here, Temperature is just another name for float. However, the code is more expressive: it tells us that these numbers are temperatures, not just any floating-point numbers.
## Why use typedef?
- **Simplifies code:** Shorter, easier-to-read type names
- **Improves clarity:** Expresses intent better (for example, Age instead of just int). Also helps avoid confusion when many variables share the same base type (like float or double)

**Good to know:** In modern C, typedef is often used together with struct, enum and function pointers to keep code clean and easier to read.
## typedef with struct
typedef can be useful with struct, because it lets you avoid writing struct every time
```c
#include <stdio.h>
// Without typedef:
struct Car{
    char brand[30];
    int year;
};

// With typedef:
typedef struct{
    char brand[30];
    int year;
} Car;

int main(){
    struct Car car1 = {"BMW", 1999}; // needs "struct"
    Car car2 = {"Ford", 1969}; // shorter with typedef

    printf("%s %d\n", car1.brand, car1.year);
    printf("%s %d\n", car2.brand, car2.year);
    return 0;
}
```
```text
BMW 1999
Ford 1969
```
**Note:** In real program, you would choose one of the two ways. In this example, struct Car and Car are two separates types that just look the same.<br>This example shows how typedef makes it easier to work with multiple struct variables, like different car models.
```c
#include <stdio.h>
// With typedef:
typedef struct{
    char brand[30];
    char model[30];
    int year;
} Car;

int main(){
    Car car1 = {"BMW", "X5", 1999};
    Car car2 = {"Ford", "Mustang", 1969};
    Car car3 = {"Toyota", "Corolla", 2011};

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
Here you can see how typedef keeps the code clean when structs are nested inside other structs
```c
#include <stdio.h>
// Define three structs with typedef
typedef struct {
    char firstName[20];
    char lastName[20];
} Owner;

typedef struct{
    char brand[20];
    int year;
    Owner owner;
} Car;

typedef struct {
    char name[30];
    Car featuredCar;
} Dealership;

int main(){
    Owner person = {"Samuel", "Mwadali"};
    Car car1 = {"Toyota", 2010, person};
    Dealership d = {"City Motors", car1};
    printf("Dealership: %s\n", d.name);
    printf("Featured Car: %s (%d), owned by %s %s\n",
           d.featuredCar.brand,
           d.featuredCar.year,
           d.featuredCar.owner.firstName,
           d.featuredCar.owner.lastName);
    return 0;
}
```
```text
Dealership: City Motors
Featured Car: Toyota (2010), owned by Samuel Mwadali
```
## typedef with Function Pointers
typedef is also useful with function pointers, which can be hard to read. Instead of writing int (*op)(int, int) every time, you can give the type a short name.
```c
#include <stdio.h>
/*  Operation is a new name for a pointer to a function
    that takes two int values and returns an int */
typedef int (*Operation)(int, int);

int add(int a, int b){
    return a + b;
}
int multiply(int a, int b){
    return a * b;
}
int main(){
    Operation op = add;
    printf("%d\n", op(5, 3)); // 8

    op = multiply;
    printf("%d\n", op(5, 3)); // 15

    return 0;
}
```
```text
8
15
```
Here, Operation is a new name for "a pointer to a function that takes two int values and returns an int". Now you can write Operation op instead of int (*op)(int, int).

---
It is up to you whether you want to use typedef or not. Your code will work the same without it. However, in modern C it is often used to make code shorter, clearer, and easier to maintain.

---
# **C Struct Alignment and Padding**
## Struct Padding
When you create a struct in C, the compiler may add some extra bytes of padding between members.<br>This is done to make the program run faster on your computer, because most CPUs read data more efficiently when it's properly aligned in memory.<br>You rarely need to worry about this unless you work with low-level memory or file formats.<br>
**In short:** Padding means the compiler sometimes adds empty spaces inside a struct to keep things fast and properly aligned in memory.
```c
#include <stdio.h>
struct Example{
    char a; // 1 byte
    int b; // 4 byte
    char c; // 1 byte
};

int main(){
    printf("Size of struct: %zu bytes\n", sizeof(struct Example));
    return 0;

```
```text
Size of struct: 12 bytes
```
You might expect the size to be 1 + 4 + 1 = 6 bytes - but it will usually print 12 bytes!
## Why?
The compiler adds padding bytes so that the int member (b) starts at a memory address that's a multiple of 4. This helps the CPU read it faster.<br>Here's how memory is actully arranged:
| Member | Bytes | Notes |
| --- | --- | --- |
| a | 1 | Stored first |
| padding | 3 | Added so b starts at a multiple of 4 |
| b | 4 | Aligned to 4 byte boundary |
| c | 1 | Stored next |
| padding | 3 | Added to make total size a multiple of 4 |

Total = 1 + 3 + 4 + 1 + 3 = 12 bytes
## How to reduce padding
Padding depends on the order of members in the struct. If you group larger types first, you can make the struct smaller.
```c
#include <stdio.h>
struct Example{
    int b; // 4 byte
    char a; // 1 byte
    char c; // 1 byte
};

int main(){
    printf("Size of struct: %zu bytes\n", sizeof(struct Example));
    return 0;

```
```text
Size of struct: 8 bytes
```
Now the struct is only 8 bytes instead of 12, because there's less padding needed.
## Why It Matters
- Padding helps programs run faster by keeping data aligned in memory
- It can make structs bigger than expected
- Reordering members can reduce the total size
- **Note:** You rarely need to worry about this unless you work with low-level memory or file formats.
## Structs vs Unions
So far, we've talked about padding inside **structs.** But what about unions?<br>
Unions store all members in the same memory location, so there is **no padding between members.** However, both structs and unions still follow alignment rules - the data must start at memory addresses that match their type size.
```c
#include <stdio.h>
struct S{
    char a;
    int b;
    char c;
};
union U{
    char a;
    int b;
    char c;
};

int main(){
    printf("Struct size: %zu\n", sizeof(struct S));
    printf("Union size: %zu\n", sizeof(union U));
    return 0;
}
```
```text
Struct size: 12
Union size: 4
```
Explanation
- **Struct** - members are stored one after another, so padding is added between them.
- **Union** - all members share the same memory, so only the largest member decides its total size

| Feature | Struct | Union |
| --- | --- | --- |
| Members stored | One after another | All share the same memory space |
| Padding between members | Yes | No |
| Aligned to | Each members's type | Largest member's type |
| Total size | Sum of members + padding | Size of largest member(plus padding, if needed)
- *Tip:* You usually don't need to worry about this, but it helps to know why structs sometimes take up more memory than expected, while unions do not.
## Summary
- Struct members are aligned based on their data type size.
- The compiler may add padding bytes to align data properly.
- The total struct size is often larger than the sum of its members.
- Reodering members can reduce padding and save memory
---