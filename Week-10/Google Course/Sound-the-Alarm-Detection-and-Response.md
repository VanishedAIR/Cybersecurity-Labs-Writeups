# Sound the Alarm: Detection and Response

## Module 1

### Introduction to the Incident Response Lifecycle

#### NIST CSF Core Functions

-   **Five core functions:** Identify, protect, detect, respond, and recover.
-   **Course focus:** Last three steps - detect, respond, and recover.
-   **Critical stages:** During incident response, analysts detect and respond to incidents and implement recovery actions.

#### NIST Incident Response Lifecycle

-   **Framework:** Another NIST framework with additional substeps dedicated to incident response.
-   **Process steps:**
    1. Preparation
    2. Detection and analysis
    3. Containment
    4. Eradication and recovery
    5. Post-incident activity
-   **Important note:** Lifecycle isn't linear process - it's a cycle.
-   **Overlap:** Steps can overlap as new discoveries are made.
-   **Purpose:** Provides blueprint for effectively responding to incidents.

#### Understanding Security Incidents

-   **NIST definition:** "An occurrence that actually or imminently jeopardizes, without lawful authority, the confidentiality, integrity, or availability of information or an information system; or constitutes a violation or imminent threat of violation of law, security policies, security procedures, or acceptable use policies."

#### Events vs. Security Incidents

-   **Key distinction:** All security incidents are events, but not all events are security incidents.
-   **Event definition:** Observable occurrence on a network, system, or device.

##### Example of an Event

-   **Scenario:** User attempts to log into email account but can't because they forgot password.
-   **Action:** User requests password reset and successfully changes password.
-   **Why it's an event:** Systems and applications log password reset requests.
-   **Evidence:** Logs provide evidence that something happened.
-   **Outcome:** Someone successfully requested password reset without violating security policies.

##### Example of a Security Incident

-   **Scenario:** Malicious actor (not rightful owner) successfully initiates password change request and changes account password.
-   **Classification:** Both an event and a security incident.
-   **Event aspect:** Observable occurrence.
-   **Incident aspect:** Malicious actor violated security policy to unlawfully access account.
-   **Key principle:** All security incidents are events, but not all events are security incidents.

#### Incident Investigation

-   **Analyst responsibility:** Handle and document evidence and findings like detectives.
-   **Investigation reveals:** Critical information about the five W's of an incident:
    -   **Who:** Triggered the incident
    -   **What:** Happened
    -   **When:** The incident took place
    -   **Where:** The incident took place
    -   **Why:** The incident occurred
-   **Documentation importance:** Essential during investigation and closure when writing final report.
-   **Method needed:** Document and reference information for easy access.

#### Incident Handler's Journal

-   **Definition:** Form of documentation used in incident response.
-   **Purpose:** Great way to document and reference incident information.
-   **Benefit:** Provides easy access to information when needed.

### Incident Response Teams

#### Team Collaboration

-   **Success requirement:** Doesn't happen in isolation.
-   **Team composition:** Both security and non-security professionals working together.
-   **Requirement:** Defined roles for effective collaboration.

#### CSIRTs (Computer Security Incident Response Teams)

-   **Definition:** Specialized group of security professionals trained in incident management and response.
-   **Goals:**
    -   Effectively and efficiently manage incidents
    -   Provide services and resources for response and recovery
    -   Prevent future incidents from occurring
-   **Shared responsibility:** Security is shared responsibility requiring cross-functional work.
-   **Collaboration:** Must work with other departments to share relevant information.

#### Cross-Functional Collaboration Examples

-   **Legal team involvement:** When incident results in breach of sensitive data (financial documents, PII).
-   **Public relations team:** When regulatory compliance requires public disclosure within certain timeframe.
-   **Purpose:** Coordinate efforts for public disclosure.

#### CSIRT Function Structure

##### Security Analyst

-   **Primary job:** Investigate security alerts to determine if incident has occurred.
-   **Responsibilities:**
    -   Determine criticality rating of incident
    -   Remediate incidents that don't require escalation
-   **Escalation:** Highly critical incidents escalated to technical lead.

##### Technical Lead

-   **Role:** Provides technical leadership.
-   **Function:** Guides security incidents through their lifecycle.
-   **Alternative title:** Can also be known as Ops lead.

##### Incident Coordinator

-   **Role:** Tracks and manages activities of CSIRT and other teams involved in response effort.
-   **Responsibilities:**
    -   Ensure incident response processes are followed
    -   Keep teams regularly updated on incident status

#### Team Variations

-   **Different names:**
    -   Incident Handling Team (IHT)
    -   Security Incident Response Team (SIRT)
-   **Focus variations:**
    -   Some teams solely dedicated to crisis management
    -   Others incorporated with SOC (Security Operations Center)
-   **Role variations:** Technical lead can also be known as Ops lead.
-   **Common goal:** All teams share same goal - incident management and response.

### Incident Response Plans

#### Importance of Preparedness

-   **Requirement:** Teams must respond quickly, efficiently, and effectively when incidents occur.
-   **Incident types:** Data breach, DDoS attack, ransomware.
-   **Potential impact:** Significant damage to organization.
-   **Regulatory requirement:** May require reporting incidents within certain timeframe.
-   **Crucial need:** Formal incident response plan for prepared and consistent process.

#### Plan Structure

-   **Basis:** Security plans consist of three basic elements - policies, standards, and procedures.
-   **Definition:** Document that outlines procedures to take in each step of incident response.
-   **Variation:** Response plans, like response teams, are not all the same.
-   **Customization:** Organizations tailor plans to meet unique requirements:
    -   Mission
    -   Size
    -   Culture
    -   Industry
    -   Structure

#### Implementation Examples

-   **Smaller organizations:** May include incident response plan in security plan.
-   **Other organizations:** May choose to have them as separate documents.

#### Common Elements

-   **Incident response procedures:** Step-by-step instructions on how to respond to incidents.
-   **System information:**
    -   Network diagrams
    -   Data flow diagrams
    -   Logging
    -   Asset inventory information
-   **Other documents:**
    -   Contact lists
    -   Forms
    -   Templates

#### Plan Improvement

-   **Reality:** Plans aren't perfect - always room to adjust and improve.
-   **Requirement:** Incident processes and procedures must be regularly reviewed and tested.
-   **Methods:**
    -   Tabletop exercises
    -   Simulations
-   **Benefits:**
    -   Ensure all team members are familiar with response plan
    -   Allow organizations to identify missing gaps in process
    -   Improve incident response plan
-   **Regulatory requirement:** Organizations may be required to complete specific types of exercises for regulatory reasons.

### The Value of Documentation

#### Definition and Purpose

-   **Definition:** Any form of recorded content used for specific purpose.
-   **Forms:** Audio, digital, handwritten instructions, and videos.
-   **Standard:** No set industry standard - organizations set their own practices.
-   **Purpose:** Provide instruction and guidance on specific topic.

#### Types of Documentation

-   **Familiar types:** From previous lessons:
    -   Playbooks
    -   Incident handler's journals
    -   Policies
    -   Plans
    -   Final reports
-   **Variation:** No industry standard means practices vary between organizations.
-   **Customization:** Organizations tailor practices according to:
    -   Their needs
    -   Legal requirements
-   **Flexibility:** May add, remove, or merge documentation types.

#### Documentation in Practice

-   **Product manual example:** Consulting manual for instructions on how to use product.
-   **Application:** Using documentation to solve issues.
-   **Playbook comparison:** In incident response, playbooks work similar to product manual.
-   **Playbook definition:** Manual that provides details about any operational action.

#### Effective vs. Ineffective Documentation

-   **Ineffective example:** Confusing product manual with unclear visuals and instructions.
-   **Result:** Unable to use documentation to solve issue.
-   **Effective documentation:** Reduces uncertainty and confusion.
-   **Critical importance:** During security incidents when tensions are high and urgent response required.

#### Documentation Requirements

-   **Professional responsibility:** Security professionals use and create documentation regularly.
-   **Essential qualities:** Documentation must be:
    -   Clear
    -   Consistent
    -   Accurate
-   **Goal:** Enable swift and decisive response by you and your team.

#### Documentation Tools

-   **Word processors:** Common way to document.
-   **Popular tools:**
    -   Google Docs
    -   OneNote
    -   Evernote
    -   Notepad++
-   **Ticketing systems:** Jira can document and track incidents.
-   **Other tools:**
    -   Google Sheets
    -   Audio recorders
    -   Cameras
    -   Handwritten notes

### Intrusion Detection Systems

#### IDS (Intrusion Detection System)

-   **Definition:** Application that monitors system and network activity and produces alerts on possible intrusions.
-   **Function:** Works similar to home intrusion sensors.
-   **Process:**
    -   Collects and analyzes system information for abnormal activities
    -   If unusual activity detected, sends alert to appropriate channels and personnel

#### IDS vs. IPS

-   **IDS:** Detects and alerts on intrusions.
-   **IPS (Intrusion Prevention System):** Has all IDS capabilities plus ability to take action to stop intrusions.

#### IPS Example

-   **Jewelry store analogy:** Window sensor detects shattered glass.
-   **Response:** Triggers steel roll-up door to automatically replace shattered window.
-   **Purpose:** Prevent unauthorized entry into store.
-   **IPS function:** Monitors system activity for intrusions and takes action to stop it.

#### Popular Tools

