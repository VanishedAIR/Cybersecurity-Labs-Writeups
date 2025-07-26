# Play It Safe: Manage Security Risks

## Module 1

### Explore the CISSP security domains, Part 1

**Domain 1: Security and Risk Management**

**Key Focus Areas:**

1. **Defining Security Goals and Objectives:**

    - Reduce risks to critical assets and data (including PII)
    - Establish clear security priorities and targets
    - Align security objectives with business goals

2. **Risk Mitigation:**

    - Implement procedures and rules to quickly reduce impact of risks
    - Develop rapid response capabilities for security incidents
    - Establish preventive measures against potential breaches

3. **Compliance:**

    - Primary method for developing internal security policies
    - Meet regulatory requirements and independent standards
    - Ensure adherence to legal and industry frameworks

4. **Business Continuity:**

    - Maintain everyday productivity during disruptions
    - Establish risk disaster recovery plans
    - Ensure operational resilience against security incidents

5. **Legal Regulations:**
    - Follow rules and expectations for ethical behavior
    - Minimize negligence, abuse, or fraud
    - Comply with worldwide security laws (goals are similar globally)

**Domain 2: Asset Security**

**Focus:** Securing digital and physical assets through proper data lifecycle management

**Key Components:**

-   **Data Storage:** Secure handling of PII and SPII on computers and networks
-   **Data Maintenance:** Ongoing protection during data use and updates
-   **Data Retention:** Proper policies for how long data is kept
-   **Data Destruction:** Secure disposal methods (e.g., hard drive destruction oversight)

**Critical Principles:**

-   Know what data you have and who has access to it
-   Protect assets whether stored, transferred, or physically collected
-   Strong security posture mitigates risk to critical assets
-   Prevent threat actor access to disposed data

**Domain 3: Security Architecture and Engineering**

**Focus:** Optimizing data security through effective tools, systems, and processes

**Core Concept - Shared Responsibility:**

-   All individuals within organization take active role in lowering risk
-   Maintain both physical and virtual security collectively
-   Encourage users to recognize and report security concerns
-   Enable quick and effective issue handling through user participation

**Domain 4: Communication and Network Security**

**Focus:** Managing and securing physical networks and wireless communications

**Protection Scope:**

-   On-site networks and data
-   Cloud-based communications
-   Remote service connections

**Remote Work Security Example:**

-   Employees in public spaces face vulnerabilities from insecure Bluetooth and public WiFi
-   Security teams remove organizational access to insecure communication channels
-   Discourage insecure behavior that threat actors could exploit
-   Implement policies that protect remote workers from network-based threats

**Domain Integration:**
These four domains work together to create comprehensive organizational security covering policy, assets, architecture, and communications.

### Explore the CISSP security domains, Part 2

**Domain 5: Identity and Access Management (IAM)**

**Focus:** Access and authorization to keep data secure through established user policies

**Primary Goal:** Reduce overall risk to systems and data by limiting user access to what employees need

**Risk Example:**

-   Shared administrator logins prevent tracking individual user access
-   During breaches, impossible to separate valid user activity from threat actor activity

**Four Main IAM Components:**

1. **Identification:**

    - User verifies identity through username, access card, or biometric data (fingerprint)
    - Establishes who is requesting access

2. **Authentication:**

    - Verification process to prove identity (password, PIN entry)
    - Confirms the user is who they claim to be

3. **Authorization:**

    - Occurs after identity confirmation
    - Determines level of access based on organizational role
    - Role-based access control implementation

4. **Accountability:**
    - Monitoring and recording user actions (login attempts, data access)
    - Proves systems and data are used properly
    - Audit trail for compliance and investigation

**Domain 6: Security Assessment and Testing**

**Focus:** Conducting security control testing, data analysis, and security audits

**Key Activities:**

**Security Control Testing:**

-   Identify new and better ways to mitigate threats, risks, and vulnerabilities
-   Examine organizational goals and objectives
-   Evaluate if current controls achieve stated goals

**Data Collection and Analysis:**

-   Regular security data analysis prevents threats and risks
-   Use testing evaluations and assessment reports for improvements
-   Implement new controls based on findings

**Example Implementation:**
Multi-factor authentication requirement to better protect against potential threats and risks

**Domain 7: Security Operations**

**Focus:** Conducting investigations and implementing preventative measures

**Investigation Process:**

1. **Incident Identification:** Heightened urgency to minimize organizational risks
2. **Active Attack Response:** Mitigate attack and prevent escalation to protect private information
3. **Threat Neutralization:** Stop immediate threat and secure environment
4. **Evidence Collection:** Gather digital and physical evidence for forensic investigation

**Digital Forensic Investigation:**

-   Identify when, how, and why breach occurred
-   Determine areas for improvement
-   Develop preventative measures for future attacks

**Domain 8: Software Development Security**

**Focus:** Using secure coding practices throughout development lifecycle

**Secure Coding Practices:**

-   Recommended guidelines for creating secure applications and services
-   Security integrated as additional step in software development lifecycle

**Security Integration by Phase:**

-   **Design Phase:** Secure design reviews
-   **Development/Testing Phase:** Secure code reviews
-   **Deployment/Implementation Phase:** Penetration testing

**Benefits:**

