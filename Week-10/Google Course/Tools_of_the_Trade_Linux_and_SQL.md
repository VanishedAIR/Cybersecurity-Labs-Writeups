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

- When you press the power button, you're interacting with the hardware.
- The computer starts by activating a special chip:  
  - **BIOS** (Basic Input/Output System) on older systems  
  - **UEFI** (Unified Extensible Firmware Interface) on most systems built after 2007
- BIOS or UEFI loads the **bootloader**, which then starts the operating system.

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
- You click the app and enter numbers.
- The app sends your input to the OS.
- The OS tells the CPU to perform the calculation.
- The CPU returns the answer to the OS.
- The OS sends the answer back to the calculator app for display.

#### Why This Matters for Security

Understanding how the OS manages requests and hardware interactions helps security analysts trace the flow of events and identify where a security incident may have occurred.

### Request to the Operating System

#### Booting the Computer

When you turn on your computer, either a **BIOS** or **UEFI** chip is activated:
- **BIOS** (Basic Input/Output System) is found in older systems.
- **UEFI** (Unified Extensible Firmware Interface) is used in most modern computers and offers enhanced security features.

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
- You (the user) place an order (make a request through an application).
- The kitchen (OS) prepares your food (processes your request).
- You receive your meal (the application displays the result).
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

- **Resource Management:**  
  The OS decides how to allocate CPU time, memory, storage, and input/output bandwidth among all running programs and processes.
- **Balancing Demands:**  
  Some tasks (like running an antivirus scan) require more resources, while others (like using a calculator) need less. The OS balances these demands so the system doesn't get overloaded.
- **Memory Management:**  
  The OS keeps track of which programs are using which parts of memory, allocating and freeing up memory as needed.
- **Process Scheduling:**  
  Multiple programs may need the CPU at the same time. The OS schedules which process gets CPU time and for how long.
- **Task Manager:**  
  Tools like the Task Manager (in Windows) or Activity Monitor (in macOS) let you see which programs are running and how much memory and CPU they're using.

Most of this resource management happens behind the scenes, but it's essential for keeping your computer responsive and efficient.

### Virtualization Technology

#### What is a Virtual Machine?

A **virtual machine (VM)** is a software-based emulation of a physical computer. Virtualization is the process of using software to create virtual versions of physical resources, such as computers, servers, or networks. Virtual machines have their own virtual CPU, storage, and other hardware components, but these are simulated by software rather than existing physically.

- Multiple VMs can run on a single physical computer, sharing its resources (CPU, RAM, storage).
- Each VM operates independently and can run its own operating system.

**Example:**  
If a computer has 16GB of RAM, it could host three VMs, each with 4GB of RAM, while the host system uses the remaining 4GB.

---

#### Benefits of Virtual Machines

**Security:**
- VMs provide isolated environments (sandboxes) on the host machine.
- If one VM is compromised (e.g., by malware), it is isolated from the host and other VMs, reducing risk.
- Security professionals can safely analyze malware or suspicious files within a VM.

> **Note:**  
> While VMs are isolated, there is still a small risk that malware could escape the VM and affect the host system.

**Efficiency:**
- Multiple VMs can be run and managed on a single physical machine, making it easier to test, explore, and perform security tasks.
- Switching between VMs is quick and convenient, streamlining workflows.
- Analogy: Like a city bus carrying many passengers, VMs allow multiple "computers" to share one set of hardware resources, saving costs and energy.

---

#### Managing Virtual Machines

- **Hypervisor:**  
  Software that manages VMs and allocates physical resources to them.
  - **Kernel-based Virtual Machine (KVM):** An open-source hypervisor built into the Linux kernel, allowing users to create and manage VMs on Linux systems without extra software.

---

#### Other Forms of Virtualization

- **Virtual Servers:** Multiple virtual servers can be created from a single physical server to maximize hardware usage.
- **Virtual Networks:** Virtual networks can be set up to efficiently use the hardware of a physical network, allowing for flexible and scalable network configurations.

---

**Summary:**  
Virtualization enables efficient, flexible, and secure use of computing resources, making it a valuable tool for security professionals and IT operations.

### GUI versus CLI

The way users interact with the operating system is through a **user interface**. There are two main types:

#### Graphical User Interface (GUI)

