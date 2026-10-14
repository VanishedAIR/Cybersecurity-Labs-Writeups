# Cybersecurity Labs Writeups

A record of my cybersecurity learning through hands-on exercises, home labs and course notes. The repository spans web application security, networking, Linux, security operations and scripting, with material from TryHackMe, Hack The Box, PortSwigger, CodePath, Security Blue Team, LabEx and certification coursework.

The work is organized into **13 weekly folders**. Some entries document practical tests with screenshots and results; others are reference notes or partial walkthroughs. The sections below provide starting points without requiring you to browse every week.

## Selected Hands-On Work

| Area | Work documented | Writeup |
|---|---|---|
| Web application defense | Configured DVWA behind SafeLine over HTTPS; compared SQL injection with protection on and off, and checked a 3-requests-per-10-seconds rate limit in WAF logs. | [DVWA + SafeLine home lab](./Week-10/Firewall-Home-LAB/Lab-Procedures-and-Steps.md) |
| SOC alert investigation | Identified a suspicious IP in a simulated alert queue, checked its reputation, escalated the event and blocked the IP within the training scenario. | [Junior Security Analyst Intro](./Week-05/TryHackMe/Jr-Security-Analyst-Intro.md) |
| Reflected cross-site scripting | Tested how a search field handled HTML and completed the PortSwigger lab by executing a JavaScript alert through reflected input. | [Reflected XSS](./Week-04/Portswigger/XSS.md) |
| HTTP requests and APIs | Documented requests with curl and browser tools, covering headers, authentication, cookies, GET/POST requests and CRUD operations. | [HTB Web Requests](./Week-01/HackTheBox/Web-Requests/) |
| Enumeration and file-upload testing | Used Nmap, Gobuster and Burp Suite to investigate an upload endpoint; obtained a reverse shell and user flag. The writeup stops before privilege escalation. | [Vulnversity](./Week-04/TryHackMe/vulnversity.md) |
| Virtual-machine networking and remote access | Troubleshot connectivity between my Kali and Windows VMs and established a reverse TCP session using an existing Metasploit payload and handler. | [Metasploit VM exercise](./Week-03/metasploit.md) |

## Explore by Topic

### Security Operations and Network Analysis

- [Junior Security Analyst exercise](./Week-05/TryHackMe/Jr-Security-Analyst-Intro.md) - Simulated alert triage, IP reputation checking and escalation.
- [Wireshark introduction](./Week-08/LabEx/Wireshark.md) - Interface, packet panes, display filters, coloring rules and profiles.
- [Detection and Response notes](./Week-10/Google%20Course/Sound-the-Alarm-Detection-and-Response.md) - Incident response, packet captures, IDS signatures, Suricata logs and SIEM search concepts.
- [Networking fundamentals](./Week-01/Notes/Networking_Fundamentals.md) - OSI/TCP-IP models, network types and protocol data units.
- [TryHackMe networking notes](./Week-01/TryHackMe/Networking-Basics/) - Subnetting, ARP, DHCP, packets, frames, firewalls and VPNs.

### Web Security, Reconnaissance and Lab Exploitation

- [SafeLine/DVWA home lab](./Week-10/Firewall-Home-LAB/Lab-Procedures-and-Steps.md) - HTTPS reverse proxy, SQL injection protection and local rate-limit testing.
- [Burp Suite basics](./Week-02/Burp-Suite/Burp_Suite_Basics.md) - Intercepting a request and modifying its User-Agent header.
- [Nmap reference notes](./Week-02/TryHackMe/nmap.md) - Scan types, service discovery and Nmap Scripting Engine concepts.
- [Blue](./Week-04/TryHackMe/blue.md) - Nmap enumeration and an existing EternalBlue module; the writeup records where progress stopped.
- [Hack The Box Starting Point](./Week-04/HackTheBox/) - Meow and Fawn: service discovery, Telnet access and anonymous FTP.
- [HTTP and API exercises](./Week-01/HackTheBox/Web-Requests/) - Web requests, responses, authentication and API operations.

### Linux, Bash, Python and SQL

- [Linux fundamentals](./Week-01/TryHackMe/Linux-Fundamentals/) - Filesystem navigation, permissions, processes, scheduled tasks, packages and logs.
- [Bash fundamentals](./Week-08/Security-Blue-Team/Intro-To-Bash.md) - Shell commands, permissions, process management and pipes.
- [Bash text processing](./Week-09/Security-Blue-Team/Intro-To-Bash.md) - grep, awk and sed concepts and examples.
- [Linux and SQL coursework](./Week-10/Google%20Course/Tools_of_the_Trade_Linux_and_SQL.md) - Operating systems, Linux administration concepts and SQL.
- [Python coursework](./Week-11/Google%20Course/Automate-Cybersecurity-Tasks-With-Python.md) - Data types, functions, modules and regular expressions.

### Course and Certification Notes

- [CodePath: SSH keys and Git signing](./Week-04/CodePath/6-11-25-lecture.md) - Course notes and project instructions covering authentication, key generation and signed commits.
- [CodePath: passwords and authentication](./Week-05/Codepath/6-18-25-lecture.md) - Authentication concepts and the Password Crack-a-thon project brief.
- [Security+ preparation](./Week-06/CompTIA%20Security%2B%20%28SY0-701%29%20Cert%20Prep/) - Fundamental security concepts, controls and related study material.
- [Google: security risk management](./Week-09/Google-Course/Play_It_Safe_Manage_Security_Risks.md) - Frameworks, NIST RMF, risk and vulnerability management.
- [Google: assets, threats and vulnerabilities](./Week-10/Google%20Course/Assets_Threats_and_Vulnerabilities.md) - Asset protection, threats and vulnerability concepts.
- [ISC2: incident response and access control](./Week-12/ISC2/) - Incident response, business continuity, disaster recovery and access controls.
- [ISC2: network security and security operations](./Week-13/ISC2/) - Network defenses, logging, cryptography and operational security.

## How to Read This Repository

- **Practical writeups** describe the steps I took, the outputs I observed and, where available, screenshots.
- **Course notes** summarize learning material, commands and examples.
- **Partial exercises** retain the troubleshooting and stopping point rather than implying full completion.
- Source courses, rooms and tutorials are linked within the individual entries. Practical exercises use training environments or my own lab VMs.

## Organization

The root contains `Week-01` through `Week-13`. Each week contains its own platform, course or notes folders. Names and capitalization reflect the original learning sequence; the topic links above provide direct navigation.

## Contact

[LinkedIn](https://www.linkedin.com/in/vp1020/) | [Email](mailto:vanshp.1005@gmail.com)