-   Security embedded at every step
-   Software remains secure with protected sensitive data
-   Mitigates unnecessary organizational risk

**Complete CISSP Framework Summary:**
All 8 domains provide comprehensive security coverage from governance and risk management through technical implementation and operations, ensuring organizations can protect assets, data, and operations against evolving threats.

### Threats, risks, and vulnerabilities

**Threat:**

-   Any circumstance or event that can negatively impact assets
-   Example: Social engineering attacks that manipulate human error to gain private information, access, or valuables
-   Phishing: Malicious links in emails appearing from legitimate sources to acquire sensitive data (usernames, passwords, banking information)

**Risk:**

-   Anything that can impact confidentiality, integrity, or availability of an asset
-   The likelihood of a threat occurring
-   Example: Lack of backup protocols for data recovery during accidents or security incidents

**Risk Rating Levels:**

**Low-Risk Assets:**

-   Information that wouldn't harm organization's reputation, operations, or finances if compromised
-   Examples: Public information (website content, published research data)

**Medium-Risk Assets:**

-   Non-public information that may cause some damage to finances, reputation, or operations
-   Example: Early release of quarterly earnings affecting stock value

**High-Risk Assets:**

-   Information protected by regulations or laws
-   Severe negative impact on finances, operations, or reputation if compromised
-   Examples: SPII, PII, intellectual property

**Vulnerability:**

-   A weakness that can be exploited by a threat
-   **Critical principle:** Both vulnerability AND threat must be present for risk to exist

**Common Vulnerability Examples:**

-   Technical: Outdated firewalls, software, or applications
-   Authentication: Weak passwords
-   Data protection: Unprotected confidential data
-   Human factors: People's actions affecting internal networks

**Human Vulnerabilities:**

-   Clients, external vendors, employees can all be vulnerabilities
-   People's actions significantly affect organizational security
-   Security requires united effort across all stakeholders

**Risk Formula:**
Risk = Threat + Vulnerability + Asset Value

**Security Strategy:**
Understanding the relationship between threats, risks, and vulnerabilities enables organizations to prioritize security efforts and allocate resources effectively based on potential impact and likelihood.

### Ransomware and Web Layers

**Ransomware:**

-   Malicious attack where threat actors encrypt organization's data and demand payment for access restoration
-   Impact: Freezes network systems, renders devices unusable, locks confidential data
-   Process: Attack → Encryption → Ransom demand → Decryption key provided after payment
-   **Decryption key:** Password provided to regain access to encrypted data

**Web Layers:**
The web consists of three interconnected layers:

**Surface Web:**

-   Layer most people use regularly
-   Content accessible using standard web browsers
-   Includes social media, online shopping, public websites

**Deep Web:**

-   Requires authorization to access
-   Example: Organization intranets accessible only to employees or authorized users
-   Private but not necessarily malicious content

**Dark Web:**

-   Accessible only through special software
-   Carries negative connotation due to criminal preference
-   Provides secrecy for illegal activities
-   Used for ransom negotiations and data leaks by threat actors

### Three Key Impacts of Security Threats

**1. Financial Impact:**

-   **Interrupted Production and Services:** Business operations disrupted during attacks
-   **Correction Costs:** Expenses to remediate security incidents and restore systems
-   **Compliance Fines:** Penalties for non-compliance with laws and regulations when assets are compromised
-   **Example:** Malware attacks causing significant financial consequences across multiple areas

**2. Identity Theft:**

-   **Data Storage Decisions:** Organizations must evaluate what private data to store and retention periods
-   **Risk Assessment:** Storing sensitive data (PII, SPII) presents inherent organizational risk
-   **Dark Web Sales:** Sensitive data can be sold or leaked through dark web channels
-   **Legal Consequences:** Threat actors may avoid legal consequences due to dark web secrecy

**3. Reputation Damage:**

-   **Customer Base Impact:** Solid customer relationships support organization's mission, vision, and financial goals
-   **Competitive Loss:** Exploited vulnerabilities drive customers to competitors
-   **Permanent Damage:** Bad press can cause lasting harm to organizational reputation
-   **Legal Ramifications:** Customer data loss results in legal penalties, fines, and ongoing financial impact

**Security Prevention Strategy:**

-   Take proper security measures and follow established protocols
-   Use comprehensive security toolkit approach
-   Prepare security teams to handle events like ransomware attacks
-   Implement layered defenses to prevent significant impact from threats, risks, and vulnerabilities

**Risk Management Principle:**
Prevention through comprehensive security measures is more cost-effective than responding to successful attacks that cause financial, identity theft, and reputational damage.

### NIST Risk Management Framework (RMF)

**Framework Overview:**
NIST provides frameworks for managing risks, threats, and vulnerabilities. The Risk Management Framework (RMF) consists of seven steps that security professionals use to systematically address organizational security challenges.

**Entry-Level Analyst Perspective:**
While analysts may not engage in all steps, understanding the framework provides foundational knowledge for risk mitigation and management, setting candidates apart in job searches.

### Seven Steps of NIST RMF

**Step 1: Prepare**

-   Activities necessary to manage security and privacy risks before breaches occur
-   **Analyst Role:** Monitor for risks and identify controls to reduce those risks
-   Proactive risk management approach

