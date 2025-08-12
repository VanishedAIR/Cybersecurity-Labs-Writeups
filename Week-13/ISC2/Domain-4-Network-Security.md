# Domain 4: Network Security

## What is Networking

- **Network:** Two or more computers linked together to share data, information, or resources

## Types of Networks

- **Local Area Network (LAN):** Spans single floor or building; limited geographical area
- **Wide Area Network (WAN):** Long-distance connections between geographically remote networks

## Network Devices

- **Hubs:** Connect multiple devices; less common in business networks; wired devices, not as smart as switches/routers
- **Switch:** Intelligent hub that knows device addresses and routes traffic to specific ports/devices
  - More efficient than hubs; creates separate broadcast domains with VLANs
- **Router:** Controls traffic flow; connects similar networks; wired or wireless; determines most efficient route
- **Firewall:** Essential for managing/controlling network traffic; filters based on defined rules/filters/access control lists
  - Deployed between private network and internet, or between departments
- **Server:** Computer providing information to other computers on network
  - Examples: web, email, print, database, file servers
  - Secured differently than workstations
- **Endpoint:** Ends of network communication link
  - One end: server with resource; other end: client making request
  - Can be server, workstation, laptop, tablet, mobile phone, or other end user device

## Other Networking Terms

- **Ethernet (IEEE 802.3):** Standard defining wired connections; ensures disparate devices can communicate over same cables
- **Device Address:**
  - **MAC Address:** Unique hardware address (e.g., 00-13-02-1F-58-F5)
    - First 3 bytes (24 bits) denote vendor/manufacturer
    - No two devices can have same MAC address in same local network
  - **IP Address:** Logical address assigned to network interface
    - Examples: 192.168.1.1 and 2001:db8::ffff:0:1
    - Maintains communications when physical device is swapped

## What is WiFi

- **Wireless Networking:** Popular method for corporate and home systems due to ease of deployment and low cost
- **Range:** Generally wide enough for most homes/small offices; range extenders can expand coverage for larger campuses
- **Evolution:** Wi-Fi standard continuously improves with each version being faster than the last
- **Security Consideration:** 
  - Wired LAN: threat actors need physical access (sniffer taps, USB devices, physical media access)
  - Wireless: intrusions can happen at a distance without physical access

## Microsegmentation

- **Purpose:** Protects against modern cyber attacks that bypass static controls and move between systems
- **Design Requirement:** Understand protection needs for internal data center traffic and internet traffic flows
- **Avoid Infrastructure-Centric Design:** More efficient service delivery and better at detecting/preventing advanced persistent threats

### Microsegmentation Characteristics

- **Granular Control:** Rules applied to individual machines/users with detailed restrictions
  - Examples: IP address limits, time-of-day restrictions, credential requirements, service limitations
- **Logical Rules:** No physical hardware changes or manual device interaction required
- **Defense-in-Depth:** Ultimate end state; no single access point leads to broader compromise
- **Shared Environments:** Crucial for cloud where multiple customers share devices and third-party personnel have access
- **Business Function Isolation:** Enforces least privilege by limiting communication between business units
  - Example: HR data (salary, medical records) isolated from other departments
- **Technology Enablers:** Virtualization and software-defined networking (SDN)
  - Cloud tools: "virtual private networks (VPN)" or "security groups"
  - Home use: Separate computers from smart TVs, appliances, HVAC systems

## Intrusion Detection Systems (IDS)

- **Intrusion:** Attacker bypasses security mechanisms to gain access to organization's resources
- **Purpose:** Automates inspection of logs and real-time system events to detect intrusion attempts and system failures
- **Role:** Part of defense-in-depth security plan; works with and complements other security mechanisms (firewalls)
- **Detection Capabilities:** Recognizes external attacks (internet) and internal attacks (malicious worms)
- **Response:** Sends alerts/raises alarms; provides timely and accurate response to intrusions
- **Types:**
  - **Host-based IDS (HIDS):** Monitors single computer/host
  - **Network-based IDS (NIDS):** Monitors network traffic patterns

### Host-based IDS (HIDS)

