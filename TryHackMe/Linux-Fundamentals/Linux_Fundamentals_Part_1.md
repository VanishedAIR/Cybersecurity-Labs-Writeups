## Learn the Linux Fundamentals - Part 1 ([TryHackMe - YouTube](https://www.youtube.com/watch?v=kPylihJRG70&list=PL0iJrrpaWpyW9FQqI_TMJiuGpLJrXGVvA&index=1))

### Summary:

#### Introduction

-   Linux is just another operating system and one of the most popular in the world powering smart cars, android devices, super computers, home appliances, enterprise servers, and more

#### A Bit of Background on Linux

-   It's fair to say that Linux is a lot more intimidating to approach than Operating System's (OSs) such as Windows.
-   Both variants have their own advantages and disadvantages.

    -   For example, Linux is considerably much more lightweight and you'd be surprised to know that there's a good chance you've used Linux in some form or another every day! Linux powers things such as:

        -   Websites that you visit
        -   Car entertainment/control panels
        -   Point of Sale (PoS) systems such as checkout tills and registers in shops
        -   Critical infrastructures such as traffic light controllers or industrial sensors

-   Flavours of Linux

-   The name "Linux" is actually an umbrella term for multiple OS's that are based on UNIX (another operating system).
-   Thanks to UNIX being open-source, variants of Linux comes in all shapes and sizes - suited best for what the system is being used for.

-   For example, Ubuntu & Debian are some of the more commonplace distributions of Linux because it is so extensible.

    -   I.e. you can run Ubuntu as a server (such as websites & web applications) or as a fully-fledged desktop.

-   Ubuntu Server can run on systems with only 512MB of RAM

-   Similar to how you have different versions Windows (7, 8 and 10), there are many different versions/distributions of Linux.

#### Running Your First few Commands

-   A large selling point of using OSs such as Ubuntu is how lightweight they can be.
-   This, of course, doesn't come without its disadvantages, where for example, often there is no GUI (Graphical User Interface) or what is also known as a desktop environment that we can use to interact with the machine (unless it has been installed).
-   A large part of interacting with these systems is using the "Terminal".

-   The "Terminal" is purely text-based

