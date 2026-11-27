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

