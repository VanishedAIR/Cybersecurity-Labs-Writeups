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

## Memorandum of Understanding (MOU) / Memorandum of Agreement (MOA)

- **Purpose:** Organizations minimize downtime and enhance Business Continuity (BC) and Disaster Recovery (DR) capabilities
- **Agreement:** If one party experiences emergency and cannot operate in their facility, the other party shares resources
- **Participants:** Often include competitors because facilities/resources meet industry needs
- **Example:** Hospital A and Hospital B (competitors) agree to share facilities during emergencies
  - Can send personnel and systems to work in other hospital during interruptions
  - Compete on service, price, and customer loyalty, not safety/security
- **Names:** Joint operating agreements (JOA), memoranda of understanding (MOU), or memoranda of agreement (MOA)
- **Regulatory:** Sometimes mandated by requirements or part of administrative safeguards
- **Difference from SLA:** MOU/MOA more directly related to what can be done with system/information
- **SLA Granularity:** Specifies intricate service aspects (e.g., two technicians available Monday-Friday, 10-minute backup access)
- **Caution:** Must understand exactly what is agreed to; legal team should review conditions before signing

## Ports and Protocols (Applications/Services)

- **Physical Ports:** Hardware interfaces on devices (routers, switches, servers, computers) for connecting cables (e.g., fiber, Cat5).
- **Logical Ports:** Software-defined endpoints (sockets) used for network communications.
  - Ports allow a single IP to handle multiple connections using different port numbers.
  - Example: HTTP uses port 80, HTTPS uses port 443.
  - Some protocols have both secure and nonsecure ports.
- **Well-known Ports (0–1023):** Reserved for core protocols (e.g., DNS, SMTP, HTTP).
- **Best Practice:** Use the most secure protocol version available.

## Networking Models

- **Purpose:** Enable interconnection and communication between diverse hardware/software for sharing info and collaboration.
- **Key Goals:**
  - Reliable, managed communications between hosts/users.
  - Layer isolation for functions.
  - Packet-based communication.
  - Standardized routing, addressing, and control.
  - Extensible functionality beyond internetworking.
  - Vendor-agnostic, scalable, resilient design.
- **Upper Layer (Host/Application Layer):**
  - Manages connection integrity and session control.
  - Handles data formatting and application communication.
  - Establishes, maintains, and terminates sessions.
- **Lower Layer (Media/Transport Layer):**
  - Receives bits from physical medium and forms frames.
  - Frames are standardized containers for data (like buckets for water).
  - Adds routing info to create packets.
  - Prepares data for delivery to the host layer.

## Network Design

- **Objective:** Meet data communication needs and ensure efficient network performance.

## Network Segmentation

- **Definition:** Controls traffic between networked devices.
  - Complete/physical segmentation: network is fully isolated, allowing communication only within the segment.

## Demilitarized Zone (DMZ)

- **DMZ:** Network area accessible to external users but separated from the organization's private network.
  - Commonly hosts public-facing servers (web, email, file, etc.).

## Virtual Local Area Network (VLAN)

- **Virtual Local Area Networks (VLANs):** Allow network administrators to use switches to create software-based LAN segments.
  - Can segregate or consolidate traffic across multiple switch ports.
- **Communication:**
  - Devices on the same VLAN communicate as if on the same Layer 2 network.
  - Traffic between different VLANs must be explicitly enabled.
- **Benefits:**
  - Limits broadcast traffic to the VLAN, reducing congestion and the effectiveness of some attacks.
  - Simplifies administration when users change physical locations or require different service access.
- **Configuration:** Can be based on switch port, IP subnet, MAC address, and protocols.
- **Security Warning:** VLANs do not guarantee security, as attacks like "VLAN hopping" can allow users to see traffic from other VLANs.
- **Summary:** VLANs logically segment a network without changing its physical structure, improving management and limiting broadcast domains.

## TCP/IP Protocol Architecture

- **Background:** TCP/IP was developed in the early 1970s, before the OSI model, and is the most widely used protocol suite today.
- **TCP/IP Stack:** Not a single protocol, but a suite of protocols based on open standards; platform-independent and widely supported.
  - **Drawback:** Consumes significant resources and was designed for usability, not security, making it easier to attack.
- **Layers:**
  - **Application Layer:** Defines protocols for the transport layer (e.g., Telnet, FTP, SMTP, DNS).
  - **Transport Layer:** Moves data between devices; main protocols are TCP (connection-oriented, full-duplex) and UDP (connectionless, simplex).
  - **Internet Layer:** Responsible for creating and inserting packets; includes protocols like ICMP.
    - **ICMP:** Used for network health checks (e.g., ping, traceroute).
      - `ping` uses ICMP echo packets to test connectivity and response time.
  - **Network Interface Layer:** Handles how data moves through the network.

## Segmentation for Embedded Systems and IoT