**Step 2: Categorize**

-   Develop risk management processes and tasks
-   Consider how confidentiality, integrity, and availability of systems/information can be impacted by risk
-   **Analyst Role:** Follow organizational processes to reduce risks to critical assets (e.g., private customer information)

**Step 3: Select**

-   Choose, customize, and capture documentation of controls that protect organization
-   **Analyst Role:** Keep playbooks up-to-date and manage documentation for efficient issue resolution
-   Ensure proper control documentation and maintenance

**Step 4: Implement**

-   Execute security and privacy plans for the organization
-   Essential for minimizing impact of ongoing security risks
-   **Example:** Notice pattern of constant password resets → Implement password requirement changes to solve issue

**Step 5: Assess**

-   Determine if established controls are implemented correctly
-   Analyze whether protocols, procedures, and controls meet organizational needs
-   **Analyst Role:** Identify potential weaknesses and determine if tools, procedures, controls, and protocols need changes for better risk management

**Step 6: Authorize**

-   Be accountable for security and privacy risks that may exist in organization
-   **Analyst Role:** Generate reports, develop action plans, establish project milestones aligned with security goals
-   Formal accountability for risk management decisions

**Step 7: Monitor**

-   Be aware of how systems are operating
-   Assess and maintain technical operations (daily analyst tasks)
-   **Key Principle:** Maintain low organizational risk by understanding how current systems support security goals
-   **Action Required:** If systems don't meet goals, implement necessary changes

### RMF Implementation Strategy

**Continuous Cycle:**
The RMF is designed as a continuous process where monitoring leads back to preparation for ongoing risk management improvement.

**Organizational Efficiency:**

-   Framework ensures organizations operate as efficiently as possible
-   Regular assessment prevents security gaps
-   Documentation and process improvement support long-term security posture

**Analyst Development:**
Understanding RMF provides entry-level analysts with comprehensive view of organizational security management and career advancement opportunities within risk management roles.

### Common Vulnerabilities

**Vulnerability Definition:**
A weakness that can be exploited by a threat. Organizations must regularly inspect systems for vulnerabilities to maintain security.

### Specific Vulnerability Examples

**ProxyLogon:**

-   Pre-authenticated vulnerability affecting Microsoft Exchange server
-   Allows threat actors to complete user authentication process
-   Enables deployment of malicious code from remote locations
-   Critical impact on email and communication systems

**ZeroLogon:**

-   Vulnerability in Microsoft's Netlogon authentication protocol
-   **Authentication Protocol:** Method to verify person's identity
-   **Netlogon Service:** Ensures user identity before allowing website location access
-   Compromises fundamental authentication mechanisms

**Log4Shell:**

-   Allows attackers to run Java code on victim's computers
-   Enables sensitive information leakage
-   **Remote Attack Capability:** Attackers can take control of internet-connected devices
-   Facilitates malicious code execution across networks

**PetitPotam:**

-   Affects Windows New Technology Local Area Network (LAN) Manager (NTLM)
-   **Theft Technique:** Enables LAN-based attackers to initiate authentication requests
-   Exploits Windows network authentication protocols
-   Facilitates credential theft and lateral movement

**Security Logging and Monitoring Failures:**

-   Insufficient logging and monitoring capabilities
-   **Critical Risk:** Attackers exploit vulnerabilities without organizational detection
-   Prevents timely incident response and threat identification
-   Creates blind spots in security posture

**Server-Side Request Forgery (SSRF):**

-   Manipulates server-side applications to access and update backend resources
-   **Data Theft Capability:** Allows threat actors to steal sensitive information
-   **Backend Access:** Unauthorized interaction with internal systems and databases
-   Bypasses security controls through application manipulation

### Vulnerability Management Strategy

**Regular Inspection Requirements:**

-   Systematic vulnerability scanning and assessment
-   Proactive identification before threat actor exploitation
-   Continuous monitoring for new vulnerability disclosures

**Risk Prioritization:**
Organizations must prioritize vulnerability remediation based on:

-   Potential impact on critical systems
-   Likelihood of exploitation
-   Available patches and mitigations
-   Business continuity requirements

**Defense Strategy:**

-   Implement layered security controls
-   Maintain current patch management programs
-   Monitor for indicators of vulnerability exploitation
-   Develop incident response procedures for vulnerability-based attacks

**Key Principle:**
Vulnerability management is an ongoing process requiring continuous attention, as new vulnerabilities are discovered regularly and threat actors actively seek to exploit known weaknesses.

## Module 2

### Frameworks

**Security Frameworks Definition:**
Guidelines used for building plans to help mitigate risks and threats to data and privacy, including social engineering attacks and ransomware.

**Comprehensive Security Scope:**
Security encompasses both virtual and physical environments, requiring holistic protection strategies.

### Physical Security Integration

**Building Access Controls:**

-   Key card or badge requirements for facility entry
-   Physical barriers to prevent unauthorized access
-   Integration with digital security protocols

**Workplace Safety Plans:**

-   Maintain safe work environments through structured security measures
-   Combine physical and digital security protocols
-   Address both cyber and physical threat vectors

### Framework Applications

**Breach Prevention, Detection, and Response:**

