# Fundamental Security Concepts

## CIA Triad

The CIA triad represents the three core goals of information security:

### 1. Confidentiality

-   Ensures only authorized individuals have access to information and resources
-   Protects secrets from unauthorized disclosure
-   **Attack type**: Disclosure attacks (making sensitive information available without consent)

### 2. Integrity

-   Prevents unauthorized changes to information
-   Protects against both intentional attacks and accidental service disruptions
-   Maintains data accuracy and completeness

### 3. Availability

-   Ensures authorized users can access information when needed
-   Critical for business operations and productivity
-   **Attack type**: Denial of Service (DoS) attacks that overwhelm or crash systems

## Authentication, authorization, and accounting (AAA)

Access control consists of three sequential steps:

### 1. Identification

-   User makes a **claim** about their identity (no proof required)
-   Example: Stating "I'm Mike Chappel" or entering a username
-   **Note**: This is only a claim and could be false

### 2. Authentication

-   User **proves** their identity to the system
-   Example: Showing driver's license or entering a password
-   **Exam tip**: Remember the distinction between identification (claim) and authentication (proof)

### 3. Authorization

-   System determines if the authenticated user is **allowed** access
-   Example: Checking appointment lists or access control lists (ACLs)
-   In digital systems: File system permissions granted to users/groups

## AAA Framework

**Authentication, Authorization, and Accounting**

-   **Authentication**: Proving identity
-   **Authorization**: Granting appropriate access
-   **Accounting**: Tracking user activity through logs for audit purposes

## Security Controls

Security controls are procedures and mechanisms organizations implement to address security risks by:

-   Reducing likelihood of risks materializing
-   Minimizing impact when risks occur
-   Detecting security issues when they happen

### Defense in Depth Principle

Multiple overlapping controls achieve the same objective to ensure security even if one control fails.

**Example**: Home security uses locks (prevention), burglar alarms (detection), and security cameras (detection) working together.

## Control Categories

### By Purpose/Function

| Control Type     | Purpose                                         | Example                             |
| ---------------- | ----------------------------------------------- | ----------------------------------- |
| **Preventive**   | Stop security issues before they occur          | Firewalls blocking unwanted traffic |
| **Detective**    | Identify potential security breaches            | Intrusion detection systems         |
| **Corrective**   | Remediate issues that have occurred             | Restoring data from backups         |
| **Deterrent**    | Discourage attackers from attempting violations | Guard dogs, barbed wire fences      |
| **Directive**    | Inform employees what to do for security        | Policies and procedures             |
| **Compensating** | Fill known gaps in security environment         | Guards at facility gates            |

### By Mechanism of Action

#### 1. Technical Controls

-   **Definition**: Use of technology to achieve security objectives
-   **Examples**: Firewalls, intrusion prevention systems, encryption, data loss prevention, antivirus software

#### 2. Operational Controls

-   **Definition**: Processes to manage technology securely (carried out by **people**)
-   **Examples**: User access reviews, log monitoring, background checks, security awareness training
-   **Exam tip**: Operational = people, Technical = technology

#### 3. Managerial Controls

-   **Definition**: Focus on risk management process mechanics
-   **Examples**:
    -   Regular risk assessments
    -   Security planning
    -   Security considerations in change management, service acquisition, and project management

#### 4. Physical Controls

-   **Definition**: Controls that impact the physical world
-   **Examples**: Fences, perimeter lighting, locks, fire suppression systems, burglar alarms

### Key Distinction for Exams

-   **Technical Control**: Firewall enforcing rules (automated by technology)
-   **Operational Control**: Administrator reviewing firewall logs (human action)

## Gap Analysis

Gap analysis is a core strategic planning tool for cybersecurity programs that compares current security state with desired security state.

### Two Key Components

#### 1. Desired State Assessment

Determines what controls should be in place to meet security objectives, based on:

**Internal Requirements**:

-   Organization's information security policies
-   Examples: Encryption at rest/transit, multi-factor authentication for sensitive systems

**External Requirements**:

-   Regulatory compliance based on industry/business practice

| Industry/Data Type     | Regulation | Full Name                                           |
| ---------------------- | ---------- | --------------------------------------------------- |
| Healthcare (US)        | HIPAA      | Health Insurance Portability and Accountability Act |
| EU Personal Data       | GDPR       | General Data Protection Regulation                  |
| Credit Card Processing | PCI DSS    | Payment Card Industry Data Security Standard        |

