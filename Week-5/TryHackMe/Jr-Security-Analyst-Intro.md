# Junior Security Analyst Intro ([TryHackMe](https://tryhackme.com/room/jrsecanalystintrouxo))

-   Switching to a more defensive side of cybersecurity

## Task Summary:

-   Act as a Jr. Security Analyst and identify suspicious activity.
    -   Find the malicious IP address in the alerts.
        -   `221.181.185.159`
        -   ![logs](Screenshot%202025-06-21%20142111.png)
    -   There are many open-source databases out there like AbuseIPDB, Cisco Talos Intelligence, where you can perform a reputation and location check for the IP address. Most security analysts use these tools to aid them with alert investigations. You can also make the Internet safer by reporting the malicious IPs, for example, on AbuseIPDB.
        -   ![ip-address](Screenshot%202025-06-21%20142255.png)
    -   Escalate the event associated with the malicious IP address to the SOC Team Lead Will Griffin
    -   Block the IP address which reveals the flag to be `THM{UNTIL-WE-MEET-AGAIN}`

## A career as a Junior (Associate) Security Analyst:

-   The responsibilities for a Junior Security Analyst or Tier 1 Security Operations Center (SOC) Analyst include:

    -   Monitor and investigate the alerts (most of the time, it's a 24x7 SOC operations environment)
    -   Configure and manage the security tools
    -   Develop and implement basic IDS (Intrusion Detection System) signatures
    -   Participate in SOC working groups, meetings
    -   Create tickets and escalate the security incidents to the Tier 2 and Team Lead if needed

-   Required qualifications (most common):

    -   0-2 years of experience with Security Operations
    -   Basic understanding of Networking ( OSI model (Open Systems Interconnection Model) or TCP/IP model (Transmission Control Protocol/Internet Protocol Model)), Operating Systems (Windows, Linux), Web applications.
    -   Scripting/programming skills are a plus

-   Desired certification:

    -   [CompTIA Security+](https://www.comptia.org/en-us/certifications/security/)

-   As you progress and advance your skills as a Junior Security Analyst, you will eventually move up to Tier 2 and Tier 3.

-   An overview of the Security Operations Center (SOC) Three-Tier Model:
    -   ![3-tier](https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/7bf731bb9c58b0e9172a4788b761ad37.png)

## Security Operations Center (SOC):

-   The core function of a SOC (Security Operations Center) is to investigate, monitor, prevent, and respond to threats in the cyber realm 24/7 or around the clock.
-   Per McAfee's definition of a SOC, "Security operations teams are charged with monitoring and protecting many assets, such as intellectual property, personnel data, business systems, and brand integrity. As the implementation component of an organization's overall cyber security framework, security operations teams act as the central point of collaboration in coordinated efforts to monitor, assess, and defend against cyber attacks".
-   The number of people working in the SOC can vary depending on the organization's size.
-   What is included in the responsibilities of the SOC?
    -   ![responsibilities](https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/e2b97e6d9224da98764e21085190e54e.png)
-   Preparation and Prevention

    -   As a Junior Security Analyst, you should stay informed of the current cyber security threats (Twitter and [Feedly](https://feedly.com/i/welcome) can be great resources to keep up with the news related to Cybersecurity). It's crucial to detect and hunt threats, work on a [security roadmap](https://www.mcafee.com/enterprise/en-us/security-awareness/cybersecurity/creating-cybersecurity-strategy.html) to protect the organization, and be ready for the worst-case scenario.

    -   Prevention methods include gathering intelligence data on the latest threats, threat actors, and their [TTPs](https://www.optiv.com/explore-optiv-insights/blog/tactics-techniques-and-procedures-ttps-within-cyber-threat-intelligence) ([Tactics, Techniques, and Procedures](https://www.optiv.com/explore-optiv-insights/blog/tactics-techniques-and-procedures-ttps-within-cyber-threat-intelligence)). It also includes the maintenance procedures like updating the firewall signatures, patching the vulnerabilities in the existing systems, block-listing and safe-listing applications, email addresses, and IPs.

    -   To better understand the TTPs, you should look into one of the CISA's (Cybersecurity & Infrastructure Security Agency) alerts on APT40 (Chinese Advanced Persistent Threat). Refer to the following link for more information, https://us-cert.cisa.gov/ncas/alerts/aa21-200a.

-   Monitoring and Investigation

    -   A SOC team proactively uses [SIEM (Security information and event management)](https://www.fireeye.com/products/helix/what-is-siem-and-how-does-it-work.html) and [EDR (Endpoint Detection and Response)](https://www.mcafee.com/enterprise/en-us/security-awareness/endpoint/what-is-endpoint-detection-and-response.html) tools to monitor suspicious and malicious network activities.
    -   Imagine being a firefighter and having a multi-alarm fire - one-alarm fires, two-alarm fires, three-alarm fires; the categories classify the seriousness of the fire, which is a threat in our case.
    -   As a Security Analyst, you will learn how to prioritize the alerts based on their level: Low, Medium, High, and Critical. Of course, it is an easy guess that you will need to start from the highest level (Critical) and work towards the bottom - Low-level alert.
    -   Having properly configured security monitoring tools in place will give you the best chance to mitigate the threat.

    -   Junior Security Analysts play a crucial role in the investigation procedure.
    -   They perform triaging on the ongoing alerts by exploring and understanding how a certain attack works and preventing bad things from happening if they can. During the investigation, it's important to raise the question "How? When, and why?".
    -   Security Analysts find the answers by drilling down on the data logs and alerts in combination with using open-source tools, which we will have a chance to explore later in this path.

-   Response
    -   After the investigation, the SOC team coordinates and takes action on the compromised hosts, which involves isolating the hosts from the network, terminating the malicious processes, deleting files, and more.

## A day In the life of a Junior (Associate) Security Analyst:

-   To understand the job responsibilities for a Junior (Associate) Security Analyst, let look at what a day in the life of the Junior Security Analyst looks like and why this is an exciting career journey.

-   To be in the frontline is not always easy and can be very challenging as you will be working with various log sources from different tools that we will walk you through in this path.
-   You will get a chance to monitor the network traffic, including IPS (Intrusion Prevention System) and IDS (Intrusion Detection System) alerts, suspicious emails, extract the forensics data to analyze and detect the potential attacks, use open-source intelligence to help you make the appropriate decisions on the alerts.

-   One of the most exciting and rewarding things is when you are finished working on an incident and have managed to remediate the threat.
-   Incident Response might take hours, days, or weeks; it all depends on the scale of the attack: did the attacker manage to exfiltrate the data? How much data does the attacker manage to exfiltrate? Did the attacker attempt to pivot into other hosts? There are many questions to ask and a lot of detection, containment, and remediation to do. We will walk you through some fundamental knowledge that every Junior (Associate) Security Analyst needs to know to become a successful Network Defender.

-   The first thing almost every Junior (Associate) Security Analyst does on their shift is to look at the tickets to see if any alerts got generated.