-   **Dual capability:** Many tools can perform both IDS and IPS functions.
-   **Popular tools:**
    -   Snort
    -   Zeek
    -   Kismet
    -   Sagan
    -   Suricata

### Overview of Detection Tools

#### Overview of IDS Tools

-   **Definition:** Application that monitors system activity and alerts on possible intrusions.
-   **Function:** Provides continuous monitoring of network events to help protect against security threats or attacks.
-   **Goal:** Detect potential malicious activity and generate alert once such activity is detected.
-   **Limitation:** Does not stop or prevent activity - security professionals investigate alert and act if necessary.

##### IDS Example

-   **Scenario:** Suspicious user login (unknown IP address logging into application or device at unusual time).
-   **Action:** IDS sends alert but does not stop or prevent further actions like blocking the login.
-   **Tools:** Zeek, Suricata, Snort®, Sagan.

#### Detection Categories

-   **Four types** security analysts should be familiar with:

##### True Positive

-   **Definition:** Alert that correctly detects presence of attack.

##### True Negative

-   **Definition:** State where there is no detection of malicious activity.
-   **Condition:** No malicious activity exists and no alert is triggered.

##### False Positive

-   **Definition:** Alert that incorrectly detects presence of threat.
-   **Scenario:** IDS identifies activity as malicious, but it isn't.
-   **Impact:** Inconvenience for security teams - spend time and resources investigating illegitimate alert.

##### False Negative

-   **Definition:** State where presence of threat is not detected.
-   **Scenario:** Malicious activity happens but IDS fails to detect it.
-   **Danger:** Security teams left unaware of legitimate attacks they can be vulnerable to.

#### Overview of IPS Tools

-   **Definition:** Application that monitors system activity for intrusive activity and takes action to stop the activity.
-   **Function:** Works similarly to IDS but also takes action to prevent activity and minimize effects.
-   **Example:** Can send alert and modify access control list on router to block specific traffic on server.
-   **Note:** Many IDS tools can also operate as IPS (Suricata, Snort, Sagan have both capabilities).

#### Overview of EDR Tools

-   **Definition:** Endpoint detection and response application that monitors endpoint for malicious activity.
-   **Installation:** Tools installed on endpoints.
-   **Endpoint definition:** Any device connected on network (computers, phones, tablets, etc.).

##### EDR Functionality

-   **Process:** Monitor, record, and analyze endpoint system activity to identify, alert, and respond to suspicious activity.
-   **Difference from IDS/IPS:** Collect endpoint activity data and perform behavioral analysis to identify threat patterns.
-   **Behavioral analysis:** Uses machine learning and artificial intelligence to analyze system behavior for malicious or unusual activity.
-   **Automation:** Can stop attacks without manual intervention of security professionals.

##### EDR Example

-   **Scenario:** EDR detects unusual process starting up on user's workstation that normally is not used.
-   **Action:** Can automatically block process from running.

##### EDR Tools

-   **Examples:** Open EDR®, Bitdefender™ Endpoint Detection and Response, FortiEDR™.

### Alert and Event Management with SIEM and SOAR Tools

#### SIEM Overview

-   **Definition:** Tool that collects and analyzes log data to monitor critical activities in organization.
-   **Function:** Provides security professionals with high-level overview of what goes on in their networks.

#### SIEM Analogy: Car Dashboard

-   **Car components:** Tires, lights, internal machinery under hood.
-   **Dashboard function:** Notifies about car's components status (tire pressure, battery voltage, fuel, door closure).
-   **Purpose:** Driver can take action to fix issues without inspecting each component.
-   **SIEM similarity:** Looks at data flows between all systems in network and analyzes them for real-time picture of potential threats.

#### SIEM Process

##### Step 1: Collect and Aggregate Data

-   **Data form:** Typically logs (record of all events that happened on given source).
-   **Data sources:** IDS/IPS, databases, firewalls, applications, and more.
-   **Aggregation:** All data from different sources gets centralized in one place.
-   **Volume:** Huge volume of raw unedited data can be collected.
-   **Relevance:** Not all collected data is relevant for security analysis purposes.

##### Step 2: Normalize Data

-   **Process:** Takes raw data and cleans it up by removing non-essential attributes.
-   **Result:** Only relevant information included.
-   **Benefit:** Creates consistency in log records.
-   **Use:** Helpful when searching for specific log information during incident investigation.

##### Step 3: Analyze Data

-   **Method:** Normalized data analyzed according to configured rules.
-   **Process:** SIEM analyzes normalized data against rule set to detect possible security incidents.
-   **Output:** Incidents categorized or reported as alerts for security analysts to review.

#### SOAR Overview

-   **Definition:** Security orchestration, automation, and response.
-   **Components:** Collection of applications, tools, and workflows.
-   **Function:** Uses automation to respond to security events.

#### SIEM vs. SOAR

-   **SIEM:** Collects, analyzes, and reports on security events for security analysts to review.
-   **SOAR:** Automates analysis and response to security events and incidents.
-   **Additional SOAR capability:** Can track and manage cases.
-   **Case management:** Multiple incidents can form a case, SOAR offers centralized view of all incidents.

## Module 2

### The Importance of Network Traffic Flows

#### Network Traffic Definition

-   **Network traffic:** Amount of data that moves across a network.
-   **Network data:** Data transmitted between devices on a network.
-   **Volume:** Can be huge depending on network size.
-   **Example:** Large multinational organization with thousands of employees sending/receiving emails simultaneously.

#### Understanding Normal vs. Abnormal Traffic

-   **Challenge:** With large volumes of traffic, how to distinguish normal from unusual behavior.
-   **Analogy:** Unexpected traffic during regular drive to work.
-   **Scenario:** Minor vehicle collision causing slowed traffic flow.
-   **Pattern recognition:** Based on commuting experience, we have expectations about traffic flows.
-   **Normal patterns:** Peak traffic like morning/evening rush hours.
-   **Abnormal patterns:** Traffic during off-peak times indicates something unexpected.

#### Network Traffic Analysis

-   **Process:** Understanding how data should flow across network.
-   **Benefit:** Develop understanding of expected network traffic flow.
-   **Detection:** By knowing what's normal, easily spot what's abnormal.
-   **Method:** Detect traffic abnormalities through observation.

#### Indicators of Compromise (IoC)

-   **Definition:** Observable evidence that suggests signs of potential security incident.
-   **Detection:** Through traffic observation to spot IoCs.

#### Data Exfiltration Example

-   **Definition:** Unauthorized transmission of data from a system.
-   **Purpose:** Attackers use to steal or leak data (usernames, passwords, intellectual property).
-   **Detection:** By observing network traffic for indicators of compromise.
-   **Sign:** Large volumes of outbound traffic leaving a host.
-   **Action:** Sign of possible data exfiltration requiring further investigation.

### Maintain Awareness with Network Monitoring

#### Network Communication Overview

-   **Network communication:** Can be noisy with events like sending email, streaming video, visiting websites.
-   **Network traffic:** Amount of data that moves across network (includes type like HTTP).
-   **Network data:** Data transmitted between devices on network.
-   **Importance:** Essential for maintaining situational awareness of any activity on network.
-   **Function:** By collecting and analyzing network traffic, organizations can detect suspicious network activity.

#### Know Your Network

-   **Network function:** Connect devices that communicate and exchange data using network protocols.
-   **Network communications provide:**
    -   Source and destination IP addresses
    -   Amount of data transferred
    -   Date and time
    -   More information
-   **Value:** Valuable for security professionals when developing baseline of normal/expected behavior.

##### Baseline Definition

-   **Definition:** Reference point used for comparison.
-   **Example:** Grocery amount for personal budget - baseline to identify patterns/changes in spending habits.
-   **Security application:** Help establish standard of expected/normal behavior for systems, devices, and networks.
-   **Benefit:** Knowing baseline of normal network behavior helps identify abnormal network behavior.

#### Monitor Your Network

-   **Process:** Once baseline determined, monitor network to identify deviations from baseline.
-   **Function:** Examining network components to detect unusual activities (large and unusual data transfers).
-   **Components monitored:** Network components that can be monitored to detect malicious activity.

##### Flow Analysis

-   **Flow definition:** Movement of network communications including information related to packets, protocols, and ports.
-   **Packets:** Travel to ports that receive and transmit communications.
-   **Ports:** Often associated with network protocols (e.g., port 443 commonly used by HTTPS).
-   **Malicious use:** Attackers can use protocols and ports not commonly associated for command and control (C2).
-   **C2 definition:** Techniques used by malicious actors to maintain communications with compromised systems.
-   **Example:** Using HTTPS protocol over port 8088 instead of commonly associated port 443.
-   **Requirement:** Organizations must know which ports should be open/approved and watch for mismatches.

##### Packet Payload Information

-   **Components:** Network packets contain components related to transmission (source/destination IP address, payload information).
-   **Payload information:** Actual data transmitted (often encrypted requiring decryption).
-   **Monitoring purpose:** Uncover unusual activity like sensitive data transmitting outside network.
-   **Indication:** Could indicate possible data exfiltration attack.

##### Temporal Patterns

-   **Time information:** Network packets contain information relating to time.
-   **Use:** Understanding time patterns.
-   **Example:** Company in North America experiences bulk traffic flows between 9 a.m. to 5 p.m. (baseline).
-   **Abnormal:** Large volumes of traffic outside normal hours considered off baseline requiring investigation.
-   **Benefit:** Organizations can promptly detect network intrusions and prevent them.