- **Monitoring:** Activity on single computer including process calls and system/application/security/firewall logs
- **Advantages:** More detailed event examination; can pinpoint compromised files; track attacker processes
- **Detection:** Can detect host system anomalies that NIDS cannot (e.g., remote control infections)
- **Management:** More costly due to administrative attention required on each system
- **Limitation:** Cannot detect network attacks on other systems

### Network-based IDS (NIDS)

- **Monitoring:** Network activity to detect attacks or event anomalies
- **Limitation:** Cannot monitor encrypted traffic content but can monitor other packet details
- **Deployment:** Single NIDS can monitor large network using remote sensors at key locations
- **Sensor Locations:** Routers, firewalls, network switches with port mirroring, network taps
- **Performance:** Minimal negative effect on network performance
- **Detection:** Can detect attack initiation/ongoing attacks but not always attack success details

### Security Information and Event Management (SIEM)

- **Purpose:** Collect information from many disparate sources to examine overall security and streamline security efforts
- **Function:** Gather log data from various enterprise sources to understand potential security concerns
- **Integration:** Used with other components as part of defense-in-depth information security program

## Preventing Threats

- **Patch Management:** Keep systems and applications updated with vendor patches for bugs and security flaws
- **Intrusion Detection/Prevention Systems:** Observe activity, detect threats, provide alerts, and often block/stop attacks
- **Firewalls:** Prevent many types of threats
  - Network-based: protect entire networks
  - Host-based: protect individual systems
- **Remove Unneeded Services/Protocols:** Attackers cannot exploit vulnerabilities in services/protocols that aren't running
- **Anti-malware Software:** Primary countermeasure for malware protection

### Antivirus

- **Best Practice:** Strongly encouraged and required for PCI DSS compliance
- **Enterprise Solutions:** Many products available that integrate with other security products
- **Detection Methods:** Signature-based identification, abnormal activity detection, pattern recognition, machine learning algorithms
- **Modern Solutions:** Beyond virus protection; detect rootkits, ransomware, spyware; include software firewalls and IDS/IPS

### Scans

- **Purpose:** Evaluate effectiveness of security controls within organization
- **Reveals:** Insufficient patches/security settings, new vulnerabilities, ineffective security policies
- **Risk:** Attackers can exploit any of these vulnerabilities

### Firewalls

- **Origin:** Computer security engineers borrowed name for devices that isolate network segments
- **Function:** Enforce policies by filtering network traffic based on rules
- **Placement:** Always at internet gateways; other locations based on network zoning and sensitivity segregation
- **Evolution:** Rapidly evolved to provide enhanced security capabilities
- **Next-Generation Features:** Proxy services, IPS, tight IAM integration, traffic management at Layers 2, 3, and 7
- **Traditional Implementation:** Control traffic at Layer 4

### Intrusion Prevention System (IPS)

- **Type:** Active IDS that automatically detects and blocks attacks before they reach target systems
- **Key Difference from IDS:** Placed in-line with traffic; all traffic must pass through
- **Function:** Analyzes traffic and chooses what to forward/block; prevents attacks from reaching targets
- **Effectiveness:** Most effective at preventing network-based attacks; commonly integrated into firewalls
- **Types:** Network-based IPS (NIPS) and Host-based IPS (HIPS)

## Network Segmentation (Demilitarized Zone)

- **Purpose:** Effective way to achieve defense in depth for distributed or multitiered applications
- **DMZ:** Common security architecture practice using demilitarized zone
- **Implementation:** Host systems accessible through firewall are physically separated from internal network
  - Methods: secured switches or additional firewall controlling traffic between web server and internal network
- **Application DMZs:** Semi-trusted networks limiting access to application servers
  - Only networks/systems with legitimate need can connect

## Virtual Private Network (VPN)

- **Definition:** Point-to-point connection between two hosts allowing communication
- **Security:** Not inherently encrypted; security depends on selected and correctly configured protocols
- **Purpose:** Provides trusted path over untrusted networks (like internet)
- **Remote Access:** Users access organization's network with most resources available as if physically at office
- **Site-to-Site:** Alternative to expensive dedicated connections; gateway-to-gateway VPNs for secure transmission between sites or business partners

