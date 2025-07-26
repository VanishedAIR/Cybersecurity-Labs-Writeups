## Learn the Linux Fundamentals - Part 2 ([TryHackMe - YouTube](https://www.youtube.com/watch?v=7Zt2Mp2IeBI&list=PL0iJrrpaWpyW9FQqI_TMJiuGpLJrXGVvA&index=2))

### Summary:

#### Accessing Your Linux Machine Using SSH (Deploy)

-   What is SSH & how Does it Work?

    -   Secure Shell or SSH simply is a protocol between devices in an encrypted form.
    -   Using cryptography, any input we send in a human-readable format is encrypted for traveling over a network -- where it is then unencrypted once it reaches the remote machine, such as in the diagram below.
    -   ![ssh](https://camo.githubusercontent.com/ec140a07cb3bddfbd7b1c97e395e4d724712c01494ffa3fa41e6a99d12a4c8a9/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f737368312e706e67)
    -   SSH allows us to remotely execute commands on another device remotely.
    -   Any data sent between the devices is encrypted when it is sent over a network such as the Internet

-   Using SSH to Login to Your Linux Machine

    -   The syntax to use SSH is very simple. We only need to provide two things:

        -   The IP address of the remote machine
        -   Correct credentials to a valid account to login with on the remote machine

    -   `ssh tryhackme@MACHINE_IP`

#### Introduction to Flags and Switches

-   Command Arguments:

    -   A majority of commands allow for arguments to be provided
    -   These arguments are identified by a hyphen and a certain keyword known as flags or switches

-   Default Command Behavior:

    -   When using a command, unless otherwise specified, it will perform its default behavior
    -   For example, ls lists the contents of the working directory, but hidden files are not shown
    -   We can use flags and switches to extend the behavior of commands

-   Example with ls Command:

    -   Using our ls example, ls informs us that there is only one folder named "folder1" as highlighted in the screenshot below

    -   ![without-flag](https://camo.githubusercontent.com/8421ff6a8f1017dede7dcddfe7fd04c7516f10bc2b0f765b298cf38b0e5bf612/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6c73312e706e67)

-   Using the -a Flag:

    -   After using the -a argument (short for --all), we now suddenly have an output with a few more files and folders such as ".hiddenfolder"
    -   Files and folders with "." are hidden files

    -   ![flag](https://camo.githubusercontent.com/5502ca2267464d6189f7c3c1fe2c4c3f814b9bec7aa561789b34829c4bd360e2/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6c73322e706e67)

-   Getting Help with Commands:

    -   Commands that accept these will also have a --help option
    -   This option will list the possible options that the command accepts, provide a brief description and example of how to use it

    -   ![help](https://camo.githubusercontent.com/80ff4ef7ad63b9c0e1590c204cd116196d8eac605db21ddb50be6219ca0ab80d/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6c73332e706e67)

-   The Man(ual) Page

    -   Documentation Resource:

        -   The manual pages are a great source of information for both system commands and applications available on a Linux machine
        -   This documentation is accessible on the machine itself and online
        -   Manual pages provide comprehensive information about how to use commands effectively

    -   Accessing Manual Pages:

        -   To access this documentation, we can use the man command and then provide the command we want to read the documentation for
        -   Using our ls example, we would use `man ls` to view the manual pages for ls like so:

    -   ![man](https://camo.githubusercontent.com/8dfabafc0ded88b429d3abddc90f6124e70755c3df2036d4e510fcd745821d7d/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6d616e312e706e67)

#### Filesystem Interaction Cont

![commands](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%202/Pastedimage20210705130931.png)

-   Pro-tip:

    -   Similarly to using `cat`, we can provide full file paths, i.e. `directory1/directory2/note` for all of these commands

-   Creating Files and Folders (touch, mkdir):
    -   Creating files and folders on Linux is a simple process
    -   First, we'll cover creating a file
    -   The `touch` command takes exactly one argument -- the name we want to give the file we create
    -   For example, we can create the file "note" by using `touch note`
    -   It's worth noting that `touch` simply creates a blank file
    -   You would need to use commands like `echo` or text editors such as `nano` to add content to the blank file

![touch](https://camo.githubusercontent.com/7f5e1a94c9b2fe47bece0b15b756284bdc0cb8cd5e21f52c17f45e20de442fb2/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f746f7563682e706e67)

-   Creating Directories:
    -   This is a similar process for making a folder, which just involves using the `mkdir` command
    -   Again providing the name that we want to assign to the directory
    -   For example, creating the directory "mydirectory" using `mkdir mydirectory`

![mkdir](https://camo.githubusercontent.com/6cb64d67e403275b01c30932fdabd19e2dd19f444ced35e91d001967a02d855f/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6d6b6469722e706e67)

-   Removing Files and Folders (rm):
    -   `rm` is extraordinary out of the commands that we've covered so far
    -   You can simply remove files by using `rm`
    -   However, you need to provide the `-R` switch alongside the name of the directory you wish to remove

![rm](https://camo.githubusercontent.com/3158290b1ff8b3d4f955f45f46047e0a17664a9ee6580ac6627d678c26d7ddba/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f726d2e706e67)

![rm-R](https://camo.githubusercontent.com/ead97fa2ed7ede7bb96f569225dbea0c0194d8b4858fa76a266c41b01923dd03/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f726d6469722e706e67)

-   Copying and Moving Files and Folders (cp, mv):
    -   Copying and moving files is an important functionality on a Linux machine
    -   Starting with `cp`, this command takes two arguments:
        -   The name of the existing file
        -   The name we wish to assign to the new file when copying
    -   `cp` copies the entire contents of the existing file into the new file
    -   In the screenshot below, we are copying "note" to "note2"

![copy](https://camo.githubusercontent.com/e980a4894d45e7240cebab795180433db4c77d2ece86a0e5d99d2ac841b11b85/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f63702e706e67)

-   Moving Files (mv):
    -   Moving a file takes two arguments, just like the `cp` command
    -   However, rather than copying and/or creating a new file, `mv` will merge or modify the second file that we provide as an argument
    -   Not only can you use `mv` to move a file to a new folder, but you can also use `mv` to rename a file or folder
    -   For example, in the screenshot below, we are renaming the file "note2" to be named "note3"
    -   "note3" will now have the contents of "note2"

![mv](https://camo.githubusercontent.com/687185a23e6e69e99f7ce711b0bd5557562e00797f17fa1b4b15028cf08f1cc3/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6d762e706e67)

-   Determining File Type:
    -   Without knowing the context of why the file is there -- we don't really know its purpose
    -   Enter the `file` command
    -   This command takes one argument
    -   For example, we'll use `file` to confirm whether or not the "note" file in our examples is indeed a text file, like so `file note`

![file](https://camo.githubusercontent.com/e1bd3eb45b3a2eb04b0c29b86053f154686a261d591976c45cf0117a495818ab/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f66696c652e706e67)

#### Permissions 101

-   Understanding File Permissions:
    -   The `ls -l` command shows detailed information about files including permissions
    -   When using this command, we can see ten columns as shown in the screenshot below
    -   However, we're primarily interested in the first three columns which relate to permissions

![ls-l](https://camo.githubusercontent.com/1ac03d3dd98e429effd98c4bf96e2db67174805a98f772b499c70689144a17ff/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6c736c2e706e67)

-   Permission Types:
    -   Although intimidating, these three columns are very important in determining certain characteristics of a file or folder
    -   They indicate whether or not we have access to the file or folder
    -   A file or folder can have three main permission types:
        -   Read
        -   Write
        -   Execute
    -   The diagram below is a great representation of how these permissions can be translated

![file-perms](https://camo.githubusercontent.com/5cc9f03780fed834b252c973580c67e67df540e42841d62e184c83d5b4cba254/68747470733a2f2f6c696e7578636f6d6d616e642e6f72672f696d616765732f66696c655f7065726d697373696f6e732e706e67)

-   Reading Permission Notation:

    -   Let's use the "cmnatic.pem" file in our initial screenshot at the top of this task
    -   It has the "-" indicator highlighting that it is a file and then "rw" followed after
    -   This means that only the owner of the file can read and write to this "cmnatic.pem" file but cannot execute it

-   The Differences Between Users & Groups:
    -   While a user technically owns a file, if the permissions have been set appropriately, a group of users can also have either the same or a different set of permissions to the exact same file
    -   This doesn't affect the permissions of the file owner itself
    -   In a real-world context, the system user that runs a web server must have permissions to read and write files for an effective web application
    -   Companies such as web hosting providers need to allow their customers to upload their own files for their website without giving them the same privileges as the webserver system user
    -   This separation prevents security compromises that would affect every customer

#### Switching Between Users

-   Using the `su` Command:

    -   Switching between users on a Linux system is easy thanks to the `su` command
    -   Unless you are the root user (or using root permissions through sudo), you are required to know two things:
        -   The username of the user you wish to switch to
        -   That user's password

-   Command Options:
    -   The `su` command takes a couple of switches that may be relevant to you
    -   For example, executing a command once you log in or specifying a specific shell to use
    -   By providing the `-l` switch to `su`, we start a shell that is much more similar to the actual user logging into the system
    -   We inherit many more properties of the new user, such as environment variables and similar settings

![su](https://camo.githubusercontent.com/c982bd6423dcc1aba498aa468237570add4cf1935f83bc141b55f4ef6f3b4e91/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f7375312e706e67)

-   Comparing `su` with and without `-l`:
    -   For example, when using `su` to switch to "user2", our new session drops us into our previous user's home directory
    -   This might be confusing as we're logged in as "user2" but still in another user's directory

![su-l](https://camo.githubusercontent.com/e774331694d384e660f9087b51e8b8482502f59ddf43ce3de0573f317770a4b1/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f7375322e706e67)

-   Using `su -l`:
    -   When using `su -l`, our new session has dropped us into the home directory of "user" automatically
    -   This creates a more complete user environment as if the user had logged in directly
    -   The `-l` option (which can also be written as `-login` or just `-`) is therefore recommended when fully switching to another user

#### Common Directories

-   /etc:
    -   This root directory is one of the most important root directories on your system
    -   The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system
    -   For example, the sudoers file highlighted in the screenshot below contains a list of the users & groups that have permission to run sudo or a set of commands as the root user
    -   Also highlighted below are the "passwd" and "shadow" files
    -   These two files are special for Linux as they show how your system stores the passwords for each user in encrypted formatting called sha512

![etc](https://camo.githubusercontent.com/789eec9e4de7ba022d225db2314fe02e4e63fe03f16be5cb821ad662e8365846/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f6574632e706e67)

-   /var:
    -   The "/var" directory, with "var" being short for variable data, is one of the main root folders found on a Linux install
    -   This folder stores data that is frequently accessed or written by services or applications running on the system
    -   For example, log files from running services and applications are written here (`/var/log`)
    -   It also stores other data that is not necessarily associated with a specific user (i.e., databases and the like)

![var](https://camo.githubusercontent.com/d7d9ba0535ec259329ca1b46374e3a30e866360b0b6c16d39dfec26ada01a0d0/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f7661722e706e67)

-   /root:
    -   Unlike the /home directory, the /root folder is actually the home for the "root" system user
    -   There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user
    -   It is worth a mention as the logical presumption is that this user would have their data in a directory such as "/home/root" by default

![root](https://camo.githubusercontent.com/5af0815b900318ea476e2a1318bb3301f5dc452490edc6e8b3c005f8486ba95b/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f726f6f742e706e67)

-   /tmp:
    -   This is a unique root directory found on a Linux install
    -   Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice
    -   Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out
    -   What's useful for us in pentesting is that any user can write to this folder by default
    -   Meaning once we have access to a machine, it serves as a good place to store things like our enumeration scripts

![tmp](https://camo.githubusercontent.com/55dd4c00270f1434c573f21c04bfbc9577a7dce5ed841ac2cd20a11a86a0345f/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274322f746d702e706e67)