#### Protect Your Network

-   **NOC (Network Operations Center):** Organizational unit that monitors network performance and responds to network disruption.
-   **NOC vs SOC:**
    -   **SOC:** Focused on maintaining security through detection and response.
    -   **NOC:** Responsible for maintaining network performance, availability, and uptime.
-   **Security analyst role:** Monitor networks to identify indicators of compromise (IoC) and protect from threats/attacks.
-   **Requirement:** Must understand environment that network communications travel through to identify deviations.

#### Network Monitoring Tools

-   **Methods:** Can be automated or performed manually.

##### Intrusion Detection Systems (IDS)

-   **Function:** Monitor system activity and alert on possible intrusions.
-   **Detection:** Will detect and alert on deviations configured to detect.
-   **Common monitoring:** Content of packet payload to detect patterns associated with threats (malware, phishing attempts).

##### Network Protocol Analyzers (Packet Sniffers)

-   **Definition:** Tools designed to capture and analyze data traffic within network.
-   **Use:** Analyze network communications manually in detail.
-   **Examples:** tcpdump and Wireshark.
-   **Function:** Security professionals can record network communications through packet captures.
-   **Investigation:** Packet captures can be investigated to identify potentially malicious activity.

### Packets and Packet Captures

#### Packet Overview

-   **Data transmission:** When data is sent, it's divided into packets.
-   **Analogy:** Like addressed envelope in mail.
-   **Function:** Contain delivery information used to route to destination.
-   **Information includes:**
    -   Sender and receiver's IP address
    -   Type of packet being sent
    -   More information
-   **Value:** Provide lots of information about communications between devices over network.

#### Packet Components

-   **Multiple components** in a packet:

##### Header

-   **Contains:** Information like type of network protocol and port being used.
-   **Analogy:** Name and mailing address located on envelope.
-   **Network protocols:** Set of rules that determine transmission of data between devices on network.
-   **Ports:** Non-physical locations on computer that organize data transmission between devices on network.
-   **Additional info:** Contains packet's source and destination IP address.
-   **Note:** More header information explored in later section.

##### Payload

-   **Contains:** Actual data being delivered.
-   **Analogy:** Content of letter inside envelope.

##### Footer

-   **Function:** Signifies end of packet.

#### Observing Network Packets

-   **Challenge:** Packets are invisible but can be captured.
-   **Analogy:** Like scents being invisible but can be smelled.
-   **Tool:** Packet sniffers (network protocol analyzers).
-   **Purpose:** Capture and analyze data traffic within network.

#### Packet Sniffers

-   **Definition:** Tool designed to capture and analyze data traffic within network.
-   **Security analyst use:** Inspect packets for indicators of compromise.
-   **Function:** Grab detailed snapshot of packets traveling over network.

#### Packet Capture (P-cap)

-   **Definition:** File containing data packets intercepted from interface or network.
-   **Analogy:** Like intercepting envelope in mail.
-   **Usefulness:** Incredibly useful during incident investigation.
-   **Benefit:** Access to communications happening between devices over network.
-   **Purpose:** Observe network interactions and build storyline to determine what exactly happened.

### Data Exfiltration Attacks

#### Initial Access

-   **Requirement:** Attackers need to gain initial access into network and computer system before data exfiltration.
-   **Method:** Social engineering attack like phishing.
-   **Process:** Tricks people into disclosing sensitive data.
-   **Technique:** Send phishing emails with attachments or links that trick target into entering credentials.
-   **Result:** Attacker successfully gains access to device.

#### Lateral Movement (Pivoting)

-   **Goal:** Maintain access in environment and avoid detection for as long as possible.
-   **Tactic:** Lateral movement or pivoting.
-   **Process:** Spend time exploring network to expand and maintain access to other systems.
-   **Activity:** Scope out environment to identify valuable assets.

#### Target Assets

-   **Valuable assets attackers seek:**
    -   Sensitive data like proprietary code
    -   Personally identifiable information (names, addresses)
    -   Financial records
-   **Search locations:**
    -   Network file shares
    -   Intranet sites
    -   Code repositories
    -   More locations

#### Data Preparation

-   **Process:** After identifying valuable assets, attackers collect, package, and prepare data for exfiltration.
-   **Method:** Reduce data size to help hide stolen data and bypass security controls.

#### Data Exfiltration

-   **Final step:** Exfiltrate data to attacker's destination of choice.
-   **Methods:** Many ways to do this.
-   **Example:** Email stolen data to themselves using compromised email account.

#### Defense Strategies

##### Prevent Attacker Access

-   **First line:** Security teams must prevent attacker access.
-   **Methods:** Many methods to protect network from phishing attempts.
-   **Example:** Requiring users to use multi-factor authentication.

##### Monitor Network Activity

-   **Challenge:** Attackers can remain unnoticed for a while.
-   **Requirement:** Security teams must monitor network activity to identify suspicious activity indicating compromise.
-   **Example:** Multiple user logins from IP addresses outside network should be investigated.

##### Asset Protection

-   **Earlier learning:** How to identify, classify, and protect assets using asset inventories and security controls.
-   **Policy requirement:** All assets should be cataloged in asset inventory as part of organization's security policy.
-   **Security controls:** Appropriate controls should be applied to protect assets from unauthorized access.

##### Detect and Stop Exfiltration

-   **Requirement:** If data exfiltration attack is successful, security teams must detect and stop it.
-   **Detection method:** Indicators of unusual data collection identified through network monitoring.
-   **Indicators include:**
    -   Large internal file transfers
    -   Large external uploads
    -   Unexpected file writes
-   **Tool:** SIEM tools can detect and alert on these activities.
-   **Response:** Once alert sent, security teams investigate and stop attack from continuing.

##### Stopping the Attack

-   **Methods:** Many ways to stop attack like this.
-   **Example:** Once unusual activity identified, block IP addresses associated with attacker using firewall rules.

### Learn More About Packet Captures

#### Header

-   **Location:** Packets begin with most essential component - the header.
-   **Multiple headers:** Packets can have several headers depending on protocols used:
    -   Ethernet header
    -   IP header
    -   TCP header
    -   More headers
-   **Function:** Provide information used to route packets to destination.
-   **Information includes:**
    -   Source and destination IP addresses
    -   Packet length
    -   Protocol
    -   Packet identification numbers
    -   More information

#### Payload

-   **Location:** Directly follows header.
-   **Contains:** Actual data being delivered.
-   **Example:** Uploading image to website - payload would be the image itself.

#### Footer

-   **Alternative name:** Also known as trailer.
-   **Location:** Located at end of packet.
-   **Ethernet protocol:** Uses footers to provide error-checking information to determine if data corrupted.
-   **Display limitation:** Ethernet network packets analyzed might not display footer information due to network configurations.
-   **Note:** Most protocols (like Internet Protocol/IP) do not use footers.

#### Network Protocol Analyzers

-   **Definition:** Tools designed to capture and analyze data traffic within network.
-   **Examples:** tcpdump, Wireshark, TShark.
-   **Uses beyond security:**
    -   Collect network statistics (bandwidth, speed)
    -   Troubleshoot network performance issues (slowdowns)
-   **Malicious use:** Malicious actors can use to capture packets containing sensitive data (account login information).

#### How Network Protocol Analyzers Work

-   **Components:** Use both software and hardware capabilities.
-   **Process:**

##### Step 1: Packet Collection

-   **Method:** Packets collected from network via Network Interface Card (NIC).
-   **NIC definition:** Hardware that connects computers to network (like router).
-   **Default behavior:** NICs only listen to network traffic addressed to them.
-   **Requirement:** To capture all network traffic, NIC must be switched to mode with access to all visible network data packets.
-   **Modes:**
    -   **Wireless interfaces:** Often called monitoring mode.
    -   **Other systems:** May be called promiscuous mode.
-   **Limitation:** Mode enables access to all visible network data packets but doesn't help access all packets across network.
-   **Positioning:** Network protocol analyzer must be positioned in appropriate network segment to access all traffic between different hosts.

##### Step 2: Data Conversion

-   **Collection format:** Network traffic collected in raw binary format.
-   **Binary format:** Consists of 0s and 1s, not easy for humans to interpret.
-   **Conversion:** Network protocol analyzer takes binary and converts to human-readable format.
-   **Benefit:** Analysts can easily read and understand information.

##### Security Note

-   **Risk:** Enabling promiscuous mode can expose device to potential attacks.
-   **Reason:** Allows sensitive information like passwords and confidential data to be captured.
-   **Requirement:** Use tools operating in promiscuous mode responsibly and with caution.

#### Capturing Packets

-   **Definition:** Packet sniffing is practice of capturing and inspecting data packets across network.
-   **P-cap:** File containing data packets intercepted from interface or network.
-   **Analysis:** Can be viewed and further analyzed using network protocol analyzers.
-   **Filtering:** Can filter packet captures to display only relevant information (e.g., packets from specific IP address).
-   **Legal note:** Using network protocol analyzers to intercept and examine private network communications without permission is illegal in many places.

#### P-cap File Formats

-   **Variety:** Come in many formats depending on packet capture library used.
-   **Differences:** Each format has different uses, network tools may use/support specific formats by default.

##### Libraries and Formats

-   **Libpcap:** Packet capture library for Unix-like systems (Linux, MacOS®).
    -   **Usage:** Tools like tcpdump use as default packet capture file format.
