Setting up Linux on your machine
==================================

What is Linux?
--------------------------
- Linux, in our context, is a general blanket-statement referring to a group of similar operating systems like Windows or MacOS. 
- There is no single version of "Linux OS" to install, which is different from something like Windows (where you assume you're installing the latest version). 
    - What you are looking for is a distribution of Linux, such as: Ubuntu, Debian, Mint, Manjaro, Fedora, Solus, and more. If you're unfamiliar with most of these, install Ubuntu.
    - Something confusing you might find is that there are also multiple Ubuntu versions. These are different user experiences, but all fundamentally do the same thing. You can try basically any of them. Or, try KDE/XFCE/Budgie as those are the most Windows-esque experiences. 
- If you have never seen/used Linux before, the learning curve is a little bit steep and there are lots of words used to refer to other things. For example, if you search to install "Linux OS", this does not exist.
- However I will do my best to help you get set up and solve problems (provided we aren't being academically dishonest). My Discord is macmoholic#2221 if you'd like to DM me for questions, but to be clear, I'm not gigabrain or anything I just have Linux experience

Installing Linux on your Computer
----------------------------------------

- Virtual Machine Install (RECOMMENDED)
    - Watch this video I made for a step-by-step guide to install Linux on VirtualBox: https://youtube.com/playlist?list=PLRtYQk6Dce3qp_i2fEkwVl8BCNceqeAM_

- Other options
    - You can also install Ubuntu on a flash drive, which is very convenient I think. Give it a whirl sometime (use Balena-Etcher to copy the installed to a flash drive, and then reboot into the flash drive through your BIOS)

Using the Linux Terminal
-----------------------------------

- Summary
    - Check the video I sent for the VM install to see the commands being used. Below is just a cheat sheet

- Commands cheat sheet
    - **ls**
        - Lists files in the current directory
    - **cd**
        - Changes directory to the specified location. Use ``cd my_folder`` to enter a folder called "my_folder"
    - **mkdir**
        - Makes a directory with the specified name. Use ``mkdir my_folder`` to make a folder called "my_folder"
    - **rmdir**
        - Removed a directory with the specified name. Use ``rmdir my_folder`` to delete a folder called "my_folder" provided the folder is empty
    - **touch**
        - Creates a file provided a specified name. Use ``touch main.c`` to create a C code file called "main.c". Works with any extension, but is generally just used to make text-based files
    - **rm**
        - **PERMANENTLY** deletes a file provided a specified name. Use ``rm main.c`` to delete a file called "main.c", or use ``rm -r my_folder`` to recursively delete all files in a folder called "my_folder", including the folder
    - **find**  
        - Searches for file names from a given directory. Use ``find my_folder -name "*bob*"`` for any file that contains the word "bob"
    - **cat**
        - Prints out all the text in a given file. Use ``cat main.c`` to print out all the code from a C code file called "main.c"
    - **grep**
        - Filters down text for specific lines. Use ``cat main.c | grep 'hello'`` to only print out lines from "main.c" containing the word "hello"
    - **gcc**
        - Compiles a C program to executable code. Use ``gcc main.c -o my_executable`` to compile "main.c" into an executable code file called "my_executable". You can run "my_executable" with ``./my_executable``
    - **apt**
        - The Ubuntu package manager. Use ``sudo apt install vim`` to install a package called "vim"
    - **snap**
        - An additional package manager on Ubuntu. Use ``snap install code`` to install a program called "code". Some programs require a classic install, like ``snap install --classic code``