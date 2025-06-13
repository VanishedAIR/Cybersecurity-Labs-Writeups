## Fawn Machine ([HackTheBox](https://app.hackthebox.com/starting-point))

### Task Solutions:

-   Task 1

    -   What does the 3-letter acronym FTP stand for?
    -   `file transfer protocol`

-   Task 2

    -   Which port does the FTP service listen on usually?
    -   Since I wasn't familiar before hand, I ran a `nmap -Pn [maching-ip-address]` scan and found out the ftp service was running on port `21` which with practice ill remember

-   Task 3

    -   FTP sends data in the clear, without any encryption. What acronym is used for a later protocol designed to provide similar functionality to FTP but securely, as an extension of the SSH protocol?
    -   Just like how http goes to https I tried ftps but didn't work so I tried `sftp` which worked

-   Task 4

    -   What is the command we can use to send an ICMP echo request to test our connection to the target?
    -   `ping`

-   Task 5

    -   From your scans, what version is FTP running on the target?
    -   Had to research how to see what ftp version is running on an ip address and it came out to running a `nmap -sV -p 21 [machine-ip-address]` scan which led to finding the version `vsftpd 3.0.3`

-   Task 6

    -   From your scans, what OS type is running on the target?
    -   From the previous scan I found it to be `unix`

-   Task 7

    -   What is the command we need to run in order to display the 'ftp' client help menu?
    -   Turns out it wasn't similar to most commands using -h instead I had to use the manual and filter it to client help using `man ftp | grep "help"` which showed `ftp -?`

-   Task 8

    -   What is username that is used over FTP when you want to log in without having an account?
    -   Looked at the HTB hint which said what are you when you don't have a name which was `anonymous`

-   Task 9

    -   What is the response code we get for the FTP message 'Login successful'?
    -   Using `ftp [machine-ip-address]` I was able to enter the ftp command line through which I entered anonymous as for the username and blank password which allowed for an anonymous log in and revealed the success code to be `230`

-   Task 10

    -   There are a couple of commands we can use to list the files and directories available on the FTP server. One is dir. What is the other that is a common way to list files on a Linux system.
    -   `ls`

-   Task 11

    -   What is the command used to download the file we found on the FTP server?
    -   I wasn't sure about this one so I used the `help` command in the ftp command line and read through all of them and `get` made the most sense and it worked

-   Submit Flag
    -   Submit root flag
    -   Using `ls` which revealed the flag.txt then using `get flag.txt` transferred the txt file to my Kali Linux Desktop through which I used `cat flag.txt` which revealed the flag to be `035db21c881520061c53e0536e44f815`
