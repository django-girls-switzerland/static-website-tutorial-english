## Final Preparations
These are the final preparations before we can finally get to the fun parts of creating our website.

### Create a Django Girls Folder on Your Computer

The next thing you will need is a folder on your computer to put your codefiles of the workshop in. Your 'Home' directory is a good choice in most cases. On Windows this might look something like this: `C:\Users\Name\` \(with `Name` your login name\).

> **NOTE:** On Windows, make sure that this directory does not contain accented or special characters; if your username contains accented characters, use a different directory, for example `C:\djangogirls`.

In this folder we will now create a subfolder with the name  `djangogirls`.

To do this we will have to open the terminal and navigate to the right place \(you can find an explanation of what the terminal is in the [Tools](/chapter1/tools.md) section\)

We will write here where you will most probably finde the Terminal on your computer. Ask your coach to help you if you don't find it:

For Windows:

Go to Start menu → All Programs → Accessories → Command Prompt.

For OS X:

Go to Applications → Utilities → Terminal.

For Linux:

Go to Applications → Accessories → Terminal

Check with your coach that you have navigated to the right place with your Terminal befor you enter the following commands!

command-line

```
$ mkdir djangogirls
$ cd djangogirls
```

Don't close the Terminal after this, you will need it again later!

### Create a Github Repository

We know already that Github is a place to store youre versioned code projects. Every project has a so called 'repository'. This is a special kind of Folder that also stores the different versions and changes you made to your files. The magic thing behind this is an invisible subfolder with the name .git

On GitHub we will know create a new repository and then clone this to our own computer, so that it appears in our file system.

In your browser go to `https://github.com/new` \(if you get a 404 error, you will have to login first\). You only have to fill in the field called repository as follows: `username.github.io` with your own Github username instead of the word username. Make sure that the part before the first dot is exactly the same as your Github username. This is because Github will only display the files of the repository called exactly like this as a website \(the other directories will just be displayed as code files\) on `http://username.github.io`. Then press 'Create Repository'.

Now you can go back to the Terminal and clone the repository you just created to youre computer with the command line commands below. To do this always replace username with your Github username, and replace Your Name and you@example.com with your name and email address. The lines that don't start with a dollar sign '$' are not meant to be typed by you, they are the answers of the computer to your commands. Your Terminal should respond more or less the same way as in the example below.

command-line

```
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com
$ git clone https://github.com/username/username.github.io
Cloning into 'username.github.io'...
warning: You appear to have cloned an empty repository.
Checking connectivity... done.
$ cd username.github.io
```

In the djangogirls folder you should now see a folder with the name  `username.github.io` . Again, don't close the terminal window, you will need itagain and again to work with git and to push you changes to Github.