-   **WinPcap:** Open-source packet capture library for Windows operating systems.
    -   **Status:** Considered older file format, not predominantly used.
-   **Npcap:** Library designed by port scanning tool Nmap.
    -   **Usage:** Commonly used in Windows operating systems.
-   **PCAPng:** Modern file format that can simultaneously capture packets and store data.
    -   **Name origin:** "ng" stands for "next generation."
    -   **Capability:** Ability to do both explains the "ng."

##### Pro Tip

-   **Practice:** Analyzing home network can be good way to practice using these tools.

### Overview of tcpdump

#### Network Protocol Analyzers

-   **Security analyst use:** Use network protocol analyzers to help defend against network intrusions.
-   **Network protocol analyzer:** Tool designed to capture and analyze data traffic within network.
-   **Packet sniffing:** Practice of capturing and inspecting data packets across network.
-   **Purpose:** Learn more about tcpdump for capturing and viewing network communications.

#### What is tcpdump?

-   **Definition:** Command-line network protocol analyzer.
-   **CLI:** Text-based user interface that uses commands to interact with computer.
-   **Function:** Used to capture network traffic.
-   **Output:** Traffic can be saved to packet capture (p-cap) file.
-   **P-cap file:** File containing data packets intercepted from interface or network.
-   **Benefits:** Can be accessed, analyzed, or shared at later time.
-   **Uses:** Troubleshooting network issues to identifying malicious activity.
-   **Installation:** Pre-installed in many Linux distributions.
-   **Compatibility:** Can be installed on other Unix-based operating systems (macOS®).

##### Note on Encryption

-   **Common issue:** Network traffic often encrypted (data encoded and unreadable).
-   **Requirement:** Inspecting network packets might require decrypting data using appropriate private keys.

#### Capturing Packets with tcpdump

##### Privilege Requirements

-   **Requirement:** Need administrator-level privileges to capture network traffic.
-   **Options:** Either logged in as root user or have ability to use sudo command.
-   **Reason:** Like many other packet sniffing tools.

##### tcpdump Syntax

-   **Command format:** `sudo tcpdump [-i interface] [option(s)] [expression(s)]`
-   **sudo tcpdump:** Begins running tcpdump using elevated permissions as sudo.
-   **-i parameter:** Specifies network interface to capture network traffic.
-   **Interface requirement:** Must specify network interface to capture from.
-   **Example:** `-i any` sniffs traffic from all network interfaces on system.
-   **option(s):** Optional and provide ability to alter execution of command.
-   **expression(s):** Way to further filter network traffic packets to isolate network traffic.

##### Note on Interface Identification

-   **Requirement:** Must identify which network interface to use before capturing.
-   **Method:** Use `-D` flag to list network interfaces available on system.

#### Options

##### Overview

-   **Function:** Apply options (flags) to end of commands to filter network traffic.
-   **Short options:** Abbreviated with hyphen and single character (e.g., `-i`).
-   **Long options:** Spelled out using double hyphen (e.g., `--interface`).
-   **Total options:** Over fifty options available.
-   **Reference:** Can explore using manual page.

##### Important Notes

-   **Case sensitivity:** Options are case sensitive.
-   **Example:** Lowercase `-w` is separate option with different use than uppercase `-W`.
-   **Spacing:** Short options can be written with or without space between option and value.
-   **Example:** `sudo tcpdump -i any -c 3` and `sudo tcpdump -iany -c3` are equivalent.

##### Essential Options

###### -w (Write)

-   **Function:** Write or save sniffed network packets to packet capture file.
-   **Benefit:** Can refer to saved file for later analysis.
-   **Example:** `sudo tcpdump -i any -w packetcapture.pcap`

###### -r (Read)

-   **Function:** Read packet capture file by specifying file name as parameter.
-   **Example:** `sudo tcpdump -r packetcapture.pcap`

###### -v (Verbose)

-   **Function:** Control how much packet information tcpdump prints out.
-   **Default:** tcpdump will not print out all packet information.
-   **Levels:** Three levels of verbosity (-v, -vv, -vvv).
-   **Usefulness:** Helpful when looking for packet information like IP header field details.
-   **Example:** `sudo tcpdump -r packetcapture.pcap -v`

###### -c (Count)

-   **Function:** Control how many packets tcpdump will capture.
-   **Examples:**
    -   `-c 1`: Only print out one single packet
    -   `-c 10`: Print out 10 packets
-   **Example command:** `sudo tcpdump -i any -c 3`

###### -n (No Name Resolution)

-   **Default behavior:** tcpdump performs name resolution.
-   **Process:** Automatically converts IP addresses to names and resolves ports to commonly associated services.
-   **Problem:** tcpdump isn't always accurate in name resolution.
-   **Example issue:** Port 80 automatically translated to HTTP, but port 80 isn't always HTTP.
-   **Security concern:** Reverse DNS lookup can alert attackers to investigation.
-   **Solution:** `-n` flag disables automatic mapping of numbers to names.
-   **Best practice:** Considered best practice when sniffing or analyzing traffic.
-   **Variations:**
    -   `-n`: Will not resolve hostnames
    -   `-nn`: Will not resolve both hostnames or ports
-   **Example:** `sudo tcpdump -r packetcapture.pcap -v -n`

##### Pro Tip on Combining Options

-   **Combination:** Can combine options together (e.g., `-vn`).
-   **Limitation:** If option accepts parameter right after it (like `-c 1` or `-r capture.pcap`), can't combine other options to it.

#### Expressions

##### Overview

-   **Function:** Filter expressions in tcpdump commands (optional but helpful).
-   **Use:** Many ways to use filter expressions during packet analysis.
-   **Purpose:** Specifically search for network traffic by protocol.

##### Protocol Filtering

-   **Method:** Use filter expressions to isolate network packets.
-   **Example:** Filter to find only IPv6 traffic using `ip6` filter expression.

##### Boolean Operators

-   **Operators:** `and`, `or`, `not`.
-   **Use:** Further filter network traffic for specific IP addresses, ports, and more.
-   **Example:** `sudo tcpdump -r packetcapture.pcap -n 'ip and port 80'`

##### Pro Tips

-   **Quotes:** Can use single or double quotes to ensure tcpdump executes all expressions.
-   **Parentheses:** Can use parentheses to group and prioritize different expressions.
-   **Complex commands:** Grouping expressions helpful for complex or lengthy commands.
-   **Example:** `ip and (port 80 or port 443)` prioritizes filters in parentheses before filtering for IPv4.

#### Interpreting Output

##### Output Format

-   **Process:** Once command runs to capture packets, tcpdump prints output as sniffed packets.
-   **Format:** One line of text for each packet.
-   **Timestamp:** Each line begins with timestamp.

##### Example Command and Output

-   **Command:** `sudo tcpdump -i any -v -c 1`
-   **Function:** Capture packets on any network interface.
-   **Options:**
    -   `-v`: Prints packet with detailed information
    -   `-c 1`: Prints out only one packet

### Reexamine the Fields of a Packet Header

#### Internet Layer Overview

-   **Function:** Accepts and delivers packets for the network.
-   **Protocol:** Internet Protocol operates as foundation for all communications on internet.
-   **Responsibility:** Making sure packets reach their destinations.
-   **Analogy:** Operates like mail courier delivering envelope.
-   **Process:** Uses information in packet header (like IP addresses) to determine best available route for packets.

#### IP Packet Headers

-   **Content:** Headers contain data fields essential to transfer of data to intended destination.
-   **Variation:** Different protocols use different headers.
-   **IP versions:**
    -   **IPv4:** Foundation of internet communications.
    -   **IPv6:** Most recent version of Internet Protocol.
-   **Note:** IPv4 and IPv6 headers differ but contain similar fields with different names.
-   **Focus:** IPv4 still most widely used, so we'll focus on IPv4 header fields.

#### IPv4 Header Fields

##### Version Field

-   **Function:** Specifies which version of IP is being used (IPv4 or IPv6).
-   **Analogy:** Like different classes of mail (priority, express, or regular).

##### IHL (Internet Header Length)

-   **Function:** Specifies length of IP header plus any options.

##### ToS (Type of Service)

-   **Function:** Tells if certain packets should be treated with different care.
-   **Analogy:** Like fragile sticker on mailed package.

##### Total Length Field

-   **Function:** Identifies length of entire packet, including headers and data.
-   **Analogy:** Like dimensions and weight of envelope.

##### Fragmentation Fields

-   **Three fields:** Identification, Flags, and Fragment Offset.
-   **Purpose:** Deal with information related to fragmentation.
-   **Fragmentation:** When IP packet gets broken up into chunks, transmitted over wire, and reassembled at destination.
-   **Function:** Specify if fragmentation used and how to reassemble broken packets in correct order.
-   **Analogy:** Like mail traveling through multiple routes (mailboxes, processing facilities, airplanes, mail trucks).

##### TTL (Time to Live)

-   **Function:** Determines how long packet can live before it gets dropped.
-   **Purpose:** Without this field, packets could loop through routers endlessly.
-   **Analogy:** Like tracking information providing details about envelope's expected delivery date.

##### Protocol Field

-   **Function:** Specifies protocol used by providing value corresponding to protocol.
-   **Example:** TCP represented by 6.
-   **Analogy:** Like including number of house in postal address.

##### Header Checksum

