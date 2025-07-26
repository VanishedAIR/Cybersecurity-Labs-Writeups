# Introduction to Bash (Security Blue Team)

## Getting Started

### Introduction to Command Line

-   Command line is a text-based interface for interacting with a computer's OS - you type commands to perform tasks
-   Terminal emulators provide a GUI for accessing the command line (they simulate old physical computer terminals)
-   Shells are command line interpreters that process your commands
    -   Bash is the most popular shell, others include Zsh, Fish, etc.

### Navigating the File System

**`ls` - List**

-   Lists files and directories in current working directory
-   Common uses:
    -   Check directory contents to see files and subdirectories
    -   Verify if specific files/directories exist
    -   `ls -l` gives detailed info: permissions, owner, size, modification date
    -   File permissions shown as `drwxr-xr-x` where:
        -   `d` = directory
        -   `r` = read permissions
        -   `w` = write permissions
        -   `x` = execute permissions

**Example:**

```
Input: ls -l
Output:
drwxr-xr-x 2 user user 4096 Jan 15 10:30 Documents
-rw-r--r-- 1 user user 1234 Jan 15 09:45 notes.txt
-rwxr-xr-x 1 user user  512 Jan 14 16:20 script.sh
```

**`cd` - Change Directory**

-   Changes current working directory to navigate the file system
-   Usage examples:
    -   `cd /path/to/directory` - go to specific directory
    -   `cd ~` - go to home directory
    -   `cd ..` - go up one level to parent directory

**`pwd` - Print Working Directory**

-   Displays current working directory with full path
-   Useful for confirming current location or using output in scripts

### Working with Files and Directories

**`touch`**

-   Creates new empty files or updates timestamps of existing files
-   Examples: `touch filename.txt` or `touch existingfile.txt`

**`mkdir` (Make Directory)**

-   Creates new directories for organized file system structure
-   `mkdir directory_name` - creates single directory
-   `mkdir -p parent_directory/child_directory` - creates nested directories

**`rm` (Remove)**

-   Removes files or directories
-   **CAUTION**: Deleted files typically NOT recoverable!
-   `rm filename.txt` - remove file
-   `rm -r directory_name` - remove directory and contents
-   `rm -rf directory_name` - force remove without confirmation prompts

### Copying and Moving Files

**`cp` (Copy)**

-   Copies files/directories from one location to another, creating duplicates
-   `cp file.txt /path/to/destination/` - copy file to different directory
-   `cp file1.txt file2.txt directory/` - copy multiple files
-   `cp -r source_directory/ destination_directory/` - copy directory and contents

**`mv` (Move)**

-   Moves files/directories (transfers original, no duplicate like cp)
-   `mv file.txt /path/to/destination/` - move file
-   `mv oldname.txt newname.txt` - rename file
-   `mv source_directory/ destination_directory/` - move directory

## Basic Commands

### Viewing File Content

**`cat` (Reading Files)**

-   Concatenates and displays entire file contents on terminal
-   Simple way to quickly view file from start to finish

**`less`**

-   Interactive pager for viewing files one screen at a time
-   Navigation options: scroll, search text, move forward/backward

**`more`**

-   Similar to less but with fewer interactive features
-   Good for scanning files without overwhelming terminal
-   Use cases: reading logs, config files, large text files

### Text Searching using GREP

GREP = "Global Regular Expression Print"

-   Powerful tool for searching and extracting text patterns in files
-   Essential for data extraction, log analysis, code searching

Basic syntax: `grep [options] pattern [file]`

Key features:

-   Supports regular expressions for complex pattern matching
-   Case-sensitive by default (use `-i` for case-insensitive)
-   Can search multiple files simultaneously
-   Output control options (line numbers, context)

**GREP Usage Examples:**

-   Basic search: `grep "search_term" file.txt`
-   Case-insensitive: `grep -i "search_term" file.txt`
-   Extended regex: `grep -E 'pattern' file.txt`
-   Show line numbers: `grep -n "pattern" file.txt`

**Examples:**

```
Input: grep "error" logfile.txt
Output:
Error: Connection failed
Fatal error: Memory allocation failed

Input: grep -n -i "ERROR" logfile.txt
Output:
3: Error: Connection failed
7: Fatal error: Memory allocation failed
12: WARNING: Error in configuration
```