## Redundancy

- **Concept:** Design systems with duplicate components to provide backup if failure occurs
- **Data Center Application:** Risk assessments should identify when multiple separate utility service entrances are needed
- **Full Redundancy Requirements:**
  - Devices with two power supplies connected to diverse power sources
  - Power sources backed up by batteries and generators
- **High-Availability Environment:** Even generators are redundant and fed by different fuel types

## Security of the Network

- **TCP/IP Vulnerabilities:** Numerous vulnerabilities in improperly implemented TCP/IP stacks across operating systems
- **Attack Types:**
  - DoS/DDoS attacks
  - Fragment attacks
  - Oversized packet attacks
  - Spoofing attacks
  - Man-in-the-middle attacks
- **Passive Attacks:** TCP/IP and most protocols subject to monitoring/sniffing
- **Network Monitoring/Sniffing:** Monitoring traffic patterns to obtain network information

## Service Models

- **Cloud Security:** Organizations must ensure security controls prevent unauthorized data access
- **Responsibility Levels:** Varying levels for maintaining assets, functionality, and system/application patches
- **Provider vs Consumer:** Cloud service provider or consumer may be responsible depending on service model

### Cloud Service Models

- **Software as a Service (SaaS):** Provider owns/manages hardware, OS, and applications; customer owns data
  - Examples: Gmail, Salesforce, Microsoft 365
  - Customer responsibility: Data and user access
- **Platform as a Service (PaaS):** Provider manages hardware, OS, and platform; customer manages applications and data
  - Examples: AWS Elastic Beanstalk, Google App Engine, Microsoft Azure
  - Customer responsibility: Applications, data, and user access
- **Infrastructure as a Service (IaaS):** Provider manages hardware and virtualization; customer manages OS, applications, and data
  - Examples: AWS EC2, Google Compute Engine, Microsoft Azure Virtual Machines
  - Customer responsibility: OS, applications, data, and user access

## Managed Service Provider (MSP)

- **Definition:** Company that manages information technology assets for another company
- **Common Use:** Small and medium-sized businesses outsourcing part or all of IT functions
- **Services:** Day-to-day operations, expertise in areas company lacks, network/security monitoring and patching
- **Modern MSPs:** Offer cloud-based services augmenting SaaS solutions with active incident investigation and response
- **Example Service:** Managed Detection and Response (MDR) - vendor monitors firewall and security tools for event triaging

## Cloud

- **Definition:** Internet-based computing resources sold as a service by cloud service providers (CSPs)
- **Analogy:** Similar to electrical/power grid - provisioned geographically, sourced through non-obvious means, available via standard interface, pay-per-use
- **Characteristics:** Scalable, elastic, and easy-to-use for provisioning and deploying IT services
- **Standards:** Various definitions per leading standards including NIST; NIST definition commonly used globally by professionals

## Service-Level Agreement (SLA)

- **Definition:** Agreement between cloud service provider and customer setting quality of cloud services delivered
- **Basis:** Cloud computing-specific terms and measurable properties (business and technical)
- **Roles Defined:** Cloud service customer, provider, and related sub-roles
- **Nature:** Combination of rule book and legal contract; crucial business document
- **Content:** Minimum levels of service, availability, security, controls, processes, communications, support, and other business elements
- **Purpose:** Document specific parameters, minimum service levels, and remedies for failure to meet requirements
- **Data Provisions:** Affirm data ownership and specify data return and destruction details

### Other Important SLA Points

- **Infrastructure & Security:** Cloud system infrastructure details and security standards
- **Service Terms:** Rights and costs for continuing/discontinuing service use
- **Performance:** Service availability and performance metrics
- **Data Protection:** Data security, privacy, location, access, and portability
- **Compliance:** Customer right to audit legal and regulatory compliance by CSP
- **Business Continuity:** Disaster recovery processes
- **Operations:** Problem identification/resolution expectations, change management processes
- **Dispute Resolution:** Mediation processes and exit strategy


