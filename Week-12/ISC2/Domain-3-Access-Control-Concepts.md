# Domain 3: Access Control Concepts

## Security Controls

-   **Control:** Safeguard or countermeasure designed to preserve CIA Triad
-   **CIA Triad:** Confidentiality, Integrity, and Availability of data

-   **Access Control:** Limiting what objects are available to what subjects according to rules
-   **Example:** Firewall as a control system
-   Prevents external threats from entering and compromising environment
-   Prevents internal information from going out to unauthorized individuals

## Controls Overview

-   **Access Controls:** Heart of information security program
-   Determines who can access organizational assets and what they can do
-   About both restricting and allowing appropriate access levels
-   Grants access to authorized personnel and processes
-   Denies access to unauthorized functions or individuals

## Subjects

-   **Subject:** Any entity that requests access to assets
-   Can be user, client, process, or program
-   Initiator of service request (active entity)
-   Examples:
    -   User, process, procedure, client/server, program
    -   Device: endpoint, workstation, smartphone, removable storage
-   Should have clearance level (permissions) for accessing services/resources

## Objects

-   **Object:** Anything that subject attempts to access
-   Responds to service requests (passive entity)
-   Examples:
    -   Building, computer, file, database, printer/scanner
    -   Server, communications resource, memory block
    -   Input/output port, person, software task, thread, process
-   Has owner who determines access rules
-   Rules recorded in rule base or access control list
-   May have classification
-   Must be protected by other system layers

## Rules

-   **Access Rule:** Instruction to allow/deny access by comparing validated subject identity to access control list
-   **Example:** Firewall access control list
-   Default: deny access from any address to any address on any port
-   Rules added to allow specific access patterns
-   Can:
    -   Compare multiple attributes for appropriate access
    -   Allow/deny access to objects
    -   Define access level amount
    -   Apply time-based access

## Defense in Depth

-   **Defense in Depth:** Layered defense strategy integrating people, technology, and operations
-   Applies multiple countermeasures in layered fashion to fulfill security objectives
-   Cannot guarantee attack prevention but deters cyberattacks
-   **Technical Example:** Multi-factor authentication
    -   Username/password (something you know)
    -   Code sent to phone (something you have)
    -   Combination much more difficult for adversaries to obtain
-   **Network Example:** Multiple firewalls separating untrusted from trusted networks
-   **Sensitive Data:** Network traffic validated by rules on multiple firewalls
-   **Control Layers:**
    -   Physical Controls (outermost)
    -   Logical/Technical Controls
    -   Administrative Controls
    -   Assets (innermost)
-   **Data Center Example:** Multiple access layers
    -   Physical lock on door
    -   Technical access rule for network access
    -   Administrative policy defining authorized individuals

## Least Privilege Examples

-   **Principle of Least Privilege:** Each user granted access only to needed items
-   **Billing Example:** Only billing personnel can view consumer financial data
-   Fewer individuals have authority to change or delete data
-   Maintains confidentiality and integrity while allowing availability
-   **Temporary Access:** Limited access for specific time periods or business hours
-   **Field-Level Access:** Limit access to specific fields
-   **Healthcare Example:** Workers may access patient data but not medical data
-   Doctors access only their own patients' data
-   Regulated by laws like HIPAA in United States
-   **Monitoring:** Systems monitor access to private information
-   Logs trigger alarms for unauthorized access attempts
-   Security administrators record incidents and alert appropriate personnel

## Logical Access Controls

-   **Logical Access Controls:** Electronic methods limiting access to systems and assets
-   Types include:
    -   Passwords
    -   Biometrics (implemented on systems like smartphones/laptops)
    -   Badge/token readers connected to systems
-   Limit logical access even if person has physical access

## Controls and Risks

-   **Control Purpose:** Reduce risk according to risk tolerance of individual or organization
-   **Seat Belt Example:**
    -   Physical control: seat belt itself
    -   Administrative control: law requiring seat belt use
    -   Both work together to reduce driving risk to acceptable level
-   **Bookshelf Example:**
    -   Risk: injury from toppling bookshelf
    -   Administrative control: building codes requiring secure attachment
    -   Physical control: actual strap/bracket attachment to wall
    -   Both controls work together to mitigate risk