-   Provide structured guidance for comprehensive security lifecycle
-   Particularly important for protecting against social engineering attacks
-   Focus on employee-targeted threats like phishing campaigns

**Human-Centric Security:**

-   **Key Principle:** People are the biggest threat to security
-   Frameworks create plans to increase employee awareness and education
-   Protect organization, co-workers, and individuals simultaneously

### Employee Education and Training

**Security Awareness Programs:**

-   Essential for minimizing breach possibilities
-   Address existing security challenges through education
-   Create security-conscious organizational culture

**Red Flag Recognition Training:**

-   Teach employees to identify potential threats
-   Recognize suspicious activities and communications
-   Develop intuitive threat detection capabilities

**Reporting and Response Procedures:**

-   Establish clear protocols for reporting security issues
-   Ensure rapid response to identified threats
-   Create communication channels for security concerns

### Analyst Responsibilities

**Framework Implementation:**

-   Understand organizational security plans and frameworks
-   Implement established protection protocols
-   Ensure compliance with security procedures

**Stakeholder Protection:**

-   Protect the organization from various security threats
-   Safeguard employees from security incidents
-   Protect people the organization serves (customers, clients, partners)

**Threat Response:**

-   Address social engineering attacks through framework guidance
-   Respond to security breaches using established procedures
-   Prevent harmful security incidents through proactive measures

### Framework Integration Strategy

**Multi-Layered Approach:**

-   Combine technical controls with human awareness
-   Integrate physical and digital security measures
-   Create comprehensive protection against diverse threat vectors

**Continuous Improvement:**

-   Regular updates to address emerging threats
-   Ongoing employee education and awareness programs
-   Adaptation of frameworks based on threat landscape changes

**Organizational Resilience:**
Security frameworks enable organizations to build resilient defenses that address human factors, technical vulnerabilities, and physical security requirements in a coordinated manner.

### Controls

**Security Controls Definition:**
Safeguards designed to reduce specific security risks. While frameworks create plans to address security risks, threats, and vulnerabilities, controls are used to reduce specific risks.

**Importance of Proper Controls:**
Without proper controls, organizations face:

-   Significant financial impacts
-   Reputation damage
-   Exposure to risks (trespassing, fake employee accounts, unauthorized benefits)

### Three Common Types of Security Controls

**1. Encryption**

**Process:** Converting data from readable format to encoded format

-   **Plaintext:** Original, readable data format
-   **Ciphertext:** Raw, encoded message unreadable to humans and computers
-   **Decryption:** Process of converting ciphertext back to original plaintext form

**Purpose:** Ensure confidentiality of sensitive data

-   Customer account information
-   Social security numbers
-   Any data requiring confidentiality protection

**2. Authentication**

**Basic Definition:** Process of verifying who someone or something is

**Basic Authentication:**

-   Username and password login to websites
-   Proves knowledge of credentials for access permission
-   Fundamental identity verification method

**Advanced Authentication - Multi-Factor Authentication (MFA):**

-   Requires password PLUS additional authentication form
-   Additional factors include:
    -   Security codes
    -   Biometrics (fingerprint, voice, face scan)
-   Challenges users to demonstrate they are who they claim to be

**Biometrics:**

-   **Definition:** Unique physical characteristics used to verify person's identity
-   **Examples:** Fingerprint, eye scan, palm scan
-   **Security Risk:** Can be exploited through vishing attacks

**Vishing (Voice Phishing):**

-   Exploitation of electronic voice communication
-   Obtain sensitive information or impersonate known sources
-   **Example:** Impersonate person's voice to steal identity and commit crimes
-   **Threat to Biometrics:** Voice-based biometric systems vulnerable to sophisticated voice impersonation

**3. Authorization**

**Definition:** Concept of granting access to specific resources within a system

-   Verifies person has permission to access a resource
-   Controls what authenticated users can access
-   Implements principle of least privilege

**Real-World Example:**
Entry-level security analyst for federal government:

-   Permission to access deep web data
-   Access to internal data restricted to federal employees only
-   Role-based access control implementation

### The relationship between frameworks and controls

**Framework and Control Integration:**
Security frameworks provide guidelines for building plans to mitigate risks and threats, while security controls are the specific safeguards that implement those plans to reduce security risks.

**Compliance Support:**
Frameworks support organizations' ability to adhere to compliance laws and regulations through structured approaches.

**Example - Healthcare HIPAA Compliance:**

-   **Framework:** HIPAA provides guidelines for protecting patient information
-   **Control:** Multi-factor authentication (MFA) requirement for patients accessing medical records
-   **Result:** Framework + Control = Compliant patient data protection

### Specific Frameworks

**Cyber Threat Framework (CTF)**

**Developer:** U.S. Government (Office of the Director of National Intelligence)

**Purpose:** Provide "a common language for describing and communicating information about cyber threat activity"

**Benefits:**

-   Enables cybersecurity professionals to analyze and share threat information more efficiently
-   Improves organizational response to evolving cybersecurity landscape
-   Standardizes communication about threat actors' tactics and techniques
-   Facilitates better collaboration across security teams and organizations

**ISO/IEC 27001 Framework**

**Scope:** Internationally recognized framework for information security management

**ISO 27000 Family Applications:**