-   **Function:** Stores value called checksum used to determine if any errors occurred in header.

##### Address Fields

-   **Source Address:** Specifies source IP address.
-   **Destination Address:** Specifies destination IP address.
-   **Analogy:** Like sender and receiver's contact information found on envelope.

##### Options Field

-   **Status:** Not required, commonly used for network troubleshooting rather than common traffic.
-   **Effect:** If used, header length increases.
-   **Analogy:** Like purchasing postal insurance for envelope.

##### Data Section

-   **Location:** At end of packet header.
-   **Content:** Packet's data resides here.
-   **Analogy:** Like text in email message.

### Investigate Packet Details

#### IPv6

-   **Adoption:** Increasing because of large address space.
-   **Header fields:** Eight fields in header.

##### IPv6 Header Fields

-   **Version:** Indicates IP version (IPv6 for IPv6 header).
-   **Traffic Class:** Similar to IPv4 Type of Service field.
    -   **Function:** Provides information about packet's priority or class to help with packet delivery.
-   **Flow Label:** Identifies packets of a flow.
    -   **Flow definition:** Sequence of packets sent from specific source.
-   **Payload Length:** Specifies length of data portion of packet.
-   **Next Header:** Indicates type of header that follows IPv6 header (such as TCP).
-   **Hop Limit:** Similar to IPv4 Time to Live field.
    -   **Function:** Limits how long packet can travel in network before being discarded.
-   **Source Address:** Specifies source address of sender.
-   **Destination Address:** Specifies destination address of receiver.

#### Wireshark

##### Display Filters

-   **Function:** Let you apply filters to packet capture files.
-   **Usefulness:** Helpful when inspecting packet captures with large volumes of information.
-   **Purpose:** Help find specific information most relevant to investigation.
-   **Filtering options:** Can filter packets based on protocols, IP addresses, ports, and virtually any other property found in packet.
-   **Focus:** Display filtering syntax and filtering for protocols, IP addresses, and ports.

##### Comparison Operators

-   **Use:** Different comparison operators to locate specific header fields and values.
-   **Expression:** Can be expressed using either abbreviations or symbols.
-   **Example:** `ip.src == 8.8.8.8` is identical to `ip.src eq 8.8.8.8`.

##### Comparison Operators Table

-   **Equal:** `==` or `eq`
-   **Not equal:** `!=` or `ne`
-   **Greater than:** `>` or `gt`
-   **Less than:** `<` or `lt`
-   **Greater than or equal to:** `>=` or `ge`
-   **Less than or equal to:** `<=` or `le`

##### Pro Tip

-   **Combination:** Can combine comparison operators with Boolean logical operators like `and` and `or` to create complex display filters.
-   **Parentheses:** Can be used to group expressions and prioritize search terms.

##### Contains Operator

-   **Function:** Used to filter packets that contain exact match of string of text.
-   **Example:** Filter that displays all HTTP streams matching keyword "moved".

##### Matches Operator

-   **Function:** Used to filter packets based on regular expression (regex) specified.
-   **Regex definition:** Sequence of characters that forms a pattern.
-   **Note:** More about regular expressions explored later in program.

##### Filter Toolbar

-   **Function:** Apply filters to packet capture using Wireshark's filter toolbar.
-   **Example:** `dns` filter means Wireshark will only display packets containing DNS protocol.

#### Filtering Methods

##### Filter for Protocols

-   **Method:** One of simplest ways to use display filters.
-   **Process:** Simply enter name of protocol to filter.
-   **Example:** To filter for DNS packets, type `dns` in filter toolbar.
-   **Protocols you can filter for:**
    -   dns
    -   http
    -   ftp
    -   ssh
    -   arp
    -   telnet
    -   icmp

##### Filter for IP Address

-   **Method:** Use display filters to locate packets with specific IP address.
-   **General filter:** `ip.addr == [IP address]`
-   **Source filter:** `ip.src == [source IP address]`
-   **Destination filter:** `ip.dst == [destination IP address]`
-   **Examples:**
    -   `ip.addr == 172.21.224.2`
    -   `ip.src == 10.10.10.10`
    -   `ip.dst == 4.4.4.4`

##### Filter for MAC Address

-   **Method:** Filter packets according to Media Access Control (MAC) address.
-   **MAC address:** Unique alphanumeric identifier assigned to each physical device on network.
-   **Example:** `eth.addr == 00:70:f4:23:18:c4`

##### Filter for Ports

-   **Method:** Filter packets based on port numbers.
-   **Usefulness:** Helpful when isolating specific types of traffic.
-   **DNS example:** DNS traffic uses TCP or UDP port 53.
-   **Examples:**
    -   UDP port: `udp.port == 53`
    -   TCP port: `tcp.port == 25`

##### Follow Streams

-   **Function:** Wireshark feature that lets you filter for packets specific to protocol and view streams.
-   **Stream definition:** Exchange of data between devices using protocol.
-   **Benefit:** Wireshark reassembles data transferred in stream in way that's simple to read.

### Packet Captures with tcpdump

#### tcpdump Overview

-   **Definition:** Popular network analyzer.
-   **Installation:** Pre-installed on many Linux distributions.
-   **Compatibility:** Can be installed on most Unix-like operating systems (like macOS).
-   **Capability:** Can easily capture and monitor network traffic such as TCP, IP, ICMP, and many more.
-   **Interface:** Command line tool (no graphical user interface).
-   **Power:** Command line is very powerful and efficient tool.

#### tcpdump Functionality

-   **Options and flags:** Can apply options and flags to commands to easily filter network traffic.
-   **Filtering capability:** Can filter for specific IP address, protocol, or port number.
-   **Purpose:** Find exactly what you're looking for in network traffic.

#### Simple tcpdump Command Example

-   **Command:** `sudo tcpdump -i any -v -c 1`
-   **Note:** Computer's traffic may appear different when using this command.

##### Command Breakdown

-   **sudo:** Used because Linux account doesn't have permission to run tcpdump.
-   **tcpdump:** Starts tcpdump.
-   **-i:** Specifies which interface to sniff traffic on.
-   **-v:** Stands for verbose (displays detailed packet information).
-   **-c:** Stands for count (specifies how many packets tcpdump will capture).
-   **1:** Specifies one packet.

#### Output Analysis

##### Initial Information

-   **Listening:** tcpdump tells us it's listening on any available network interfaces.
-   **Additional info:** Provides capture size and other details.

##### Packet Information Fields

###### Timestamp

-   **Location:** First field.
-   **Content:** Specific time of packet travel.
-   **Format:** Hours, minutes, seconds, and fractions of a second.
-   **Usefulness:** Especially helpful during incident investigation.
-   **Purpose:** Determine timelines and correlate traffic.

###### IP Version Field

-   **Content:** Listed as IP (means IPv4).
-   **Verbose option:** Gives more details about IP packet fields.
-   **Details include:** Protocol type and length of packet.

##### IP Packet Fields

###### ToS (Type of Service)

-   **Function:** Tells if certain packets should be treated with different care.
-   **Representation:** Value in hexadecimal.

###### TTL (Time to Live)

-   **Function:** Tells how long packet can travel across network before getting dropped.

###### Fragmentation Fields

-   **Three fields:** Identification, Offset, and Flags.
-   **Purpose:** Provide information relating to fragmentation.
-   **Function:** Provide instructions on how to reassemble packets in correct order.
-   **Example:** DF beside flags stands for Don't Fragment.

###### Protocol Field

-   **Function:** Specifies protocol in use.
-   **Content:** Provides value corresponding to protocol.
-   **Example:** TCP represented by number 6.

###### Length Field

-   **Function:** Total Length of packet including IP header.

##### Communication Information

-   **IP addresses:** Can observe IP addresses communicating with each other.
-   **Direction:** Arrow indicates direction of traffic flow.
-   **Port information:** Last piece of IP address indicates port number or name.

##### Checksum Field

-   **Function:** Corresponds to Header Checksum.
-   **Purpose:** Stores value used to determine if any errors occurred in header.
-   **Status:** "Correct" indicates no errors.

##### TCP Fields

-   **Flags:** Indicate TCP flags.
-   **P flag:** Push flag.
-   **Period:** Indicates ACK flag.
-   **Meaning:** Packet is pushing out data.

## Module 3

### Detection and Analysis Phase

#### Detection Overview

-   **Function:** Enables prompt discovery of security events.
-   **Key principle:** Not all events are incidents, but all incidents are events.
-   **Event examples:** Regular occurrences in business operations (website visits, password reset requests).

#### Detection Tools and Process

-   **Tools used:** IDS and SIEM tools collect and analyze event data from different sources.
-   **Purpose:** Identify potential unusual activity and send alerts when incidents are detected.

#### Analysis Phase

-   **Trigger:** Security teams begin analysis phase after detection.
-   **Function:** Investigation and validation of alerts.
-   **Requirements:** Analysts must apply critical thinking and incident analysis skills.
-   **Process:** Investigate and validate alerts.
-   **Focus:** Examine indicators of compromise to determine if incident has occurred.

#### Detection Challenges

-   **Inherent Limitations:** Impossible to detect everything due to tool limitations and deployment issues.
-   **High Alert Volume:** Analysts often receive thousands of alerts per shift, primarily from misconfigured settings.
-   **Alert Configuration Issues:** Overly broad rules create false positives; alternatively, high volumes may indicate legitimate attacks exploiting new vulnerabilities.