## Controls Assessments

-   **Risk Reduction:** Depends on control effectiveness and adaptation to changing environment
-   **Secure Storage Facility Example:**
    -   5 doors must be secured for confidential file storage
    -   Site assessment determines control needs
    -   Options: biometric scanners, permanent door removal, wall replacement
    -   Cost must align with value of protected assets

## Role-Based Access Control (RBAC)

-   **RBAC:** Provides privileges based on organizational role
-   **Examples:**
    -   HR: access to personnel files only
    -   Finance: access to bank accounts only
    -   Managers: access to own direct reports and department
    -   System administrators: access to everything
    -   New employees: minimal access required for job
-   **Monitoring Importance:** Prevents privilege creep/permissions creep
-   **Privilege Creep:** Temporary permissions not revoked when no longer needed
-   **Best Practice:** Don't copy user profiles to new users
-   Use standard roles rather than actual user profiles for new employees

## Privileged Access Management

-   **Privileged Access Management (PAM):** Controls and monitors elevated access to critical systems
-   **Traditional Model:** Privileges statically assigned to admin users, always active
-   **Risk:** Security relies solely on login process; privileges are always available
-   **Just-in-Time PAM:** Role-based, specific privileges activated only when needed in real time
-   Reduces risk of misuse by limiting duration and scope of elevated access

## Privileged Accounts

-   **Privileged Accounts:** Accounts with permissions beyond normal users
-   Used by managers and administrators with elevated privileges
-   **User Classes:**
    -   Systems administrators: operating systems, applications, performance management
    -   Help desk/IT support: endpoints, servers, applications platforms
    -   Security analysts: entire IT infrastructure, systems, endpoints, data environment
    -   Project/client service teams: greater control over data and applications
-   **Risk Mitigation Measures:**
    -   More extensive logging than regular accounts
    -   More stringent access control (MFA, just-in-time identity)
    -   Deeper trust verification (background checks, NDAs, financial investigation)
    -   More auditing and monitoring than regular accounts

## Monitoring (Physical)

-   **Cameras:** Centrally monitored; deter, detect (with sensors), and provide forensic evidence
-   Used where access is difficult or a recorded audit trail is needed
-   **Sensors:**
    -   Motion (infrared, microwave, laser) for exterior/perimeter detection
    -   Door/gate/turnstile sensors; strain/vibration for fence scaling
    -   Proper integration alerts on intrusions across open space or fence line

## Physical Logs

-   **Definition:** Records of physical access/events (e.g., guard sign-in sheet, electronic access system)
-   **Retention:** Keep as long as required by legal/business needs (consult legal)
    -   Example: PCI DSS requires 1 year of log data retention
-   **Protection:** Safeguard against tampering and unauthorized disclosure (logs may contain sensitive data)
-   **Review:** Organization should have policy for regular log reviews
-   **Anomalies:** Identify gaps, lockouts, unusual writes; avoid logging everything to prevent data overload

## Alarm Systems

-   **Door/Window Alarms:** Alert when opened unexpectedly; authorized badge/code access should not trigger
-   **Fire Alarms:** Triggered by heat/smoke; audible warnings and automatic contact with responders
-   **Panic Buttons:** Directly alert police/security when activated

## Security Guards

-   **Role:** Effective physical control; deter impersonation and tailgating
-   **Program:** Pair with physical access controls, monitoring of personnel/equipment, and auditing/logging of physical events

## Mandatory Access Control (MAC)

-   System-enforced access based on centralized policy; minimal individual discretion
-   Common in government environments with security clearances and classified resources
-   Access decisions use labels/classifications for subjects and objects
-   Paired with separation of duties to limit scope of work
-   RBAC can support operational constraints alongside MAC

-   **Uniform Enforcement:** Applies across all subjects/objects within the system boundary
-   **Rule Changes:** Only designated security administrators can modify access rules
-   **Subject Constraints (cannot):**
    -   Pass information to unauthorized subjects/objects
    -   Grant their privileges to other subjects
    -   Change security attributes on subjects/objects/system/components
    -   Choose security attributes for new/modified objects
    -   Change rules governing access control