-   Organizations of all sectors and sizes
-   Manage security of various assets:
    -   Financial information
    -   Intellectual property
    -   Employee data
    -   Information entrusted to third parties

**Framework Structure:**

-   Outlines requirements for information security management system
-   Provides best practices and controls
-   Supports organization's ability to manage risks
-   Does not mandate specific controls but provides control collection for security posture improvement

### Security Control Categories

**Control Purpose:**
Used alongside frameworks to reduce possibility and impact of security threats, risks, or vulnerabilities. Controls typically prevent, detect, or correct security issues.

**Physical Controls:**

-   **Perimeter Security:** Gates, fences, and locks
-   **Personnel Security:** Security guards
-   **Surveillance Systems:** CCTV, surveillance cameras, and motion detectors
-   **Access Control:** Access cards or badges to enter office spaces

**Technical Controls:**

-   **Network Security:** Firewalls
-   **Authentication:** Multi-factor authentication (MFA)
-   **Endpoint Protection:** Antivirus software

**Administrative Controls:**

-   **Operational Security:** Separation of duties
-   **Access Management:** Authorization processes
-   **Information Management:** Asset classification

### Control Implementation Strategy

**Layered Defense Approach:**

-   **Physical Controls:** Protect physical assets and facilities
-   **Technical Controls:** Protect digital systems and data
-   **Administrative Controls:** Provide governance and process controls

**Framework-Control Alignment:**

-   Frameworks provide strategic direction and compliance structure
-   Controls provide tactical implementation of security measures
-   Combined approach ensures comprehensive security coverage

**Risk Reduction Model:**
Framework Guidelines → Control Selection → Risk Mitigation → Compliance Achievement

**Best Practices:**

-   Select controls that align with chosen frameworks
-   Implement multiple control types for defense-in-depth
-   Regular assessment of control effectiveness
-   Update controls based on framework evolution and threat landscape changes

**Organizational Benefits:**

-   Structured approach to security management
-   Compliance with regulatory requirements
-   Reduced security risks through systematic implementation
-   Improved security posture through standardized practices

### Explore the CIA triad

**CIA Triad Model:**
A foundational model that helps organizations consider risk when setting up systems and security policies. Entry-level analysts constantly refer to these three core principles to protect organizations and the people they serve.

### Three Core Principles

**Confidentiality:**

-   Only authorized users can access specific assets or data
-   Sensitive data available on "need to know" basis
-   Access limited to people authorized to handle certain assets or data
-   Essential for protecting private and sensitive information

**Integrity:**

-   Data is correct, authentic, and reliable
-   Determining data integrity and analyzing usage helps security professionals decide data trustworthiness
-   Ensures data hasn't been tampered with or corrupted
-   Critical for maintaining accurate and reliable information

**Availability:**

-   Data is accessible to those authorized to access it
-   Inaccessible data isn't useful and prevents people from doing their jobs
-   Systems, networks, and applications must function properly for timely and reliable access
-   Part of everyday work responsibilities for security professionals

### Real-World Application - Banking Example

**Confidentiality in Banking:**

-   Essential for organizations with large amounts of private data
-   Banks must keep personal and financial information safe
-   Protect customer privacy and prevent unauthorized access to sensitive financial data

**Integrity in Banking:**

-   High priority for financial institutions
-   **Example:** Dramatic changes in spending habits or purchasing locations trigger account security measures
-   Bank disables account access until they verify account owner (not threat actor) is making purchases
-   Prevents fraudulent transactions and protects customer assets

**Availability in Banking:**

-   Critical for customer satisfaction and business operations
-   Banks invest significant effort ensuring easy web-based account access
-   Information must be protected from threat actors while remaining accessible to legitimate users
-   **Validation Process:** Minimize damage when customer accounts suspected of being compromised

### CIA Triad Implementation Strategy

**Balanced Approach:**

-   All three principles must work together for effective security
-   Over-emphasis on one principle can compromise others
-   Security professionals must balance protection with usability

**Risk Consideration:**

-   CIA triad guides risk assessment and policy development
-   Helps determine appropriate security controls and measures
-   Informs decision-making for system design and implementation

**Daily Application:**
Entry-level analysts use CIA triad principles to:

-   Evaluate security incidents and their impact
-   Design and implement security controls
-   Make decisions about data access and protection
-   Assess whether security measures effectively protect organizational assets

**Organizational Protection:**
The CIA triad provides a comprehensive framework for protecting:

-   The organization's assets and data
-   Customer and employee information
-   Business operations and continuity
-   Stakeholder trust and confidence

**Key Principle:**
CIA triad serves as the foundation for all cybersecurity decisions, ensuring that security measures protect confidentiality, maintain integrity, and provide availability while supporting business objectives and regulatory requirements.

### NIST Framework

**National Institute of Standards and Technology (NIST):**
NIST provides frameworks that support ongoing security efforts for all types of organizations—profit, nonprofit, and government agencies. While NIST is US-based, its guidance is globally applicable and helps analysts implement essential cybersecurity practices.

### NIST Cybersecurity Framework (CSF)

**Overview:**

-   Voluntary framework consisting of standards, guidelines, and best practices to manage cybersecurity risk
-   Widely respected and essential for maintaining security in any organization

**Five Core Functions:**