- **Embedded Systems:** Computers built into larger products, focused on specific functions (e.g., network printers, smart TVs, HVAC controls, medical devices).
- **Network-Enabled Devices:** Any device with built-in network capabilities, often wireless (e.g., smartphones, tablets, smart TVs, streaming devices, game systems).
- **Internet of Things (IoT):** Collection of devices that communicate over the internet to monitor or control the real world (smart-home equipment, industrial controls).
- **Security Considerations:**
  - Embedded and IoT devices often control physical mechanisms, so breaches can cause real-world harm.
  - Devices may have multiple access methods (Ethernet, Wi-Fi, Bluetooth), increasing risk.
  - Special care is needed to isolate these devices from the rest of the network.
- **Segmentation Methods:**
  - Use VLANs, MAC/IP address filtering, physical ports, protocols, application filtering, routing, and access control to separate IoT/embedded devices.
  - Logical network segmentation helps prevent malicious access and limits attack impact.

## On-Premises Data Centers

- **Ownership:** Organizations can own (on-premises) or outsource data centers.
- **Physical Requirements:** Need a dedicated building/space, power, HVAC, fire suppression, and redundancy.

### 1. Data Center/Closets

- **Wiring Infrastructure:** Critical for security and reliability; physical access must be protected to prevent damage.
- **Components:** May include phone/network connections, ISP/telecom equipment, servers, wiring, and switches.
- **Cooling:** High-density/enclosed equipment needs adequate airflow and cooling.
  - Recommended temp: 64°–81°F (18°–27°C).
  - Use three sensors (top, middle, bottom) per rack to monitor temps.

### 2. HVAC / Environmental

- **Airflow:** Control contaminants (dust, fumes) to protect equipment.
- **Monitoring:** Integrate water/gas leak, sewer overflow, and HVAC failure detection with alarms.
- **Contingency Planning:** Prioritize systems to minimize impact of failures on people, operations, and infrastructure.

### 3. Power

- **Power Supply:** Must be constant and consistent; fluctuations reduce lifespan, outages halt operations.
- **Backup:** Generators sized for critical load; batteries bridge gap until generators start.
- **Testing:** Regularly test failover systems to ensure reliability.

### 4. Fire Suppression

- **Considerations:** Choose suppression based on room size, occupancy, exit routes, and equipment risk.
- **Methods:** Water can damage electronics; gas-based systems are safer for equipment but may be hazardous to people.

## Open Systems Interconnection (OSI) Model

- **Purpose:** Provides a standard framework for describing how protocols and network components interact.
- **Structure:** Divides networking into seven layers, each with specific functions to support data exchange between computers.
  - Layers communicate directly with the one above and below.
- **Layer Overview:**
  - **Layer 1: Physical** – Transmits raw binary data over physical media (e.g., Ethernet cables).
  - **Layer 2: Data Link** – Handles frames; includes switches, bridges, WAPs.
  - **Layer 3: Network** – Manages packets and routing; routers operate here.
  - **Layer 4: Transport** – Manages end-to-end connections (TCP/UDP).
  - **Layer 5: Session** – Manages sessions/logical ports (e.g., NetBIOS).
  - **Layer 6: Presentation** – Translates data formats (e.g., JPEG, PNG).
  - **Layer 7: Application** – Closest to the user; interfaces with software applications.
- **Encapsulation:** As data moves down the OSI layers, each layer adds its own header (and sometimes footer), wrapping the previous layer's data.
  - Data unit size increases as it moves down the layers.
- **De-encapsulation:** As data moves up the layers, headers/footers are removed and interpreted, shrinking the data unit.
- **Usage:** The OSI model is a conceptual tool for understanding how different networking technologies and protocols fit together.

## Network Access Control (NAC)

- **Purpose:** Controls and monitors access to the organization's network by enforcing security policies for all connecting devices.
- **Scope:** Applies to both internal (employees, contractors) and external (guests, partners, vendors) users and devices.
- **Modern Challenges:** Includes BYOD (bring your own device) and IoT, expanding the range of devices needing control (e.g., HVAC, cameras, sensors, vending machines).
- **Capabilities:**
  - Enforces access control and security policies (does not create them).
  - Provides network visibility for access security and incident response.
  - Can isolate noncompliant devices in a quarantine network and offer remediation (e.g., enabling endpoint protection).
  - Ensures only compliant devices can join the network.
- **Use Cases:** Medical devices, IoT, BYOD/mobile devices (laptops, tablets, smartphones), guest users, and contractors.
- **Best Practice:** All mobile/temporary devices should be onboarded and checked for compliance each time they connect.

## Deployment Models

- **Public Cloud:** Open to the public, hosted by an external cloud service provider (CSP), shared resource pool, easy access for anyone who pays. Service-level agreements (SLAs) help ensure acceptable service.
- **Private Cloud:** Built and used by a single organization, not shared with the public. Organization is responsible for maintenance, but can also rent resources from third parties. Offers private access to cloud resources.
- **Hybrid Cloud:** Combines two or more cloud models (usually public and private). Lets organizations keep control over critical systems while using public cloud for non-critical workloads. Benefits include flexibility, scalability, cost savings, and reuse of existing investments.
- **Community Cloud:** Built for a specific group or community with shared interests (e.g., industry-specific). Can be public or private, allowing members to share IT resources for common goals.

## Types of Threats

