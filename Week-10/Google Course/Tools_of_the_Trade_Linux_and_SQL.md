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