-   **MAC vs DAC:**
    -   MAC: administrators assign rights/permissions
    -   DAC: object owners grant access at their discretion

## Physical Security Controls

-   **Definition:** Tangible mechanisms to prevent, monitor, or detect physical access to sites/systems
-   **Examples (condensed):** Security guards, locks/doors, fences, badges/swipe cards, mantraps/turnstiles, cameras, motion/magnetic sensors, alarms, lighting, cable/laptop locks
-   **Priority:** Protect people first, then facilities, equipment, and information assets
-   **Purpose:** Prevent unauthorized entry; reduce theft, tampering, and safety risks
-   **Approach:** Use in layers with logical and administrative controls (see Defense in Depth)

## Separation of Duties

-   **Concept:** No single person controls an entire high-risk transaction end-to-end
-   **Mechanism:** Split tasks; different people execute each part
-   **Examples:**
    -   Invoices: employee submits; manager approves before payment
    -   System changes: proposal requires technical and management review/approval
-   **Benefit:** Prevents fraud; detects errors before implementation
-   **Nuance:** Permissions can differ across activities (submit vs approve in different areas)
-   **Risk:** Collusion (two people cooperate to bypass controls)
-   **Dual Control:** Two separate keys/codes required (e.g., bank vault with two combinations)

## Two-Person Integrity (Two-Person Rule)

-   **Requirement:** Minimum two people must be present in selected high-security areas
-   **Enforcement:** Access systems can require accompanied entry
-   **Purpose:** Reduce insider threats; provide life safety (assistance if medical emergency)

## Discretionary Access Control (DAC)

-   Owner-driven policy: object owners grant/revoke access at their discretion
-   Subjects with access may (policy permitting):
    -   Pass information to other subjects/objects
    -   Grant their privileges to other subjects
    -   Change security attributes on subjects/objects/systems
    -   Choose security attributes for new/modified objects
    -   Change rules governing access control
-   Common in Windows and Unix/Linux/iOS; uses subject↔object permission tables
    -   Object's Access Control List (ACL): subjects with permissions for that object
    -   Subject's capabilities list: objects the subject has permissions for
-   Pros/Cons: flexible for owners; not very scalable and harder to trace access issues
-   Workplace examples:
    -   Online file sharing: creator selects who can view/edit
    -   Temporary low-tech: visitor badge issued at security desk

## Authorized vs Unauthorized Personnel

-   **Authentication:** Confirms subject identity
-   **Authorization:** Verifies permissions for requested action via security matrix/ACL
-   **Examples:**
    -   Data center door: badge ID checked against matrix; door unlocks only if authorized
    -   File delete: filesystem checks permissions; allow/deny accordingly

## User Provisioning

-   **New Employee:** Manager requests account; security admin creates ID with appropriate access; extra approval for elevated rights per policy
-   **Change of Position:** Update permissions to match new role; remove access no longer needed
-   **Separation:** Disable at termination date/time; retain account briefly for audit trail, then delete; remove from roles/profiles
-   **Best Practice:** Avoid copying user profiles to new users to prevent privilege/permission creep; provision from standard roles

## Types of Physical Access Controls

### Environmental Design (CPTED)

-   Passive design to deter crime using organizational, mechanical, and natural design methods
-   Directs people flow, signals who belongs, increases visibility of hidden areas
-   Supports secure, functional spaces for creating/processing/storing information

### Badge Systems and Gate Entry

-   Access system compares badge to verified database; unlocks doors/gates if authenticated
-   Integrates with logging for authorized/unauthorized access events
-   High-security environments may include biometric enrollment

### Biometrics

-   Authenticates identity using unique personal characteristics (PII; obtain consent)
-   Processes:
    -   Enrollment: store biometric template (system or user smart card)
    -   Verification: present biometric to match stored template
-   Physiological examples: fingerprints, iris/retina, palm/vein scans; liveness checks to prevent spoofing
-   Behavioral examples: voiceprints, signature dynamics, keystroke dynamics (hold/transfer rates)
-   Considerations: higher cost and maintenance, privacy concerns, device sanitization challenges