### Cybersecurity Incident Detection Methods

#### Methods of Detection Overview

-   **Phase:** Detection and Analysis Phase of incident response lifecycle.
-   **Process:** Security teams notified of possible incident and work to investigate and verify.
-   **Method:** Collect and analyze data.
-   **Reminder:** Detection refers to prompt discovery of security events.
-   **Analysis:** Involves investigation and validation of alerts.

#### Detection Tools

-   **IDS:** Intrusion detection system can detect possible intrusions and send alerts.
-   **SIEM:** Security information and event management tools detect, collect, and analyze security data.

#### Detection Challenges

-   **Reality:** Even best security teams can fail to detect real threats.
-   **Tool limitations:** Detection tools can only detect what security teams configure them to monitor.
-   **Configuration issues:** If not properly configured, can fail to detect suspicious activity.
-   **Risk:** Leaves systems vulnerable to attack.
-   **Solution:** Use additional methods of detection to increase coverage and accuracy.

#### Threat Hunting

##### Overview

-   **Evolution:** Threats evolve and attackers advance their tactics and techniques.
-   **Limitation:** Automated, technology-driven detection can be limited in keeping up with evolving threat landscape.
-   **Solution:** Human-driven detection like threat hunting combines technology with human element.
-   **Purpose:** Discover hidden threats left undetected by detection tools.

##### Threat Hunting Definition

-   **Definition:** Proactive search for threats on network.
-   **Uses:**
    -   Uncover malicious activity not identified by detection tools
    -   Do further analysis on detections
    -   Detect threats before they cause damage

##### Example: Fileless Malware

-   **Challenge:** Difficult for detection tools to identify.
-   **Technique:** Uses sophisticated evasion techniques like hiding in memory instead of using files or applications.
-   **Bypass:** Allows it to bypass traditional methods of detection like signature analysis.
-   **Solution:** Threat hunting combines active human analysis and technology to identify such threats.

##### Threat Hunters

-   **Definition:** Threat hunting specialists known as threat hunters.
-   **Responsibilities:**
    -   Perform research on emerging threats and attacks
    -   Determine probability of organization being vulnerable to particular attack
-   **Tools used:** Combination of threat intelligence, indicators of compromise, indicators of attack, and machine learning.

#### Threat Intelligence

-   **Definition:** Evidence-based information providing context about existing or emerging threats.
-   **Sources:** Industry reports, government advisories, and threat data feeds containing indicators like IP addresses, domains, and file hashes.
-   **Management:** Threat Intelligence Platforms (TIPs) collect, centralize, and analyze intelligence from different sources.
-   **Best practice:** Use threat feeds to add context to detections, not drive them completely.

#### Cyber Deception

-   **Definition:** Techniques that deliberately deceive malicious actors to increase detection.
-   **Example - Honeypots:** Decoy systems or resources created to attract intruders and alert security teams when accessed.

### Indicators of Compromise (IoCs)

#### Overview

-   **Definition:** Observable evidence suggesting signs of a potential security incident.
-   **Comparison with IoAs:** IoCs identify the "who" and "what" after an attack; IoAs focus on the "why" and "how" of ongoing attacks.
-   **Note:** IoCs aren't always confirmation of security incidents; they may result from human error or system malfunctions.

#### Pyramid of Pain

-   **Concept:** Different types of IoCs provide varying levels of value to security teams.
-   **Structure:** Represents the "pain" levels attackers face when security teams block activity associated with different IoC types.
-   **Types of IoCs (from easiest to hardest for attackers to change):**
    -   **Hash Values:** Unique references to specific malware samples
    -   **IP Addresses:** Network identifiers like 192.168.1.1
    -   **Domain Names:** Web addresses such as www.google.com
    -   **Network Artifacts:** Observable evidence on networks (e.g., User-Agent strings)
    -   **Host Artifacts:** Observable evidence on devices (e.g., malware-created files)
    -   **Tools:** Software used by attackers (e.g., password crackers)
    -   **TTPs (Tactics, Techniques, and Procedures):** Attacker behaviors, hardest to detect

### Ongoing Monitoring and Threat Detection

#### CI/CD Pipeline Security

-   **Purpose:** Protect software supply chain through automated monitoring.
-   **Common IoCs in CI/CD Pipelines:**
    -   Unauthorized code changes (suspicious timing, location, or content)
    -   Suspicious deployment patterns (unusual systems, times, or user accounts)
    -   Compromised dependencies (CVEs, unexpected additions, untrusted sources)
    -   Unusual pipeline execution (failures, delays, unauthorized changes)
    -   Secrets exposure attempts

#### Automated Detection Methods

-   **Comprehensive Logging:** Monitor pipeline execution, code commits, access, and deployment logs.
-   **SIEM Integration:** Use machine learning and analytics to find anomalies and implement rules for known IoCs.
-   **Real-time Alerting:** Notify teams about unusual build failures, suspicious code changes, secrets exposure attempts, and unusual network traffic.
-   **Performance Monitoring:** Track system performance to identify potential IoAs that may lead to IoCs.
-   **Vulnerability Scanning:** Regularly check infrastructure for weaknesses in CI/CD tools, plugins, and containers.

### The Power of Crowdsourcing

#### Threat Intelligence Sharing

-   **Definition:** Gathering security information through public input and collaboration.
-   **Advantage:** Organizations can leverage knowledge from millions of cybersecurity professionals instead of working in isolation.
-   **Sources:** Cybersecurity vendors, government agencies, cloud providers, and information-sharing organizations.

#### Information-Sharing Organizations

-   **ISACs (Information Sharing and Analysis Centers):** Share sector-specific threat intelligence.
-   **OSINT (Open-Source Intelligence):** Collect and analyze publicly available information.

#### VirusTotal

-   **Function:** Analyze suspicious files, domains, URLs, and IP addresses for malicious content.
-   **Report Components:**
    -   **Detection Tab:** Third-party security vendor verdicts
    -   **Details Tab:** Static analysis information (hashes, file types, creation time)
    -   **Relations Tab:** Connected IoCs (contacted URLs, domains, IP addresses)
    -   **Behavior Tab:** Observed activity in sandboxed environments
    -   **Community Tab:** Expert insights and comments
-   **Scoring:** Vendors' detection ratio and community scores indicate likelihood of malicious intent

### Documentation and Chain of Custody

#### Chain of Custody Forms

-   **Definition:** Documentation of evidence possession and control during incident lifecycle.
-   **Components:**
    -   **Description of Evidence:** Location, hostname, MAC address, IP address
    -   **Custody Log:** Names, dates, times, and purposes of transfers
-   **Importance:** Establishes evidence integrity, reliability, and accuracy for legal proceedings.
-   **Broken Chain Impact:** Inconsistencies in collection and logging can compromise evidence validity.

#### Documentation Benefits

-   **Transparency:** Critical for compliance, insurance requirements, and legal proceedings.
-   **Standardization:** Supports improvement efforts, knowledge transfer, and onboarding.
-   **Clarity:** Helps people quickly access needed information and take appropriate action.

#### Documentation Best Practices

-   **Know Your Audience:** Tailor content to meet specific audience needs (technical vs. non-technical).
-   **Be Concise:** Establish purpose immediately and create brief, scannable summaries.
-   **Update Regularly:** Review and revise to address evolving threats and process gaps.

### Cybersecurity Playbooks

#### Overview

-   **Definition:** Manuals providing detailed instructions for operational actions during incidents.
-   **Function:** Offer structure during chaotic incident response, reducing guesswork and uncertainty.
-   **Components:** Checklists and step-by-step procedures for specific incident types (ransomware, data breach, malware, DDoS).

#### Types of Playbooks

-   **Non-Automated:** Require step-by-step actions performed by analysts.
-   **Automated:** Use tools to automate tasks like severity categorization and evidence gathering.
-   **Semi-Automated:** Combine human action with automation for tedious or error-prone tasks.

#### Maintenance

-   **Requirement:** Regular updates to address evolving threats and process improvements.

### Triage in Incident Response

#### Overview

-   **Definition:** Prioritizing incidents according to importance or urgency to allocate limited resources effectively.
-   **Analogy:** Similar to hospital emergency departments prioritizing patients based on condition severity.

#### Triage Process

##### Step 1: Receive and Assess

-   **Actions:** Review alerts, gather information, and verify validity.
-   **Verification Questions:**
    -   Is the alert a false positive?
    -   Has this alert occurred before?
    -   Is it related to a known vulnerability?
    -   What is the severity level?

##### Step 2: Assign Priority

-   **Factors:**
    -   **Functional Impact:** Effect on business operations and system functionality
    -   **Information Impact:** Consequences for data confidentiality, integrity, and availability
    -   **Recoverability:** Possibility and cost of recovery

##### Step 3: Collect and Analyze

-   **Process:** Gather evidence, conduct research, document investigation
-   **Goal:** Collect sufficient information for informed decision-making
-   **Escalation:** Refer to higher-level analysts when necessary

#### Benefits of Triage

-   **Reduced Impact:** Timely response to high-priority threats
-   **Resource Management:** Focus on urgent issues rather than lower-priority tasks
-   **Standardized Approach:** Consistent alert assessment and validation process

### Containment, Eradication, and Recovery Phase

-   **Containment:** Limiting and preventing additional damage caused by an incident. Organizations outline containment strategies in incident response plans.
    -   Example: isolating malware-infected system by disconnecting from network to prevent spread.
