# Commands

## 1 Getting Started with the Console

### 1.1 Running Commands

* **ls** (list files)
  * **-l** (prints long form of file list)
  * **-a** (show all files, including hidden files)
* **clear** (clear the screen)

### 1.2 Moving Around the Filesystem

- **cd** (change directory)
- **pwd** (print working directory)

#### Further Reading

[The Unix home directory](https://en.wikipedia.org/wiki/Home_directory#Unix)

### 1.3 Reading Files

- **less**
- **cat**

### 1.4 Editing Files

- **touch**
- **nano**

#### Advanced Editors

- **emacs**
- **vim**

### 1.5 Moving and Deleting Files

- **mv** (move)
- **cp** (copy)
  - **-r**
- **rm** (remove)
  - **-r**
- **mkdir** (make directory)

### 1.6 If You Have Any Questions

- **man** (Manual Page)

## 2 Users and Permissions

### 2.1 Creating Users

- **whoami** - Print which user you are
- **adduser** - Interactive tool for creating users
- **su** - Switch user
- **sudo** - Perform a command as the super user

### 2.2 File Permissions

- **ls -l** - List files in long format, including permissions info
- **chmod** - Change the permissions (mode) of a file or directory

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

**chown** - Change the owner of a file or directory.

### 2.4 Sudo

- **sudo** - Run a command as the super user.
- **sudo !!** - Run the previous command as the super user.

## 3 Processes

### 3.1 Processes

- **top** - Show active processes
- **ps** - Show process statuses
- **grep** - Search for a pattern

**Find a process by name**

Use the following command to search for a running process using a pattern.

```ps aux | grep "SEARCH PATTERN"```

### 3.2 Pausing and Resuming

#### Key Sequences

- **ctrl + z** - Stop (pause) a process
- **ctrl + c** - Terminate (exit) a process

#### Commands

- **fg** - Bring a job to the foreground
- **jobs** - List jobs for your session

### 3.3 Killing Processes

- **kill** - Send a signal to a process

#### Signals

- **KILL** or **9** - Force a process to exit
- **TERM** (default) - Request a process terminate normally
- **STOP** - Stop or pause a process

## 4 Environment and Redirection

### 4.1 Environment Variables

- **VARIABLE=value** - set a local environment variable
- **export VARIABLE=value** - set an environment variable that will be visible to child processes
- **env** - view environment variables
- **bash** - start a new session within your current session
- **echo** - display the arguments sent to echo

### 4.2 Find and Grep

- **find . -name "search"** - look for files with the name search starting from your current location
- **grep "pattern" file** - find any lines that contain the pattern in the given file

### 4.3 Pipes and Redirection

- **somecommand < inputfile** run somecommand with input from inputfile, instead of the keyboard
- **somecommand > outputfile** run somecommand with output to outputfile instead of the terminal screen.
- **command1 | command2** pipe the output of command1 to the input of command 2

## 5 Installing Software

### 5.1 Building Software From Source

- **sudo apt-get update** - Update your computer's catalog of available software
- **sudo apt-get install build-essential** - Install the tools needed to build software from source code
- **curl -O URL** - Download the file at the URL
- **tar -xvf FILENAME.tar.gz** - Decompress the tar.gz file to the current directory
- **./configure** - Run the configure script that comes with the source code. This creates a Makefile
- **make** - Run the build specified in the Makefile
- **sudo make install** - Run the install script from the Makefile. This installs the program
- **which**

#### Related Links

- [SQLite.org](http://sqlite.org/)

### 5.2 Introduction to Package Managers

- **apt-get update** - Update your package catalog on your computer
- **apt-cache search PATTERN** - Search the available packages for a pattern
- **apt-get install** - PACKAGE Install one or more packages
- **apt-get upgrade** - Upgrade to the latest version of all the packages installed
- **apt-get remove PACKAGE** - Remove or uninstall package from your computer
