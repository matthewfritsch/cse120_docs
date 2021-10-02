Using git 
=======================

What is git?
-----------------------
- **git** is a program developed for version control in developing programs. It's widely used in the industry for collaborating on projects, as well as managing multiple versions of a single project. 
- **git** is relatively easy to use on a regular basis, but there are situations where it can become difficult to solve a problem (serious merge conflicts, for example). In our course, we will likely have very few (if any) of these challenges.

How does git differ from GitHub?
------------------------------------
- When working with **git**, a user creates a "repository" of their code. This is often a folder where all of the code sits, and the code can automatically switch between different versions of itself. This repository is stored on your local machine, somewhere on your drive.
- GitHub is a website for storing your git repositories remotely. This way, if your device was destroyed, all of the code would be saved. 
- GitHub also has lots of tools to make it easy to collaborate with others. For example, if two developers are not working on the same network, it's very easy for user A to allow user B to develop on their mutual GitHub repository. There also exists a number of project development tools for aiding in the process (like task boards).

How do I use git?
------------------------------------
- Working with git isn't super challenging. The first thing you want to answer for yourself is this:
    * Do I want to pull code from an already existing git repository, or
    * Do I want to create a new git repository?

I want to pull code from an already existing repository.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Cool! This is very easy. In your terminal, type ``git clone <repository link>``. You can also use an ssh key, but I'm going to focus on https repo links.
- If you entered the link correctly, you should see something along these lines:
    .. code:: text
        
        Cloning into 'folder_name'...
        remote: Enumerating objects: 209, done.
        remote: Counting objects: 100% (209/209), done.
        remote: Compressing objects: 100% (134/134), done.
        remote: Total 209 (delta 120), reused 163 (delta 74), pack-reused 0
        Receiving objects: 100% (209/209), 286.43 KiB | 2.75 MiB/s, done.
        Resolving deltas: 100% (120/120), done.

- You should now have a folder with the same name as 'folder_name'. In this folder is all the code you need to work with. 
- **NOTE**: If you are trying to take your already existing code and put it on GitHub/similar, you want to follow the steps above! Before you do them however, 
    * Open your GitHub
    * Create a new repository on GitHub
    * Copy the URL or SSH key provided, as this will be your URL to use in the above steps. 
    * Do the above steps to clone the empty repository
    * Move your current code files into the empty folder
    * Follow the below steps, starting **after** the ``git init`` part.
        
I want to make my own git repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Awesome. This is a few more commands, but I promise I will try to help make sense of each one for ya.

* Initialize the repository
    * Go to the folder with your code, or the folder where your code will be (see the Linux help page for doing this with terminal. ``cd`` and ``ls`` will be helpful)
    * Run ``git init``, which will add the necessary files to identify this folder as a git repository. Now, running git commands will work! 
* Make the necessary changes
    * This is all you. Whatever code you need to write, files you need to add, now is when you do them. Move on to the next step as soon as you're ready to save your work in the repository.
* Stage your files to be saved
    * It's time to choose what files you want to commit to the repository. Use ``git status`` to show what your repository looks like. Here is an example output:
        .. code:: text

            On branch master

            No commits yet
            
            Untracked files:
            (use "git add <file>..." to include in what will be committed)
                thing.c
            
            nothing added to commit but untracked files present (use "git add" to track)
        
    * From the list of files under "Untracked files", you want to add each file you intend to commit to the repository. If you want to add just a few, use ``git add <filename>`` to add that one. If you want to add all, use ``git add *``, which uses * to mean "everything".
* Commit your changes
    * What you just did was *not* save the files. You told git specifically which files you want to save. Now you can save them using ``git commit -m <message>``. The message is necessary to indicate what changes you're making to the repository. That way, when you look at the history of your file, you can find the time/date when a change was made. Plus, if you want, you can look at the code before that change was made!
    * If you forget the -m, you might be thrown into a vim entry, which you can leave by typing "ESC" and ":wq". Don't forget the -m!
* Push, if needed
    * You just committed your changes, but they only exist on your local machine. If that's all you want to do, no worries, you're done! If you do want to push your changes to GitHub/etc. keep reading
    * Use ``git push`` to send your changes to the remote repository. If you have an error because there is no remote, then you may not have linked the remote repository to the one on your computer. Try using ``git remote add origin <remote URL>`` and then ``git push --set-upstream origin master``. This will link the two, and you can now use ``git push`` regularly

Starting Homework Assignment 1
-------------------------------------

- The above is a guide for starting with git. Now, since you know how to do that stuff, you can easily follow those steps to get the remote git repository.
    - On the instructions, Professor Litz provides us a link to clone (https://code.videolan.org/videolan/x264). Follow the above steps for cloning a repository to your local machine. Don't worry, it's not too hard. The resulting folder is called 'x264'.