- Uses icons, menus, and windows to help users manage tasks visually.
- Common in most operating systems, personal computers, and smartphones.
- Components often include a start menu, task bar, and desktop with icons and shortcuts.
- Users can click icons or search for files and applications by name.
- **Analogy:** Using a GUI is like ordering food from a restaurant—you choose from what's on the menu.

#### Command-Line Interface (CLI)

- Text-based interface where users type commands to interact with the OS.
- No icons or graphics—just a prompt for entering commands.
- More flexible and powerful than a GUI, allowing for advanced customization and automation.
- **Analogy:** Using a CLI is like cooking your own meal from scratch—you have more control and can combine ingredients however you want.

**Example:**  
If you need to move hundreds of JPEG files from one folder to another:
- With a GUI, you would manually select and move each file, which can be slow.
- With a CLI, you can use a single command to move all JPEG files at once, making the process much faster and more efficient.

**Key Point:**  
GUIs are user-friendly and great for everyday tasks, while CLIs offer more power and efficiency for complex or repetitive operations.

## Module 2

### Introduction to Linux

Linux is an **open-source operating system** that originated in the early 1990s. It was created by combining two major projects:
- **The Linux kernel** by Linus Torvalds, inspired by UNIX and designed to be open and accessible.
- **The GNU project** by Richard Stallman, which aimed to create free software for everyone.

By combining the GNU tools and the Linux kernel, a fully functional operating system was born. Linux is licensed under the GNU Public License, which means anyone can use, modify, and share it freely. This open philosophy has led to a large, active community and the creation of over 600 different Linux distributions (or "distros").

Linux is widely used in IT and cybersecurity. As a security analyst, you’ll often use Linux to:
- Examine system logs to investigate issues
- Manage access and authorization
- Run a variety of security tools

**Key Point:**  
Linux’s flexibility, strong community, and open-source nature make it a core part of modern computing and security work.

### Linux Architecture

The architecture of Linux is made up of several main components that work together to run the system:

- **User:**
    - The person interacting with the computer.
    - Linux supports multiple users at the same time (multi-user system), allowing several people to use the same resources simultaneously.
- **Applications:**
    - Programs that perform specific tasks, like text editors (e.g., Nano), web browsers, or calculators.
    - Applications are often installed using package managers—a tool that helps you install, manage, and remove software packages.
- **Shell:**
    - The command-line interface (CLI) that lets users communicate with the system by typing commands.
    - Acts as a translator between you and the computer, passing your commands to the kernel and displaying the results.
- **Filesystem Hierarchy Standard (FHS):**
    - The way Linux organizes files and directories, like a digital filing cabinet, so data can be easily found and managed.
    - Directories (also called folders) can contain files or other directories.
    - The FHS defines where different types of data are stored in the system.
- **Kernel:**
    - The core of the operating system.
    - Manages memory, processes, and communicates with the hardware using drivers.
    - Responsible for allocating resources and routing commands from applications, ensuring the system runs efficiently.
- **Hardware:**
    - The physical components of the computer.
    - **Internal hardware:**
        - **Motherboard:** The main circuit board connecting all components.
        - **CPU (Central Processing Unit):** Executes instructions from programs and performs general computing tasks.
        - **RAM (Random Access Memory):** Provides short-term memory for active tasks; data in RAM is lost when the computer is turned off.
        - **Hard Drive:** Stores programs and files for long-term access, even after the computer is powered down.
    - **Peripheral devices:**
        - Hardware that can be added or removed, such as monitors, printers, keyboards, and mice.

### Linux Distributions

Linux is highly customizable, and there are many different versions available—these are called distributions (or distros/flavors). Each distribution includes the Linux kernel, utilities, a package management system, and an installer. Understanding your distribution is important because it determines what tools and apps are available to you.

- **Distributions (distros):** Different versions of Linux, each with its own set of tools, preinstalled programs, and user interface.
- **Analogy:** The Linux kernel is like an engine, and distributions are like different types of vehicles built around that engine (cars, trucks, buses, airplanes, etc.), each serving different purposes.
- **Customization:** Because the kernel is open source, anyone can modify it to create a new distribution tailored to specific needs or preferences.
- **Parent distributions:** Some distros are "parents" to others. For example:
    - **Red Hat®** is the parent of CentOS.
    - **Slackware®** is the parent of SUSE®.
    - **Debian** is the parent of Ubuntu and Kali Linux™.
