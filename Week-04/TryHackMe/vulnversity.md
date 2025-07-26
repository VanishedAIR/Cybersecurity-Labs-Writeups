# Vulnversity ([TryHackMe](https://tryhackme.com/room/vulnversity))

## Reconnaissance:

-   This was another review of nmap and port scanning aka recon the targe machine
-   Some nmap flags for review:

    -   `-sV` Attempts to determine the version of the services running
    -   `-p <x>` or `-p-` Port scan for port <x> or all scan all ports
    -   `-Pn` Disable host discover and scan for open ports
    -   `-A` Enables OS detection and version detection, and executes in-build script for further enum
    -   `-sC`Scan with the default nmap scripts
    -   `-v` Verbose mode aka more detail
    -   `-sU` UDP port scan
    -   `-sS` TCP SYN port scan

-   ![recon](Screenshot%202025-06-15%20201342.png)
-   From this we can see there are 6 open ports, and the machine is likely running Ubuntu as its operating system

## Locating directories using Gobuster:

-   Here we are using Gobuster, my first time using it, and it is a tool for brute-forcing URLs (directories and files), DNS subdomains, and virtual host names.
-   For this machine we are going ot brute-force the directories, according to the information provided
-   I personally used `gobuster dir -u http://10.10.91.35:3333 -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt` where `dir` I'm guessing is for finding directories, the `-u` is for target url specification, `-w` is the path to the worlist, in this case I used 2.3 small under dirbuster since I think it's going to be the fastest.
-   Other flags mentioned on THM are `-e` which prints the full URLs in the console, `-U` and `-P` which is for Username and Password for basic authentication, `-p <x>` proxy to use for requests, `-c <http cookies>` specify a cookie for simulating your auth.
-   Turns out even the small txt took a long while so I just stopped it at 50-ish percent
-   ![gobuster-scan](Screenshot%202025-06-15%20203108.png)
-   In this picture, we can see that images, css, js, fonts are normal to a website and I know this because I am pretty good at front-end dev, but internal seems worth to check out.
-   ![uplaod](Screenshot%202025-06-15%20203254.png)
-   Turns out the internal directory leads to a file upload, we may be able to do something with this, but I'm not sure so I'm just going to see what THM says

## Compromise the Webserver:

-   So I was definitely confused about a big portion of this but after looking at some youtube walkthrough, I found out I needed to get a extension called hack tools which would create a reverse shell php file that I would upload to the internal directory file upload.
-   ![reverse-shell-php](Screenshot%202025-06-15%20205743.png)
-   I was intercepting all requests through burp suite so when I pressed submit, I was told to sent it to intruder and add a `§` to the file extension and upload a txt config file containing extensions
-   ![burp-suite-intercepted](Screenshot%202025-06-15%20205801.png)
-   The result was a bunch of 200 HTTP status codes and upon inspecting all responses it said every extension is not allowed which according to the walkthrough is weird. ![200](Screenshot%202025-06-15%20205812.png)
-   Looking at the instructions further down the page, it says to rename the reverse shell file to have a `phtml` tag instead of `html`
-   Which ends up looking like: ![phtml-ss](Screenshot%202025-06-17%20174550.png)
-   Even in this inspecting the 200 status code responses it still said every extension is not allowed
-   Next, the instruction says to listen to the incoming connections using netcat through `nc -lvnp 1234` Then upload the shell and navigate to `http://10.10.141.237/internal/uploads/php-reverse-shell.phtml`
-   This ended up working as it provided us access to the target user's terminal as seen here: ![user-terminal](Screenshot%202025-06-17%20180539.png)
-   After going to the home directory then doing `ls` I was able to find the user's name, which was `bill` and cd into bill and then `ls` I found a txt file containing the flag `8bd7992fbe8a6ad22a63361004cfcedb`.

## Privilege Escalation

-   SUID (set owner userId upon execution) is a particular type of file permission given to a file.
-   SUID gives temporary permissions to a user to run the program/file with the permission of the file owner (rather than the user who runs it)
-   The binary file to change your password has the SUID bit set on it (/usr/bin/passwd). This is because to change your password, you will need to write to the shadowers file that you do not have access to; root does, so it has root privileges to make the right changes
-   ![password](https://tryhackme-images.s3.amazonaws.com/user-uploads/62a7685ca6e7ce005d3f3afe/room-content/62a7685ca6e7ce005d3f3afe-1716555383491)
-   Using an online command (`find / -perm -u=s -type f 2>/dev/null`) I found /bin/systemctl as a file on the system that stood out
-   I was asked to find the flag, however, it seems way too complex from the instructions I found online, so instead of just copy and pasting commands and not really standing them, I'm going to stop here.
