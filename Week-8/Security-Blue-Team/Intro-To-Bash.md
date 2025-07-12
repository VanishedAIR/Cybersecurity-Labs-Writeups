# Introduction to Bash

## Getting Started

### Introduction to Command Line

-   Command line is a text-based interface for interacting with a computer's OS, and requires users to type text commands to perform tasks
-   Terminal emulators are software applications that provide a gui for accessing the command line.
    -   They mimic the behavior of physical computer terminals
-   Shells are command line interpreters that process your commands
    -   Bash is one of the most popular shell, and other shells include Zsh, Fish, and more.

### Navigating the File System

-   `ls` - List

    -   Used to list the files and directories in the current working directories
    -   Uses Cases:
        -   Checking contents of a directory to see which files and subdirectories are present
        -   Verifying the existence of specific files or directories
        -   Specifying the `l` option provides more information regarding the file permissions, owner, size, and modification date
        -   ![1](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/17d76689a4bbe85ba7852c4593b1b72e9268e6f7b66cd6f889cdb132932a81f7ae9c858f285af4d6d6afe83126a7.png)
        -   File type and permissions are shown as `drwxr-xr-x`
            -   `d` represents directory
            -   `r` represents reading permissions for that user
            -   `w` represents writing permissions for that user
            -   `x` represents execution permissions for that user

-   `cd` - Change Directory

    -   Used to change the current working directory, allowing the user to navigate the file system by moving into different directories
    -   Use Cases:
        -   Changing to a specific directory to access its contents
        -   Navigating to parent or child directories
        -   Using the `~` character to quickly switch to home directory
        -   ![2](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/15675661f27c3dab53f51ba0bd363e253a87ba66ce79bd7c23fca292f76159bb1e42c341e1a05049f6f2fd816195.png)
        -   To change to a specific directory: `cd /path/to/directory`
        -   To navigate to the home directory: `cd ~`
        -   To go up one level to the parent directory `cd ..`

-   `pwd` - Print Working Directory
    -   Used to display current working directory, showing the full path of the directory the user's in
    -   Use Cases:
        -   Confirming user's current location in the file system
        -   Using the output of pwd as part of a command or script
    -   ![3](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8a8410492f8a79f5eea8ec64b45670089c1fe05a1ed201aad514d2dc0daefb74830011c2304b3bbaa8b5097e8385.png)

### Working with Files and Directories

-   `touch` - Used to create new, empty files or update the timestamp of existing files

    -   If the specified file does not exist, touch will create it.
    -   Use Cases:
        -   Creating a new empty file: `touch filename.txt`
        -   Update the modification timestamp of a file: `touch existingfile.txt`
    -   ![4](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/34a68d27e318a32cede1c8be4d2c504f435d823cddce1e1398090805ddb893e48af65ee12c4e208daf4b31fdcc27.png)

-   `mkdir` (Make Directory) - Used to create new directories (folders) within the file system, allowing a more organized and structured file system

    -   Use Cases:
        -   Creating a new directory: `mkdir directory_name`
        -   Creating nested directories: `mkdir -p parent_directory/child_directory`
    -   ![5](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a2f84ad9dd4cfe089b95de6de0634e1f20e458d5be1931cf35dc4894d865a0111bc7c04ba34bb7f64de1165a6fd1.png)

-   `rm` (Remove) - Used to remove files or directories
    -   **Be cautious** when using this command, as deleted files are typically **not** recoverable, and removing directories with contents requires special handling
    -   Use Cases:
        -   Removing a file: `rm filename.txt`
        -   Removing a directory and its contents _(use with caution)_: `rm -r directory_name`
        -   Force removing a directory and its contents _(use with caution)_: `rm -rf directory_name`
            -   The `f` here skips the recurring prompts asking for confirmation
    -   ![6](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/34775de678464769176d840e4e221b903cc586fdf713c7790f41bc695ddffb2adb1e70496a158d1b526bfda4ec2c.png)

### Copying and Moving Files

-   `cp` (Copy) - Used to copy files or directories from one location to another, by creating a duplicate of the source file or directory in the destination

    -   Use Cases:
        -   Copying a file to a different directory: `cp file.txt /path/to/destination/`
        -   Copying multiple files into a directory: `cp file1.txt file2.txt directory/`
        -   Copying a directory and its contents: `cp -r source_directory/ destination_directory/`
    -   ![7](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/92cd039b63b4390233a010d3eca6640bae5897259da573190d4d563f876580cedd26f3d420cc3c13868019f11c9d.png)

-   `mv` (Move) - Used to move files or directories from one location to another
    -   Unlike `cp`, it does not create a duplicate; it transfers the original to the new location
    -   Use Cases:
        -   Moving a file to a different directory: `mv file.txt /path/to/destination/`
        -   Renaming a file: `mv oldname.txt newname.txt`
        -   Moving a directory and its contents: `mv source_directory/ destination_directory/`
    -   ![8](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/90b1019f98e9e4adb0a7d245e93a13e8b523a53f5d3dbfb7e8aa1461805d48fb8cbcb653b3916d4a23940c07a66f.png)

