## Meow Machine ([HackTheBox](https://app.hackthebox.com/starting-point))

### Task Solutions:

-   Task 1

    -   What does the acronym VM stand for?
    -   `Virtual Machine`

-   Task 2

    -   What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell.
    -   `Terminal`

-   Task 3

    -   What service do we use to form our VPN connection into HTB labs?
    -   `Openvpn`

-   Task 4

    -   What tool do we use to test our connection to the target with an ICMP echo request?
    -   `Ping`

-   Task 5

    -   What is the name of the most common tool for finding open ports on a target?
    -   `nmap`

-   Task 6

    -   What service do we identify on port 23/tcp during our scans?
    -   By using `nmap -Pn [machine ip-address]` I was able to identify the only open port running `telnet`

-   Task 7

    -   What username is able to log into the target over telnet with a blank password?
    -   I had to do a bit of searching on how to log in through telnet which could be done through `telnet [machine-ip-address]` and as for the password, I tried admin but that required a password so doing `root` bypassed the password and allowed me to access the system.

-   Submit Flag
    -   Submit root flag
    -   After doing ls while in the system, I located a file called flag.txt and using `cat flag.txt` it revealed the flag `b40abdfe23665f766f9c61ecba8a4c19`
