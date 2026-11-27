# **C Files**
## File handling
In C, you create, open, read, and write to files by declaring a pointer of type FILE, and using the fopen() function:
```c
FILE *fptr;
fptr = fopen(filename, mode);
```
FILE is basically a data type, and we need to create a pointer variable to work with it (fptr). For now, this line is not important. It's just something you need when working with files.<br>To actually open a file, use the fopen() function, which takes two parameters:
| Parameter | Description |
| --- | --- |
| filename | The name of the actual file you want to open (or create), like filename.txt |
| mode | A letter in double qoutes, like "w", which represents what you want to do with file (read, write or append): (w) - Writes to a file (a) - Appends new data to a file (r) - Reads from a file |
## Create a File
To create a file, you can use the (w) mode inside fopen() function. The w mode is used to write to a file. However, if the file does not exist, it will create one of you.
```c
#include <stdio.h>

int main(){
    FILE *fptr;

    // Create a file
    fptr = fopen("filename.txt","w");
    // Close the file
    fclose(fptr);
    return 0;
}
```
**Note:** If you do not specify a folder, the file is created in the folder where your programs runs(usually the same folder as your C file)<br> **Tip:** If you want to create the file in a specific folder, just provide an absolute path (remember to use double backlash to create a single backlash (\), like we specified in string special characters):
```c
fptr = fopen("C:\\directoryname\\filename.txt", "w");
```
## Closing the file
Did you notice the fclose() function in our example above?<br> This will close the file when we are done with it.<br>It is considered as good practice, because it makes sure that.
- Changes are saved properly
- Other programs can use the file (if you want)
- Clean up unnecessary memory space
---
# **C Write To Files**
## Write To a File
Let's use the w mode from the previous chapter again, and write something to file we just created. The w mode means that the file is opened for writing. To write content to it, you can use the fprintf() function and add the pointer variable (fptr in our example) and some text.
```c
FILE *fptr;
// Open a file in writing mode
fptr = fopen("filename.txt", "w");
// Write some text to the file
fprintf(fptr, "Some text");
// Close the file
fclose(fptr);
```
**Note:** If you write to a file that already exists, the old content is deleted, and new content is inserted. This is important to know, as you might accidentally erase existing content.<br> **For example:**
```c
fprintf(fptr, "Hello world!");
```
## Append content to a file
If you want to add content to a file without deleting the old content, you can use the a mode. The a mode appends content at the end of the file.
```c
FILE *fptr;

// Open a file in append mode
fptr = fopen("filename.txt", "a");

// Append some text to the file
fprintf(fptr, "\n Hi everybody!");

// Close the file
fclose(fptr);
```
**Note:** Just like the w mode: if the file does not exist, the a mode will create a new file with the "appended" content.
---
# **C Read Files**
## Read a File
In the previous chapter, we wrote to a file using w and a modes inside the fopen() function. To read from a file, you can use the r mode.<br>To read from a file, you can use the r mode
```c
FILE *fptr;

// Open a file in read mode
fptr = fopen("filename.txt", "r");
```
This opens filename.txt for reading.<br>Reading a file in C takes a few steps. We will guide you through them, one by one.<br>Next, we need to create a string that should be big enough to store line of text from the file.<br>For example, let's create a string that can store up to 100 characters.
```c
FILE *fptr;

// Open a file in read mode
fptr = fopen("filename.txt", "r");

// Store the content of the file
char myString[100];
```
In order to read the content of the filename.txt, we can use the fgets(), function.<br>The fgets() function takes three parameters.
```c
fgets(myString, 100, fptr);
```
- The first parameter specifies where to store the file content, which will be in the myString array we just created.
- The second parameter specifies the maximum size of data to read, which should match the size of myString(100).
- The third parameter requires a file pointer that is used to read the file(fptr in our example)

Now, we can print the string, which will output the content of the file
```c
FILE *fptr;

// Open a file in read mode
fptr = fopen("filename.txt", "r");

// Read the content and store it inside myString
fgets(myString, 100, fptr);

// Print the file content
printf("%s", myString);

//Close the file
fclose(fptr);
```
**Note:** The fgets function only reads the first line of the file. If you remember, there were two lines of text in filename.txt<br>To read every line of the file, you can use a while loop
```c
FILE *fptr;

// Open a file in read mode
fptr = fopen("filename.txt", "r");

// Store the content of the file
char myString[100];

// Read the content and print it
while(fgets(myString, 100, fptr)){
    printf("%s", myString);
}

// Close the file
fclose(fptr);
```
The loop reads one line at a time. When there are no more lines, fgets() returns NULL (no value), and the loop stops.
## Good Practice
If you try to open a file for reading that does not exist, the fopen() function will return NULL.<br>*Tip:* As a good practice, we can use an if statement to test for NULL, and print some text instead (when the file does not exist)
```c
FILE *fptr;
// Open a file in read mode
fptr = fopen("loremipsum.txt", "r");

// Print some text if the file does not exist
if (fptr == NULL){
    printf("Not able to open the file.");
} else {
    // Close the file (only if it was opened)
    fclose(fptr);
}
```
With this in mind, we can create more reliable code if we use our "read a file" example above again.<br> **Example** <br> If the file exists, read the content and print it. if the file does not exist, print a message.
```c
#include <stdio.h>
int main(){
    FILE *fptr;
    // Open a file in read mode
    fptr = fopen("filename.txt", "r");

    // Store the content of the file
    char myString[100];

    // If the files exits
    if (fptr != NULL){
        // Read the content and print it
        while (fgets(myString, 100, fptr)){
            printf("%s", myString);
        }
        // Close the file
        fclose(fptr);
    } else {
        // If the file does not exist
        printf("Not able to open the file.");
        }
    return 0;
}
```
**Note:** Only close a file with fclose() if it was opened. When fopen() returns NULL, there is no file to close and fclose(NULL) can make the program crash.

---
