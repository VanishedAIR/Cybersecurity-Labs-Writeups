# Tools of the Trade: Linux and SQL

## Module 1

### Introduction to Operating Systems

An **operating system (OS)** is the software that acts as an interface between computer hardware and the user. Its main job is to manage hardware resources and make the computer easy and efficient to use.

-   **Hardware** refers to the physical parts of a computer, like the CPU, memory, keyboard, and mouse.
-   The OS allows users to run multiple programs at once and interact with external devices (printers, USB drives, etc.).
-   Early computers lacked operating systems, so users had to manually load and run each program one at a time, making tasks slow and inconvenient.

Modern operating systems have evolved to:

-   Run several applications simultaneously (multitasking)
-   Manage communication between hardware and software
-   Provide a user-friendly interface so people don’t need to understand binary (the 0s and 1s computers use)
-   Enable secure access to files and data, protecting against threats like viruses and malware

**Key Point:**  
The OS is essential for both usability and security, helping users interact with computers safely and efficiently.

### Legacy Operating Systems

A **legacy operating system** is an outdated OS that is still in use, often because critical software or equipment depends on it. This is common in industries with specialized hardware that requires embedded software.

**Risks of legacy OS:**

-   No longer receives security updates or patches
-   Increased vulnerability to new threats and exploits

**Other OS Vulnerabilities**

Even up-to-date operating systems can have vulnerabilities. Security analysts should regularly check trusted resources for updates and known issues, such as:

-   **Microsoft Security Response Center (MSRC):**  
    Lists vulnerabilities for Microsoft products and services.

-   **Apple Security Updates:**  
    Provides security updates for macOS, iOS, and other Apple products.

-   **Common Vulnerabilities and Exposures (CVE) for Ubuntu:**  
    Tracks vulnerabilities for Ubuntu Linux.

-   **Google Cloud Security Bulletin:**  
    Lists vulnerabilities for Google Cloud products.

**Best Practice:**  
Keep operating systems updated whenever possible. If legacy systems must be used, understand the risks and take extra precautions to secure them.

### Inside the Operating System

The operating system (OS) acts like the engine of a car—handling all the complex details so users can focus on their tasks without worrying about how everything works behind the scenes.

#### Booting Up

-   When you press the power button, you're interacting with the hardware.
-   The computer starts by activating a special chip:
    -   **BIOS** (Basic Input/Output System) on older systems
    -   **UEFI** (Unified Extensible Firmware Interface) on most systems built after 2007
-   BIOS or UEFI loads the **bootloader**, which then starts the operating system.

> **Security Note:**  
> The BIOS/UEFI is not always scanned by antivirus software, making it a potential target for malware.

#### How the OS Handles Tasks

1. **User Action:**  
   You use an application (like a calculator) to perform a task.
2. **Application Request:**  
   The application sends your request to the OS.
3. **OS Management:**  
   The OS interprets the request and communicates with the appropriate hardware component (e.g., CPU).
4. **Hardware Response:**  
   The hardware processes the request and sends the result back to the OS.
5. **Result Display:**  
   The OS delivers the result to the application, which displays it to you.

**Example:**  
When you use a calculator app:

-   You click the app and enter numbers.
-   The app sends your input to the OS.
-   The OS tells the CPU to perform the calculation.
-   The CPU returns the answer to the OS.
-   The OS sends the answer back to the calculator app for display.

#### Why This Matters for Security

Understanding how the OS manages requests and hardware interactions helps security analysts trace the flow of events and identify where a security incident may have occurred.

### Request to the Operating System

#### Booting the Computer

When you turn on your computer, either a **BIOS** or **UEFI** chip is activated:

-   **BIOS** (Basic Input/Output System) is found in older systems.
-   **UEFI** (Unified Extensible Firmware Interface) is used in most modern computers and offers enhanced security features.

Both BIOS and UEFI contain instructions for starting up the computer, such as checking hardware health. The final step is to activate the **bootloader**, a small program that loads the operating system. Once the OS is loaded, your computer is ready for use.

---

#### Completing a Task: The Four-Part Process

![process](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/bfvQyeg_SC-DSgUsegf8PQ_8405d4e94af147e1b98df5150c2fd7f1_CS_R-060_User-Application-Operating-System-Hardware.png?expiry=1753488000000&hmac=e6cBelzViEVwYb8VooklA56tgMq56rpJi473WplRnac)

1. **User:**  
   Initiates a task (e.g., wants to download a file or print a document).

2. **Application:**  
   The software the user interacts with (e.g., web browser, calculator, word processor).

3. **Operating System:**  
   Receives the request from the application, interprets it, and sends it to the appropriate hardware.

4. **Hardware:**  
   Performs the actual work (e.g., CPU processes data, hard drive saves files) and sends the result back through the OS to the application, which displays it to the user.

---

#### The OS at Work Behind the Scenes

Think of the OS like a restaurant kitchen:

-   You (the user) place an order (make a request through an application).
-   The kitchen (OS) prepares your food (processes your request).
-   You receive your meal (the application displays the result).
    You don’t see the kitchen’s work, but it’s essential for getting what you want.

---

#### Example: Downloading a File from a Browser

