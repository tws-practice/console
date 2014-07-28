# Commands

## 1 Getting Started with the Console

### 1.1 Running Commands

* **ls** -- list directory contents
  * **-l** -- list in long format.
  * **-a** -- include directory entries whose names begin with a dot (.).
* **clear** -- clear the terminal screen

### 1.2 Moving Around the Filesystem

- **cd** -- change directory
- **pwd** -- print working directory

#### Further Reading

[The Unix home directory](https://en.wikipedia.org/wiki/Home_directory#Unix)

### 1.3 Reading Files

- **less** -- Less is a program  similar to more (1), but which allows backward movement in the file as well as forward movement.  Also, less does not have to read the entire input file before starting, so with large input files it starts up faster than text editors like vi (1).  Less uses termcap (or terminfo on some systems), so it can run on a variety of terminals.  There is even limited support for hardcopy terminals.  (On a hardcopy terminal, lines which should be  printed  at the top of the screen are prefixed with a caret.)
- **cat** -- concatenate and print files

### 1.4 Editing Files

- **touch** -- change file access and modification times
- **nano** -- nano is a small, free and friendly editor which aims to replace Pico, the default editor included in the non-free Pine package.  Rather than just copying Pico's look and feel, nano also implements some missing (or disabled by default) features in Pico, such as "search and replace" and "go to line and column number".

#### Advanced Editors

- **vim**
- **emacs**

### 1.5 Moving and Deleting Files

- **mv** -- move files
- **cp** -- copy files
  - **-R** or **-r** -- copy directories recursively
- **rm** -- remove files
  - **-r** -- remove directories and their contents recursively
- **mkdir** -- make directories

### 1.6 If You Have Any Questions

- **man** -- format and display the on-line manual pages

## 2 Users and Permissions

### 2.1 Creating Users

- **whoami** -- print which user you are
- **adduser** -- interactive tool for creating users
- **su** -- switch user
- **sudo** -- perform a command as the super user

### 2.2 File Permissions

- **ls -l** -- list files in long format, including permissions info
- **chmod** -- change the permissions (mode) of a file or directory

**rwx notation**

In ls -l, each file has a 10 character permission representation such as **drwxrwxrwx**. Each character represents a permission on the file. If the letter is replaced with a dash (**-**), it indicates the permission is not granted. For example **-rwxr-xr-x**.

The first character denotes if it is a dirctory. **d** means directory, **-**, means not a directory.

The next 9 characters can be grouped into triplets of **rwx**. The leftmost triplet is for the owner of the file, the middle is the group owner, and the right is permissions for others. **rwx** stand for the **read**, **write**, and **execute** permissions, respectively.

**Octal notation**

You may read or set permissions using a 3 digit octal number. The digits represent the owner, group, and other permissions, from left to right. Each digit may be 0 through 7 representing the different combinations of read, write, and execute.

To compute what each digit means, use this formula.

**read**/**r** = 4

**write**/**w** = 2

**execute**/**x** = 1

For each permission you want to grant, sum their corresponding values.

### 2.3 File Ownership

**chown** -- change the owner of a file or directory.

### 2.4 Sudo

- **sudo** -- run a command as the super user.
- **sudo !!** -- run the previous command as the super user.

## 3 Processes

### 3.1 Processes

- **top** -- show active processes
- **ps** -- show process statuses
- **grep** -- search for a pattern

**Find a process by name**

Use the following command to search for a running process using a pattern.

```ps aux | grep "SEARCH PATTERN"```

### 3.2 Pausing and Resuming

#### Key Sequences

- **ctrl + z** -- stop (pause) a process
- **ctrl + c** -- terminate (exit) a process

#### Commands

- **fg** -- bring a job to the foreground
- **jobs** -- list jobs for your session

### 3.3 Killing Processes

- **kill** -- send a signal to a process

#### Signals

- **KILL** or **9** -- force a process to exit
- **TERM** (default) -- request a process terminate normally
- **STOP** -- stop or pause a process

## 4 Environment and Redirection

### 4.1 Environment Variables

- **VARIABLE=value** -- set a local environment variable
- **export VARIABLE=value** -- set an environment variable that will be visible to child processes
- **env** -- view environment variables
- **bash** -- start a new session within your current session
- **echo** -- display the arguments sent to echo

### 4.2 Find and Grep

- **find . -name "search"** -- look for files with the name search starting from your current location
- **grep "pattern" file** -- find any lines that contain the pattern in the given file

### 4.3 Pipes and Redirection

- **somecommand < inputfile** -- run somecommand with input from inputfile, instead of the keyboard
- **somecommand > outputfile** -- run somecommand with output to outputfile instead of the terminal screen.
- **command1 | command2** -- pipe the output of command1 to the input of command 2

## 5 Installing Software

### 5.1 Building Software From Source

- **sudo apt-get update** -- update your computer's catalog of available software
- **sudo apt-get install build-essential** -- install the tools needed to build software from source code
- **curl -O URL** -- download the file at the URL
- **tar -xvf FILENAME.tar.gz** -- decompress the tar.gz file to the current directory
- **./configure** -- run the configure script that comes with the source code. This creates a Makefile
- **make** -- run the build specified in the Makefile
- **sudo make install** -- run the install script from the Makefile. This installs the program
- **which** -- locate a program file in the user's path

#### Related Links

- [SQLite.org](http://sqlite.org/)

### 5.2 Introduction to Package Managers

- **apt-get update** -- update your package catalog on your computer
- **apt-cache search PATTERN** -- search the available packages for a pattern
- **apt-get install** -- pACKAGE Install one or more packages
- **apt-get upgrade** -- upgrade to the latest version of all the packages installed
- **apt-get remove PACKAGE** -- remove or uninstall package from your computer