- **Spoofing:** Using a fake identity to gain access (can target IP, MAC, usernames, system names, SSIDs, email, etc.).
- **Denial-of-Service (DoS) / Distributed Denial-of-Service (DDoS):** Overloads a system to prevent legitimate use; DDoS uses many compromised systems.
- **Worms:** Self-propagating malware that spreads without user action.
- **On-Path Attack (Man-in-the-Middle, MITM):** Attacker intercepts or alters communication between two parties.
- **Advanced Persistent Threat (APT):** Highly sophisticated, long-term attacks by organized groups.
- **Malware:** Any program inserted to compromise confidentiality, integrity, or availability, or to disrupt the victim.
- **Phishing:** Tricks users into visiting malicious sites or revealing sensitive info, often via fake emails/links.
- **Virus:** Self-replicating code that spreads with user assistance (e.g., opening files/links); causes damage.
- **Trojan:** Malicious software disguised as legitimate, often used to deliver ransomware or other payloads.
- **Side-Channel Attack:** Passive attack using indirect methods (e.g., power, timing, or fault analysis) to gather info.
- **Insider Threat:** Risk from trusted individuals (employees, contractors) who may act maliciously or be manipulated.
- **Ransomware:** Malware that encrypts files and demands payment for decryption.

## Defense in Depth

- **Concept:** Uses multiple, layered security controls (administrative, technical, physical) to protect assets, similar to layers of a castle.
- **Purpose:** Deters attackers by making compromise more difficult; encourages attackers to move on to easier targets.
- **Layers/Examples:**
  - **Data:** Encryption, data leak prevention, identity/access management, data controls.
  - **Application:** Application firewalls, database monitors, DLP for apps.
  - **Host:** Antivirus, endpoint firewalls, configuration, patch management.
  - **Perimeter:** Gateway firewalls, honeypots, malware analysis, DMZs.
  - **Internal Network:** IDS/IPS, internal firewalls, network access controls.
  - **Physical:** Locks, walls, access control systems.
  - **Policies & Awareness:** Administrative controls, training, procedures to reduce insider threats and identify risks early.
- **Trusted Elements:** Includes trusted admins, developers, update processes, LANs, web apps, facilities, and internal users.

## Internet Protocol (IPv4 and IPv6)

- **IPv4:** 32-bit address, written as four octets (e.g., 192.168.1.1), each 0-255.
  - First octet 0 = network, 255 = broadcast.
  - Address split into network and host parts.
  - Subnets use subnet masks (e.g., 255.255.255.0) to define network portions.
  - Private address ranges (not routable on the internet):
    - 10.0.0.0 – 10.255.255.254
    - 172.16.0.0 – 172.31.255.254
    - 192.168.0.0 – 192.168.255.254
  - 127.0.0.1 is the loopback address for local testing.
- **IPv6:** 128-bit address, written as eight groups of four hex digits (e.g., 2001:db8::ff:0:1).
  - Uses colons (:) as separators; can be shortened by omitting leading zeros and using "::" for consecutive zeros.
  - Vast address space (2^128 addresses).
  - Security: IPsec is mandatory in IPv6.
  - Improved quality of service (QoS) support.
  - Reserved addresses:
    - ::1 is the loopback address (like 127.0.0.1 in IPv4).
    - 2001:db8::/32 for documentation/examples.
    - fc00::/7 for internal/private use (not routable on the internet).

## Secure and Insecure Ports

- **Cleartext Protocols:** Some protocols transmit data unencrypted, making them vulnerable to sniffing attacks (usernames, passwords, files).
- **Best Practice:** Use secure alternatives that encrypt data in transit.

| Insecure Port | Protocol | Description                                   | Secure Alternative                          | Secure Protocol          |
| ------------- | -------- | --------------------------------------------- | ------------------------------------------- | ------------------------ |
| 80            | HTTP     | Web traffic, not encrypted                    | 443                                         | HTTPS (TLS)              |
| 445           | SMB      | Windows file sharing, unencrypted             | 2049 (recommended: block both at perimeter) | NFS (can use encryption) |
| 21            | FTP      | File transfer, sends credentials in plaintext | 22                                          | SFTP                     |
| 23            | Telnet   | Remote terminal, plaintext                    | 22                                          | SSH                      |
| 25            | SMTP     | Email sending, unencrypted                    | 587                                         | SMTP with TLS            |
| 37            | Time     | Legacy time sync                              | 123                                         | NTP                      |
| 53            | DNS      | Domain name resolution, unencrypted           | 853                                         | DNS over TLS (DoT)       |
| 143           | IMAP     | Email retrieval, unencrypted                  | 993                                         | IMAP with SSL/TLS        |
| 161/162       | SNMP     | Network management, sensitive info            | 161/162                                     | SNMPv3 (encrypted)       |
| 389           | LDAP     | Directory services, unencrypted               | 636                                         | LDAPS (SSL/TLS)          |

- **Notes:**
  - SSL is deprecated; use TLS 1.3 or higher for secure web traffic.
  - SNMPv3 uses the same ports as earlier versions but adds encryption and security features.
  - Avoid allowing insecure protocols through firewalls, especially at the network perimeter.