-   **Eradication:** Complete removal of incident elements from all affected systems through vulnerability tests and patches.
    -   Occurs after incident has been contained.
-   **Recovery:** Process of returning affected systems to normal operations through reimaging, password resets, and firewall adjustments.
    -   Can disrupt key business operations and services.

### Post-Incident Activity Phase

-   **Lessons Learned Meeting:** Held within two weeks after incident with all parties involved. Purpose is to review incident, assess response actions, and identify improvements.
    -   Also called post-mortem meeting with agenda distributed beforehand.
-   **Key Questions:** What happened and when, who discovered it, how was it contained, what recovery actions were taken, what could have been done differently.
-   **Final Report:** Comprehensive review of incident with executive summary, detailed timeline, investigation actions, and recommendations.
    -   Format varies across organizations with audience consideration for non-security professionals.
-   **Recommendations:** Prioritized actions to improve incident handling processes like updating playbooks and implementing new security tools.
    -   Benefits include identifying errors, gaps in processes, and ineffective security controls.

## Module 4

### The Importance of Logs

#### Log Collection Process

-   **Log forwarders:** Software that collects logs from various sources and automatically forwards them to centralized log repository for storage.
-   **Data sources:** Different types of devices and systems create logs in environment.
-   **Types of logs:**
    -   Network logs: Generated by proxies, routers, switches, and firewalls
    -   System logs: Generated by operating systems
    -   Application logs: Related to software applications
    -   Security logs: Generated by security tools like IDS or IPS
    -   Authentication logs: Record login attempts

#### Network Log Example

-   **Action field:** Specifies ALLOW - router's firewall settings allowed access from specific IP address to google.com.
-   **Source field:** Lists IP address showing network traffic source.
-   **Timestamp field:** Most essential field identifying exact date and time of action.
    -   Useful for correlating multiple events to develop incident timeline.

#### Best Practices for Log Collection and Management

##### What to Log

-   **Consideration:** Choose which log sources contain most useful information for events of interest.
-   **Configuration:** Reduce data recorded by excluding excessive verbosity.
-   **PII handling:** Personally identifiable information (phone numbers, email addresses, names) requires special handling and may not be loggable in some jurisdictions.

##### The Issue with Overlogging

-   **Common mistake:** Logging everything because it can be logged.
-   **Disadvantages:**
-   Increases storage and maintenance costs
-   Increases system load causing performance issues
-   Affects usability making it difficult to search for important events

##### Log Retention

-   **Regulatory requirements:** Organizations in certain industries must retain logs for set periods.
-   **Industries with requirements:**
    -   Public sector: Federal Information Security Modernization Act (FISMA)
    -   Healthcare: Health Insurance Portability and Accountability Act (HIPAA)
    -   Financial services: PCI DSS, Gramm-Leach-Bliley Act (GLBA), Sarbanes-Oxley Act (SOX)

##### Log Protection

-   **Threat:** Malicious actors modify logs to mislead security teams and hide activity.
-   **Centralized storage:** Store logs in dedicated server instead of local machines.
    -   Creates barrier between attacker and log location
    -   Makes it more difficult for attackers to access logs

#### Variations of Logs

##### Log Characteristics

-   **Analogy:** Logs are similar to receipts - while receipts record purchases, logs record events or activities on network or system.
-   **Common elements:** Timestamps, system characteristics (IP addresses), description of event including action taken and who performed it.
-   **Format variations:** Different log sources generate logs in different formats.
-   **Readability:** Some designed to be human-readable while others are machine-readable.
-   **Verbosity:** Some logs contain lots of information while others are short and simple.

##### Common Log Formats

###### JSON (JavaScript Object Notation)

-   **Type:** Lightweight file format used to store and transmit data.
-   **Usage:** Web technologies and cloud environments.
-   **Syntax components:**
    -   Key-value pairs: "Alert": "Malware"
    -   Commas: Separate data elements
    -   Double quotes: Enclose text data (strings)
    -   Curly brackets: Enclose objects
    -   Square brackets: Enclose arrays
-   **Advantage:** Known for simplicity and easy readability.

###### Syslog

-   **Type:** Standard for logging and transmitting data with three capabilities.
-   **Protocol:** Transports logs to centralized server using port 514 (plaintext) or 6514 (encrypted).
-   **Service:** Consolidates logs from multiple sources into single location.
-   **Log format:** Native format used in Unix systems.
-   **Structure:** Header, structured-data, and message.
-   **Header fields:** Timestamp, Hostname, Application name, Message ID.
-   **Priority (PRI):** Indicates urgency with angle brackets - lower numbers are more urgent.

###### XML (eXtensible Markup Language)

-   **Type:** Native file format used in Windows systems.
-   **Syntax components:**
    -   Tags: Start tag <tag> and end tag </tag>
    -   Elements: Data contained inside tags with root and child elements
    -   Attributes: Additional information about elements in quotes
-   **Structure:** Uses tags and keys instead of key-value pairs.

###### CSV (Comma Separated Value)

-   **Type:** Uses commas to separate data values.
-   **Structure:** Position of data corresponds to field name.
-   **Note:** Field names might not be included in log - critical to understand source device fields.

###### CEF (Common Event Format)

-   **Type:** Log format using key-value pairs to structure data.
-   **Syntax:** CEF:Version|Device Vendor|Device Product|Device Version|Signature ID|Name|Severity|Extension
-   **Fields:** Separated with pipe character |.
-   **Extension:** Must be written in key-value format.
-   **Transport:** Syslog commonly used to transport CEF logs.

### Security Monitoring with Detection Tools

#### Telemetry

-   **Definition:** Collection and transmission of data for analysis.
-   **Comparison:** While logs record events occurring on systems, telemetry describes the data itself.
-   **Example:** Packet captures are considered network telemetry.
-   **Use:** Logs and telemetry are sources of evidence for investigations.

#### Intrusion Detection Systems (IDS)

-   **Function:** Application that monitors activity and alerts on possible intrusions.
-   **Monitoring scope:** Different parts of system or network like endpoints.
-   **Endpoint definition:** Any device connected on network (laptop, tablet, desktop, smartphone).
-   **Target importance:** Endpoints are entry points into network, making them key targets for malicious actors.

#### Host-Based Intrusion Detection Systems

-   **Function:** Application that monitors activity of host on which it's installed.
-   **Host definition:** Any device that communicates with other devices on network.
-   **Installation:** Installed as agent on single host (laptop computer or server).
-   **Process:** Monitors host to detect suspicious activity, records output as logs, generates alerts.

#### Network-Based Intrusion Detection Systems

-   **Function:** Collects and analyzes network traffic and network data.
-   **Operation:** Works similar to packet sniffers analyzing network traffic at specific points.
-   **Deployment:** Common to deploy multiple IDS sensors at different points for adequate visibility.
-   **Process:** When suspicious network activity detected, logs it and generates alert.

#### Detection Methods

-   **Signature analysis:** Most common detection method used to find events of interest.
-   **Signature definition:** Set of rules that IDS refers to when monitoring activity.
-   **Process:** If activity matches signature rules, IDS logs it and sends alert.
-   **Example:** Signature can generate alert if failed login happens three times in row (possible password attack).

#### IDS Logs

-   **Recording:** IDS technologies record information of devices, systems, and networks they monitor.
-   **Storage:** IDS logs can be sent, stored, and analyzed in centralized log repository like SIEM.

#### Detection Tools and Techniques

##### Host-Based Intrusion Detection System (HIDS)

-   **Function:** Application that monitors activity of host on which it's installed.
-   **Installation:** Installed as agent on host (endpoint like computer or server).
-   **Monitoring scope:** Internal activity happening on host to identify unauthorized or abnormal behavior.
-   **Capabilities:** Monitors inbound/outbound traffic flows, file systems, system resource usage, user activity.
-   **Process:** If unusual activity detected (like unauthorized application installation), logs it and sends alert.

##### Network-Based Intrusion Detection System (NIDS)

-   **Function:** Application that collects and monitors network traffic and network data.
-   **Installation:** Installed on devices at specific network points for monitoring.
-   **Operation:** Inspects network traffic from different devices on network.
-   **Process:** If malicious network traffic detected, logs it and generates alert.
-   **Multi-layered approach:** Using combination of HIDS and NIDS provides comprehensive view of activity.

##### Detection Techniques

###### Signature-Based Analysis

-   **Method:** Detection method used to find events of interest.
-   **Signature definition:** Pattern associated with malicious activity containing specific patterns like binary numbers, bytes, or IP addresses.
-   **Use of IoCs:** Indicators of compromise and attack can be useful for creating targeted signatures.
-   **Example:** Anti-malware signature contains patterns associated with malware including malicious scripts.
-   **Advantages:**
    -   Low rate of false positives
    -   Very efficient at detecting known threats
-   **Disadvantages:**
    -   Signatures can be evaded by attackers modifying behaviors
    -   Signatures require updates for new exploits
    -   Cannot detect unknown threats like zero-day attacks

###### Anomaly-Based Analysis

-   **Method:** Detection method that identifies abnormal behavior.
-   **Two phases:**
    -   Training phase: Establish baseline of normal/expected behavior
    -   Detection phase: Compare current activity against baseline
-   **Process:** Activity outside baseline gets logged and alert generated.
-   **Advantages:**
    -   Ability to detect new and evolving threats
    -   Can detect unknown threats unlike signature-based analysis
