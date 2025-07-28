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
- **Data transmission:** When data is sent, it's divided into packets.
- **Analogy:** Like addressed envelope in mail.
- **Function:** Contain delivery information used to route to destination.
- **Information includes:**
    - Sender and receiver's IP address
    - Type of packet being sent
    - More information
- **Value:** Provide lots of information about communications between devices over network.

#### Packet Components
- **Multiple components** in a packet:

##### Header
- **Contains:** Information like type of network protocol and port being used.
- **Analogy:** Name and mailing address located on envelope.
- **Network protocols:** Set of rules that determine transmission of data between devices on network.
- **Ports:** Non-physical locations on computer that organize data transmission between devices on network.
- **Additional info:** Contains packet's source and destination IP address.
- **Note:** More header information explored in later section.

##### Payload
- **Contains:** Actual data being delivered.
- **Analogy:** Content of letter inside envelope.

##### Footer
- **Function:** Signifies end of packet.

#### Observing Network Packets
- **Challenge:** Packets are invisible but can be captured.
- **Analogy:** Like scents being invisible but can be smelled.
- **Tool:** Packet sniffers (network protocol analyzers).
- **Purpose:** Capture and analyze data traffic within network.

#### Packet Sniffers
- **Definition:** Tool designed to capture and analyze data traffic within network.
- **Security analyst use:** Inspect packets for indicators of compromise.
- **Function:** Grab detailed snapshot of packets traveling over network.

#### Packet Capture (P-cap)
- **Definition:** File containing data packets intercepted from interface or network.
- **Analogy:** Like intercepting envelope in mail.
- **Usefulness:** Incredibly useful during incident investigation.
- **Benefit:** Access to communications happening between devices over network.
- **Purpose:** Observe network interactions and build storyline to determine what exactly happened.

### Data Exfiltration Attacks

#### Initial Access
- **Requirement:** Attackers need to gain initial access into network and computer system before data exfiltration.
- **Method:** Social engineering attack like phishing.
- **Process:** Tricks people into disclosing sensitive data.
- **Technique:** Send phishing emails with attachments or links that trick target into entering credentials.
- **Result:** Attacker successfully gains access to device.

#### Lateral Movement (Pivoting)
- **Goal:** Maintain access in environment and avoid detection for as long as possible.
- **Tactic:** Lateral movement or pivoting.
- **Process:** Spend time exploring network to expand and maintain access to other systems.
- **Activity:** Scope out environment to identify valuable assets.

#### Target Assets
- **Valuable assets attackers seek:**
    - Sensitive data like proprietary code
    - Personally identifiable information (names, addresses)
    - Financial records
- **Search locations:**
    - Network file shares
    - Intranet sites
    - Code repositories
    - More locations

#### Data Preparation
- **Process:** After identifying valuable assets, attackers collect, package, and prepare data for exfiltration.
- **Method:** Reduce data size to help hide stolen data and bypass security controls.

#### Data Exfiltration
- **Final step:** Exfiltrate data to attacker's destination of choice.
- **Methods:** Many ways to do this.
- **Example:** Email stolen data to themselves using compromised email account.

#### Defense Strategies

##### Prevent Attacker Access
- **First line:** Security teams must prevent attacker access.
- **Methods:** Many methods to protect network from phishing attempts.
- **Example:** Requiring users to use multi-factor authentication.

##### Monitor Network Activity
- **Challenge:** Attackers can remain unnoticed for a while.
- **Requirement:** Security teams must monitor network activity to identify suspicious activity indicating compromise.
- **Example:** Multiple user logins from IP addresses outside network should be investigated.

##### Asset Protection
- **Earlier learning:** How to identify, classify, and protect assets using asset inventories and security controls.
- **Policy requirement:** All assets should be cataloged in asset inventory as part of organization's security policy.
- **Security controls:** Appropriate controls should be applied to protect assets from unauthorized access.

##### Detect and Stop Exfiltration
- **Requirement:** If data exfiltration attack is successful, security teams must detect and stop it.
- **Detection method:** Indicators of unusual data collection identified through network monitoring.
- **Indicators include:**
    - Large internal file transfers
    - Large external uploads
    - Unexpected file writes