### Quiz:

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

## Basic Commands

### Viewing File Content

-   `cat` (Reading Files)

    -   The cat command is used to concatenate and display the entire contents of a file on your terminal.
    -   It's a straightforward way to quickly view a file's content from start to finish
    -   ![9](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3b71305c243ee67c09b6e0aee5f7db1618c5c3f70d72740b88f6f3af795cc9988f626ca90b43f82696d02f2630b0.png)

-   `less`

    -   The less is an interactive pager that enables you to view file contents one screen at a time.
    -   It provides navigation options, allowing you to scroll through the content, search for text, and move forward and backward within the file
    -   ![10](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6a4274b7a1336d4e310d487313ca5ad149968897f581783ce24fb74ecf994ad7a56d36d04704372d70ac7bc02003.png)

-   `more`
    -   Similar to less, more is a pager that displays text files one screen at a time.
    -   It doesn't have as many interactive features as less but is still useful for quickly scanning through files without overwhelming your terminal with too much content
    -   Use Cases:
        -   Reading log files.
        -   Inspecting configuration files.
        -   Viewing large text files systematically.
    -   ![11](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8e164038e305ba8be14dbe39b80798041b4b33ded4e4f02ac1bb2b853d700c265ee2122540ca71d6b3e27a7c784b.png)

### Text Searching using GREP

-   GREP stands for "Global Regular Expression Print."
-   It is a powerful command-line tool used for searching and extracting text patterns within files.
-   Grep is an essential utility for finding specific content within text files and is particularly valuable for tasks like data extraction, log analysis, and code searching.

-   Basic Usage:

    -   `grep [options] pattern [file]`
    -   `pattern`: The text or regular expression you want to search for.
    -   `file` (optional): The file(s) in which you want to search. If not specified, grep will read from standard input.

-   Key Features:

    -   Regular Expressions: Grep supports regular expressions, which are powerful text patterns for matching complex strings. This allows you to find text that follows specific patterns or contains certain keywords.
    -   Case Sensitivity: By default, grep is case-sensitive. You can use the `i` option to perform case-insensitive searches.
    -   Multiple Files: Grep can search across multiple files simultaneously, making it efficient for finding information in entire directories of text files.
    -   Output Control: Grep provides options to control the output, such as showing line numbers or the context around matched lines.

-   GREP Usage Examples:

    -   **We will be using the file `Module2_test_file.txt` for searches**
    -   Basic search for a word in a file: `grep "search_term" file.txt`
    -   This command searches for the exact occurrence of "`search_term`" in the `file.txt`
        -   ![12](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/89bf40634823467d93ca22a7c947bd4192a6b24a086358e42617ee1f94c4bc0f7c1973746e2ace6cf8efb7325789.png)
    -   Search for a word case-insensitively: `grep -i "search_term" file.txt`
    -   The `i` option makes the search case-insensitive, allowing you to find "`search_term`" regardless of its letter case.
        -   ![13](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4aa370c6b5cf43a3d6bf8c798607a99f9e9459b3c83c74f9c0bf092ada3d35e12af51f2f3c40bdcd7019d9844cd0.png)
    -   Use regex pattern for searching: `grep -E ‘pattern’ file.txt`
    -   The `E` option enables extended regular expressions, allowing you to search using more complex patterns.
        -   ![14](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cc37d4024c03a54635684b8d84fecb7361410581d9017e8947dae5409f19322623fa6e85129f1caba8c6e64ef514.png)
    -   Display line numbers with matches: `grep -n "pattern" file.txt`
    -   The n option shows line numbers for each matching line in the output.
        -   ![15](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f9dcd3e39e8909ffb2e4fbaf54a36d63eee4136534593eb4f668e546aaee4d673a247217bc6bbab40259cb6669ed.png)

-   GREP Use Cases:
    -   Log Analysis: Grep is commonly used to extract specific events or errors from log files, helping diagnose issues in software systems.
    -   Code Searching: Developers use grep to search for functions, variables, or specific code snippets in source code files.
    -   Data Extraction: It's useful for extracting structured data from unstructured text files, such as extracting email addresses or phone numbers from a document.
    -   System Administration: System administrators rely on grep to find configuration settings or diagnose issues by searching through system logs.

### Identifying File Information

-   `file`
    -   The `file` command is used to determine the type and format of a file.
    -   It helps you identify the nature of a file, such as whether it is a text file, an image, an executable, or another type, without relying solely on file extensions.
    -   Identifying File Types without Relying on Extensions: The `file` command is particularly useful when file extensions are missing or unreliable. It offers a way to inspect the contents of a file and determine its format accurately.
    -   Verifying the Integrity of Downloaded Files: When downloading files from the internet, you can use `file` to verify that the downloaded file matches its expected type. This helps ensure the integrity of downloaded content and prevents potential security risks.
    -   ![16](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/97eb6d7366147407f992af74586a2d5aaa2c3099fc6c5f01b783ef25d98d68a2c9401cb5cf1d9b8779a6aa84cd72.png)

