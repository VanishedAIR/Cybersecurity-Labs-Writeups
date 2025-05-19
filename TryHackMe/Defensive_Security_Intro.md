## Defensive Security Intro (TryHackMe)

### Task Summary:

- Pretend I am a SOC analyst. I see that the user's password has expired, then they made multiple wrong login attempts. Then they try to log in from a Unknown IP address which raises suspicions, and then log in from that unknown IP address. I reverse search the IP address to find out if its from a known threat and it was. I bring it up to the SOC team lead and am given permission to block the IP address.

- I found out there are many open-source db out there, like AbuseIPDB, and Cisco Talos Intelligence, where I can perform a reputation and location check on an IP address.

### Summary:

- In defensive security, the goal is to prevent intrusions from occurring and detecting intrusions when they occur, and responding properly.

- Some tasks related to defensive security include:

  - Train users about cyber security to prevent attacks
  
  - Have knowledge about the systems and devices needed to be protected
  
  - Ensure systems are updated and patched against and known vulnerabilities
  
  - Set up preventative security devices: firewall, intrusion prevention systems (IPS: detects and stops intrusions, usually deployed in front of the protected asset and block any potential threat from reaching their target). Firewalls control what network traffic goes inside and what can leave the system or network. IPS blocks network traffic matching present rules and attack signatures.
  
  - Set up proper logging and monitoring devices such that if a new unauthorized device appears on uor network, we should be able to detect it.

- Security Operations Center (SOC), a team of cyber security professionals that monitors the network and its systems to detect malicious cyber security events. Main areas of interest for a SOC include:

  - Vulnerability: Fix a known vulnerability by updating or patching the system. When fix is unavailable, necessary measures should be taken to prevent an attacker from exploiting it.

  - Policy Violation: Security policy is a set of rules required to protect the network and systems.

  - Unauthorized activity: Example situation where user's login and password are stolen, and if they attackers try to use them to log into the network, a soc must detect and block asap before further damage is done.

  - Network intrusions: Detect intrusions asap to prevent further damage.

- Threat Intelligence:

  - Collects information to help company better prepare against potential adversaries with the purpose bto achieve a threat-informed defense.

  - Intelligence needs data, which has to be collected, processed, and analyzed.
    - It can be collected from local sources such as network logs and public sources such as forums.
    - Data Processing arranges it into a format suitable for analysis.
    - Analysis phase seeks to find more info about the attackers and their motives, aiming to create a list of recommendations and actionable steps.

  - Learning about the adversaries is important to understand their tactics, techniques, and procedures.

- Digital Forensics and Incident Response (DFIR)

  - Digital Forensics focuses on:
    - File System: Analyzing a digital forensics image (low-level copy) of a system's storage reveals much information, such as installed programs, created files, partially overwritten files, and deleted files.
    - System memory: If malicious program was ran without saving to disk, then taking a forensic image (low-level copy) of the system's memory is the best way to analyze its contents and learn about the attack.
    - System logs: Client and server computer maintains a different log files about what is happening. It provides plenty of info about what happened on a system, even if attacker tries to clear their traces, some traces will remain.
    - Network logs: Logs of the network packets that have traversed a network would help answer more questions about whether an attack is occurring and what it entails.

- Incident Response:
  - Specifies the methodology that should be followed to handle an incident. The aim is to reduce damage and recover in the shortest time possible. Ideally you would develop a plan that is ready for incident response. 4 major phases of incident response process are:

    - Preparation: Ideally, various measures are put in place to prevent incidents from happening in the first place.
    - Detection and Analysis: Team has the necessary resources to detect any incident and analyze any detected incident further to learn about its severity.
    - Containment, Eradication, and Recovery: Once detected, stop it from affecting other systems, eliminate it, recover affected systems.
    - Post-Incident Activity: After a successful recovery, a report is produced to learn and prevent similar future incidents.

- Malware Analysis:
  - Malware includes many types:
    - Virus: Piece of code that attaches itself to a program designed to spread from one computer to another and works by altering, overwriting, and deleting files once infecting a computer. Causes the computer to become slow to unusable.
    - Trojan Horse: Shows itself as one desirable function but hides a malicious function underneath.
    - Ransomware: Encrypts files and demands a ransom payment to decrypt them.

  - Malware analysis aims to learn about such malicious programs by:
    - Static analysis works by inspecting the malicious program without running it. Requires knowledge of assembly language.
    - Dynamic analysis works by running the malware in controlled env and monitoring its behavior.