1. The user clicks "Download" in the browser.
2. The browser sends the download request to the OS.
3. The OS tells the hardware to start downloading the file.
4. The hardware processes the download, and the OS updates the browser, which then notifies the user when the download is complete.

---

Understanding these processes helps security analysts trace how requests flow through a system and identify where security incidents may occur.

### Resource Allocation via the Operating System

The operating system (OS) doesn't just connect users and hardware—it also manages the computer's resources to keep everything running smoothly and efficiently.

Think of the OS as the conductor of an orchestra, making sure each instrument (program or process) gets the attention and resources it needs at the right time.

#### How the OS Manages Resources

-   **Resource Management:**  
    The OS decides how to allocate CPU time, memory, storage, and input/output bandwidth among all running programs and processes.
-   **Balancing Demands:**  
    Some tasks (like running an antivirus scan) require more resources, while others (like using a calculator) need less. The OS balances these demands so the system doesn't get overloaded.
-   **Memory Management:**  
    The OS keeps track of which programs are using which parts of memory, allocating and freeing up memory as needed.
-   **Process Scheduling:**  
    Multiple programs may need the CPU at the same time. The OS schedules which process gets CPU time and for how long.
-   **Task Manager:**  
    Tools like the Task Manager (in Windows) or Activity Monitor (in macOS) let you see which programs are running and how much memory and CPU they're using.

Most of this resource management happens behind the scenes, but it's essential for keeping your computer responsive and efficient.

### Virtualization Technology

#### What is a Virtual Machine?

A **virtual machine (VM)** is a software-based emulation of a physical computer. Virtualization is the process of using software to create virtual versions of physical resources, such as computers, servers, or networks. Virtual machines have their own virtual CPU, storage, and other hardware components, but these are simulated by software rather than existing physically.

-   Multiple VMs can run on a single physical computer, sharing its resources (CPU, RAM, storage).
-   Each VM operates independently and can run its own operating system.

**Example:**  
If a computer has 16GB of RAM, it could host three VMs, each with 4GB of RAM, while the host system uses the remaining 4GB.

---

#### Benefits of Virtual Machines

**Security:**

-   VMs provide isolated environments (sandboxes) on the host machine.
-   If one VM is compromised (e.g., by malware), it is isolated from the host and other VMs, reducing risk.
-   Security professionals can safely analyze malware or suspicious files within a VM.

> **Note:**  
> While VMs are isolated, there is still a small risk that malware could escape the VM and affect the host system.

**Efficiency:**

-   Multiple VMs can be run and managed on a single physical machine, making it easier to test, explore, and perform security tasks.
-   Switching between VMs is quick and convenient, streamlining workflows.
-   Analogy: Like a city bus carrying many passengers, VMs allow multiple "computers" to share one set of hardware resources, saving costs and energy.

---

#### Managing Virtual Machines

-   **Hypervisor:**  
    Software that manages VMs and allocates physical resources to them.
    -   **Kernel-based Virtual Machine (KVM):** An open-source hypervisor built into the Linux kernel, allowing users to create and manage VMs on Linux systems without extra software.

---

#### Other Forms of Virtualization

-   **Virtual Servers:** Multiple virtual servers can be created from a single physical server to maximize hardware usage.
-   **Virtual Networks:** Virtual networks can be set up to efficiently use the hardware of a physical network, allowing for flexible and scalable network configurations.

---

**Summary:**  
Virtualization enables efficient, flexible, and secure use of computing resources, making it a valuable tool for security professionals and IT operations.

### GUI versus CLI

The way users interact with the operating system is through a **user interface**. There are two main types:

#### Graphical User Interface (GUI)

-   Uses icons, menus, and windows to help users manage tasks visually.
-   Common in most operating systems, personal computers, and smartphones.
-   Components often include a start menu, task bar, and desktop with icons and shortcuts.
-   Users can click icons or search for files and applications by name.
-   **Analogy:** Using a GUI is like ordering food from a restaurant—you choose from what's on the menu.

#### Command-Line Interface (CLI)

-   Text-based interface where users type commands to interact with the OS.
-   No icons or graphics—just a prompt for entering commands.
-   More flexible and powerful than a GUI, allowing for advanced customization and automation.
-   **Analogy:** Using a CLI is like cooking your own meal from scratch—you have more control and can combine ingredients however you want.

**Example:**  
If you need to move hundreds of JPEG files from one folder to another:

-   With a GUI, you would manually select and move each file, which can be slow.
-   With a CLI, you can use a single command to move all JPEG files at once, making the process much faster and more efficient.

**Key Point:**  
GUIs are user-friendly and great for everyday tasks, while CLIs offer more power and efficiency for complex or repetitive operations.

## Module 2

### Introduction to Linux

Linux is an **open-source operating system** that originated in the early 1990s. It was created by combining two major projects:

-   **The Linux kernel** by Linus Torvalds, inspired by UNIX and designed to be open and accessible.
-   **The GNU project** by Richard Stallman, which aimed to create free software for everyone.

By combining the GNU tools and the Linux kernel, a fully functional operating system was born. Linux is licensed under the GNU Public License, which means anyone can use, modify, and share it freely. This open philosophy has led to a large, active community and the creation of over 600 different Linux distributions (or "distros").