### User and Group Management

-   `whoami`

    -   The `whoami` command is used to display the username of the current user who is logged into the system. It helps you quickly identify the user context you are operating within.

-   `id`

    -   The `id` command is used to show detailed user and group information, including the user's UID (User ID), GID (Group ID), and group memberships.

-   Key Points:

    -   Understanding the Active User Context: whoami and id are valuable for understanding your current user context. They provide information about your identity, which is crucial when performing tasks that require certain permissions.
    -   Checking Group Memberships: The id command, in particular, helps you identify your group memberships. This is essential for tasks where group-based access control is in place or when you need to confirm your access to specific resources.
    -   ![17](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/60da09207a6b981f011a13082b151256c3bd0311db014e72fae154299b738a817d6b3f3430ee54e7aa210516b843.png)

-   File Permissions

-   `chmod`

    -   The `chmod` command is used to change file permissions, allowing you to specify who can read, write, and execute a file. It operates on both individual files and directories and provides fine-grained control over access rights.

-   `chown`

    -   The `chown` command is used to change the owner and group of a file. It is commonly used by system administrators to modify file ownership and group assignments.

-   Key Points:

    -   File Permissions in Octal Notation: `chmod` allows you to set file permissions using octal notation (e.g., 644, 755). This notation provides a concise way to express permission settings.
    -   Ownership Changes for System Administrators: `chown` is typically employed by system administrators when files or directories need to be reassigned to different users or groups. It is an essential tool for managing file ownership in multi-user environments.

-   Using `chmod` to allow script execution `x`

    -   First, we created a simple shell script “`.sh`” extension.
    -   Then, we inspect the permission of the file using ‘`ls -l`’ where we can see there’s no ‘`x`’ indicated. (RED BOX)
    -   Next, we execute it by running ‘`./testfile.sh`’ and as we expected it denied the execution.
    -   Now, we use ‘`chmod +x`’ command where we assign ‘`x`’ execute permission to the script and we can see that a ‘`x`’ is added when we list the file again using ‘`ls -l`’. (YELLOW BOX)
    -   Finally, we try to execute it and the script runs and print the word ‘`test`’.
    -   ![18](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/62f851e5857cdf1586b410dc4d4bc9608f47e16cf8e6095f478d9aa1334206445c4f6ae69812bf65d4840f890add.png)

-   Understanding File Permission Digits
    -   File permissions in Unix-like operating systems are represented by a three-digit number, often called an octal (base-8) number, where each digit corresponds to a different permission category.
    -   The three digits represent the permissions for the owner, the group, and others, respectively. Here's how it works:
        -   First Digit: Owner's Permissions
            -   4: Read (`r`) permission
            -   2: Write (`w`) permission
            -   1: Execute (`x`) permission
        -   Second Digit: Group's Permissions
            -   4: Read (`r`) permission
            -   2: Write (`w`) permission
            -   1: Execute (`x`) permission
        -   Third Digit: Others' Permissions
            -   4: Read (`r`) permission
            -   2: Write (`w`) permission
            -   1: Execute (`x`) permission
    -   To calculate the permission number, you add up the values for the specific permissions you want to assign. For example:
        -   **Read-only**: 4 (owner) + 4 (group) + 4 (others) = 444
        -   **Read and write for owner, read-only for group and others**: 4 (owner read) + 2 (owner write) + 4 (group read) + 4 (others read) = 644
        -   **Full control for owner, read-only for group and others**: 4 (owner read) + 2 (owner write) + 1 (owner execute) + 4 (group read) + 4 (others read) = 744
        -   **Execute permission for all**: 1 (owner execute) + 1 (group execute) + 1 (others execute) = 111
    -   Example octal permission numbers
        -   **400**: Read permission for the owner only.
        -   **644**: Read and write for the owner, read-only for group and others.
        -   **755**: Read, write, and execute for the owner, read and execute for group and others (common for executable files).
        -   **777**: Full control for everyone (not recommended for security reasons).
-   Using ‘`chown`’ to change the file owner and group.
    -   For this demo we will be using the user “`elearning`” as our sample user and the contents of “`Pictures`” directory .
        -   First, we list the details of directory content using ‘`ls -l`’ command.
        -   Then, we use ‘`sudo chown elearning: Pictures/<file>`’ command to change the file owner from ‘`ubuntu`’ to ‘`elearning`’.
        -   Then, we use ‘`ls -l`’ to inspect the details of the files to see if it changes the owner. Here, we can see the changes.
        -   Now, we want to change the group owner of the same file by running ‘`sudo chown elearning:ubuntu Pictures/<file>`’ command
        -   Finally, we list again to see if the group owner changed to our desired group.
        -   ![19](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5851395aeb4700c52de34bbe3cf2cec0cb155dd3613bd2b36ee124376e04aebfe36549f92058c73e07415d345dc3.png)

### Quiz

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
