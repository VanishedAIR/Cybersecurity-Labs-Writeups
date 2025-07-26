## CodePath 6/4/25 Lecture

### Security Mindset

-   Built overtime, not overnight
-   Involves asking lots of questions like:

    -   How do you craft and environment that can withstand ever-evolving security threats?
    -   When an attack occurs, what will you do to address it?
    -   How will you ensure data privacy within your organization?

-   CIA triad is a model designed to guide policies for information security

    -   C (Confidentiality):
        -   Data is kept private, secret, and secure
        -   Authentication is required to view data
    -   I (Integrity):
        -   Data and security are always accurate and reliable
        -   Checksums are used to detect high-level data errors
    -   A (Availability):
        -   Systems remain available to users when needed
        -   Backups and redundancy keep systems online

-   Company Assets

    -   Organizational resources used to maintain operations and achieve organization's mission
    -   Critical assets are unique to each organization
    -   Several broad categories, such as:
        -   People, Information, Technology, Facility
        -   People:
            -   Employees, contractors, vendors, visitors
        -   Information:
            -   Data: Employee PII, proprietary information, documents
            -   Customer Information: Contact and purchase details
            -   Processes: Supply chain connections
            -   Systems: Data collection, alarms
        -   Technology
            -   IT systems, networks, communication
            -   At least one thing that is physical, but the boundary between Information and Technology is broad
        -   Facility
            -   Facilities: Buildings, land
            -   Equipment: Vehicles, machinery, other built in equipment as well

-   Vulnerabilities, Threats, and Risks

    -   Vulnerability: a weakness or flaw in a system, process, or set of controls that allows for exploitation
        -   CVE: Common Vulnerability Enumeration
    -   Threat: when an attacker has the opportunity, capability, and intent to exploit a vulnerability
        -   Affects an aspect of the CIA triad
    -   Risk: probable frequency and magnitude of loss

-   Threat Actors
    -   Any entity (person or organization) that is responsible for a cybersecurity incident
    -   Many types of threat actors
        -   Nation-State actor: government-sponsored groups (usually Russia, Iran, North Korea, or China)
        -   Hacktivist: promoting a political agenda or social change
        -   Cybercriminal: an entity perpetrating a crime for financial gain, retribution, etc.
        -   Insiders: an entity within an organization that deliberately or unknowingly causes an incident
-   Controls

    -   Any policy, procedure, or action designed to mitigate cybersecurity risk
    -   Designed to meet control objectives
        -   Ex: "Out controls provide reasonable assurance that access to db is restricted to authorized users"

-   Control Functions

    -   Preventative:
        -   Designed to stop cybersecurity incidents before they occur
    -   Detective:
        -   Designed to detect or alert to incidents after they occur
    -   Corrective:
        -   Designed to restore resources to their prior state after an incident occurs
    -   Physical:
        -   Tangible deterrents, such as fences, guards, and badges
    -   Technical:
        -   Hardware or software, such as antivirus software and authentication
    -   Administrative:
        -   Policies and guidelines, such as audits and data classifications

-   Mitigating Vulnerabilities

    -   Can use a knowledge graph of vulnerabilities and countermeasures, such as Mitre Att&ck and Mitre D3fend
    -   Stay current with the OWASP Top 10, an "awareness document" with the most critical risks to web application, and the versions they put out for specific platforms you use, like AI or Mobile Apps
    -   Review the CIS Critical Security Controls, including inventory, malware defense, etc.
    -   Scanners and automated tooling, which you can set up at various point sin your processes

-   Improving Cybersecurity
    -   NIST Framework for Improving CyberSecurity provides guidelines for organizations
    -   Helps assess and mitigate risk
    -   Identify -> Protect -> Detect -> Respond -> Recover

### Week 1 Project 1: Cyberchef CTF

-   Use Cyberchef and Googling to solve challenges
-   Required points 8, any mix of 1 point or 2 point questions out of the 16 total points available

-   The ones I solved:

    -   Challenge 1: Honesty is Best Policy (1 point)

        -   This aspect of the CIA triad is about ensuring that information is not altered accidentally or by entities unauthorized to make alterations.
        -   Answer: Integrity
        -   How to Solve: The I in the CIA triad is Integrity, meaning we need to make sure the information remains unchanged.

    -   Challenge 2: Lots of Jobs! (1 point)

        -   According to CyberSeek, which state has the highest numbers of cybersecurity job openings?
        -   CyberSeek.org
            -   Florida
            -   Virginia
            -   Texas
            -   California
        -   Answer: Virginia
        -   How to Solve: Go to the heat map and look at the darker blue color states, and compare the numbers.

    -   Challenge 3: Hostage (1 point)

        -   This kind of malicious software will encrypt the files on your hard drive and only provide a decryption key when you pay hackers a hefty fee, usually in cryptocurrency.
        -   (Solution is a type of malicious software, not the name of one particular virus.)
        -   Answer: Ransomware
        -   How to Solve: Ransomware stands for the fact that when a target machine is compromised, the attackers ask for ransom to avoid releasing or stealing the information on the machine.

    -   Challenge 5 (1pt):  Read Me
    
        -   Can you read me and find the "flag"? You need the README file for this challenge.
        -   Answer: flag{h3r3syerfl@g}
        -   How to Solve: If you look at the start of the document after importing the README.txt file into CyberChef input it says PDF which then led me to search for pdf tools in the search for cyberchef then i used extract files and it extracted to 4 zlib and one pdf file, and i opened the pdf file since it was first and it revealed the flag.

    -   Challenge 7 (2pts): Shifty

        -   What's the password? Qeb mxpptloa fp MibxpbZexkdbJb
        -   Answer: PleaseChangeMe
        -   How to Solve: Looked at the fact that it says shifty, and searched up “shift ciphers.” Caesar came up, so I used ROT13, which is a simple Caesar substitution cipher that rotates the character, and at amount 3, it reveals the password

    -   Challenge 8 (2pts): Encoded Message

        -   aXRnZXRzaGFyZGVyZnJvbWhlcmU= Hmmmmm. What's that equal sign at the end all about?
        -   Answer: itgetsharderfromhere
        -   How to Solve: searched up encoded message ending with an = sign, and it said Base64, so I searched it up and decoded it using From Base64 on cyberchef to get it.

    -   Challenge 10 (2pts): But are there eggs?
        -   The message below is encoded using a cipher developed by a 17th century lawyer, statesman, and philosopher.
        -   AAAAA AAAAB BAAAA AAAAA AAABA AAAAA AAABB AAAAA AAAAB BAAAA AAAAA
        -   Answer: ABRACADABRA
        -   How to Solve: Funny enough, the cipher is called the Bacon cipher decode which was found through the hint that it was created by a 17th century lawyer, so I just searched up 17th century lawyer cipher