**GREP Use Cases:**

-   Log analysis: extract specific events/errors from log files
-   Code searching: find functions, variables, code snippets
-   Data extraction: pull structured data from unstructured text
-   System admin: find config settings, diagnose issues

### Identifying File Information

**`file` command**

-   Determines file type and format
-   Identifies file nature (text, image, executable, etc.) without relying on extensions
-   Useful for verifying downloaded file integrity and security

### User and Group Management

**`whoami`** - Shows username of current logged-in user
**`id`** - Shows detailed user/group info including UID, GID, group memberships

Key points:

-   Understanding active user context is crucial for permission-based tasks
-   `id` helps identify group memberships for access control verification

### File Permissions

**`chmod`** - Changes file permissions (read, write, execute)
**`chown`** - Changes file owner and group

Important concepts:

-   `chmod` uses octal notation (644, 755, etc.)
-   `chown` typically used by system administrators
-   Example: `chmod +x script.sh` allows script execution

**Permission Examples:**

```
Input: ls -l script.sh
Output: -rw-r--r-- 1 user user 245 Jan 15 10:00 script.sh

Input: chmod +x script.sh
Input: ls -l script.sh
Output: -rwxr-xr-x 1 user user 245 Jan 15 10:00 script.sh

Input: chmod 644 file.txt
Input: ls -l file.txt
Output: -rw-r--r-- 1 user user 1024 Jan 15 10:00 file.txt
```

**Understanding Permission Digits:**
Three digits represent owner, group, others permissions:

-   4 = Read, 2 = Write, 1 = Execute
-   Add values for combined permissions

Common examples:

-   400: Read for owner only
-   644: Read/write owner, read-only group/others
-   755: Full control owner, read/execute group/others
-   777: Full control everyone (not recommended)

## Process Listing and Management

**`ps` (Process Status)**

-   Lists currently running processes with PIDs, terminals, CPU/memory usage
-   `ps aux` shows detailed list of all processes

**Example:**

```
Input: ps aux
Output:
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.1 168588 11016 ?        Ss   09:00   0:01 /sbin/init
user      1234  2.1  5.2 892456 85432 ?        Sl   09:15   0:45 /usr/bin/firefox
user      1456  0.0  0.1  21584  4532 pts/0    Ss   09:20   0:00 bash
user      1789  0.0  0.0  19312  1876 pts/0    R+   10:30   0:00 ps aux
```

**`top` (Process Viewing)**

-   Interactive, dynamic process viewer with real-time updates
-   Shows system performance including CPU and memory usage

**`kill` (Terminate Process)**

-   Terminates processes by PID
-   Can send different signals (SIGTERM -15 for graceful termination)
-   Example: `kill -15 PID`

**`killall` (Terminate All Process)**

-   Terminates processes by name rather than PID
-   Example: `killall -9 firefox` forcefully kills all Firefox instances

**`bg` and `fg` (Background/Foreground)**

-   Manage background and foreground jobs
-   `bg %1` moves job ID 1 to background
-   `fg` brings backgrounded job to foreground

**`nice` and `renice`**

-   Set and adjust process priority
-   Lower values = higher priority = more CPU time
-   `nice` starts new process with specific priority
-   `renice` modifies existing process priority

**`htop`** - Enhanced interactive process viewer with user-friendly interface

**`strace` (Syscall Trace)** - Traces system calls and signals for troubleshooting

## Introduction to Pipes

Pipes connect multiple commands together for data processing and manipulation.

**Using Pipes:**

-   Pipe symbol `|` connects stdout of one command to stdin of another
-   Allows data to flow from command to command
-   Example: `cat sample.txt | grep "^A" | sort`
    -   `cat sample.txt` displays file contents
    -   `grep "^A"` filters lines starting with "A"
    -   `sort` alphabetically sorts the results

**Pipe Examples:**

```
Input: cat names.txt
Output:
Alice
Bob
Anna
Charlie
Andrew

Input: cat names.txt | grep "^A" | sort
Output:
Alice
Andrew
Anna

Input: ps aux | grep firefox
Output:
user      1234  2.1  5.2 892456 85432 ?    Sl   09:15   0:45 /usr/bin/firefox
user      1567  0.0  0.1  12345  2341 pts/0 S+   10:35   0:00 grep firefox
```

