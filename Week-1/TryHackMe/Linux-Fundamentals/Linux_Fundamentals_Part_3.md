## Learn the Linux Fundamentals - Part 3 ([TryHackMe - YouTube](https://www.youtube.com/watch?v=bwgaZCb2ft8))

### Summary:

#### Terminal Text Editors

-   Nano

    -   It is easy to get started with Nano! To create or edit a file using nano, we simply use `nano filename` -- replacing "filename" with the name of the file you wish to edit.

    -   ![nano](https://camo.githubusercontent.com/dc97097c0a1d8ec3936a1989595eaa984df13f1ed830eb82c7eb5271779252f2/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6e616e6f312e706e67)

    -   Once we press enter to execute the command, nano will launch! Where we can just begin to start entering or modifying our text. You can navigate each line using the "up" and "down" arrow keys or start a new line using the "Enter" key on your keyboard.

    -   ![nano2](https://camo.githubusercontent.com/28a8a52bb2300f1acd061b7821b03c17da489c0400fb14378477aa86d4f3097d/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6e616e6f322e706e67)

    -   Nano has a few features that are easy to remember & covers the most general things you would want out of a text editor, including:

        -   Searching for text

        -   Copying and Pasting

        -   Jumping to a line number

        -   Finding out what line number you are on

    -   You can use these features of nano by pressing the "Ctrl" key (which is represented as an ^ on Linux) and a corresponding letter. For example, to exit, we would want to press "Ctrl" and "X" to exit Nano.

-   VIM

    -   VIM is a much more advanced text editor
    -   ![vim](https://camo.githubusercontent.com/0716760c38a9d63d3045eb42a3a70b4af55d8df4c5e6ced363e11fe747e046e9/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f76696d312e706e67)

    -   Some of VIM's benefits, albeit taking a much longer time to become familiar with, includes:

        -   Customizable - you can modify the keyboard shortcuts to be of your choosing
        -   Syntax Highlighting - this is useful if you are writing or maintaining code, making it a popular choice for software developers
        -   VIM works on all terminals where nano may not be installed
        -   There are a lot of resources such as [cheatsheets](https://vim.rtorr.com/), tutorials, and the sorts available to you use.

#### General/Useful Utilities

-   Downloading Files:
    -   We're going to cover the use of `wget`
    -   This command allows us to download files from the web via HTTP -- as if you were accessing the file in your browser
    -   We simply need to provide the address of the resource that we wish to download
    -   For example, if I wanted to download a file named "myfile.txt" onto my machine, assuming I knew the web address, it would look something like this:
    -   `wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt`

![wget-example](https://camo.githubusercontent.com/19bbe49ee3f5da33cc3f9fc2cae7f456b0f7fb874b7ab096649679462e572953/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f777365742e706e67)

-   Transferring Files From Your Host - SCP (SSH):
    -   Secure copy, or SCP, is just that -- a means of securely copying files
    -   Unlike the regular cp command, this command allows you to transfer files between two computers using the SSH protocol to provide both authentication and encryption
    -   Working on a model of SOURCE and DESTINATION, SCP allows you to:
        -   Copy files & directories from your current system to a remote system
        -   Copy files & directories from a remote system to your current system
    -   Provided that we know usernames and passwords for a user on your current system and a user on the remote system

![scp-export](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%203/Pastedimage20210705132236.png)

-   SCP Example - Local to Remote:

    -   With this information, let's craft our scp command (remembering that the format of SCP is just SOURCE and DESTINATION)
    -   `scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt`
    -   The command above will copy the file "important.txt" from our system to the machine with the IP address of "192.168.1.30"
    -   The file will be saved as "transferred.txt" on the remote machine
    -   You will be prompted for the password for the "ubuntu" user on the remote machine

-   SCP Example - Remote to Local:
    -   And now let's reverse this and layout the syntax for using scp to copy a file from a remote computer that we're not logged into
    -   The command will now look like the following: `scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt`
    -   This command will copy the file "documents.txt" from the remote machine (at 192.168.1.30) to our current system
    -   The file will be saved as "notes.txt" on our local machine

![scp-import](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%203/Pastedimage20210705132259.png)

-   Serving Files From Your Host - WEB:
    -   Ubuntu machines come pre-packaged with python3
    -   Python helpfully provides a lightweight and easy-to-use module called "HTTPServer"
    -   This module turns your computer into a quick and easy web server that you can use to serve your own files
    -   These files can then be downloaded by another computer using commands such as `curl` and `wget`
    -   Python3's "HTTPServer" will serve the files in the directory that you run the command, but this can be changed by providing options that can be found in the manual pages
    -   Simply, all we need to do is run `python3 -m http.server` to start the module!
    -   In the screenshot below, we are serving from a directory called "webserver", which has a single file named "file"

![python-http.server](https://camo.githubusercontent.com/565cee7f18718a82993f1d16aca05275d2fcebfa66366c194e30b98eda569401/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f707974686f6e312e706e67)

-   Downloading From a Python HTTP Server:
    -   Now, let's use `wget` to download the file using the computer's IP address and the name of the file
    -   One flaw with this module is that you have no way of indexing, so you must know the exact name and location of the file that you wish to use
    -   This is why I prefer to use Updog
    -   [What's Updog?](https://github.com/sc0tfree/updog) A more advanced yet lightweight webserver
    -   But for now, let's stick to using Python's "HTTP Server"

![python-wget](https://camo.githubusercontent.com/d65e323b342b86e1e1727731cf748193387da740c765de23f096096221cefce3/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f707974686f6e322e706e67)

-   Server Logs:
    -   In the screenshot above, we can see that `wget` has successfully downloaded the file named "file" to our machine
    -   This request is logged by SimpleHTTPServer much as any web server would, which is captured in the screenshot below

![log](https://camo.githubusercontent.com/fed3594f77d355e75dd2d644a26576fec368578a80b606f5d17ddcc102dd8c26/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f707974686f6e332e706e67)

#### Processes 101

-   What are Processes:

    -   Processes are the programs that are running on your machine
    -   They are managed by the kernel, where each process will have an ID associated with it, also known as its PID
    -   The PID increments for the order in which the process starts
    -   For example, the 60th process will have a PID of 60

-   Viewing Processes:
    -   We can use the friendly `ps` command to provide a list of the running processes as our user's session
    -   This shows additional information such as the status code, the session that is running it, how much usage time of the CPU it is using, and the name of the actual program or command that is being executed

![pid](https://camo.githubusercontent.com/15a460f50a5ec5384b82510f10636e8e94bdbb3b7b8cfd65f9301b9a8a49ba21/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f7073312e706e67)

-   Viewing All Processes:
    -   To see the processes run by other users and those that don't run from a session (i.e. system processes), we need to provide aux to the ps command like so: `ps aux`

![ps-aux](https://camo.githubusercontent.com/60d9046b47f6b65cf8d103b2c646d94ff87eccc29f85b2b53a1edb53d9b6eccf/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f7073322e706e67)

-   Real-time Process Monitoring:
    -   Another very useful command is the `top` command
    -   `top` gives you real-time statistics about the processes running on your system instead of a one-time view
    -   These statistics will refresh every 10 seconds, but will also refresh when you use the arrow keys to browse the various rows
    -   It's a great command to gain insight into your system's performance and resource usage

![top](https://camo.githubusercontent.com/1ac7f755165356976d8e302a11f103d525fb9f331d2694863169449a33646d18/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f746f70312e706e67)

-   Managing Processes:

    -   You can send signals that terminate processes using the `kill` command
    -   There are a variety of signal types that correlate to exactly how "cleanly" the process is dealt with by the kernel
    -   To kill a command, we use the `kill` command followed by the PID we wish to kill
    -   For example, to kill PID 1337, we'd use `kill 1337`

-   Common Kill Signals:

    -   `SIGTERM` - Kill the process, but allow it to do some cleanup tasks beforehand
    -   `SIGKILL` - Kill the process - doesn't do any cleanup after the fact
    -   `SIGSTOP` - Stop/suspend a process

-   How do Processes Start?
    -   The Operating System uses namespaces to split up resources available on the computer (such as CPU, RAM and priority)
    -   Namespaces isolate processes from one another for security - only processes in the same namespace can see each other
    -   The process with an ID of 0 is started when the system boots - on Ubuntu this is systemd
    -   systemd sits between the operating system and the user to manage processes
    -   Any program we want to start will run as a child process of systemd with its own PID

![systemd](https://camo.githubusercontent.com/9055b2535f54e92df95f95e258b4edb3325ab45c1dd0d912208664d7e3f1b4d6/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f70726f63657373312e706e67)

-   Starting Services on Boot:

    -   Critical applications like web servers, database servers or file transfer servers often need to start during system boot
    -   We use `systemctl` to interact with the systemd process/daemon
    -   The command follows this format: `systemctl [option] [service]`
    -   For example, to start Apache web server, we'd use `systemctl start apache2`
    -   To have Apache start automatically on boot, we'd use `systemctl enable apache2`

-   Four Main Options with systemctl:

    -   `start` - Start a service
    -   `stop` - Stop a service
    -   `enable` - Configure a service to start on boot
    -   `disable` - Configure a service to not start on boot

-   Backgrounding and Foregrounding Processes:

    -   Processes can run in two states: in the background and in the foreground
    -   Foreground processes are those you interact with directly in your terminal
    -   Background processes run behind the scenes without requiring your direct input

-   Running Commands in Background:
    -   The `&` operator at the end of a command runs it in the background
    -   This is useful for commands like file copying where you don't want to wait for completion

![&](https://camo.githubusercontent.com/3a72457b64e146fb60f70b50c25a484355b62b68ca252b41dbe6f8b7cec83ba9/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6267312e706e67)

-   Backgrounding Running Processes:
    -   You can use `Ctrl + Z` to suspend and background a running process
    -   This effectively "pauses" the execution of a script or command

![ctrlz](https://camo.githubusercontent.com/550d23444b71e1944c2349817e2b34f6efd6ba1aa1a006ce23080db689c7d9a8/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6267322e706e67)

-   Foregrounding Background Processes:
    -   The `fg` command brings a backgrounded process back to the foreground
    -   This allows you to interact with the process again
    -   When brought to the foreground, the output of the process will return to your terminal

![fg](https://camo.githubusercontent.com/cf4ab1bfecade913b02d1786a9622ebed9d539cc0d269add3cc078bb3500bd4c/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6267332e706e67)

![fg-cont](https://camo.githubusercontent.com/a56a2d9253e7af38ca397b4f1bf916334ecafe5599c2581eff9ecbe1fd0cce06/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6267352e706e67)

#### Maintaining Your System: Automation

-   Introduction to Cron Jobs:
    -   Users may want to schedule certain tasks to occur automatically at specific times
    -   Common examples include running commands, backing up files, or launching applications at boot
    -   Linux uses the cron daemon to facilitate and manage scheduled tasks
    -   Crontab (cron table) is the configuration file that specifies these scheduled jobs

![cron](https://camo.githubusercontent.com/923ba7e464ad649a26ed240011badf1595ff71448a31b5089d50cbfbebe53e1e/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f63726f6e312e706e67)

-   Crontab Structure:
    -   A crontab is a special file with specific formatting that the cron process recognizes
    -   Each line in a crontab represents a scheduled job that will execute automatically
    -   Crontab entries require 6 specific values that determine when and how often the task runs

![cron-syntax](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Linux%20Part%203/Pastedimage20210705133121.png)

-   Understanding the Format:

    -   The first five fields specify the schedule (minute, hour, day of month, month, day of week)
    -   The sixth part (after the time fields) contains the command to be executed
    -   Each field can contain specific values, ranges, lists, or wildcards

-   Example Use Case:

    -   Let's use the example of backing up files
    -   If you want to backup a user's "Documents" directory every 12 hours, you would use:
    -   `0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/`
    -   This command will run at minute 0 of every 12th hour, regardless of day, month or weekday

-   Using Wildcards:

    -   An interesting feature of crontabs is the support for wildcards (asterisk \*)
    -   If you don't care about a specific time field, you can use an asterisk
    -   For example, if you only care that something runs every 12 hours (not which day or month), you place asterisks in those fields
    -   The asterisk means "every" instance of that time unit

-   Helpful Crontab Resources:

    -   Creating crontab entries can be confusing for beginners
    -   Several online tools can help generate properly formatted crontab entries:
        -   [Crontab Generator](https://crontab-generator.org/) - A user-friendly application to create crontab formatting
        -   [Cron Guru](https://crontab.guru/) - An interactive editor that explains cron expressions in plain English

-   Editing Your Crontab:
    -   To create or modify your user's crontab, use the command `crontab -e`
    -   This opens your crontab file in your default text editor (often Nano)
    -   After saving and exiting, the cron daemon automatically loads your changes

![cron](https://camo.githubusercontent.com/cd858d0de626f4a2a2a41146b6bf6861b6a92d98f5451a371127bf70a00db48e/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f63726f6e322e706e67)

![cron-edit](https://camo.githubusercontent.com/d16c9d1c425ca4414fd401d82f44c16619960389a682dafc3ae2fb56c2429a50/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f63726f6e332e706e67)

-   Common Crontab Options:
    -   `crontab -l` - List your current crontab entries
    -   `crontab -r` - Remove your current crontab
    -   `crontab -e` - Edit your crontab
    -   System-wide crontabs are stored in `/etc/crontab` and `/etc/cron.d/`

#### Maintaining Your System: Package Management

-   Introducing Packages & Software Repos:
    -   When developers wish to submit software to the community, they will submit it to an "apt" repository
    -   If approved, their programs and tools will be released into the wild
    -   Two of the most redeeming features of Linux shine to light here: User accessibility and the merit of open source tools
    -   When using the `ls` command on a Ubuntu 20.04 Linux machine, these files serve as the gateway/registry

![/etc/apt-ls](https://camo.githubusercontent.com/cb6ce60e955f8ec50b342112a88440704c450af8991bcc73a4d3826165f45681/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f617074312e706e67)

![source.list](https://camo.githubusercontent.com/08aa30c7652f79b3483ab9b7e68d88a29b08d1a6e660df4ef976fe0cde52af22/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f617074322e706e67)

-   Adding External Repositories:

    -   Whilst Operating System vendors maintain their own repositories, you can also add community repositories to your list
    -   This allows you to extend the capabilities of your OS
    -   Additional repositories can be added by using the `add-apt-repository` command or by listing another provider
    -   Some vendors will have a repository that is closer to their geographical location

-   Managing Your Repositories:

    -   Normally we use the `apt` command to install software onto our Ubuntu system
    -   The apt command is part of the package management software also named apt
    -   Apt contains a whole suite of tools that allows us to manage the packages and sources of our software
    -   When adding software, the integrity of what we download is guaranteed by GPG (Gnu Privacy Guard) keys
    -   These keys are essentially a safety check from the developers saying, "here's our software"
    -   If the keys do not match up to what your system trusts, the software will not be downloaded

-   Adding a Repository Example - Sublime Text 3:

    -   Step 1: Download and trust the GPG key:

        -   `wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -`

    -   Step 2: Add the repository to our apt sources list
        -   Create a file for the repository in the sources directory

![.list](https://camo.githubusercontent.com/705cdf59181ad39200aaf4f03f8517c44a9ce361a789af48d55342ad612542fa/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f736f7572636573312e706e67)

    - Step 3: Edit the file and add the repository information

![nano-file](https://camo.githubusercontent.com/ddc923fba3fd61a9b28a3301e973c3ed7435b30ad32331f2250689b306f0a893/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f736f7572636573322e706e67)

    - Step 4: Update apt to recognize the new entry
      - `sudo apt update`

    - Step 5: Install the software
      - `sudo apt install sublime-text`

-   Removing Repositories and Software:
    -   Removing packages is as easy as reversing the process
    -   To remove a repository, use:
        -   `sudo add-apt-repository --remove ppa:PPA_Name/ppa`
    -   Or manually delete the file we previously created
    -   To remove software, use:
        -   `sudo apt remove [software-name-here]`
    -   For example:
        -   `sudo apt remove sublime-text`

#### Maintaining Your System: Logs

-   Introduction to Log Files:

    -   Located in the `/var/log` directory, these files and folders contain logging information for applications and services running on your system
    -   The Operating System has become pretty good at automatically managing these logs in a process that is known as "rotating"
    -   Log rotation ensures logs don't consume too much disk space by archiving and compressing older logs

-   Example Services and Their Logs:
    -   The screenshot below highlights logs from three important services running on a Ubuntu machine:
        -   An Apache2 web server
        -   Logs for the fail2ban service, used to monitor attempted brute forces
        -   The UFW service which functions as a firewall

![services](https://camo.githubusercontent.com/1a7e3994e00435a6457369e78b150d15473800fd7f13bf61128464b7ff0f3d79/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6c6f67312e706e67)

-   Benefits of Log Monitoring:

    -   Logs are a great way to monitor the health of your system and protect it
    -   They contain information about every single request or action
    -   This allows developers or administrators to diagnose performance issues or investigate security incidents
    -   Logs provide a chronological record of events that can be crucial for troubleshooting

-   Important Web Server Log Types:
    -   Two types of log files are particularly important for web servers:
        -   Access log: Records every request made to the web server, including IP addresses, requested resources, and response codes
        -   Error log: Contains information about problems encountered by the server when processing requests

![logs](https://camo.githubusercontent.com/d9578119da74ea34eb49c0bb47528ebb1e35dae9029c000bea23be7aa4c1e0e3/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6c696e75782d66756e64616d656e74616c732f70617274332f6c6f67322e706e67)

-   System Operation Logs:

    -   Beyond application logs, there are logs that store information about how the OS is running itself
    -   These logs track actions performed by users, such as authentication attempts
    -   Common system logs include:
        -   `/var/log/auth.log` or `/var/log/secure`: Authentication and authorization attempts
        -   `/var/log/syslog` or `/var/log/messages`: General system activities
        -   `/var/log/kern.log`: Kernel messages and errors

-   Working with Logs:
    -   You can use standard text processing tools to extract information from logs:
        -   `cat`: Display the entire log file
        -   `grep`: Search for specific patterns in logs (e.g., `grep "Failed password" /var/log/auth.log`)
        -   `tail -f`: Follow log updates in real-time (e.g., `tail -f /var/log/apache2/access.log`)
    -   For larger log files, tools like `less` provide a more manageable way to browse the content