Linux is widely used in IT and cybersecurity. As a security analyst, you’ll often use Linux to:

-   Examine system logs to investigate issues
-   Manage access and authorization
-   Run a variety of security tools

**Key Point:**  
Linux’s flexibility, strong community, and open-source nature make it a core part of modern computing and security work.

### Linux Architecture

The architecture of Linux is made up of several main components that work together to run the system:

-   **User:**
    -   The person interacting with the computer.
    -   Linux supports multiple users at the same time (multi-user system), allowing several people to use the same resources simultaneously.
-   **Applications:**
    -   Programs that perform specific tasks, like text editors (e.g., Nano), web browsers, or calculators.
    -   Applications are often installed using package managers—a tool that helps you install, manage, and remove software packages.
-   **Shell:**
    -   The command-line interface (CLI) that lets users communicate with the system by typing commands.
    -   Acts as a translator between you and the computer, passing your commands to the kernel and displaying the results.
-   **Filesystem Hierarchy Standard (FHS):**
    -   The way Linux organizes files and directories, like a digital filing cabinet, so data can be easily found and managed.
    -   Directories (also called folders) can contain files or other directories.
    -   The FHS defines where different types of data are stored in the system.
-   **Kernel:**
    -   The core of the operating system.
    -   Manages memory, processes, and communicates with the hardware using drivers.
    -   Responsible for allocating resources and routing commands from applications, ensuring the system runs efficiently.
-   **Hardware:**
    -   The physical components of the computer.
    -   **Internal hardware:**
        -   **Motherboard:** The main circuit board connecting all components.
        -   **CPU (Central Processing Unit):** Executes instructions from programs and performs general computing tasks.
        -   **RAM (Random Access Memory):** Provides short-term memory for active tasks; data in RAM is lost when the computer is turned off.
        -   **Hard Drive:** Stores programs and files for long-term access, even after the computer is powered down.
    -   **Peripheral devices:**
        -   Hardware that can be added or removed, such as monitors, printers, keyboards, and mice.

### Linux Distributions

Linux is highly customizable, and there are many different versions available—these are called distributions (or distros/flavors). Each distribution includes the Linux kernel, utilities, a package management system, and an installer. Understanding your distribution is important because it determines what tools and apps are available to you.

-   **Distributions (distros):** Different versions of Linux, each with its own set of tools, preinstalled programs, and user interface.
-   **Analogy:** The Linux kernel is like an engine, and distributions are like different types of vehicles built around that engine (cars, trucks, buses, airplanes, etc.), each serving different purposes.
-   **Customization:** Because the kernel is open source, anyone can modify it to create a new distribution tailored to specific needs or preferences.
-   **Parent distributions:** Some distros are "parents" to others. For example:
    -   **Red Hat®** is the parent of CentOS.
    -   **Slackware®** is the parent of SUSE®.
    -   **Debian** is the parent of Ubuntu and Kali Linux™.
-   **Choice:** Users often pick a distro based on their needs (e.g., security, stability, user interface) or personal preference—just like choosing a type of vehicle.

### Kali Linux

Kali Linux™ is a Debian-based distribution developed by Offensive Security, designed specifically for penetration testing and digital forensics. It comes with many pre-installed security tools.

-   **Purpose:** Built for penetration testing (simulated attacks to find vulnerabilities) and digital forensics (analyzing data after incidents).
-   **Best practice:** Always use Kali Linux in a virtual machine to avoid damaging your main system and to easily revert to previous states.
-   **Pre-installed tools:**
    -   **Metasploit:** Finds and exploits vulnerabilities.
    -   **Burp Suite:** Tests web applications for weaknesses.
    -   **John the Ripper:** Password cracking tool.
    -   **tcpdump:** Command-line packet analyzer for capturing network traffic.
    -   **Wireshark:** GUI tool for analyzing live or captured network traffic.
    -   **Autopsy:** Forensic tool for analyzing hard drives and smartphones.
-   **Use in security:** Popular among security professionals for both pen testing and forensic investigations due to its wide range of included tools.

### More Linux Distributions

-   **Ubuntu:**
    -   Open-source, user-friendly, and widely used in security and other industries.
    -   Offers both CLI and GUI.
    -   Debian-derived; comes with common applications and access to many more via package manager.
    -   Large community support and resources.
    -   Popular for cloud computing and often used in cloud-based cybersecurity work.
-   **Parrot:**
    -   Open-source, Debian-based, and focused on security.
    -   Comes with pre-installed tools for penetration testing and digital forensics.
    -   User-friendly with both GUI and CLI.
-   **Red Hat® Enterprise Linux®:**
    -   Subscription-based, built for enterprise use.
    -   Not free; includes dedicated support for customers.
-   **AlmaLinux:**
    -   Community-driven, designed as a stable replacement for CentOS.
    -   Drop-in compatible with CentOS 8, ensuring continued support for existing applications and configurations.

### Package Managers for Installing Applications