1. **Identify:** Understand and manage cybersecurity risks to systems, assets, data, and capabilities
2. **Protect:** Implement safeguards to ensure delivery of critical services and limit or contain the impact of a potential event
3. **Detect:** Develop and implement activities to identify the occurrence of a cybersecurity event
4. **Respond:** Take action regarding a detected cybersecurity incident to minimize impact
5. **Recover:** Maintain plans for resilience and restore any capabilities or services impaired due to a cybersecurity incident

**Workplace Example:**

-   Receive high-risk notification of a compromised workstation
-   Identify the workstation and discover an unknown device plugged in
-   Block the unknown device remotely to stop the threat
-   Remove the infected workstation to prevent spread
-   Use tools to detect additional threat actor behavior and identify the device
-   Respond by investigating who used the device, how the threat occurred, what was affected, and where the attack originated
-   Discover the cause (e.g., employee charging an infected phone via USB)
-   Recover files/data and correct any damage to the workstation

**Benefits:**

-   Provides specific guidance and direction for security professionals
-   Helps develop plans to handle incidents quickly and appropriately
-   Lowers risk, protects against threats, and mitigates vulnerabilities

### NIST Special Publication 800-53 (SP 800-53)

-   Expands CSF to the protection of US federal government systems
-   Provides a unified framework for protecting information systems within the federal government
-   Applies to both government agencies and private companies providing systems for federal use

**Key Principle:**
NIST frameworks help organizations manage cybersecurity risks and recover from attacks.

**Update:**  
The latest NIST Cybersecurity Framework adds a new core function: **Govern**.

-   Focuses on strong cybersecurity governance at all levels
-   Includes setting objectives, leadership commitment, risk management strategy, and continuous improvement

**NIST CSF Core Functions (now 6):**

1. **Govern** – Set objectives, leadership commitment, and risk management strategy
2. **Identify** – Manage cybersecurity risk and its effect on people/assets
    - Example: Monitor internal networks to spot potential security issues
3. **Protect** – Implement policies, procedures, training, and tools to mitigate threats
    - Example: Update policies based on past incidents and new threats
4. **Detect** – Identify potential security incidents and improve monitoring
    - Example: Ensure security tools flag and alert on low/medium/high risks
5. **Respond** – Use proper procedures to contain, neutralize, and analyze incidents
    - Example: Document incidents and suggest process improvements
6. **Recover** – Return systems to normal operation after an incident
    - Example: Restore affected systems, data, and assets after a breach

These functions help organizations manage risk, respond to incidents, and improve security over time.

### OWASP Security Principles

**1. Minimize the Attack Surface Area**

-   Attack surface: All potential vulnerabilities and attack vectors (e.g., phishing emails, weak passwords)
-   Reduce risk by disabling unnecessary features, restricting access, and enforcing strong password policies

**2. Principle of Least Privilege**

-   Users get only the access needed for their tasks
-   Limits damage if credentials are compromised
-   Example: Analyst can view logs but can't change user permissions

**3. Defense in Depth**

-   Use multiple security controls to address risks in different ways
-   Examples: MFA, firewalls, IDS, permission settings
-   Multiple layers make it harder for attackers to breach systems

**4. Separation of Duties**

-   No one person should have enough privileges to misuse the system
-   Example: The person who signs paychecks shouldn't prepare them

**5. Keep Security Simple**

-   Avoid overly complex security controls
-   Simpler solutions are easier to manage and support collaboration

**6. Fix Security Issues Correctly**

-   Quickly identify and address root causes of incidents
-   Test fixes to ensure vulnerabilities are resolved
-   Example: Enforce stronger password policies if weak wifi passwords are found

**7. Establish Secure Defaults**

-   The most secure state should be the default for users
-   It should require extra effort to make an application less secure

**8. Fail Securely**

-   When a control fails, it should default to the most secure option
-   Example: If a firewall fails, it should block all connections, not allow everything

**9. Don’t Trust Services**

-   Don’t assume third-party partners have strong security
-   Always verify data and actions from external services
-   Example: An airline should verify reward point balances from a vendor before sharing with customers

**10. Avoid Security by Obscurity**

-   Security should not depend on keeping system details or source code secret
-   Rely on strong controls like good password policies, defense in depth, and audit controls

These additional OWASP principles help ensure applications and systems remain secure, even when facing failures or unexpected conditions.

### Plan a security audit

**Internal Security Audit:**

-   Conducted by compliance officers, security managers, and security team members
-   Purpose: Improve security posture and avoid compliance fines

**Benefits:**

-   Identify organizational risk
-   Assess controls
-   Correct compliance issues

**Common Audit Elements:**

1. **Establish Scope and Goals**

    - Scope: Identify people, assets, policies, procedures, and technologies that impact security
    - Goals: Outline security objectives (e.g., implement NIST CSF functions, ensure compliance, strengthen controls)
    - Entry-level analysts may review and understand scope/goals to support the audit

    _Example Scope:_ Assess user permissions, controls, policies, procedures, and current technology  
    _Example Goals:_ Implement framework functions, establish compliance policies, strengthen system controls