![terminal](https://camo.githubusercontent.com/cb9c2b2e8bd0efa76cbd1beddf4607e4dea4e4e5281fcefc24961aabf35f2433/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f666565646261636b2f7434312e706e67)

-   A picture of what a "Terminal" looks like

-   We need to be able to do basic functions like navigate to files, output their contents and make files!
-   The commands to do so are self-explanatory

-   Lets look at two of the first commands in the table below:

![two-commands](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%202/Linux%20Part%201/Pastedimage20210705123913.png)

See the screenshots below for an example of each command being used...

Using `echo` to output the text "Hello Friend"

![echo](https://camo.githubusercontent.com/90e44973a52907f1d87241bb82aa537787c32b9f6266c8944e91cc596a6218d0/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f666565646261636b2f7434322e706e67)

Using `whoami` to find out the username of who we're logged in as

![whoami](https://camo.githubusercontent.com/879b8327e1f191e0b5083abec9ad908c05950200d902549cc843362f8afd8a7c/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f666565646261636b2f7434332e706e67)

#### Interacting With the Filesystem

![commands](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%202/Linux%20Part%201/Pastedimage20210705124110.png)

-   Listing Files in Our Current Directory (ls)

    -   Before we can do anything such as finding out the contents of any files or folders, we need to know what exists in the first place. This can be done using the `ls` command (short for listing)

    -   ![ls](https://camo.githubusercontent.com/65e841e796cf6ec6c4435de5b1c10d004474420bfc90202a6dece6d8588738a1/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f6c73312e706e67)

    -   In the screenshot above, we can see there are the following directories/folders:

        -   Important Files
        -   My Documents
        -   Notes
        -   Pictures

    -   Pro tip: You can list the contents of a directory without having to navigate to it by using `ls` and the name of the directory. I.e. `ls Pictures`

-   Changing Our Current Directory (cd)

    -   Now that we know what folders exist, we need to use the `cd` command (short for change directory) to change to that directory.
    -   Say if we wanted to open the "Pictures" directory - we would do `cd Pictures`.
    -   Where again, we want to find out the contents of this "Pictures" directory and to do so, we'd use `ls` again:

    -   ![cd](https://camo.githubusercontent.com/314593dd2bd6101517d5c942b0ecec740595ab9cac5a4650ffd48f351d9e581b/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f666565646261636b2f7435312e706e67)

    -   In this case, it looks like there are 4 pictures of dogs!

-   Outputting the Contents of a File (cat)

    -   `cat` is short for concatenating & is a fantastic way us to output the contents of files (not just text files!).

    -   In the screenshot below, you can see how you can combine the use of `ls` to list the files within a directory called "Documents":

    -   ![combined](https://camo.githubusercontent.com/e1630168ccad50aeebc2653e7decb89dc13d1af48f65ce70f6b34c240a48ad56/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f6c73342e706e67)

    -   We've applied some knowledge from earlier in this task to do the following:

        -   Used `ls` to let us know what files are available in the "Documents" folder of this machine.
        -   In this case, it is called "todo.txt".
        -   We have then used `cat todo.txt` to concatenate/output the contents of this "todo.txt" file, where the contents are `Here's something important for me to do later!`

    -   Pro tip: You can use `cat` to output the contents of a file within directories without having to navigate to it by using `cat` and the name of the directory. I.e. `cat /home/ubuntu/Documents/todo.txt`

    -   Sometimes things like usernames, passwords, flags or configuration settings are stored within files where "cat" can be used to retrieve these.

-   Finding out the full Path to our Current Working Directory (pwd)

    -   Using the example machine from before, we are currently in the "Documents" folder — but where is this exactly on the Linux machine's filesystem? We can find this out using this `pwd` command like within the screenshot below:

    -   ![pwd](https://camo.githubusercontent.com/3a62fa6b222ed4eb2c7d507a8526c637f2dd787015c509e433b4612c13450e81/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f666565646261636b2f7435322e706e67)

    -   Let's break this down:
        -   We have used the `pwd` (print working directory) command to find the full file path of this "Documents" folder.
        -   We're helpfully told by Linux that this "Documents" directory is stored at `/home/ubuntu/Documents` on the machine — great to know!
        -   Now in the future, if we find ourselves in a different location, we can just use `cd /home/ubuntu/Documents` to change our working directory to this "Documents" directory.

#### Searching for Files

-   Using Find

    -   Finding Files When You Know the Name:

        -   Directories can contain even more directories within themselves
        -   It becomes a headache when we're having to go through every single one just to try and look for specific files
        -   We can use find to do just this for us
        -   Let's assume that we already know the name of the file we're looking for — but can't remember where it is exactly
        -   In this case, we're looking for `passwords.txt`
        -   We can simply use `find -name passwords.txt` where the command will look through every folder in our current directory for that specific file

    -   ![find](https://camo.githubusercontent.com/112c10fe0edd916551939fa208db24d651aa4b4f7232d2965bc3767afdb37f9a/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f66696e64322e706e67)

    -   Using Wildcards for Broader Searches:

        -   "Find" has managed to find the file — it turns out it is located in `folder1/passwords.txt`
        -   But let's say that we don't know the name of the file, or want to search for every file that has an extension such as `.txt`
        -   We can use what's known as a wildcard (\*) to search for anything that has `.txt` at the end
        -   To find every `.txt` file in our current directory, we can construct a command such as `find -name *.txt`
        -   "Find" will locate every `.txt` file and give us the location of each one

    -   ![find-wildcard](https://camo.githubusercontent.com/bc8e1204fdcc9ab919c88acff1e76c6e7109c0921e1d61dc7135ec0e491e2284/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f666565646261636b2f7436312e706e67)

    -   Find has managed to locate: - `passwords.txt` located within `folder1` - `todo.txt` located within `Documents`

-   Using Grep

    -   Another great utility that is a great one to learn about is the use of `grep`.
    -   The `grep` command allows us to search the contents of files for specific values that we are looking for.

    -   Take for example the access log of a web server. In this case, the `access.log` of a web server has 244 entries.

    -   Using a command like `cat` isn't going to cut it too well here.
    -   Let's say for example if we wanted to search this log file to see the things that a certain user/IP address visited? Looking through 244 entries isn't all that efficient considering we want to find a specific value.

    -   We can use grep to search the entire contents of this file for any entries of the value that we are searching for.
    -   Going with the example of a web server's access log, we want to see everything that the IP address `81.143.211.90` has visited

    -   ![grep](https://camo.githubusercontent.com/575e14c3b0a9d4420c747fc8af5955aeb92d4a384032336f3f7ded5a06df56f7/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f67726570312e706e67)

    -   `grep` has searched through this file and has shown us any entries of what we've provided and that is contained within this log file for the IP.

#### An Introduction to Shell Operators

![shell-operators](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%202/Linux%20Part%201/Pastedimage20210705124445.png)

-   Operator "&"

    -   This operator allows us to execute commands in the background.
    -   For example, let's say we want to copy a large file.
    -   This will obviously take quite a long time and will leave us unable to do anything else until the file successfully copies.

    -   The `&` shell operator allows us to execute a command and have it run in the background (such as this file copy) allowing us to do other things!

-   Operator "&&"

    -   Unlike the `&` operator, we can use `&&` to make a list of commands to run for example `command1 && command2`.
    -   However, it's worth noting that command2 will only run if command1 was successful.

-   Operator ">"

    -   This operator is what's known as an output redirector. What this essentially means is that we take the output from a command we run and send that output to somewhere else.

    -   Let's say we wanted to create a file named "welcome" with the message "hey". We can run `echo hey > welcome` where we want the file created with the contents "hey" like so:

    -   ![>](https://camo.githubusercontent.com/4ee4d2047945bff53aa6c6fbd4cb102654d9f1c3000a5abef14b2375b518c2ac/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f6f70657261746f72312e706e67)

    -   Note: If the file i.e. "welcome" already exists, the contents will be overwritten!

-   Operator ">>"

    -   This operator different in the sense that rather than overwriting any contents within a file, for example, it instead just puts the output at the end.

    -   Following on with our previous example where we have the file "welcome" that has the contents of "hey". If were to use echo to add "hello" to the file using the `>` operator, the file will now only have "hello" and not "hey".

    -   The `>>` operator allows to append the output to the bottom of the file — rather than replacing the contents like so:

    -   ![>>](https://camo.githubusercontent.com/c4a8cc5aa7f68dc131f9ab5ae2dd12bd4e6f3d9f45c37814886f755a552b1c19/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274312f6f70657261746f72322e706e67)