-   **Package:** A piece of software that can be combined with others to form an application. Packages include all necessary files and dependencies (supplemental files needed to run the application).
-   **Package manager:** A tool that helps users install, manage, and remove packages or applications. It also resolves dependency issues and keeps software up to date.
    -   Always use the most recent version of a package for security and bug fixes.
-   **Types of package managers:**
    -   Different distributions use different package managers, often based on their parent distro.
    -   **Debian-derived distros** (e.g., Kali Linux™, Ubuntu, Parrot): use package managers like **dpkg** (.deb files).
    -   **Red Hat-derived distros** (e.g., CentOS): use **RPM** (.rpm files).
-   **Package management tools:**
    -   Tools that make it easier to manage packages from the shell.
    -   **APT (Advanced Package Tool):** Used with Debian-based distros to manage, search, and install packages from the CLI.
    -   **YUM (Yellowdog Updater Modified):** Used with Red Hat-based distros to manage, search, and install .rpm packages from the CLI.

## Module 3

### Introduction to the Shell

-   The shell is the command-line interpreter that lets you communicate with the operating system through text commands.
-   Provides the command-line interface (CLI) for interacting with the OS.
-   Commands are instructions you enter to tell the computer what to do; the shell passes these to the kernel for execution.
-   Acts as a language interpreter between you and your system, since humans don’t speak computer language or binary.
-   While the OS can run without the shell, the shell is essential for users to access system features, run applications, and automate tasks.
-   Allows you to combine commands and connect applications, making complex and automated operations possible.

### Input and Output in the Shell

-   **Standard input (stdin):** Information entered by the user via the keyboard into the shell (e.g., typing a command).
    -   Analogy: Like asking your friend a question in a conversation.
-   **Standard output (stdout):** The result or response returned by the OS through the shell after executing a command.
    -   Example: Typing `echo hello` and pressing enter returns `hello` as output.
    -   Analogy: Like your friend answering your question.
-   **Standard error (stderr):** Error messages returned by the OS through the shell when a command fails or is invalid.
    -   Example: Typing `eco hello` (misspelling `echo`) returns an error message.
    -   Analogy: Like your friend saying they can't answer your question.