- **Tool:** SIEM tools can detect and alert on these activities.
- **Response:** Once alert sent, security teams investigate and stop attack from continuing.

##### Stopping the Attack
- **Methods:** Many ways to stop attack like this.
- **Example:** Once unusual activity identified, block IP addresses associated with attacker using firewall rules.

### Learn More About Packet Captures

#### Header
- **Location:** Packets begin with most essential component - the header.
- **Multiple headers:** Packets can have several headers depending on protocols used:
    - Ethernet header
    - IP header
    - TCP header
    - More headers
- **Function:** Provide information used to route packets to destination.
- **Information includes:**
    - Source and destination IP addresses
    - Packet length
    - Protocol
    - Packet identification numbers
    - More information

#### Payload
- **Location:** Directly follows header.
- **Contains:** Actual data being delivered.
- **Example:** Uploading image to website - payload would be the image itself.

#### Footer
- **Alternative name:** Also known as trailer.
- **Location:** Located at end of packet.
- **Ethernet protocol:** Uses footers to provide error-checking information to determine if data corrupted.
- **Display limitation:** Ethernet network packets analyzed might not display footer information due to network configurations.
- **Note:** Most protocols (like Internet Protocol/IP) do not use footers.

#### Network Protocol Analyzers
- **Definition:** Tools designed to capture and analyze data traffic within network.
- **Examples:** tcpdump, Wireshark, TShark.
- **Uses beyond security:**
    - Collect network statistics (bandwidth, speed)
    - Troubleshoot network performance issues (slowdowns)
- **Malicious use:** Malicious actors can use to capture packets containing sensitive data (account login information).

#### How Network Protocol Analyzers Work
- **Components:** Use both software and hardware capabilities.
- **Process:**

##### Step 1: Packet Collection
- **Method:** Packets collected from network via Network Interface Card (NIC).
- **NIC definition:** Hardware that connects computers to network (like router).
- **Default behavior:** NICs only listen to network traffic addressed to them.
- **Requirement:** To capture all network traffic, NIC must be switched to mode with access to all visible network data packets.
- **Modes:**
    - **Wireless interfaces:** Often called monitoring mode.
    - **Other systems:** May be called promiscuous mode.
- **Limitation:** Mode enables access to all visible network data packets but doesn't help access all packets across network.
- **Positioning:** Network protocol analyzer must be positioned in appropriate network segment to access all traffic between different hosts.

##### Step 2: Data Conversion
- **Collection format:** Network traffic collected in raw binary format.
- **Binary format:** Consists of 0s and 1s, not easy for humans to interpret.
- **Conversion:** Network protocol analyzer takes binary and converts to human-readable format.
- **Benefit:** Analysts can easily read and understand information.

##### Security Note
- **Risk:** Enabling promiscuous mode can expose device to potential attacks.
- **Reason:** Allows sensitive information like passwords and confidential data to be captured.
- **Requirement:** Use tools operating in promiscuous mode responsibly and with caution.

#### Capturing Packets
- **Definition:** Packet sniffing is practice of capturing and inspecting data packets across network.
- **P-cap:** File containing data packets intercepted from interface or network.
- **Analysis:** Can be viewed and further analyzed using network protocol analyzers.
- **Filtering:** Can filter packet captures to display only relevant information (e.g., packets from specific IP address).
- **Legal note:** Using network protocol analyzers to intercept and examine private network communications without permission is illegal in many places.

#### P-cap File Formats
- **Variety:** Come in many formats depending on packet capture library used.
- **Differences:** Each format has different uses, network tools may use/support specific formats by default.

##### Libraries and Formats
- **Libpcap:** Packet capture library for Unix-like systems (Linux, MacOS®).
    - **Usage:** Tools like tcpdump use as default packet capture file format.
- **WinPcap:** Open-source packet capture library for Windows operating systems.
    - **Status:** Considered older file format, not predominantly used.
- **Npcap:** Library designed by port scanning tool Nmap.
    - **Usage:** Commonly used in Windows operating systems.
- **PCAPng:** Modern file format that can simultaneously capture packets and store data.
    - **Name origin:** "ng" stands for "next generation."
    - **Capability:** Ability to do both explains the "ng."