2. **Conduct a Risk Assessment**

    - Identify potential threats, risks, and vulnerabilities
    - Helps determine what security measures should be implemented and monitored
    - Managers/stakeholders often complete, but analysts may analyze details to recommend controls and compliance needs

    _Example Risk Assessment Findings:_

    - Inadequate controls, processes, and procedures
    - Poor management of physical/digital assets (e.g., employee equipment not secured)
    - Insufficient controls for access to private information in internal networks

### Complete a security audit

Before completing these last three elements, review the scope, goals, and risk assessment, and ask:

-   What is the audit meant to achieve?
-   Which assets are most at risk?
-   Are current controls sufficient?
-   If not, what controls and compliance regulations need to be implemented?

**3. Complete a Controls Assessment**

-   Review existing assets and evaluate risks to ensure controls are effective
-   Classify controls:
    -   **Administrative controls:** Policies/procedures (e.g., password policies)
    -   **Technical controls:** Hardware/software (e.g., IDS, encryption)
    -   **Physical controls:** Physical barriers (e.g., cameras, locks)

**4. Assess Compliance**

-   Determine if the organization follows required laws/regulations
-   Example: If operating in the EU and accepting credit cards, must comply with GDPR and PCI DSS

**5. Communicate Results**

-   Share audit results and recommendations with stakeholders
-   Summarize scope, goals, and identified risks (with urgency)
-   List compliance requirements and suggest improvements for security posture

Internal audits help identify and address security gaps within an organization

## Module 3

### Logs and SIEM tools

A log is a record of events that occur within an organization's systems and networks. Security analysts access logs from different sources to monitor activity and detect threats.

**Common log sources:**

-   **Firewall logs:** Record attempted or established connections for incoming and outgoing internet traffic.
-   **Network logs:** Track all computers and devices entering/leaving the network and connections between devices/services.
-   **Server logs:** Record events related to services like websites, emails, or file shares (e.g., login, password, and username requests).

Monitoring these logs helps security teams spot vulnerabilities and potential data breaches.

**SIEM (Security Information and Event Management) tools:**

-   Collect and analyze log data from multiple sources
-   Provide real-time visibility, event monitoring, analysis, and automated alerts
-   Store all log data in a centralized location
-   Index and minimize logs for efficient review

SIEM tools must be configured and customized for each organization's needs. As new threats and vulnerabilities emerge, organizations should continually update their SIEM tools to ensure effective threat detection

### SIEM Dashboards

SIEM tools can be used to create dashboards that present security information in an easy-to-understand format, similar to how weather apps display data with charts and graphs.

**Purpose:**

-   Help security analysts quickly access and interpret security data as charts, graphs, or tables
-   Enable fast decision-making based on visualized information

**Example:**

-   Analyst receives an alert about a suspicious login
-   Uses the SIEM dashboard to see 500 login attempts for a user in five minutes, from unusual locations and times
-   Visual timeline and location data help the analyst quickly spot suspicious activity

**Metrics:**

-   Dashboards can show key metrics like response time, availability, and failure rate
-   Metrics help assess software and security performance

**Customization:**

-   Dashboards can be tailored to display data relevant to different roles (e.g., network traffic volume for business operations)

SIEM dashboards make it easier for analysts and stakeholders to monitor, investigate, and respond to security

### The future of SIEM tools

**Current SIEM solutions:**

-   SIEM tools collect and analyze log data for real-time monitoring and tracking of security events.
-   Dashboards help teams manage and monitor organizational data.
-   Human interaction is still needed to analyze and respond to security events.

**Cloud SIEM:**

-   **Cloud-hosted SIEM:** Vendor-managed infrastructure, accessed via the internet. Good for organizations that don't want to maintain their own systems.
-   **Cloud-native SIEM:** Built to fully use cloud capabilities (availability, flexibility, scalability), also vendor-managed and internet-accessible.

**Trends and future developments:**

-   SIEM tools are evolving to handle more data from interconnected devices (IoT), increasing the attack surface and data volume.
-   AI and machine learning will improve threat detection, dashboard visualization, and data storage.
-   Automation will allow SIEM tools to respond faster to incidents, reducing the need for manual intervention.
-   **SOAR (Security Orchestration, Automation, and Response):** Uses automation to handle common security incidents, freeing analysts to focus on complex cases.
-   Expect more integration and communication between cybersecurity platforms, though full interoperability

### Explore common types of SIEM tools

**Self-hosted SIEM:**

-   Organization installs, operates, and maintains the tool on its own physical infrastructure (servers, storage, etc.)
-   Managed by the organization's IT department
-   Ideal for organizations needing physical control over confidential data

**Cloud-hosted SIEM:**

-   Maintained and managed by the SIEM provider, accessed via the internet
-   Good for organizations that don't want to invest in their own infrastructure

**Hybrid SIEM:**

-   Combines self-hosted and cloud-hosted solutions
-   Lets organizations leverage cloud benefits while maintaining physical control over sensitive data

**Common SIEM tools:**

-   **Splunk Enterprise:** Self-hosted SIEM for real-time log retention, analysis, and alerts
-   **Splunk Cloud:** Cloud-hosted SIEM for collecting, searching, and monitoring log data (suitable for hybrid/cloud environments)
-   **Google Chronicle:** Cloud-native SIEM designed for log monitoring, data analysis, and collection; fully managed and scalable