#### 2. Current State Assessment

Honest evaluation of existing cybersecurity controls through:

-   Internal assessment
-   External security consultant review

### Gap Analysis Process

1. **Compare States**: Examine current security program against desired state
2. **Identify Gaps**: Controls that are missing or fall short of expectations
3. **Remediation Planning**: Address all identified gaps to achieve desired state

### Security Program Roadmap

**Purpose**: Prioritize remediation efforts and align activities with organizational security needs

**Timeline**: Often spans several years depending on:

-   Number of gaps identified
-   Complexity of required tasks
-   Available resources

**Benefits**:

-   Strategic prioritization of security efforts
-   Alignment with organizational needs
-   Clear path to desired security state

## Zero Trust Network Access (ZTNA)

Zero Trust represents a paradigm shift from traditional perimeter-based security to a "never trust, always verify" approach.

### Core Principle

**No user or device should be granted access to resources based solely on network location**

Traditional approach: Trust based on IP addresses or network location
Zero Trust approach: Strong authentication and authorization regardless of location

### Key Benefits

-   Simplifies network requirements
-   Adapts to flexible technology environments
-   Enforces principle of least privilege
-   Supports remote workforce accessing cloud and on-premises services

### Architecture Components

#### Two Network Realms

-   **Control Plane**: Where network policy decisions are made
-   **Data Plane**: Where decisions are enforced and access is granted

#### Four Key Capabilities (The Open Group Principles)

| Capability                       | Description                                                   |
| -------------------------------- | ------------------------------------------------------------- |
| **Adaptive Identity**            | Support for multiple user types whose roles/identities evolve |
| **Threat Scope Reduction**       | Maintains agility while minimizing security risks             |
| **Policy-Driven Access Control** | Flexible environment supporting changing access needs         |
| **Implicit Trust Zones**         | Configured zones for protected data (PII, credit card data)   |

### NIST Zero Trust Model Components

| Component                          | Location                  | Function                                          |
| ---------------------------------- | ------------------------- | ------------------------------------------------- |
| **Subject**                        | Data Plane                | User/system requesting access to trusted resource |
| **Policy Enforcement Point (PEP)** | Data/Control Plane Bridge | Intercepts requests, enforces decisions           |
| **Policy Decision Point**          | Control Plane             | Makes access decisions                            |
| - Policy Engine                    | Control Plane             | Decides to grant or deny access                   |
| - Policy Administrator             | Control Plane             | Sends configuration commands to PEP               |

## Secure Access Service Edge (SASE)

SASE builds upon Zero Trust to deliver a fully-integrated, cloud-aware network security approach.

### Key Components

SASE combines:

-   **Software-Defined Networking (SDN)**
-   **Zero Trust Network Access (ZTNA)**
-   **Cloud Access Security Brokers (CASB)**
-   **Firewalls as a Service (FWaaS)**
-   **Other network security services**

### Implementation Timeline

-   **Zero Trust**: Short to medium-term objective
-   **SASE**: Long-term architectural goal
-   **Evolution**: Gradual replacement of outdated security technologies

### Strategic Approach

1. **Short-term**: Adopt Zero Trust principles for remote workforce security
2. **Long-term**: View new networking projects through SASE lens
3. **Integration**: SASE requires and enables Zero Trust approach

## Physical Access Controls

Physical security controls focus on perimeter protection to deter, prevent, and detect intrusions before gaining access to secured areas.

### Lock Types

| Lock Type            | Authentication Method                                  | Use Case              | Key Management                  |
| -------------------- | ------------------------------------------------------ | --------------------- | ------------------------------- |
| **Preset Locks**     | Physical hardware key                                  | Traditional security  | Requires key management program |
| **Cipher Locks**     | Combination/keypad                                     | Areas with many users | Combination rotation needed     |
| **Biometric Locks**  | Physical characteristics (fingerprint, retinal, voice) | High-security areas   | No physical tokens to manage    |
| **Card-based Locks** | Magnetic stripe or proximity cards                     | Facility access       | Card inventory and replacement  |

### Access Control Mechanisms

#### Access Control Vestibules (Mantraps)