##### Pro Tip
- **Practice:** Analyzing home network can be good way to practice using these tools.

### Overview of tcpdump

#### Network Protocol Analyzers
- **Security analyst use:** Use network protocol analyzers to help defend against network intrusions.
- **Network protocol analyzer:** Tool designed to capture and analyze data traffic within network.
- **Packet sniffing:** Practice of capturing and inspecting data packets across network.
- **Purpose:** Learn more about tcpdump for capturing and viewing network communications.

#### What is tcpdump?
- **Definition:** Command-line network protocol analyzer.
- **CLI:** Text-based user interface that uses commands to interact with computer.
- **Function:** Used to capture network traffic.
- **Output:** Traffic can be saved to packet capture (p-cap) file.
- **P-cap file:** File containing data packets intercepted from interface or network.
- **Benefits:** Can be accessed, analyzed, or shared at later time.
- **Uses:** Troubleshooting network issues to identifying malicious activity.
- **Installation:** Pre-installed in many Linux distributions.
- **Compatibility:** Can be installed on other Unix-based operating systems (macOS®).

##### Note on Encryption
- **Common issue:** Network traffic often encrypted (data encoded and unreadable).
- **Requirement:** Inspecting network packets might require decrypting data using appropriate private keys.

#### Capturing Packets with tcpdump

##### Privilege Requirements
- **Requirement:** Need administrator-level privileges to capture network traffic.
- **Options:** Either logged in as root user or have ability to use sudo command.
- **Reason:** Like many other packet sniffing tools.

##### tcpdump Syntax
- **Command format:** `sudo tcpdump [-i interface] [option(s)] [expression(s)]`
- **sudo tcpdump:** Begins running tcpdump using elevated permissions as sudo.
- **-i parameter:** Specifies network interface to capture network traffic.
- **Interface requirement:** Must specify network interface to capture from.
- **Example:** `-i any` sniffs traffic from all network interfaces on system.
- **option(s):** Optional and provide ability to alter execution of command.
- **expression(s):** Way to further filter network traffic packets to isolate network traffic.

##### Note on Interface Identification
- **Requirement:** Must identify which network interface to use before capturing.
- **Method:** Use `-D` flag to list network interfaces available on system.

#### Options

##### Overview
- **Function:** Apply options (flags) to end of commands to filter network traffic.
- **Short options:** Abbreviated with hyphen and single character (e.g., `-i`).
- **Long options:** Spelled out using double hyphen (e.g., `--interface`).
- **Total options:** Over fifty options available.
- **Reference:** Can explore using manual page.

##### Important Notes
- **Case sensitivity:** Options are case sensitive.
- **Example:** Lowercase `-w` is separate option with different use than uppercase `-W`.
- **Spacing:** Short options can be written with or without space between option and value.
- **Example:** `sudo tcpdump -i any -c 3` and `sudo tcpdump -iany -c3` are equivalent.

##### Essential Options

###### -w (Write)
- **Function:** Write or save sniffed network packets to packet capture file.
- **Benefit:** Can refer to saved file for later analysis.
- **Example:** `sudo tcpdump -i any -w packetcapture.pcap`

###### -r (Read)
- **Function:** Read packet capture file by specifying file name as parameter.
- **Example:** `sudo tcpdump -r packetcapture.pcap`

###### -v (Verbose)
- **Function:** Control how much packet information tcpdump prints out.
- **Default:** tcpdump will not print out all packet information.
- **Levels:** Three levels of verbosity (-v, -vv, -vvv).
- **Usefulness:** Helpful when looking for packet information like IP header field details.
- **Example:** `sudo tcpdump -r packetcapture.pcap -v`

###### -c (Count)
- **Function:** Control how many packets tcpdump will capture.
- **Examples:**
    - `-c 1`: Only print out one single packet
    - `-c 10`: Print out 10 packets
- **Example command:** `sudo tcpdump -i any -c 3`