- **Choice:** Users often pick a distro based on their needs (e.g., security, stability, user interface) or personal preference—just like choosing a type of vehicle.

### Kali Linux

Kali Linux™ is a Debian-based distribution developed by Offensive Security, designed specifically for penetration testing and digital forensics. It comes with many pre-installed security tools.

- **Purpose:** Built for penetration testing (simulated attacks to find vulnerabilities) and digital forensics (analyzing data after incidents).
- **Best practice:** Always use Kali Linux in a virtual machine to avoid damaging your main system and to easily revert to previous states.
- **Pre-installed tools:**
    - **Metasploit:** Finds and exploits vulnerabilities.
    - **Burp Suite:** Tests web applications for weaknesses.
    - **John the Ripper:** Password cracking tool.
    - **tcpdump:** Command-line packet analyzer for capturing network traffic.
    - **Wireshark:** GUI tool for analyzing live or captured network traffic.
    - **Autopsy:** Forensic tool for analyzing hard drives and smartphones.
- **Use in security:** Popular among security professionals for both pen testing and forensic investigations due to its wide range of included tools.

### More Linux Distributions

- **Ubuntu:**
    - Open-source, user-friendly, and widely used in security and other industries.
    - Offers both CLI and GUI.
    - Debian-derived; comes with common applications and access to many more via package manager.
    - Large community support and resources.
    - Popular for cloud computing and often used in cloud-based cybersecurity work.
- **Parrot:**
    - Open-source, Debian-based, and focused on security.
    - Comes with pre-installed tools for penetration testing and digital forensics.
    - User-friendly with both GUI and CLI.
- **Red Hat® Enterprise Linux®:**
    - Subscription-based, built for enterprise use.
    - Not free; includes dedicated support for customers.
- **AlmaLinux:**
    - Community-driven, designed as a stable replacement for CentOS.
    - Drop-in compatible with CentOS 8, ensuring continued support for existing applications and configurations.

### Package Managers for Installing Applications

- **Package:** A piece of software that can be combined with others to form an application. Packages include all necessary files and dependencies (supplemental files needed to run the application).
- **Package manager:** A tool that helps users install, manage, and remove packages or applications. It also resolves dependency issues and keeps software up to date.
    - Always use the most recent version of a package for security and bug fixes.
- **Types of package managers:**
    - Different distributions use different package managers, often based on their parent distro.
    - **Debian-derived distros** (e.g., Kali Linux™, Ubuntu, Parrot): use package managers like **dpkg** (.deb files).
    - **Red Hat-derived distros** (e.g., CentOS): use **RPM** (.rpm files).
- **Package management tools:**
    - Tools that make it easier to manage packages from the shell.
    - **APT (Advanced Package Tool):** Used with Debian-based distros to manage, search, and install packages from the CLI.
    - **YUM (Yellowdog Updater Modified):** Used with Red Hat-based distros to manage, search, and install .rpm packages from the CLI.

### Introduction to the Shell

- The shell is the command-line interpreter that lets you communicate with the operating system through text commands.
- Provides the command-line interface (CLI) for interacting with the OS.
- Commands are instructions you enter to tell the computer what to do; the shell passes these to the kernel for execution.
- Acts as a language interpreter between you and your system, since humans don’t speak computer language or binary.
- While the OS can run without the shell, the shell is essential for users to access system features, run applications, and automate tasks.
- Allows you to combine commands and connect applications, making complex and automated operations possible.

### Input and Output in the Shell

- **Standard input (stdin):** Information entered by the user via the keyboard into the shell (e.g., typing a command).
    - Analogy: Like asking your friend a question in a conversation.
- **Standard output (stdout):** The result or response returned by the OS through the shell after executing a command.
    - Example: Typing `echo hello` and pressing enter returns `hello` as output.
    - Analogy: Like your friend answering your question.
- **Standard error (stderr):** Error messages returned by the OS through the shell when a command fails or is invalid.
    - Example: Typing `eco hello` (misspelling `echo`) returns an error message.
    - Analogy: Like your friend saying they can't answer your question.
- Communication with the shell involves:
    - Input (command from user)
    - Output (system response)
    - Error (system can't process the command)