-   **Purpose**: Prevent tailgating attacks
-   **Design**: Two-door system with verification between doors
-   **Verification Methods**: Cameras, scales, weight sensors
-   **Process**: Exterior door closes before interior door can open

#### Tailgating Prevention

-   **Problem**: Unauthorized individuals following authorized users through doors
-   **Solution**: Access control vestibules and security awareness training

### Monitoring Systems

#### Sensor Types

| Sensor Type            | Detection Method                 | Use Case                  |
| ---------------------- | -------------------------------- | ------------------------- |
| **Motion Sensors**     | Movement detection               | Room monitoring           |
| **Noise Sensors**      | Sound detection (glass breaking) | Perimeter security        |
| **Pressure Sensors**   | Footstep detection               | Floor monitoring          |
| **Microwave Sensors**  | Microwave technology             | People detection          |
| **Ultrasonic Sensors** | High-frequency sound waves       | Advanced people detection |

#### Video Surveillance Systems

**Functions**:

-   **Deterrent Control**: Visible cameras discourage intrusion attempts
-   **Detective Control**: Real-time monitoring and intrusion detection
-   **Investigation Tool**: Evidence collection and individual identification

**Technologies**:

-   **CCTV**: Dedicated closed-circuit television networks
-   **IP-based**: Network-connected camera systems
-   **Infrared Detection**: Heat signature detection in low-light conditions
-   **Motion Detection Software**: Automated alerts for unexpected movement

### Physical Barriers

#### Perimeter Security

| Barrier Type | Purpose                   | Application                    |
| ------------ | ------------------------- | ------------------------------ |
| **Fences**   | Block foot/vehicle access | Property perimeter             |
| **Cages**    | Equipment protection      | Data center segregation        |
| **Bollards** | Vehicle barrier           | Building/pedestrian protection |

#### Additional Security Measures

-   **Proper Lighting**: Increases detection likelihood by guards/passersby
-   **Security Signs**: Legal basis for trespassing charges, deterrent effect
-   **Industrial Camouflage**: Hide sensitive facilities in nondescript locations

### Modern Challenges

#### Drone/UAV Threats

-   **Challenge**: Aerial surveillance and potential attacks
-   **Response**: Facilities must appear innocuous from ground **and** air
-   **Example**: Data centers designed to look like standard industrial buildings

### Access Management Best Practices

1. **Authorized Access Lists**: Maintain current lists of permitted individuals
2. **Prompt Revocation**: Remove access immediately when no longer needed
3. **Key Management**: Strong inventory tracking for physical keys
4. **Multi-layered Approach**: Combine multiple physical controls for defense in depth

## Physical Security Personnel

Human guards play a crucial role in physical security, providing judgment and decision-making that technology cannot fully replace.

### Human Security Guards

#### Key Functions

-   **Access Control**: Evaluate visitor requests using human judgment
-   **Public Relations**: Present welcoming face while maintaining security
-   **Flexibility**: Handle situations requiring interpretation and discretion

#### Guard Types

| Guard Type                 | Appearance                    | Purpose                        | Characteristics                         |
| -------------------------- | ----------------------------- | ------------------------------ | --------------------------------------- |
| **Covert Guards**          | Appear as receptionists       | Maintain welcoming environment | Blend into normal business operations   |
| **Overt Uniformed Guards** | Clearly identifiable security | Project security presence      | May be armed (depending on regulations) |

#### Benefits of Human Guards

-   **Irreplaceable judgment** for complex situations
-   **Customer service** while maintaining security
-   **Adaptability** to unexpected scenarios
-   **Authority presence** when needed

### Emerging Technology

#### Robot Sentries

-   **Function**: Patrol facilities for abnormal activity
-   **Capabilities**:
    -   Challenge intruders directly
    -   Summon human response when necessary
-   **Status**: Beginning to supplement human guards

### Two-Person Rule

Critical security principle ensuring appropriate behavior in sensitive operations through redundancy and oversight.

#### Two-Person Integrity

| Aspect               | Description                                           |
| -------------------- | ----------------------------------------------------- |
| **Purpose**          | Prevent unauthorized activity by single individual    |
| **Requirement**      | Two people present for access to sensitive areas      |
| **Application**      | Areas with valuable items or sensitive materials      |
| **Security Benefit** | Deters theft, requires collusion for illicit activity |

#### Two-Person Control