###### -n (No Name Resolution)
- **Default behavior:** tcpdump performs name resolution.
- **Process:** Automatically converts IP addresses to names and resolves ports to commonly associated services.
- **Problem:** tcpdump isn't always accurate in name resolution.
- **Example issue:** Port 80 automatically translated to HTTP, but port 80 isn't always HTTP.
- **Security concern:** Reverse DNS lookup can alert attackers to investigation.
- **Solution:** `-n` flag disables automatic mapping of numbers to names.
- **Best practice:** Considered best practice when sniffing or analyzing traffic.
- **Variations:**
    - `-n`: Will not resolve hostnames
    - `-nn`: Will not resolve both hostnames or ports
- **Example:** `sudo tcpdump -r packetcapture.pcap -v -n`

##### Pro Tip on Combining Options
- **Combination:** Can combine options together (e.g., `-vn`).
- **Limitation:** If option accepts parameter right after it (like `-c 1` or `-r capture.pcap`), can't combine other options to it.

#### Expressions

##### Overview
- **Function:** Filter expressions in tcpdump commands (optional but helpful).
- **Use:** Many ways to use filter expressions during packet analysis.
- **Purpose:** Specifically search for network traffic by protocol.

##### Protocol Filtering
- **Method:** Use filter expressions to isolate network packets.
- **Example:** Filter to find only IPv6 traffic using `ip6` filter expression.

##### Boolean Operators
- **Operators:** `and`, `or`, `not`.
- **Use:** Further filter network traffic for specific IP addresses, ports, and more.
- **Example:** `sudo tcpdump -r packetcapture.pcap -n 'ip and port 80'`

##### Pro Tips
- **Quotes:** Can use single or double quotes to ensure tcpdump executes all expressions.
- **Parentheses:** Can use parentheses to group and prioritize different expressions.
- **Complex commands:** Grouping expressions helpful for complex or lengthy commands.
- **Example:** `ip and (port 80 or port 443)` prioritizes filters in parentheses before filtering for IPv4.

#### Interpreting Output

##### Output Format
- **Process:** Once command runs to capture packets, tcpdump prints output as sniffed packets.
- **Format:** One line of text for each packet.
- **Timestamp:** Each line begins with timestamp.

##### Example Command and Output
- **Command:** `sudo tcpdump -i any -v -c 1`
- **Function:** Capture packets on any network interface.
- **Options:**
    - `-v`: Prints packet with detailed information
    - `-c 1`: Prints out only one packet

### Reexamine the Fields of a Packet Header

#### Internet Layer Overview
- **Function:** Accepts and delivers packets for the network.
- **Protocol:** Internet Protocol operates as foundation for all communications on internet.
- **Responsibility:** Making sure packets reach their destinations.
- **Analogy:** Operates like mail courier delivering envelope.
- **Process:** Uses information in packet header (like IP addresses) to determine best available route for packets.

#### IP Packet Headers
- **Content:** Headers contain data fields essential to transfer of data to intended destination.
- **Variation:** Different protocols use different headers.
- **IP versions:**
    - **IPv4:** Foundation of internet communications.
    - **IPv6:** Most recent version of Internet Protocol.
- **Note:** IPv4 and IPv6 headers differ but contain similar fields with different names.
- **Focus:** IPv4 still most widely used, so we'll focus on IPv4 header fields.

#### IPv4 Header Fields

##### Version Field
- **Function:** Specifies which version of IP is being used (IPv4 or IPv6).
- **Analogy:** Like different classes of mail (priority, express, or regular).

##### IHL (Internet Header Length)
- **Function:** Specifies length of IP header plus any options.

##### ToS (Type of Service)
- **Function:** Tells if certain packets should be treated with different care.
- **Analogy:** Like fragile sticker on mailed package.

##### Total Length Field
- **Function:** Identifies length of entire packet, including headers and data.
- **Analogy:** Like dimensions and weight of envelope.

##### Fragmentation Fields
- **Three fields:** Identification, Flags, and Fragment Offset.
- **Purpose:** Deal with information related to fragmentation.
- **Fragmentation:** When IP packet gets broken up into chunks, transmitted over wire, and reassembled at destination.
- **Function:** Specify if fragmentation used and how to reassemble broken packets in correct order.
- **Analogy:** Like mail traveling through multiple routes (mailboxes, processing facilities, airplanes, mail trucks).