This creates powerful command pipelines for complex data processing tasks.

### Quiz: Getting Started

1. What is the primary purpose of the command line in Unix-like systems?
    - To provide a graphical interface for easier file management
    - To enhance the security of the system by restricting access
    - To allow users to execute programs and manipulate files and directories using commands ✅
    - To support programming in Java and Python
2. Which command is used to list all directories and files within the current directory?
    - ls ✅
    - cd
    - pwd
    - mkdir
3. What does the pwd command display?
    - The current user's username
    - The current directory path ✅
    - The list of previously executed commands
    - The directory permissions
4. How do you create a new directory in Bash?
    - mkfile ✅
    - touch
    - mkdir
    - cp
5. Which command is used to remove a directory?
    - rmdir ✅
    - cd
    - ls
    - mv
6. What is the difference between the cp and mv commands?
    - cp renames files, mv copies files
    - Both commands delete files after copying
    - cp copies files, mv moves/renames files ✅
    - There is no difference
7. How would you move a file to a different directory in Bash?
    - cp file /new/location
    - touch file /new/location
    - mv file /new/location ✅
    - ls file /new/location
8. Which practice is recommended for safe command line usage?
    - Always review commands carefully before executing, especially if running as the root user ✅
    - Use complex commands as much as possible to perform operations in bulk
    - Use root access for daily operations to avoid permission issues
    - Avoid using command line interfaces in favor of GUI tools

### Quiz: Basic Commands

1. Which command is used to display the entire contents of a text file in Bash?
    - ls
    - echo
    - cat ✅
    - dir
2. Which command allows you to view a large text file one page at a time?
    - more ✅
    - less
    - cat
    - tail
3. What does the -i option do when used with the grep command?
    - Includes only the first instance of a match
    - Inverts the search to display non-matching lines
    - Ignores case when searching ✅
    - Indicates the line number of each matching line
4. To find out the type of a file, which command should be used?
    - ls -l
    - file ✅
    - chmod
    - chown
5. What does the whoami command display?
    - All users currently logged in
    - The username of the current user ✅
    - The groups to which the current user belongs
    - Information about the current user's session
6. Which command is used to change the ownership of a file?
    - chown ✅
    - chgrp
    - chmod
    - usermod

### Quiz: Process Management

1. Which command is used to display a list of currently running processes?
    - ls
    - exec
    - ps ✅
    - run
2. What does the top command do in a Unix-like system?
    - Displays dynamic real-time information about running processes ✅
    - Lists the highest priority tasks
    - Shows the top directory of the file system
    - Sorts files in descending order
3. How can you terminate a process using its Process ID (PID)?
    - del PID
    - kill PID ✅
    - remove PID
    - clear PID
4. What command would you use to change the priority of a running process?
    - mod
    - chpri
    - nice ✅
    - prichange
5. Which option with the ps command shows all the processes running on the system, not just those tied to the current user?
    - ps -u
    - ps -c
    - ps -e ✅
    - ps -r

### Quiz: Pipes

1. What is the main function of pipes in Unix-like systems?
    - To increase the processing speed of the CPU
    - To create new files in the directory
    - To direct the output of one command to the input of another command ✅
    - To display text files on the screen
2. Which symbol is used to create a pipe in Unix-like command lines?
    - &
    - \
    - | ✅
    - /
3. How would you use a pipe to count the number of lines in a file?
    - cat filename | wc -l ✅
    - cat filename < wc -l
    - wc -l > filename
    - wc -l filename | cat
4. What is the correct usage of a pipe in this command sequence to list all directories only?
    - ls -l > grep '^d'
    - ls -l | grep '^d' ✅
    - ls -l < grep '^d'
    - grep '^d' | ls -l
5. What key advantage do pipes provide in command line operations?
    - They simplify syntax for complex commands.
    - They allow for the combination of multiple tools and commands to perform complex tasks efficiently. ✅
    - They prevent errors by managing command dependencies.
    - They increase the security of command executions.