| Aspect              | Description                                        |
| ------------------- | -------------------------------------------------- |
| **Purpose**         | Control access to very sensitive functions         |
| **Requirement**     | Concurrence of two individuals for action          |
| **Classic Example** | Nuclear missile launch requiring two keys          |
| **Design**          | Keys positioned too far apart for single person    |
| **Process**         | Simultaneous action required from both individuals |

## Deception Technologies

Deception technologies allow security analysts to gain advantage over attackers by creating false targets and misleading information to detect unauthorized activities.

### Core Concept

**Challenge**: Distinguishing between legitimate traffic and attack activity
**Solution**: Create false targets that only attackers would interact with

### Deception Technology Types

| Technology        | Description                                          | Purpose                         | Detection Method                                |
| ----------------- | ---------------------------------------------------- | ------------------------------- | ----------------------------------------------- |
| **Darknets**      | Reserved IP address space with no legitimate systems | Detect network reconnaissance   | Any traffic to these addresses indicates attack |
| **Honey Tokens**  | Fake records in databases/file systems               | Database breach detection       | Fake email addresses routing to SOC             |
| **Honeyfiles**    | Files resembling sensitive data containing garbage   | File access monitoring          | Access to fake sensitive files                  |
| **Honeypots**     | Fake systems designed to attract attackers           | Trap and monitor attackers      | System interaction and compromise attempts      |
| **Honeynets**     | Large-scale deployment of multiple honeypots         | Comprehensive attack monitoring | Network-wide deception environment              |
| **DNS Sinkholes** | Redirect malicious domains to controlled servers     | Botnet disruption               | Command and Control communication interception  |

## Change Management

Change management is a systematic approach to planning, implementing, and monitoring modifications to systems and processes to minimize risks and maximize benefits.

### Core Change Management Processes

| Process                                  | Description                                                                    | Purpose                                              |
| ---------------------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------- |
| **Approval Process**                     | Systematic evaluation, authorization, and documentation                        | Reduce risk of unauthorized modifications            |
| **Change Ownership**                     | Assigned responsibility for each change                                        | Maintain accountability and streamline communication |
| **Stakeholder Engagement**               | Involve IT personnel, administrators, department heads, security professionals | Gather insights and ensure thorough evaluation       |
| **Impact Analysis**                      | Assess potential consequences, risks, vulnerabilities, conflicts               | Make informed decisions and mitigate risks           |
| **Testing**                              | Verify changes work as intended                                                | Minimize disruption and security breach risks        |
| **Back-out Plan**                        | Steps to reverse failed changes                                                | Restore systems and minimize downtime                |
| **Maintenance Windows**                  | Scheduled timeframes for changes                                               | Minimize disruption to business operations           |
| **Standard Operating Procedures (SOPs)** | Best practices and guidelines                                                  | Ensure consistent execution and reduce errors        |

### Technical Implications

#### Access Control Changes

-   **Allow Lists**: Modify to permit certain actions
-   **Deny Lists**: Update to prohibit certain activities
-   **Purpose**: Control access to resources and prevent unauthorized actions

#### Security Restrictions

-   **Activity Restrictions**: Disable unnecessary services, restrict user privileges
-   **Purpose**: Mitigate potential vulnerabilities

#### System Operations

-   **Downtime**: Plan for temporary service interruptions
-   **Service/Application Restarts**: Required to apply modifications
-   **Communication**: Effective planning to minimize disruptions

#### Legacy System Considerations

-   **Challenge**: Impact on unsupported or outdated applications
-   **Requirement**: Ensure modifications don't compromise security or functionality

#### Dependency Management

-   **Dependencies**: Changes may affect other systems, applications, or components
-   **Critical**: Understanding and managing dependencies to avoid disruptions

### Change Control Documentation

#### Version Control

-   **Purpose**: Maintain systematic record of all changes
-   **Documentation**: Purpose, scope, and details of every modification
-   **Benefits**:
    -   Enables change reversal if necessary
    -   Supports incident investigation
    -   Facilitates audits and traceability

#### Documentation Updates

-   **Post-Implementation**: Update diagrams, procedures, and policies
-   **Accuracy**: Reflect new state of IT infrastructure
-   **Stakeholder Access**: Ensure all parties have accurate information
-   **Benefit**: Reduce confusion and enable efficient problem-solving