##### TTL (Time to Live)
- **Function:** Determines how long packet can live before it gets dropped.
- **Purpose:** Without this field, packets could loop through routers endlessly.
- **Analogy:** Like tracking information providing details about envelope's expected delivery date.

##### Protocol Field
- **Function:** Specifies protocol used by providing value corresponding to protocol.
- **Example:** TCP represented by 6.
- **Analogy:** Like including number of house in postal address.

##### Header Checksum
- **Function:** Stores value called checksum used to determine if any errors occurred in header.

##### Address Fields
- **Source Address:** Specifies source IP address.
- **Destination Address:** Specifies destination IP address.
- **Analogy:** Like sender and receiver's contact information found on envelope.

##### Options Field
- **Status:** Not required, commonly used for network troubleshooting rather than common traffic.
- **Effect:** If used, header length increases.
- **Analogy:** Like purchasing postal insurance for envelope.

##### Data Section
- **Location:** At end of packet header.
- **Content:** Packet's data resides here.
- **Analogy:** Like text in email message.

### Investigate Packet Details

#### IPv6
- **Adoption:** Increasing because of large address space.
- **Header fields:** Eight fields in header.

##### IPv6 Header Fields
- **Version:** Indicates IP version (IPv6 for IPv6 header).
- **Traffic Class:** Similar to IPv4 Type of Service field.
    - **Function:** Provides information about packet's priority or class to help with packet delivery.
- **Flow Label:** Identifies packets of a flow.
    - **Flow definition:** Sequence of packets sent from specific source.
- **Payload Length:** Specifies length of data portion of packet.
- **Next Header:** Indicates type of header that follows IPv6 header (such as TCP).
- **Hop Limit:** Similar to IPv4 Time to Live field.
    - **Function:** Limits how long packet can travel in network before being discarded.
- **Source Address:** Specifies source address of sender.
- **Destination Address:** Specifies destination address of receiver.

#### Wireshark

##### Display Filters
- **Function:** Let you apply filters to packet capture files.
- **Usefulness:** Helpful when inspecting packet captures with large volumes of information.
- **Purpose:** Help find specific information most relevant to investigation.
- **Filtering options:** Can filter packets based on protocols, IP addresses, ports, and virtually any other property found in packet.
- **Focus:** Display filtering syntax and filtering for protocols, IP addresses, and ports.

##### Comparison Operators
- **Use:** Different comparison operators to locate specific header fields and values.
- **Expression:** Can be expressed using either abbreviations or symbols.
- **Example:** `ip.src == 8.8.8.8` is identical to `ip.src eq 8.8.8.8`.

##### Comparison Operators Table
- **Equal:** `==` or `eq`
- **Not equal:** `!=` or `ne`
- **Greater than:** `>` or `gt`
- **Less than:** `<` or `lt`
- **Greater than or equal to:** `>=` or `ge`
- **Less than or equal to:** `<=` or `le`

##### Pro Tip
- **Combination:** Can combine comparison operators with Boolean logical operators like `and` and `or` to create complex display filters.
- **Parentheses:** Can be used to group expressions and prioritize search terms.

##### Contains Operator
- **Function:** Used to filter packets that contain exact match of string of text.
- **Example:** Filter that displays all HTTP streams matching keyword "moved".

##### Matches Operator
- **Function:** Used to filter packets based on regular expression (regex) specified.
- **Regex definition:** Sequence of characters that forms a pattern.
- **Note:** More about regular expressions explored later in program.

##### Filter Toolbar
- **Function:** Apply filters to packet capture using Wireshark's filter toolbar.
- **Example:** `dns` filter means Wireshark will only display packets containing DNS protocol.

#### Filtering Methods

##### Filter for Protocols
- **Method:** One of simplest ways to use display filters.
- **Process:** Simply enter name of protocol to filter.
- **Example:** To filter for DNS packets, type `dns` in filter toolbar.
- **Protocols you can filter for:**
    - dns
    - http
    - ftp
    - ssh
    - arp
    - telnet
    - icmp

##### Filter for IP Address
- **Method:** Use display filters to locate packets with specific IP address.
- **General filter:** `ip.addr == [IP address]`
- **Source filter:** `ip.src == [source IP address]`
- **Destination filter:** `ip.dst == [destination IP address]`
- **Examples:**
    - `ip.addr == 172.21.224.2`
    - `ip.src == 10.10.10.10`
    - `ip.dst == 4.4.4.4`