-   Communication with the shell involves:
    -   Input (command from user)
    -   Output (system response)
    -   Error (system can't process the command)

### Find What You Need with Linux

#### grep

-   Searches a file for lines containing a specified string and returns those lines.
    -   Syntax: `grep <string> <filename>`
    -   Example: `grep OS updates.txt` returns all lines in updates.txt containing 'OS'.
    -   Useful for quickly finding information in large files.

#### Piping (`|`)

-   Sends the output of one command as input to another command for further processing.
    -   Analogy: Like a physical pipe carrying water from one place to another, piping carries data between commands.
    -   Example: `ls reports | grep users` lists only files/directories in the reports directory that contain 'users' in their name.
    -   Allows you to combine commands for powerful filtering and searching.

### Filter Content in Linux

#### find

-   Searches for directories and files that meet specified criteria.
    -   Can search by name, file size, modification time, and more.
    -   Syntax: `find <start_path> <options>`
    -   Example: `find /home/analyst/projects` searches everything under the projects directory.
    -   Options modify the search and usually start with a hyphen (-).
    -   **-name:**
        -   Searches for names containing a specific string (case-sensitive).
        -   Use quotes and wildcards (`*`) to match patterns (e.g., `find /home/analyst/projects -name "*log*"`).
    -   **-iname:**
        -   Like -name, but case-insensitive.
    -   **-mtime:**
        -   Finds files or directories modified within a certain number of days.
        -   Example: `find /home/analyst/projects -mtime -3` returns items modified in the last 3 days.
        -   `-mtime +1`: modified more than 1 day ago; `-mtime -1`: less than 1 day ago.
        -   Use `-mmin` to search by minutes instead of days.

### Navigating Linux and Reading File Content

#### Filesystem Hierarchy Standard (FHS)

-   Defines how directories and files are organized in Linux.
    -   The system is hierarchical, starting from the root directory (`/`).
    -   **Root directory (`/`):** The highest-level directory; all other directories branch from here.
    -   **Standard FHS directories:**
        -   `/home`: Each user gets a personal home directory.
        -   `/bin`: Contains binary files and executables.
        -   `/etc`: Stores system configuration files.
        -   `/tmp`: Temporary files; accessible by all users (often targeted by attackers).
        -   `/mnt`: Used for mounting external media (USB drives, hard drives).
    -   **User-specific subdirectories:**
        -   Each user has subdirectories under `/home` (e.g., `/home/analyst/logs`).
        -   The tilde (`~`) represents the current user's home directory (e.g., `~/logs`).
    -   **File paths:**
        -   **Absolute path:** Starts from the root (e.g., `/home/analyst/projects`).
        -   **Relative path:** Starts from the current directory (e.g., `../projects`).
        -   `.` represents the current directory; `..` represents the parent directory.
    -   **Pro Tip:** Use `man hier` to learn more about the FHS and standard directories.

#### Key commands for navigating the file system

-   `pwd`: Prints the absolute path of the current working directory.
    -   **Pro Tip:** Use `whoami` to display your current username.
-   `ls`: Lists files and directories in the current directory.
    -   Add a path as an argument to list contents of another directory (e.g., `ls projects`).
-   `cd`: Changes the current directory.
    -   Use a subdirectory name, absolute path, or relative path as an argument.
    -   `cd ..` moves up one level in the directory structure.

#### Common commands for reading file content

-   `cat <filename>`: Displays the entire contents of a file.
-   `head <filename>`: Shows the first 10 lines of a file.
    -   **Pro Tip:** Use `head -n 5 <filename>` to display the first 5 lines.
-   `tail <filename>`: Shows the last 10 lines of a file.
    -   **Pro Tip:** Useful for viewing the most recent entries in log files.
-   `less <filename>`: Opens the file one page at a time for easy navigation.
    -   **Controls in less:**
        -   Space bar: Forward one page
        -   b: Back one page
        -   Down arrow: Forward one line
        -   Up arrow: Back one line
        -   q: Quit and return to terminal

### Create and Modify Directories and Files

-   **Organization:** Directories (folders) help keep files and subdirectories organized, making it easier to manage and secure data.

#### Creating and Removing Directories

-   `mkdir <directory>`: Creates a new directory.
    -   Example: `mkdir drafts` creates a drafts directory.
-   `rmdir <directory>`: Removes an empty directory.
    -   Warns you if the directory is not empty.
    -   Example: `rmdir oldreports` removes the oldreports directory.

#### Creating and Removing Files

-   `touch <filename>`: Creates a new, empty file.
    -   Example: `touch email_patches.txt` creates a new file.
-   `rm <filename>`: Removes (deletes) a file.
    -   Example: `rm email_patches.txt` deletes the file.

#### Moving and Copying Files/Directories

-   `mv <source> <destination>`: Moves a file or directory to a new location.
    -   Example: `mv email_policy.txt drafts/` moves the file into the drafts directory.
-   `cp <source> <destination>`: Copies a file or directory to a new location.
    -   Example: `cp vulnerabilities.txt ../projects/` copies the file to the projects directory.

#### Editing Files

-   **nano:** A beginner-friendly file editor accessible via the command line.
    -   Open a file: `nano OS_patches.txt`
    -   Save changes: `Ctrl+O`, then Enter
    -   Exit nano: `Ctrl+X`
    -   Useful for writing or editing reports and configuration files.

### Manage Directories and Files: Standard Output Redirection

#### Output Redirection Operators

-   `>` and `>>` are used to redirect standard output to a file instead of the screen.
    -   `>` overwrites the file with new content.
    -   `>>` appends new content to the end of the file.
    -   Both operators create the file if it doesn't already exist.

#### Usage Examples

-   `echo "last updated date" >> permissions.txt`
    -   Appends "last updated date" to the end of permissions.txt.
-   `echo "time" > permissions.txt`
    -   Overwrites permissions.txt with "time" as the only content.

#### Notes

-   Use `>` carefully, as it will overwrite the entire file and recovery is difficult.
-   These operators can be used with many commands, not just echo, to save or append output to files.

### File Permissions and Ownership

#### Permissions

-   Define the type of access granted for a file or directory (authorization).
-   Three types of permissions:
    -   **Read (r):**
        -   File: Can read contents.
        -   Directory: Can list files in the directory.
    -   **Write (w):**
        -   File: Can modify contents.
        -   Directory: Can create or delete files in the directory.
    -   **Execute (x):**
        -   File: Can execute the file if it's an executable.
        -   Directory: Can enter the directory and access its files.

#### Ownership Types

-   **User:** The owner of the file (usually the creator).
-   **Group:** A set of users; group permissions apply to all users in the group.
-   **Other:** All other users on the system.

#### Permission String Format

-   Permissions are shown as a 10-character string (e.g., `drwxrwxrwx`).
    -   1st character: File type (`d` for directory, `-` for file).
    -   2nd-4th: User permissions (rwx).
    -   5th-7th: Group permissions (rwx).
    -   8th-10th: Other permissions (rwx).
    -   Hyphens (`-`) indicate missing permissions.
-   Example: `-rw-r--r--` means user can read/write, group and other can only read.

#### Security Implications

-   Only grant access on a need-to-know basis.
-   World-writable files (write permission for user, group, and other) are a security risk.
-   Sensitive files (e.g., payroll) should be restricted to appropriate users/groups.

#### Checking Permissions

-   **Options** modify command behavior (single letter or word).
-   `ls -l`: Lists files/directories with permissions and ownership info.
-   `ls -a`: Shows hidden files (names start with a period).
-   `ls -la`: Combines both to show permissions for all files, including hidden ones.
    -   Example output: `-rw-r--r-- 1 analyst security 1234 Jan 1 12:00 project1.txt`
        -   Shows permissions, user, group, file size, date, and file name.

### Change Permissions with chmod

-   `chmod` (change mode) changes permissions on files and directories.
-   Focus on symbolic mode for changing permissions.

#### Symbolic Mode Structure

-   Syntax: `chmod [owner][operator][permission] <file>`
    -   **Owner types:**
        -   `u`: user (owner)
        -   `g`: group
        -   `o`: other
    -   **Operators:**
        -   `+`: add permission
        -   `-`: remove permission
    -   **Permissions:**
        -   `r`: read
        -   `w`: write
        -   `x`: execute
-   Multiple owner types can be separated by commas (e.g., `g+w,o-r`).

#### Example

-   `chmod g+w,o-r access.txt`
    -   Adds write permission for group.
    -   Removes read permission for other.
-   Use `ls -l` before and after to verify permission changes.
    -   Hyphens (`-`) in the permission string indicate missing permissions.

#### Notes

-   You don't need to memorize all options; references are always available.
-   Adjust permissions carefully to maintain security.

### Add and Delete Users

#### User Management

-   Only authorized users should have access to the system.
-   Add new users when people join or change roles; delete users when they leave or no longer need access.

#### Root User and sudo

-   **Root user (superuser):** Has full system privileges; can create, modify, or delete any file and run any program.
    -   Running as root is risky (security, mistakes, lack of accountability).
    -   Best practice: Disable direct root logins and use sudo for elevated tasks.
-   **sudo:** Temporarily grants elevated permissions to specific users for running commands.
    -   Users must be granted sudo access in the sudoers file.
    -   Prompts for the current user's password.

#### Adding and Deleting Users

-   Only root or users with sudo privileges can add or delete users.
-   **Add a user:**
    -   `sudo useradd <username>`
    -   Example: `sudo useradd salesrep7` adds a new user named salesrep7.
-   **Delete a user:**
    -   `sudo userdel <username>`
    -   Example: `sudo userdel salesrep7` deletes the user salesrep7.
-   Successful commands return a new Bash prompt with no error message.

### Responsible Use of sudo and User Management Commands

#### useradd

-   Adds a user to the system (requires sudo/root privileges).
    -   Syntax: `sudo useradd <username>`
    -   `-g <group>`: Sets the user's primary group.
        -   Example: `sudo useradd -g security fgarcia` assigns fgarcia to the security group.
    -   `-G <group1,group2>`: Adds user to supplemental (secondary) groups.
        -   Example: `sudo useradd -G finance,admin fgarcia` adds fgarcia to finance and admin groups.

#### usermod

-   Modifies existing user accounts.
    -   `-g <group>`: Changes the primary group.
        -   Example: `sudo usermod -g executive fgarcia` changes fgarcia's primary group to executive.
    -   `-G <group1,group2>`: Sets supplemental groups (replaces existing unless used with -a).
    -   `-a -G <group>`: Appends user to additional groups (use only with -G).
        -   Example: `sudo usermod -a -G marketing fgarcia` adds fgarcia to marketing group.
    -   `-d <directory>`: Changes the user's home directory.
        -   Example: `sudo usermod -d /home/garcia_f fgarcia`
    -   `-l <newname>`: Changes the user's login name.
    -   `-L`: Locks the account (prevents login).
        -   Example: `sudo usermod -L fgarcia`
    -   **Note:** Omitting `-a` with `-G` will replace all supplemental groups.

#### userdel

-   Deletes a user from the system.
    -   Syntax: `sudo userdel <username>`
    -   `-r`: Deletes the user's home directory and files.
        -   Example: `sudo userdel -r fgarcia`
    -   **Best practice:** Backup important files before deleting a user.
    -   To deactivate (not delete) a user, use `usermod -L` to lock the account.

#### chown

-   Changes ownership of a file or directory.
    -   Syntax: `sudo chown <user> <file>` changes user owner.
        -   Example: `sudo chown fgarcia access.txt`
    -   Syntax: `sudo chown :<group> <file>` changes group owner.
        -   Example: `sudo chown :security access.txt`
    -   Use a colon (:) before the group name to specify group ownership.

#### Best Practices

-   Use sudo responsibly—only grant elevated privileges when necessary.
-   Always double-check commands before running as root or with sudo to avoid accidental changes or deletions.
-   Consider deactivating accounts instead of deleting them to preserve data and track ownership.

## Module 4

### Introduction to Databases

#### What is a Database?

-   An organized collection of information or data.
-   Similar to a spreadsheet, but designed for multiple users and large amounts of data.
-   Can perform complex tasks and allow simultaneous access by many users.
-   Commonly used by security analysts to store and access information (e.g., login attempts, software updates, machine ownership).

#### Relational Databases

-   A structured type of database made up of related tables.
-   Each table contains:
    -   **Fields (columns):** Categories of information (e.g., employee_id, device_id, username).
    -   **Records (rows):** Individual entries with data for each field.
-   Multiple tables can be related to each other using keys.

#### Keys

-   **Primary key:**
    -   A column where every row has a unique, non-empty value.
    -   Uniquely identifies each record in a table (e.g., employee_id in an employees table).
    -   Only one primary key per table.
-   **Foreign key:**
    -   A column in one table that is a primary key in another table.
    -   Used to connect tables together.
    -   Can have duplicates and empty values.
    -   A table can have multiple foreign keys.

#### Example

-   Employees table: employee_id (primary key), username, department
-   Machines table: device_id (primary key), employee_id (foreign key)
-   The employee_id column links the machines to their assigned employees.

### Query Databases with SQL

#### What is SQL?

-   SQL (Structured Query Language) is a programming language for creating, interacting with, and requesting information from databases.
-   Used by nearly all relational databases (with minor differences between versions).

#### What is a Query?

-   A query is a request for data from a database table or a combination of tables.
-   SQL queries allow you to extract specific information quickly, even from very large datasets.

#### SQL in Security Work

-   Security analysts use SQL to retrieve and analyze logs (records of events in systems).
    -   Examples of logs: machine configurations, website visitors, user activity.
-   SQL helps:
    -   Find machines that aren't configured properly.
    -   Detect unusual patterns or potential malicious activity.
    -   Identify machines missing security patches.
    -   Determine optimal times for updates based on usage patterns.
-   SQL is also widely used for basic data analytics, supporting security decisions and investigations.

### SQL Filtering vs Linux Filtering

#### Accessing SQL

-   Many interfaces and versions of SQL exist; one way to access SQL is through the Linux command line.
    -   Example: Enter `sqlite3` in the terminal to access SQLite.
    -   After launching, commands entered are interpreted as SQL, not Linux commands.

#### Differences Between Linux and SQL Filtering

-   **Purpose:**

    -   Linux: Filters data in files and directories (e.g., searching files, managing permissions, handling processes).
    -   SQL: Filters data within a database (querying/manipulating tables, retrieving specific information).

-   **Syntax:**

    -   Linux: Uses various commands and options (e.g., `find`, `sed`, `cut`, `grep`). Syntax varies by tool.
    -   SQL: Uses standardized keywords and clauses (e.g., `SELECT`, `WHERE`, `JOIN`).

-   **Structure:**

    -   SQL: Highly structured—data is organized in tables with columns and rows, making it easy to select and analyze specific fields.
    -   Linux: More free-form—data is often printed as lines of text, less organized for column-based analysis.

-   **Joining Tables:**

    -   SQL: Can join multiple tables to combine related data for analysis.
    -   Linux: Cannot join data from different files in the same way; more limited for complex relationships.

-   **Best Uses:**
    -   SQL: Best for structured data stored in databases, especially when you need to join tables or analyze specific columns.
    -   Linux: Best for filtering and searching unstructured data in text files or logs that are not in a database format.
    -   Security analysts should know both methods, as some data will be in databases (use SQL) and some in text files (use Linux tools).

### Basic SQL Queries

#### SELECT and FROM

-   `SELECT` specifies which columns to return.
-   `FROM` specifies which table to query.
-   Syntax is similar to natural language (e.g., "select apples and bananas from the box").

#### Selecting Specific Columns

-   To return specific columns:
    -   Example: `SELECT employee_id, device_id FROM employees;`
    -   Returns only the employee_id and device_id columns from the employees table.
    -   Columns are separated by commas.

#### Selecting All Columns

-   Use an asterisk (`*`) to select all columns:
    -   Example: `SELECT * FROM employees;`
    -   Returns all columns from the employees table.

#### Syntax Tips

-   SQL keywords are not case-sensitive, but are often written in uppercase for readability.
-   End each SQL statement with a semicolon (`;`).

### Query a Database: ORDER BY

-   `ORDER BY` sequences the records returned by a query based on specified column(s).
-   Can sort in ascending (default) or descending order.

#### Sorting in Ascending Order

-   By default, `ORDER BY` sorts numbers from smallest to largest and text from A to Z.
-   Example:

```sql
SELECT customerid, city, country
FROM customers
ORDER BY city;
```

#### Sorting in Descending Order

-   Use `DESC` to sort in descending order (numbers: largest to smallest, text: Z to A).
-   Example:

```sql
SELECT customerid, city, country
FROM customers
ORDER BY city DESC;
```

#### Sorting Based on Multiple Columns

-   You can specify more than one column; SQL sorts by the first, then by the next for ties.
-   Example:

```sql
SELECT customerid, city, country
FROM customers
ORDER BY country, city;
```

### Basic Filters on SQL Queries

#### Filtering with WHERE

-   Filtering selects only data that matches a certain condition.
-   Use the `WHERE` clause to specify the filter condition in a SQL query.
-   Example: Return all records from the log_in_attempts table where country is USA:

```sql
SELECT * FROM log_in_attempts
WHERE country = 'USA';
```

#### Using Operators

-   Operators define the condition for filtering (e.g., `=`, `>`, `<`, `LIKE`).
-   Example: `country = 'USA'` returns records where the country column is exactly USA.

#### Pattern Matching with LIKE

-   Use `LIKE` with `WHERE` to filter for patterns (not just exact matches).
-   `%` is a wildcard for any number of characters.
-   Example: Return all offices that start with 'East':

```sql
SELECT * FROM employees
WHERE office LIKE 'East%';
```

-   Example: Return all log-in attempts where country starts with 'US' (matches both US and USA):

```sql
SELECT * FROM log_in_attempts
WHERE country LIKE 'US%';
```

#### Wildcards

-   Wildcards are special characters used in pattern matching with SQL's `LIKE` operator.
    -   `%` substitutes for any number of characters.
    -   `_` substitutes for exactly one character.
-   Wildcards can be placed before, after, or around a string to match different patterns.

| Pattern | Results that could be returned |
| ------- | ------------------------------ |
| 'a%'    | apple123, art, a               |
| 'a\_'   | as, an, a7                     |
| 'a\_\_' | ant, add, a1c                  |
| '%a'    | pizza, Z6ra, a                 |
| '\_a'   | ma, 1a, Ha                     |
| '%a%'   | Again, back, a                 |
| '_ a _' | Car, ban, ea7                  |

### Filter Dates and Numbers

#### Common Data Types

-   **String:** Ordered sequence of characters (letters, numbers, symbols). Example: username 'analyst10'.
-   **Numeric:** Numbers that can be used in mathematical operations. Example: count of log-in attempts.
-   **Date and Time:** Represents dates and/or times. Example: patch dates, log-in timestamps.

#### Comparison Operators

-   Used to filter numeric and date/time data.

    -   `=` : equals
    -   `<>` or `!=` : not equal to
    -   `>` : greater than (later than, for dates/times)
    -   `<` : less than (earlier than, for dates/times)
    -   `>=` : greater than or equal to
    -   `<=` : less than or equal to

-   Example: Find log-in attempts after 6 pm (18:00):

```sql
SELECT * FROM log_in_attempts
WHERE time > '18:00';
```

#### BETWEEN Operator

-   Filters for values within a range (numbers or dates).
-   Example: Find all patches installed between March 1st, 2021 and September 1st, 2021:

```sql
SELECT * FROM machines
WHERE OS_patch_date BETWEEN '2021-03-01' AND '2021-09-01';
```

### Filters with AND, OR, and NOT

#### AND Operator

-   Used to combine multiple conditions that must all be true.
-   Example: Select machines with both OS 1 and Email Client 1:

```sql
SELECT * FROM machines
WHERE operating_system = 'OS 1' AND email_client = 'Email Client 1';
```

#### OR Operator

-   Used to combine conditions where at least one must be true.
-   Example: Select machines with OS 1 or OS 3:

```sql
SELECT * FROM machines
WHERE operating_system = 'OS 1' OR operating_system = 'OS 3';
```

#### NOT Operator

-   Used to exclude records that match a condition.
-   Example: Select all machines that are NOT running OS 3:

```sql
SELECT * FROM machines
WHERE NOT operating_system = 'OS 3';
```

### Join Tables in SQL

#### Table and Column Reference Syntax

-   When working with multiple tables, specify the table and column as `table.column` (e.g., `employees.employee_id`).
-   This clarifies which table's column is being referenced, especially when columns have the same name in both tables.

#### INNER JOIN

-   An `INNER JOIN` returns rows where there is a match on a specified column in both tables.
-   Typically, a primary key in one table is matched to a foreign key in another.
-   Example: Join employees and machines tables on employee_id to get usernames, office locations, and operating systems:

```sql
SELECT employees.username, employees.office, machines.operating_system
FROM employees
INNER JOIN machines
    ON employees.employee_id = machines.employee_id;
```

-   The result includes only rows where employee_id exists in both tables.

#### NULL Values

-   `NULL` represents missing values (e.g., machines not assigned to any employee).
-   INNER JOIN will exclude rows where there is no match (i.e., where employee_id is NULL in one table).

### Types of Joins

#### LEFT JOIN

-   Returns all records from the left (first) table, and matching records from the right (second) table.
-   If there is no match, columns from the right table are filled with NULL.
-   Example:

```sql
SELECT employees.username, machines.operating_system
FROM employees
LEFT JOIN machines
    ON employees.employee_id = machines.employee_id;
```

#### RIGHT JOIN

-   Returns all records from the right (second) table, and matching records from the left (first) table.
-   If there is no match, columns from the left table are filled with NULL.
-   Example:

```sql
SELECT employees.username, machines.operating_system
FROM employees
RIGHT JOIN machines
    ON employees.employee_id = machines.employee_id;
```

#### FULL OUTER JOIN

-   Returns all records from both tables.
-   If there is no match in either table, columns from the missing side are filled with NULL.
-   Example:

```sql
SELECT employees.username, machines.operating_system
FROM employees
FULL OUTER JOIN machines
    ON employees.employee_id = machines.employee_id;
```

-   Use the same syntax as INNER JOIN, but replace with LEFT JOIN, RIGHT JOIN, or FULL OUTER JOIN as needed.

### Aggregate Functions

#### What Are Aggregate Functions?

-   Functions that perform a calculation over multiple data points and return a single result (not the actual data).
-   Commonly used to summarize or analyze data in a table.

#### Common Aggregate Functions

-   `COUNT`: Returns the number of rows (excluding NULL values).
-   `AVG`: Returns the average of numerical data in a column.
-   `SUM`: Returns the sum of numerical data in a column.

#### Syntax

-   Place the aggregate function after `SELECT`, with the column name in parentheses.
-   Example: Count total customers in the customers table:

```sql
SELECT COUNT(firstname)
FROM customers;
```

-   Example: Count customers from the USA only:

```sql
SELECT COUNT(firstname)
FROM customers
WHERE country = 'USA';
```

-   The same syntax applies for `AVG` and `SUM` (e.g., `SELECT AVG(age) FROM users;`).

# Certificate Completed

![Certificate proof in case I have to pay for it](image-1.png)