-   **Disadvantages:**
    -   High rate of false positives
    -   Pre-existing compromise during training phase can include malicious behavior in baseline

#### Components of a Detection Signature

##### Signature Overview

-   **Function:** Specifies detection rules outlining types of network intrusions IDS should detect.
-   **Example:** Signature can detect and alert on suspicious traffic attempting to connect to port.
-   **Rule language:** Differs depending on different network intrusion detection systems (NIDS).
-   **Components:** NIDS rules consist of three components: action, header, and rule options.

##### Action Component

-   **Position:** First item specified in signature.
-   **Function:** Determines action to take if rule criteria matches are met.
-   **Common actions:** Alert, pass, or reject (differ across NIDS rule languages).
-   **Example:** If rule specifies to alert on suspicious network traffic establishing unusual connection to port, IDS inspects traffic packets and sends alert.

##### Header Component

-   **Function:** Defines signature's network traffic.
-   **Information includes:** Source and destination IP addresses, source and destination ports, protocols, traffic direction.
-   **Example:** To detect alert on suspicious traffic connecting to port, must first define source of suspicious traffic in header.
-   **Sources:** Suspicious traffic can originate from IP addresses outside local network or use specific/unusual protocols.

##### Rule Options Component

-   **Function:** Customize signatures with additional parameters.
-   **Capabilities:** Many different options available to use.
-   **Example:** Can set options to match content of network packet to detect malicious payloads.
-   **Malicious payloads:** Reside in packet's data and perform malicious activity like deleting or encrypting data.
-   **Format:** Typically separated by semi-colons and enclosed in parentheses.
-   **Common options:**
    -   msg (message): Provides alert's text
    -   sid (signature ID): Attaches unique ID to each signature
    -   rev (revision): Changes when signature is updated (number indicates version)

#### Examine Signatures with Suricata

##### Suricata Overview

-   **Type:** Open source signature-based IDS.
-   **Pre-written signatures:** Many NIDS technologies come with customizable templates.
-   **Function:** Signature templates provide starting point for writing and defining rules.
-   **Customization:** Can write and add own rules.

##### Examining Suricata Files

-   **Location:** Configuration files live in etc/suricata directory.
-   **Rules folder:** Contains pre-written signatures and custom signatures.
-   **Rule templates:** Available for different protocols and services.

##### Signature Analysis Example

-   **File:** custom.rules file contains custom rules for HTTP connections.
-   **Comments:** Lines beginning with # provide context and are ignored by Suricata.
-   **Signature components:**
    -   **Action:** First word specifies signature's action (alert generates alert when conditions met)
    -   **Header:** Specifies protocol (http), source IP (HOME_NET), source port (ANY), destination IP (EXTERNAL_NET), destination port (ANY)
    -   **Direction:** Arrow indicates traffic from home network to external network
-   **Rule options:** Enclosed in parentheses and separated by semicolons.
    -   **Message option:** Shows "GET on wire" when alert triggered
    -   **Flow option:** Matches direction of network traffic flow (established = successful connection)
    -   **Content option:** Inspects packet content for text "GET" (HTTP request to retrieve data)

##### Signature Summary

-   **Function:** Alerts when Suricata observes text "GET" in HTTP connection from home network to external network.
-   **Customization importance:** Every environment different - signatures must be tested and tailored.
-   **Analyst role:** May test, modify, or create IDS signatures to improve threat detection and reduce false positives.

#### Examine Suricata Logs

##### EVE JSON Format

-   **Format:** Suricata outputs alerts and events in EVE JSON format.
-   **EVE:** Extensible Event Format.
-   **JSON:** JavaScript Object Notation using key-value pairs.
-   **Advantage:** Simplifies searching and extracting text from log files.

##### Types of Log Data

###### Alert Logs

-   **Content:** Information relevant to security investigations.
-   **Source:** Output of signatures that have triggered alerts.
-   **Example:** Signature detecting suspicious traffic generates alert log capturing traffic details.
-   **Purpose:** Security-relevant information for investigations.

###### Network Telemetry Logs

-   **Content:** Information about network traffic flows.
-   **Nature:** Not always security relevant - simply recording network activity.
-   **Example:** Connection being made to specific port.
-   **Purpose:** Provides information to build story during investigation.

##### Log Examples

###### Alert Log Example

-   **Event type:** Field says "alert" indicating alert event.
-   **Details included:** IP addresses, protocol, signature message and ID.
-   **Example:** Alert relates to detection of malware based on signature message.

###### Network Telemetry Log Example

-   **Event type:** Field says "http" indicating http log.
-   **Details included:**
    -   Hostname: Website that was accessed
    -   User agent: Software connecting to website (e.g., Mozilla 5.0 web browser)
    -   Content type: Data http request returned (e.g., HTML text)

#### Overview of Suricata

##### Configuration File

-   **Purpose:** Must properly configure settings before deployment so tools know what to do.
-   **Function:** File used to configure application settings.
-   **Customization:** Lets you customize exactly how IDS interacts with environment.
-   **File:** Suricata's configuration file is suricata.yaml using YAML file format for syntax and structure.

##### Log Files

-   **Two types:** Suricata generates when alerts are triggered.

###### eve.json

-   **Type:** Standard Suricata log file.
-   **Content:** Detailed information and metadata about events and alerts in JSON format.
-   **Features:** Contains unique identifier called flow_id to correlate related logs/alerts to single network flow.
-   **Use:** More detailed analysis, better format for log parsing and SIEM log ingestion.

###### fast.log

-   **Type:** Records minimal alert information including basic IP address and port details.
-   **Use:** Basic logging and alerting.
-   **Status:** Legacy file format not suitable for incident response or threat hunting tasks.

##### Key Difference

-   **Level of detail:** fast.log records basic information while eve.json contains additional verbose information.

### Log Searches and Log Ingestion

#### Log Ingestion

-   **Requirement:** Data is required for SIEM tools to work effectively.
-   **Process:** SIEM tools must first collect data using log ingestion.
-   **Definition:** Process of collecting and importing data from log sources into SIEM tool.
-   **Data sources:** Any source that generates log data like servers.
-   **Storage:** SIEM creates copy of event data and retains it within own storage.
    -   Allows analysis without modifying original source logs
-   **Centralized platform:** Collection of event data provides platform for security analysts to analyze data and respond to incidents.
-   **Event data includes:** Authentication attempts, network activity, and more.

#### Log Forwarders

-   **Methods:** Many ways SIEM tools can ingest log data (manual upload or software).
-   **Manual upload:** May be inefficient and time-consuming for networks with thousands of systems.
-   **Software solution:** Easier to use software that helps collect data.
-   **Log forwarders:** Software that automates process of collecting and sending log data.
-   **Native forwarders:** Some operating systems have native log forwarders.
-   **Third-party:** If no native forwarder, need to install third-party log forwarding software.
-   **Configuration:** After installation, configure software to specify which logs to forward and where to send them.
-   **Processing:** SIEM tool processes and normalizes data for easy searching, exploration, correlation, and analysis.
-   **Options:** Many SIEM tools utilize proprietary log forwarders or integrate with open-source log forwarders.
-   **Selection factors:** Depends on system requirements, organization needs, compatibility with existing infrastructure.

#### Query for Events

##### Search Query Optimization

-   **Example:** Searching for failed login event using keywords "failed login".
-   **Broad queries:** Can return thousands of results and slow down response times.
-   **Optimization:** Specify additional parameters like event ID and date/time range to narrow search.
-   **Importance:** Search queries should be specific to find exactly what you're looking for and save time.

##### Splunk Search Processing Language (SPL)

-   **Language:** Splunk uses its own query language called Search Processing Language (SPL).
-   **Features:** Many different search options to optimize search results.
-   **Example search:** "buttercupgames error OR fail\*"
    -   Specifies index (buttercupgames)
    -   Search terms: error OR fail
    -   Boolean operator OR ensures both keywords searched
    -   Wildcard (\*) searches for all possible endings containing "fail"
-   **Time range:** Select specific time range (e.g., last 30 days) for better results.
-   **Results display:**
    -   Timeline showing visual representation of events over period
    -   Events viewer with list of matching events
    -   Highlighted search terms in each event
    -   Timestamp and raw logged data
    -   Data source information (host name, source, source type)
-   **Raw log search:** Slower performance since it extracts log data fields during search process.

##### Google SecOps (Chronicle)

-   **Function:** Allows search and filter log data.
-   **Language:** Uses YARA-L language to define rules for detection.
-   **Search fields:** Can search for hostname, domain, IP, URL, email, username, file hash.
-   **Search methods:**
    -   **UDM search (default):** Unified Data Model searches through normalized data.
    -   **Raw log search:** Searches through logs that have not been normalized.
-   **UDM search example:** "metadata.event_type = 'USER_LOGIN' AND security_result.action = 'BLOCK'"
    -   metadata.event_type: Details event type (user login)
    -   AND: Logical operator containing both terms
    -   security_result.action: Specifies security action (BLOCK = failed login)
-   **Results display:**
    -   Bar graph timeline visualizing events over period
    -   List of events with timestamps and assets (device names)
    -   Quick Filters for additional filtering options
-   **Raw log access:** Can click event to open associated raw log for investigation details.

# Certificate Completed

![Certificate proof in case I have to pay for it](Screenshot%202025-07-28%20at%2011.29.46 PM.png)