##### Filter for MAC Address
- **Method:** Filter packets according to Media Access Control (MAC) address.
- **MAC address:** Unique alphanumeric identifier assigned to each physical device on network.
- **Example:** `eth.addr == 00:70:f4:23:18:c4`

##### Filter for Ports
- **Method:** Filter packets based on port numbers.
- **Usefulness:** Helpful when isolating specific types of traffic.
- **DNS example:** DNS traffic uses TCP or UDP port 53.
- **Examples:**
    - UDP port: `udp.port == 53`
    - TCP port: `tcp.port == 25`

##### Follow Streams
- **Function:** Wireshark feature that lets you filter for packets specific to protocol and view streams.
- **Stream definition:** Exchange of data between devices using protocol.
- **Benefit:** Wireshark reassembles data transferred in stream in way that's simple to read.

### Packet Captures with tcpdump

#### tcpdump Overview
- **Definition:** Popular network analyzer.
- **Installation:** Pre-installed on many Linux distributions.
- **Compatibility:** Can be installed on most Unix-like operating systems (like macOS).
- **Capability:** Can easily capture and monitor network traffic such as TCP, IP, ICMP, and many more.
- **Interface:** Command line tool (no graphical user interface).
- **Power:** Command line is very powerful and efficient tool.

#### tcpdump Functionality
- **Options and flags:** Can apply options and flags to commands to easily filter network traffic.
- **Filtering capability:** Can filter for specific IP address, protocol, or port number.
- **Purpose:** Find exactly what you're looking for in network traffic.

#### Simple tcpdump Command Example
- **Command:** `sudo tcpdump -i any -v -c 1`
- **Note:** Computer's traffic may appear different when using this command.

##### Command Breakdown
- **sudo:** Used because Linux account doesn't have permission to run tcpdump.
- **tcpdump:** Starts tcpdump.
- **-i:** Specifies which interface to sniff traffic on.
- **-v:** Stands for verbose (displays detailed packet information).
- **-c:** Stands for count (specifies how many packets tcpdump will capture).
- **1:** Specifies one packet.

#### Output Analysis

##### Initial Information
- **Listening:** tcpdump tells us it's listening on any available network interfaces.
- **Additional info:** Provides capture size and other details.

##### Packet Information Fields

###### Timestamp
- **Location:** First field.
- **Content:** Specific time of packet travel.
- **Format:** Hours, minutes, seconds, and fractions of a second.
- **Usefulness:** Especially helpful during incident investigation.
- **Purpose:** Determine timelines and correlate traffic.

###### IP Version Field
- **Content:** Listed as IP (means IPv4).
- **Verbose option:** Gives more details about IP packet fields.
- **Details include:** Protocol type and length of packet.

##### IP Packet Fields

###### ToS (Type of Service)
- **Function:** Tells if certain packets should be treated with different care.
- **Representation:** Value in hexadecimal.

###### TTL (Time to Live)
- **Function:** Tells how long packet can travel across network before getting dropped.

###### Fragmentation Fields
- **Three fields:** Identification, Offset, and Flags.
- **Purpose:** Provide information relating to fragmentation.
- **Function:** Provide instructions on how to reassemble packets in correct order.
- **Example:** DF beside flags stands for Don't Fragment.

###### Protocol Field
- **Function:** Specifies protocol in use.
- **Content:** Provides value corresponding to protocol.
- **Example:** TCP represented by number 6.

###### Length Field
- **Function:** Total Length of packet including IP header.

##### Communication Information
- **IP addresses:** Can observe IP addresses communicating with each other.
- **Direction:** Arrow indicates direction of traffic flow.
- **Port information:** Last piece of IP address indicates port number or name.

##### Checksum Field
- **Function:** Corresponds to Header Checksum.
- **Purpose:** Stores value used to determine if any errors occurred in header.
- **Status:** "Correct" indicates no errors.

##### TCP Fields
- **Flags:** Indicate TCP flags.
- **P flag:** Push flag.
- **Period:** Indicates ACK flag.
- **Meaning:** Packet is pushing out data.
