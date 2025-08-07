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