Organizations use a mix of these tools to protect data and systems as threat actors evolve

### More about cybersecurity tools

**Open-source tools:**

-   Free to use and often user friendly
-   Built collaboratively by the public, which can improve security and allow for more customization
-   Source code and training materials are available for anyone to use, modify, and improve (as long as the license is respected)
-   Examples:
    -   **Linux:** Open-source operating system, highly customizable via command-line interface
    -   **Suricata:** Open-source network analysis and threat detection software, inspects network traffic for suspicious behavior and integrates with many SIEM tools

**Proprietary tools:**

-   Developed and owned by a person or company; usually require payment for use and training
-   Only the owner can access and modify the source code
-   Users may need to pay for updates and can only modify limited features
-   Examples:
    -   **Splunk®:** Proprietary SIEM tool
    -   **Google SecOps (Chronicle):** Proprietary SIEM tool

**Common misconceptions:**

-   Some believe open-source tools are less effective or less safe than proprietary tools
-   In reality, open-source tools are often industry standards and can be more secure due to public review and rapid issue resolution

Open-source and proprietary tools both play important roles in cybersecurity, and professionals often use a mix of both depending

### Use SIEM tools to protect organizations

**Splunk Dashboards:**

-   **Security posture dashboard:**  
    Shows notable security events and trends from the last 24 hours. Used by SOCs to monitor if security infrastructure and policies are working as intended. Helps analysts investigate real-time threats, like suspicious activity from a specific IP.

-   **Executive summary dashboard:**  
    Provides a high-level overview of the organization's security health over time. Useful for sharing security trends and incident summaries with stakeholders.

-   **Incident review dashboard:**  
    Highlights suspicious patterns and high-risk items during incidents. Offers a visual timeline of events leading up to an incident for easier investigation.

-   **Risk analysis dashboard:**  
    Identifies risk for each object (user, computer, IP). Shows changes in risk-related activity, like logins outside normal hours or high network traffic. Helps prioritize risk mitigation.

**Chronicle Dashboards:**

-   **Enterprise insights dashboard:**  
    Highlights recent alerts and suspicious domain names (IOCs), with confidence scores and severity levels. Used to monitor critical assets for unusual access attempts.

-   **Data ingestion and health dashboard:**  
    Shows event log counts, log sources, and data processing success rates. Ensures logs are received correctly and helps troubleshoot log issues.

-   **IOC matches dashboard:**  
    Displays top threats, risks, and vulnerabilities by tracking domain names, IPs, and device IOCs. Helps focus on the highest priority threats and investigate related activity.

-   **Main dashboard:**  
    Gives a summary of data ingestion, alerts, and event activity over time. Useful for spotting trends like spikes in failed logins across sources and locations.

-   **Rule detections dashboard:**  
    Shows stats on incidents with the most occurrences and severities. Lists alerts triggered by specific detection rules (e.g., opening a malicious email attachment). Helps manage recurring incidents and plan mitigation.

-   **User sign in overview dashboard:**  
    Tracks user sign-in events to spot unusual behavior, like logins from multiple locations at once. Used to mitigate threats to user

## Module 4

### Phases of an incident response playbook

A playbook is a manual that outlines operational actions and tools for responding to security incidents. In cybersecurity, incident response playbooks ensure teams act quickly, efficiently, and consistently to reduce risk.

**Six phases of an incident response playbook:**

1. **Preparation**

    - Document procedures, establish staffing plans, and educate users
    - Create incident response plans and define team roles/responsibilities

2. **Detection and Analysis**

    - Detect and analyze events using defined processes and technology
    - Determine if a breach occurred and assess its magnitude

3. **Containment**

    - Prevent further damage and reduce immediate impact
    - Take actions to contain the incident and protect critical assets

4. **Eradication and Recovery**

    - Remove all incident artifacts (e.g., malicious code, vulnerabilities)
    - Restore affected systems and return to normal operations (IT restoration)

5. **Post-Incident Activity**

    - Document the incident, inform leadership, and apply lessons learned
    - Conduct root cause analysis and update security measures as needed

6. **Coordination**
    - Report incidents and share information according to standards
    - Ensure compliance and enable coordinated response

### Use a playbook to respond to threats, risks, or vulnerabilities

An incident response playbook is a guide that helps security professionals act quickly and accurately during incidents. Playbooks create structure, ensure compliance, and outline steps for communication and documentation.

Organizations may have different playbooks for specific attacks (e.g., ransomware, malware, DDoS).

**Example: Using a playbook for a SIEM malware alert**

1. **Assess the alert**

    - Determine if the alert is valid by analyzing log data and metrics to understand why the SIEM triggered it.

2. **Contain the incident**

    - Follow playbook instructions to isolate/disconnect the infected system to prevent malware from spreading.

3. **Eradicate and recover**

    - Remove all traces of the malware.
    - Restore the operating system and affected data from a clean backup.

4. **Post-incident activity and coordination**
    - Create a final report for stakeholders or authorities (e.g., FBI).
    - Communicate lessons learned and update the playbook as needed.

Playbooks are living documents—security teams update them regularly to address new threats, refine procedures, and improve the organization's security posture based on lessons learned from past

# Certificate Completed

![Certificate proof in case I have to pay for it](image-1.png)
