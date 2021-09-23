FAQ Topics
==================================

- This page is for things like "RISC ISA" and "GCC" that was foreign and concerning for some in the discord chat. Just DM me on discord to add more things here (macmoholic#2221)

RISC
--------------------------------
- You may end up seeing RISC used lots of different ways: RISC, RISC-V, RISC ISA, etc. These all mean different things, but this definition is just for defining the general topic of RISC.
- Imagine assembly language as a real, speakable language. That would make each of the instructions (add, mul, mov, etc.) as individual letters, and combining groups of these letters together would make a speakable word, or runnable function. Kinda make sense? So maybe a function that checks if an integer is odd is analogous to a word, and the main branch of code that runs all of our defined functions is a sentence.
- x86-64, the assembly architecture that runs in Intel and AMD processors, is like a language with over 1000 letters: that's a whole shitton of letters! We don't need to remember all of these letters, but our processors do, which sounds like a nightmare to me.
    - Remember, 'letters' are analogous to 'instructions', so it's less about remembering the shape of a letter and more about remembering how to perform an operation when given an instruction. e.g if someone tells you to write the letter 'b', you're gonna know what it looks like and how it sounds to say it. But when a computer is provided the instruction ``mov ax,8``, it needs to know how to move things, find where the register ``ax`` is, and then put ``8`` there. 
- **RISC** is an acronym for 'Reduced Instruction Set Computing'. The RISC concept was developed much later than x86-64 with the entire goal being: use much a much smaller instruction set. The benefits of this are, of course, that our processors don't need to be programmed to know lots and lots of instructions, they just need to know a few. 
    - To further the analogy above, RISC-V or MIPS (which are both RISC assembly languages) have a smaller set of letters, which means the processors built on RISC-V/MIPS don't need to remember so many different letters to create the same sentences.

RISC ISA
--------------------------------
- RISC, as explained above, stands for Reduced Instruction Set Computing. ISA stands for Instruction Set Architecture. The ISA, in our context, is like the index of all instructions you can use in a language. The x86-64 ISA consists of thousands of different instructions, and the RISC ISA consists of much, much fewer than this.

RISC-V
--------------------------------
- RISC-V is a specific kind of RISC assembly language. While RISC is more of a concept/set of expectations you can have about a particular assembly language, RISC-V is an actual language that follows these expectations. 
- RISC-V only has 47 instructions. The thousands of instructions in x86-64 that do NOT exist in RISC-V have to be written by hand. Luckily, these 47 are the absolute most common instructions used, so don't fret.

GCC
--------------------------------
- It's just occurred to me that this is not in alphabetical order. Bug me about this if it bothers you. Sorry D:
- GCC stands for "GNU Compiler Collection". GNU is a collection of free software from the Free Software Foundation, so think of GCC as "a collection of free code compilers from a group of people who make free code-related programs". GCC in our experience will probably refer to the "GNU C Compiler", which as the name states, will compile C code into executable binary code.
- GCC is the most common way to compile C/C++/other languages on Linux machines. You may actually have it installed on your MacOS machine too (open the terminal and type ``gcc --version`` and it may provide GCC version information)

Linux
--------------------------------
- Linux is an operating system kernel. You don't super need to know what a kernel is, but just know that it's the core of the operating system experience. Windows uses the Windows NT kernel, and MacOS uses the XNU kernel. XNU and Linux are both based on Unix, so there is a lot of overlap in how MacOS and Linux work. 
- If you're panicking because you've only used Windows/MacOS for your entire life, that's totally okay I promise! But you may want to consider diving head-first into the Linux user experience this quarter. As our professor mentioned: it is very, very unlikely the devices you work on in the future will be running Windows or MacOS. Please see the "linux_help" page on this site for further info :)

make
--------------------------------
- ``make`` is a program made by the Free Software Foundation, just like GCC. It takes code written in a language, and performs operations for you to make compiling, cleaning, etc. easier and shorter.
    - Imagine you have a folder with a single program, ``main.cpp``. You want to compile it and run it. So, you could probably run the GCC compiler to make it into an executable program: ``g++ main.cpp -o myprogram``. You type that into your Linux terminal, and ta-da! You have runnable code.
    - However, now you also want to compile it and turn on warnings. So you re-type the whole thing but with an additional argument: ``g++ main.cpp -o myprogram -Wall -Wextra``, which works fine.
    - Your boss provides you a set of new arguments they want your code compiled with: ``g++ main.cpp -o myprogram -pedantic -Wall -Wextra -Wcast-align -Wcast-qual -Wctor-dtor-privacy -Wdisabled-optimization -Wformat=2 -Winit-self -Wlogical-op -Wmissing-declarations -Wmissing-include-dirs -Wnoexcept -Wold-style-cast -Woverloaded-virtual -Wredundant-decls -Wshadow -Wsign-conversion -Wsign-promo -Wstrict-null-sentinel -Wstrict-overflow=5 -Wswitch-default -Wundef -Werror -Wno-unused``. You shit a brick, because there's no chance in hell you're typing that every single time you need to compile a single program.
    - make can define a set of commands to allow you to run the first one, the second one, or the third one without typing all that nonsense.
- Utilizing ``make`` is really easy. In a terminal, in the directory containing a Makefile (a file for defining all of our make shortcuts), a user can define a set of commands to run to make the development process much easier.
    - For example, in a previous class, my professor last quarter defined the following:
        - ``make build``  which compiles all the code, but will NOT run it
        - ``make check``  which compiles all the code, runs it, and checks to see if the output is correct
        - ``make clean``  which deletes all the binary files that are no longer needed
        - ``make run``    which compiles all the code, and then runs it
        - ``make submit`` which compiles all the code, runs it, and submits it to the professor
    
ssh
--------------------------------
- ``ssh`` is a program that means "Secure SHell". It's a way of connecting your computer to another computer, and performing commands on that other computer.
    - Example time: imagine a programming workplace where 60 different developers need a ton of computing power. Instead of creating lots of big, powerful computers for every individual worker to use, the workplace creates a single supercomputer. "Well 60 workers can't possibly share a single computer" you say? Sure they can! Each developer gets a cheap laptop/uses a home computer, and will use ``ssh`` to remotely connect to the computer.
    - The above example is based around our UCSC UNIX Timeshare, where the single supercomputer is the machine the timeshare is running on, and the 60 developers are all the students and staff of the UCSC CSE courses. The "cheap laptops/home computers" I referred to are any/all of the devices we are using to take the course, so you can absolutely install ssh on your machine. But don't do it yet. I'll update this page when we know what we need to ssh into.
    - ``ssh`` is a terminal-only program. We're most likely to use this when working on the UCSC Unix Timeshare. As this becomes a much more important factor in the quarter, like I said, I will update this. If you're looking for ways to connect to the Unix Timeshare, please find the "timeshare_help" page on this site. It uses ``ssh``, or ``sshfs``.
