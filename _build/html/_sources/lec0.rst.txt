Lecture 0 Prerequisites
=========================

Assembly
-------------------------
- **Branches**: Kind of like Python tabs or areas of code encapsulated in squiggly braces ({}), they're areas of code that are called upon to perform a task
-  **Operands**: add, mul, general operations you can perform
-  **Registers**: Areas of memory (or cache) that can be accessed for remembering values or pointers to values

C
-------------------------
-  **Memory Allocation**: If you haven't done C before, manual memory allocation is going to be something to read about. A standard int is made in an area of memory called "the stack". A pointer to an int is made in an area of memory called "the heap". Creating memory on the stack is cool, but limited and requires the system to manage the deletion of it. Creating memory on the heap is much cooler and easier to manage, i.e *you* have to manage the deletion of the memory.
-  **Pointers**: dawg if you're unfamiliar with this, I'm sorry but CSE120 might not be the move.

Linux
-------------------------
-  **find**: A program used in the terminal for finding... something. I've really only used it to find files. For example:
    .. code:: bash
        
        find /my/folder/location/ -name "*wombat*"

    looks for a file name containing "wombat" (like 'wombat.txt' or 'best_wombat_pic.png'), but only files in the folder called "location", which is inside the folder called "folder", which is inside the folder called "my".
- **cat**: A program used in the terminal for reading all the information in a file. For example:
    .. code:: bash
    
        cat /my/folder/location/wombat.txt

    will print all the information from wombat.txt to the terminal.
-  **grep**: A program used in the terminal for filtering information. For example:
    .. code:: bash

        cat /my/folder/location/wombat.txt | grep 'wally wombat'
        
    will use the ``cat`` program to print all the information from wombat.txt, but then passes all that text to ``grep`` which will only let lines containing the string "wally wombat" be printed.
-  **emacs/vi**: ``emacs`` and ``vi`` are two text editing programs using in the command line. Both have merits, and are awesome for programming with. ``vi`` is kinda garbage, so a newer, somewhat more user-friendly version was released called ``vim``. Probably watch a YouTube video on using either of these, it's really long-winded and I'm lazy.

GCC/Make
-------------------------
-  GCC and Make were explained in the FAQ page. In short: GCC is a collection of compilers that you can use in Linux to turn your human-readable code into computer-readable code. Make is a means of quickly and easily turning your development process into a breeze.
-  **Compiler**
    -  A compiler turns your higher-level language code (C, C++, Rust, etc.) into a lower-level language (Assembly, probably). It consists of different parts that each serve a purpose to decipher your code and generate assembly code.
    -  ``gcc main.c -o my_program`` will turn your C code into an executable called "my_program". It will not be written in assembly (because GCC assumes you're trying to make a runnable program), but will be ready for the operating system to execute the code.
-  **Linker**
    -  Look at the following code in main.c:
        
        .. code:: C
            
            int main(){
                printf("Hello\n");
                return 0;
            }

        If we tried to compile the above code using ``gcc main.c -o print_hello``, it would throw errors. This is because printf is not a part of the C language, it's from a library in the C language. By changing the code to include the proper library, the code compiles and links the library code we requested:
    
            .. code:: C

                #include <stdio.h>
                int main(){
                    printf("Hello\n");
                    return 0;
                }
    
    - Since printf is not a part of the language by default, the linker resolves the issue when the compiler says "what the heck is this thing?" by fetching the function defined for printf to work properly from the file "stdio.h"

