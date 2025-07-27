# Assets, Threats, and Vulnerabilities

## Module 1

### Understand Risks, Threats, and Vulnerabilities

#### Key Definitions
- **Risk:** Anything that can impact the confidentiality, integrity, or availability of an asset.
- **Threat:** Any circumstance or event that can negatively impact assets.
- **Vulnerability:** A weakness that can be exploited by a threat.
- These terms are often used interchangeably in everyday life, but have specific meanings in security.

#### Security Risk
- Organizations define risk based on their valued assets and business needs.
- Risk can be calculated as:
    - **Likelihood x Impact = Risk**
    - Example: Risk of being late to work = likelihood of a flat tire x impact of being late (e.g., losing your job).
- Calculating risk helps organizations:
    - Prevent costly/disruptive events
    - Identify improvements
    - Determine tolerable risks
    - Prioritize critical assets
- Security professionals often focus on reducing the likelihood of negative events.

#### Risk Factors
- Two main risk factors:
    - **Threats**
    - **Vulnerabilities**
- Risk increases when a threat exploits a vulnerability.
    - Example: A nail (threat) punctures a tire (vulnerability), increasing the risk of being late.

#### Categories of Threat
- **Intentional:** Malicious actions (e.g., hackers targeting misconfigured applications).
- **Unintentional:** Accidental actions (e.g., employee letting an unknown person into a restricted area).

#### Categories of Vulnerability
- **Technical:** Weaknesses in systems or software (e.g., misconfigured software allowing unauthorized access).
- **Human:** Weaknesses due to human behavior (e.g., employee losing an access card).

### Security Starts with Asset Classification

#### Asset Management
- Asset management is the process of tracking assets and the risks that affect them.
- All security plans revolve around asset management.
- Assets include anything of value to an organization (equipment, data, intellectual property, etc.).

#### Asset Inventory
- Asset inventory is a catalog of all assets that need to be protected.
- Helps organizations keep track of what's important, allocate resources, and detect when something is missing.
- Analogy: Like a shepherd keeping count of sheep to protect and care for them.

#### Asset Classification
- Asset classification is labeling assets based on their sensitivity and importance.
- Common classification levels:
    - **Public:** Can be shared with anyone.
    - **Internal-only:** Can be shared within the organization, not outside.
    - **Confidential:** Only accessible to those working on a specific project.
    - **Restricted:** Highly sensitive, need-to-know only (e.g., intellectual property, health or payment info).
- Examples:
    - Internal emails about a new product = confidential.
    - Office doors labeled "restricted" to limit access.
- Classification determines whether an asset can be disclosed, altered, or destroyed.

#### Continuous Process
- Asset management is ongoing and helps uncover security gaps and potential risks.
- Keeping track of all important assets is essential for effective security planning.

### Assets in a Digital World

#### Value of Digital Assets
- Today, information (data) is often the most valuable asset for organizations.
- Data is information that is translated, processed, or stored by computers.
- Billions of devices exchange data globally, making digital asset protection critical.

#### States of Data
- Security teams protect data in three states:
    - **Data in use:**
        - Data being accessed or processed by users or applications.
        - Example: Checking your email on a laptop at a park.
    - **Data in transit:**
        - Data moving from one point to another (e.g., over the internet).
        - Example: Sending an email reply.
    - **Data at rest:**
        - Data stored on a device and not actively being accessed.
        - Example: Laptop closed and data stored on the hard drive.
        - Note: With cloud storage, data may not be "at rest" even if the device is.

#### Importance of Information Security (InfoSec)
- InfoSec is the practice of keeping data in all states away from unauthorized users.
- Weak information security can lead to identity theft, financial loss, and reputational damage.
- Protecting digital assets is essential for organizations, their partners, and customers.

### The Emergence of Cloud Security

#### Cloud-Based Services
- Cloud technologies have made it easier and cheaper for businesses to operate online and scale quickly.
- Cloud-based services are on-demand/web-based business solutions, including:
    - **Software as a Service (SaaS):**
        - Front-end applications accessed via web browser (e.g., Gmail, Slack, Zoom).
        - Provider manages all back-end systems.
    - **Platform as a Service (PaaS):**
        - Online tools for app development, deployment, and management (e.g., Google App Engine, Heroku, VMware Cloud Foundry).
        - Provider hosts and maintains back-end hardware/software.
    - **Infrastructure as a Service (IaaS):**
        - Remote access to servers, storage, networking, and more (e.g., Google Cloud Platform, Microsoft Azure).
        - Resources are licensed as needed, reducing costs.

#### Cloud Security
- Cloud security focuses on protecting data, applications, and infrastructure in the cloud.
- In traditional IT, security was managed entirely on premises by internal teams.
- In the cloud, responsibilities are shared between the client and the provider (shared responsibility model):
    - Clients secure what they control (e.g., identity and access management, resource configuration, data handling).
    - Providers secure the underlying infrastructure.
    - The division of responsibility depends on the service type (SaaS, PaaS, IaaS).

#### Cloud Security Challenges
- **Misconfiguration:** Customers are responsible for configuring their own security, and default settings may not meet their needs.
- **Cloud-native breaches:** More likely if services are misconfigured.
- **Monitoring access:** Can be difficult depending on the client and service level.
- **Regulatory compliance:** Meeting standards like HIPAA, PCI DSS, and GDPR can be challenging.
- As cloud adoption grows, so does the demand for cloud security professionals.

### Elements of a Security Plan

#### Purpose of Security Plans
- Security plans help organizations prepare for and respond to risks affecting digital and physical assets.
- Effective plans require participation from everyone and consider diverse perspectives.
- Focus on protecting the confidentiality, integrity, and availability of assets.

#### Risk Categories and Factors
- Risks are often categorized by:
    - Damage, disclosure, or loss of information
    - Physical damage or device malfunctions
    - Attacks and human error
- Example: New hires may sign agreements to prevent human error (e.g., not using personal email for sensitive info).

#### Three Core Elements
- **Policies:**
    - Set of rules to reduce risk and protect information.
    - Foundation of every security plan; provide strategic guidance (scope, objectives, limitations).
    - Example: Acceptable Use Policy (AUP) for employees.
- **Standards:**
    - Tactical references that inform how to set and measure policies.
    - Serve as points of reference for best practices.
    - Example: NIST password standard requiring at least 8 characters.
- **Procedures:**
    - Step-by-step instructions for specific security tasks.
    - Ensure accountability, consistency, and efficiency.
    - Example: How to choose or reset a secure password.

- Clear communication of policies, standards, and procedures ensures everyone knows their role in protecting assets.

### The NIST Cybersecurity Framework

#### Compliance
- Compliance means adhering to internal standards and external regulations.
- Important for maintaining trust, reputation, safety, and data integrity.
- Non-compliance can result in fines, penalties, lawsuits, and reputational damage—especially in regulated industries (health care, energy, finance).
- Regulations are rules set by authorities to protect people and information.

#### NIST Cybersecurity Framework (CSF)
- Developed by the National Institute of Standards and Technology (NIST).
- Voluntary framework of standards, guidelines, and best practices for managing cybersecurity risk.
- Helps businesses secure information and meet regulatory requirements.

#### Three Main Components
- **Core:**
    - Simplifies the functions of a security plan into five categories:
        - Identify
        - Protect
        - Detect
        - Respond
        - Recover
    - Acts as a security checklist.
- **Tiers:**
    - Measure performance across the five core functions.
    - Range from Level-1 (passive, minimum standards) to Level-4 (adaptive, exemplary standards).
    - Tiers show what is and isn't working in a security plan (not just yes/no).
- **Profiles:**
    - Capture the current state of a security plan (like a snapshot in time).
    - Comparing profiles over time helps organizations see progress and identify areas for improvement.

## Module 2

### Security Control

#### What Are Security Controls?
- Security controls are safeguards designed to reduce specific security risks.
- They protect assets before, during, and after security events.
- Organizations implement them to protect information from being stolen or exposed.

#### Types of Security Controls
- **Technical controls:**
    - Technologies used to protect assets (e.g., encryption, authentication systems).
- **Operational controls:**
    - Day-to-day security activities performed by people (e.g., awareness training, incident response).
- **Managerial controls:**
    - Focus on how the other two types reduce risk (e.g., policies, standards, procedures).

#### Information Privacy
- Information privacy is the protection of unauthorized access and distribution of data.
- It's about the right to choose when, how, and to what extent private information is shared.
- Security controls regulate information privacy.

#### Principle of Least Privilege
- Security controls should limit access based on the user and situation.
- Example: Marketing employees shouldn't have access to customer credit card information.
- Customer support agents should only access payment info when helping with a reservation.

#### Data Ownership and Custodianship
- **Data owner:**
    - Person who decides who can access, edit, use, or destroy their information.
    - Can be multiple owners (e.g., organizational intellectual property).
- **Data custodian:**
    - Responsible for safe handling, transport, and storage of information.
    - Can be people, organizations, or systems.

### Access Control and Authentication Systems

#### What are Access Controls?
- Security controls that manage access, authorization, and accountability of information.
- When implemented well, they maintain data confidentiality, integrity, and availability.
- Help users get information quickly while maintaining security.

#### The AAA Framework
- Access controls are broken down into three related functions:
    - **Authentication:** Verifies identity ("who are you?").
    - **Authorization:** Determines what resources a user can access.
    - **Accounting:** Tracks user activities and access.

#### Authentication Systems
- Ask the fundamental question: "Who are you?"
- Organizations collect answers differently based on security policy objectives.
- Responses can be based on three factors of authentication.

#### Three Factors of Authentication
- **Knowledge (Something you know):**
    - Passwords or answers to security questions.
    - Information the user has memorized.
- **Ownership (Something you have):**
    - Physical items the user possesses.
    - Example: One-time passcodes (OTP) sent via text or email.
- **Characteristic (Something you are):**
    - Biometric features unique to the user.
    - Examples: Fingerprint scans, facial recognition.
    - Becoming more common as it's harder for criminals to impersonate.

#### Authentication Process
- Information provided during authentication must match information on file.
- **Match:** Access granted.
- **No match:** Authentication fails, access denied.

#### Single Sign-On (SSO)
- Technology that combines several different logins into one.
- Establishes user identity once, allowing faster access to company resources.
- Solves the problem of repeatedly authenticating with the same organization.
- **Vulnerability:** Can present significant security risks when used alone.

#### Multi-Factor Authentication (MFA)
- Security measure requiring users to verify identity in two or more ways.
- Combines two or more independent credentials (e.g., knowledge + ownership).
- Strengthens authentication systems beyond single-factor methods.
- **Best practice:** Use SSO and MFA together for both convenience and security.

### The Rise of SSO and MFA

#### A Better Approach to Authentication
- **Single Sign-On (SSO)** combines several different logins into one.
- Companies adopt SSO for three main reasons:
    - **Improved user experience:** Eliminates need to remember multiple usernames/passwords.
    - **Cost reduction:** Streamlines management of connected services.
    - **Enhanced security:** Reduces number of access points attackers can target.

#### Combating Password Fatigue
- SSO became available in mid-1990s to address password fatigue.
- Password fatigue: People's tendency to reuse passwords across services.
- SSO shifts authentication burden away from users.
- Solves the dilemma of remembering many passwords vs. reusing the same password.

#### How SSO Works
- Automates trust establishment between user and service provider.
- Uses trusted third-parties to prove user identity.
- Exchanges encrypted access tokens between identity provider and service provider.

#### SSO Protocols
- **LDAP (Lightweight Directory Access Protocol):**
    - Mostly used for on-premises information transmission.
- **SAML (Security Assertion Markup Language):**
    - Mostly used for off-premises/cloud information transmission.
- Note: LDAP and SAML protocols are often used together.

#### Limitations of SSO
- Usernames and passwords alone aren't always the most secure.
- Risk: Lost or stolen password could expose information across multiple services.
- Still relies on single form of authentication.

#### MFA to the Rescue
- **Multi-Factor Authentication (MFA)** requires identity verification in two or more ways.
- Similar to ATM withdrawal process:
    - Insert debit card (first factor).
    - Enter PIN number (second factor).
    - Both factors verify identity before access.

#### Strengthening Authentication
- MFA builds on SSO benefits.
- Users must provide two factors (2FA) or three factors (3FA).
- **Three types of proofs:**
    - **Something you know:** Username and password.
    - **Something you have:** One-time passcode (OTP) sent via SMS.
    - **Something you are:** Fingerprints or facial scans.
- **Benefits:**
    - Effective security measure, especially in cloud environments.
    - Reduces risk of authenticating wrong users.
    - Forms of identification difficult to imitate or brute force.

### The Data Lifecycle

#### Five Stages of the Data Lifecycle
- The data lifecycle describes how data flows through an organization from creation to disposal:
    - **Collect:** Gathering data from internal and external sources.
    - **Store:** Safely storing data for future use.
    - **Use:** Accessing and processing data for business purposes.
    - **Archive:** Moving data to long-term storage when no longer actively used.
    - **Destroy:** Securely disposing of data when no longer needed.
- Security teams must protect information at each stage to keep it accessible and recoverable.

#### Data Governance
- Data governance is a set of processes that define how an organization manages information.
- Includes policies for keeping data private, accurate, available, and secure throughout its lifecycle.
- Three key roles:
    - **Data owner:** Decides who can access, edit, use, or destroy their information.
    - **Data custodian:** Responsible for safe handling, transport, and storage of information.
    - **Data steward:** Maintains and implements data governance policies set by the organization.
- Security professionals often serve as data custodians, responsible for maintaining security and privacy rules.

#### Legally Protected Information
- Governments and regulatory agencies have created rules for protecting certain types of data by default:
    - **PII (Personally Identifiable Information):** Information used to identify, contact, or locate someone.
    - **PHI (Protected Health Information):** Health-related information regulated by HIPAA (U.S.) and GDPR (EU).
    - **SPII (Sensitive Personally Identifiable Information):** PII that requires stricter handling (e.g., bank account numbers, login credentials).
- All personal information must be protected from unauthorized use and disclosure.

### Information Privacy: Regulations and Compliance

#### Information Security vs. Information Privacy
- **Information privacy:** Protection of unauthorized access and distribution of data.
- **Information security (InfoSec):** Practice of keeping data away from unauthorized users.
- Key difference: Privacy is about control over personal information; security is about protecting that information from threats.
- Example: A retail company discloses how customer data will be used and offers opt-out options (privacy), then implements security controls to protect that data.

#### Why Privacy Matters in Security
- Data privacy became a major concern in the late 1990s when companies began storing and using personal data for business purposes.
- The more data collected, stored, and used, the more vulnerable it is to breaches and threats.
- Organizations became more transparent about data practices and implemented security measures, but protections were inconsistent without clear rules.

#### Notable Privacy Regulations
- **GDPR (General Data Protection Regulation):**
    - EU regulation giving data owners total control over their personal information.
    - Applies to any business handling EU citizen/resident data, regardless of location.
- **PCI DSS (Payment Card Industry Data Security Standard):**
    - Security standards for credit/debit card transactions to prevent data theft and fraud.
- **HIPAA (Health Insurance Portability and Accountability Act):**
    - U.S. law requiring protection of sensitive patient health information.
    - Prohibits disclosure of medical information without consent.

#### Security Assessments and Audits
- **Security audit:**
    - Review of security controls, policies, and procedures against set expectations.
    - Performed less frequently (about once per year), internally or by third parties.
    - Determines compliance with legal regulations.
- **Security assessment:**
    - Check of how resilient current security implementations are against threats.
    - Performed more frequently (every 3-6 months), typically by internal employees.
    - Often prepares for security audits.
- Both are essential for ensuring systems effectively protect privacy.

### Fundamentals of Cryptography

#### Personally Identifiable Information (PII)
- PII is any information that can be used to infer an individual's identity.
- Examples: name, medical/financial information, photos, emails, fingerprints.
- Maintaining PII privacy online requires proper security controls.

#### What is Cryptography?
- Cryptography transforms information into a form that unintended readers can't understand.
- Two-step process:
    - **Encryption:** Hides information by converting plaintext (readable) to ciphertext (unreadable).
    - **Decryption:** Unhides information by converting ciphertext back to plaintext.
- Example: Email encryption scrambles the message during transmission, then unscrambles it for the recipient.

#### Caesar's Cipher
- One of the earliest cryptographic methods, used by Julius Caesar.
- Simple algorithm that shifts letters in the alphabet by a fixed number of spaces.
- Example: With a shift of 3, "hello" becomes "khoor" (A→D, B→E, C→F, etc.).
- A cipher is an algorithm that encrypts information.

#### Cryptographic Keys
- A cryptographic key is a mechanism that decrypts ciphertext.
- The key tells you how to unlock the hidden message (e.g., the shift value in Caesar's cipher).
- Every form of encryption relies on both a cipher and a key.

#### Flaws in Caesar's Cipher
- **Limited alphabet:** Only 26 characters make it vulnerable to brute force attacks (trying all 26 possible shifts).
- **Single key:** If the key is lost or stolen, all encrypted information is compromised.
- **Key management:** Keys must be stored securely and shared separately from the encrypted information.

### Public Key Infrastructure

#### What is PKI?
- Public Key Infrastructure (PKI) is an encryption framework that secures online information exchange.
- Makes accessing information fast, easy, and secure.
- Solves the problem of managing encryption keys for all personal information online.

#### Two Types of Encryption
- **Asymmetric encryption:**
    - Uses a public and private key pair.
    - Public key: Can only add items to the "box" (encrypt), can be shared widely.
    - Private key: Opens the "box" fully (decrypt), only accessible to the owner.
    - More secure but slower than symmetric encryption.
- **Symmetric encryption:**
    - Uses a single secret key for both encryption and decryption.
    - Faster and simpler, but less secure.
    - The same key is shared between parties.

#### PKI in Practice
- PKI uses both asymmetric and symmetric encryption depending on priorities.
- Example: Mobile chat apps use asymmetric encryption to establish secure connections, then switch to symmetric encryption for faster communication.
- Both types share a vulnerability: establishing trust between sender and receiver.

#### Digital Certificates
- Digital certificates verify the identity of a public key holder.
- Most online information exchange uses digital certificates.
- **Certificate Authority (CA):**
    - Trusted organization that creates digital certificates.
    - Verifies company identity and encrypts data with its own private key.
    - Creates a digital certificate containing encrypted company data and CA's digital signature.
- Example: When a business registers a domain, the hosting company sends information to a CA, which verifies the company's identity and creates a digital certificate.

### Symmetric and Asymmetric Encryption

#### Types of Encryption
- **Symmetric encryption:**
    - Uses a single secret key for both encryption and decryption.
    - Sender and receiver must both know the secret key.
    - Faster but requires secure key sharing.
- **Asymmetric encryption:**
    - Uses a public and private key pair.
    - Public key encrypts data, private key decrypts it.
    - Private key only given to authorized users.
    - More secure but slower than symmetric encryption.

#### Importance of Key Length
- Ciphers are vulnerable to brute force attacks (trial and error).
- Longer key lengths = more secure (more possibilities to try).
- Drawback: Longer keys mean slower processing times.
- Balance needed between security and speed for online communication.

#### Approved Symmetric Algorithms
- **Triple DES (3DES):**
    - Block cipher that applies DES algorithm three times.
    - Uses three different 56-bit keys (effective 168-bit key length).
    - Being phased out due to data limitations but still used for backwards compatibility.
- **Advanced Encryption Standard (AES):**
    - Most secure symmetric algorithm today.
    - Generates 128, 192, or 256-bit keys.
    - Considered safe from brute force attacks (128-bit could take billions of years).

#### Approved Asymmetric Algorithms
- **RSA (Rivest Shamir Adleman):**
    - Named after its three MIT creators.
    - One of the first asymmetric encryption algorithms.
    - Key sizes: 1,024, 2,048, or 4,096 bits.
    - Mainly used for highly sensitive data.
- **DSA (Digital Signature Algorithm):**
    - Standard introduced by NIST in early 1990s.
    - Generates 2,048-bit keys.
    - Widely used as complement to RSA in PKI.

#### Generating Keys
- **OpenSSL:** Open-source command line tool for generating public and private keys.
- Used by computers to verify digital certificates in PKI.
- Note: OpenSSL had Heartbleed bug vulnerability in 2014 (patched later that year).
- Importance of using up-to-date software for security.

#### Security Principle: Obscurity is Not Security
- **Kerckhoff's principle:** All algorithm details should be knowable except the private key.
- Ciphers must be proven unbreakable before claiming security.
- Example: AES details are publicly available but still unbreakable.
- Custom encryption algorithms often get cracked quickly when made public.
- Cryptographic systems shouldn't require secrecy around how they work.

#### Encryption in Practice
- Companies use both symmetric and asymmetric encryption together.
- **Website example:**
    - Asymmetric encryption for usernames/passwords during login.
    - Switches to symmetric encryption for faster web sessions.
- **Regulatory compliance:**
    - FIPS 140-3 and GDPR require data encryption.
    - Compliance demonstrates responsible data handling to partners and governments.

### Non-repudiation and Hashing

#### What are Hash Functions?
- Hash functions are algorithms that produce codes that cannot be decrypted.
- Unlike asymmetric and symmetric algorithms, they are one-way processes.
- Do not generate decryption keys.
- Produce a unique identifier known as a hash value or digest.

#### How Hash Functions Work
- **Example scenario:** Company has an internal application stored on a shared drive.
- After passing through a hashing function, the program receives its hash value.
- Even a small change (one line of code) produces a completely different hash value.
- By comparing hash values, we can validate if files are identical or different.

#### Data Integrity and Non-repudiation
- **Data integrity:** Accuracy and consistency of information.
- **Non-repudiation:** Concept that authenticity of information cannot be denied.
- Hash functions are security controls that make proven data integrity possible.
- Help identify when files have been modified or tampered with.

#### Practical Applications
- **File validation:** Compare hash values against known malicious files.
- **Application security:** Verify that programs haven't been modified.
- **Attack detection:** Identify when attackers replace legitimate programs with malicious versions.

#### Using Hash Functions in Linux
- **Command example:**
    ```bash
    sha256sum newfile.txt
    ```
- Generates a unique hash value for any file.
- Common hashing algorithms: SHA-256, MD5 (though MD5 is less secure).
- Longer hash values are generally more secure.

#### Security Tools
- **VirusTotal:** Popular tool among security practitioners.
- Useful for analyzing suspicious files, domains, IPs, and URLs.
- Compares file hashes against known malicious file databases.
- Helps identify malware and other security threats.

#### Rainbow Tables and Salting
- **Rainbow tables:** Files containing pre-generated hash values and their associated plaintext.
- Like dictionaries of weak passwords.
- Attackers can use them to compare against password databases.
- Functions with larger digests are less vulnerable to rainbow table attacks.

#### Salting as Protection
- **Salt:** Random string of characters added to data before hashing.
- Produces more unique hash values.
- Makes salted data resilient to rainbow table attacks.
- **Example:** Database with multiple "password" entries.
    - Without salt: All entries would have identical hash values.
    - With salt: Each entry produces a completely different hash.
    - Attackers using rainbow tables cannot find matching values.

### The Mechanisms of Authorization

#### Authorization vs. Authentication
- **Authentication:** Validates who the user is.
- **Authorization:** Determines what the user is allowed to do.
- Both work closely together in access control systems.
- Authorization assigns responsibility for systems and processes.

#### Key Authorization Principles
- **Principle of least privilege:** Access only lasts as long as needed.
- **Separation of duties:** Users shouldn't have authorization levels that allow system misuse.
- Reduces risk of system failures and inappropriate behavior.
- Applies to people, networks, databases, processes, and all organizational aspects.

#### Separation of Duties Examples
- **Customer service example:** Person providing customer service shouldn't rate their own performance.
- **Security system example:** Person developing and testing a security system might be unaware of its weaknesses.
- Prevents conflicts of interest and ensures oversight.

#### HTTP Basic Authentication
- **HTTP:** Hypertext Transfer Protocol for network communications.
- **Basic auth:** Technology used to establish user's request to access a server.
- Sends an identifier every time user communicates with a web page.
- **Vulnerability:** Transmits usernames and passwords openly over the network.
- Most websites now use HTTPS (Hypertext Transfer Protocol Secure) instead.

#### OAuth Authorization Protocol
- **OAuth:** Open-standard authorization protocol that shares designated access between applications.
- **Example:** Telling Google it's okay for another website to access your profile to create an account.
- Uses API tokens instead of sending sensitive usernames/passwords over the network.

#### API Tokens
- Small blocks of encrypted code containing user information.
- Contain identity, site permissions, and more.
- Passed from server to user's device for access requests.
- **Benefits:**
    - Additional layer of encryption.
    - Keeps passwords safe in event of breach on another platform.
    - MFA benefits still apply when using OAuth.

#### Authorization Tools
- Basic auth and OAuth are examples of authorization tools.
- Designed with least privilege and separation of duty principles.
- Many other controls help limit unauthorized access risk.
- Important to monitor access in addition to controlling it.

### Why We Audit User Activity

#### What is Accounting?
- **Accounting:** Practice of monitoring access logs of a system.
- Access logs contain information about:
    - Who accessed the system.
    - When they accessed it.
    - What resources they used.
- Essential for security analysts in investigating security events.

#### Uses of Access Logs
- **Identify trends:** Failed login attempts, unusual patterns.
- **Uncover hackers:** Detect unauthorized access to systems.
- **Detect incidents:** Data breaches and security events.
- Often the first procedure when investigating a security event.

#### How Sessions Work
- **Session:** Sequence of network HTTP basic auth requests and responses associated with the same user.
- Example: Visiting a website.
- Access logs record sessions from user entry to exit.

#### Session Management
- **Two actions triggered when session begins:**
    - **Session ID creation:** Unique token identifying user and device.
        - Attached to user until browser closes or session times out.
    - **Session cookie exchange:** Token between server and user device.
        - Validates session and determines session duration.
        - Determines what information website should show user.

#### Benefits of Session Cookies
- Make web sessions safer and more efficient.
- Exchange tokens instead of sensitive information (usernames/passwords).
- Prevent attackers from obtaining sensitive data.

#### Session Hijacking
- **Session hijacking:** Attackers obtain legitimate user's session ID.
- **Risk:** With stolen cookie, attacker can impersonate user using session token.
- **Potential harm:**
    - Money or private data stolen.
    - Access to additional systems through stolen SSO credentials.
- **Detection:** Unusual activity on access logs can indicate improper access or theft.

#### Importance of Accounting
- Provides valuable insight that makes information safer.
- Essential for detecting and responding to security threats.
- Helps maintain system security and user privacy.

### Lab: Decrypt an Encrypted Message

#### Task 1: Read the Contents of a File
- **Starting location:** `/home/analyst` directory.
- **Step 1:** List files in current directory.
    ```bash
    ls /home/analyst
    ```
    - Output shows: `Q1.encrypted`, `README.txt`, and `caesar` subdirectory.
- **Step 2:** Read the README.txt file.
    ```bash
    cat README.txt
    ```
    - Message indicates data is encrypted and a hidden file exists in the `caesar` subdirectory.

#### Task 2: Find a Hidden File
- **Step 1:** Navigate to the caesar subdirectory.
    ```bash
    cd caesar
    ```
- **Step 2:** List all files (including hidden ones).
    ```bash
    ls -a
    ```
    - Shows hidden file `.leftShift3`.
- **Step 3:** View the encrypted content.
    ```bash
    cat .leftShift3
    ```
    - Contains scrambled text encrypted with Caesar cipher (3-letter left shift).

#### Caesar Cipher Decryption
- **Command used:**
    ```bash
    cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
    ```
- **How the tr command works:**
    - `tr` translates characters from one set to another.
    - First parameter: input character set.
    - Second parameter: output character set.
    - Example: `tr "abcd" "pqrs"` would convert "ac" to "pr".
- **Caesar cipher explanation:**
    - 3-letter left shift means "d" represents "a", "e" represents "b", etc.
    - The pattern `"d-za-cD-ZA-C"` maps shifted letters back to original positions.
    - `"a-zA-Z"` represents the normal alphabet (lowercase and uppercase).

#### Decryption Result
- The decrypted message provides the OpenSSL command to recover the encrypted file:
    ```bash
    openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
    ```
- **OpenSSL command breakdown:**
    - `aes-256-cbc`: Uses AES-256 encryption in CBC mode.
    - `-pbkdf2`: Uses PBKDF2 key derivation function.
    - `-a`: Base64 encoding.
    - `-d`: Decrypt mode.
    - `-in Q1.encrypted`: Input file.
    - `-out Q1.recovered`: Output file.
    - `-k ettubrute`: Password/key for decryption.

### Identity and Access Management

#### Fundamental Security Principles
- **Principle of least privilege:** User granted minimum level of access required to complete tasks.
- **Separation of duties:** Users shouldn't have authorization levels that allow system misuse.
- Both principles support each other.
- **Example:** Person approving IT purchases shouldn't approve all department purchases (least privilege).
- Person approving purchases should be different from person inputting purchases (separation of duties).

#### What is IAM?
- **Identity and Access Management (IAM):** Collection of processes and technologies managing digital identities.
- Similar to AAA framework: authenticates users, determines access privileges, tracks activities.
- Ensures right user gets access to right resources at right time for right reasons.
- **Note:** User can be a person, device, or software.

#### Authenticating Users
- Requires proof that user is who they claim to be.
- **Three authentication factors:**
    - **Knowledge:** Something the user knows.
    - **Ownership:** Something the user possesses.
    - **Characteristic:** Something the user is.
- **Tools used:**
    - Login credentials.
    - Single Sign-On (SSO).
    - Multi-Factor Authentication (MFA).

#### User Provisioning
- **User provisioning:** Process of creating and maintaining user's digital identity.
- **Example:** College creates new user account when hiring instructor.
- Account configured for instructor-only resources while teaching.
- Security analysts involved in provisioning users and access privileges.
- **Deprovisioning:** Removing user access rights when no longer needed.

#### Authorization Frameworks
- **Three common frameworks:**
    - **Mandatory Access Control (MAC):**
        - Strictest framework, based on need-to-know basis.
        - Access granted manually by central authority.
        - Common in law enforcement, military, government agencies.
        - Also called non-discretionary control.
    - **Discretionary Access Control (DAC):**
        - Data owner decides appropriate access levels.
        - Example: Google Drive folder sharing (editor, viewer, commentor access).
    - **Role-Based Access Control (RBAC):**
        - Authorization determined by user's organizational role.
        - Example: Marketing user has analytics access but not network administration.

#### Access Control Technologies
- Users experience authentication and authorization as seamless experience.
- Tools offer speed and automation for administrators.
- Decrease errors and potential risks.
- **Typical IAM/AAA system components:**
    - User directory.
    - Tools for managing directory data.
    - Authorization system.
    - Auditing system.
- **Options:**
    - **Custom development:** Tailored to security needs but costly in time/resources.
    - **Third-party solutions:** Licensed tools for quick system securing.
- **Important:** Configure technologies to provide secure environment, not just combine tools.


## Module 3

### Vulnerability Management

#### Understanding Vulnerabilities
- **Vulnerability:** Weakness that can be exploited by a threat.
- The word "can" is important - indicates potential for exploitation.
- **Example:** Important document is vulnerable to theft, fire, water damage.
- Security teams plan protections based on vulnerabilities and how they can be exploited.

#### What are Exploits?
- **Exploit:** Way of taking advantage of a vulnerability.
- Security planning relies on thinking about potential exploits.
- **Example:** Windows are vulnerable to being broken.
- Burglar can exploit this by using a rock to break the window.
- Thinking ahead allows planning defenses (alarm systems, police alerts).

#### The Four-Step Process
- **Vulnerability management:** Process of finding and patching vulnerabilities.
- Helps keep assets safe by stopping threats before they become problems.
- **Four steps:**
    1. **Identify vulnerabilities.**
    2. **Consider potential exploits** of those vulnerabilities.
    3. **Prepare defenses** against threats.
    4. **Evaluate those defenses.**
- Process happens in a cycle - starts again after evaluation.
- Regular part of security team responsibilities.

#### Importance of Diverse Perspectives
- Wide range of backgrounds and experiences strengthens security teams.
- Helps find exploits that might otherwise be overlooked.
- Even large, diverse teams can't keep track of everything.
- New vulnerabilities constantly being discovered.

#### Zero-Day Exploits
- **Zero-day exploit:** Previously unknown exploit.
- Term refers to zero days to fix it - happening in real time.
- **Dangerous:** Represent threats that haven't been planned for.
- **Example:** Lock falling off door from intense heat (unexpected).
- **Digital example:** New form of spyware infecting popular website.
- Can leave assets more vulnerable than they already are.

#### Continuous Process
- Vulnerability management is performed regularly at most organizations.
- Most important step: identifying vulnerabilities.
- Process must be ongoing due to constantly evolving threats.

### Vulnerabilities of CI/CD

#### What is CI/CD and Why Does it Matter?
- **CI/CD** automates the entire software release process from code creation to deployment.
- Enables modern development teams to be agile and respond quickly to user needs.
- **Three key components:**
    - **Continuous Integration (CI):** Frequently merging code changes, automated building and testing.
    - **Continuous Delivery (CD):** Code always ready for release, manual approval before production.
    - **Continuous Deployment (CD):** Fully automated releases to production with no manual approval.

#### Security Benefits of CI/CD
- **Secure Automation:** Reduces manual errors and speeds processes when implemented securely.
- **Improved Code Quality:** Automated security tests check code before release.
- **Faster Security Updates:** Accelerates delivery of security patches and bug fixes.
- **Enhanced Collaboration:** Encourages collaboration between development, security, testing, and operations teams.
- **Reduced Risk:** Frequent, smaller releases are less risky than large, infrequent releases.

#### Common CI/CD Pipeline Vulnerabilities
- **Insecure Dependencies:**
    - Third-party libraries with known vulnerabilities (CVEs).
    - Can be unknowingly added during automated build process.
    - **Action:** Regularly scan and update dependencies.
- **Misconfigured Permissions:**
    - Weak access controls in CI/CD tools and repositories.
    - Unauthorized access can modify code or inject malicious content.
    - **Action:** Implement strong RBAC (Role-Based Access Control).
- **Lack of Automated Security Testing:**
    - Missing SAST and DAST tools in pipeline.
    - Vulnerabilities go undetected until after release.
    - **Action:** Integrate automated security testing (SAST and DAST).
- **Exposed Secrets:**
    - Hardcoded API keys, passwords, and tokens in code or pipeline settings.
    - Can lead to major security breaches.
    - **Action:** Use secure vaults or secrets management tools.
- **Unsecured Build Environments:**
    - Vulnerable CI/CD infrastructure (servers and systems).
    - Attackers can compromise to alter builds or steal data.
    - **Action:** Harden build environments with secure containers or VMs.

#### Building a Secure CI/CD Pipeline
- **Integrate Security from Start:**
    - Adopt DevSecOps mindset.
    - Build security into every development stage.
- **Implement Strong Access Controls:**
    - Use principle of least privilege.
    - Implement MFA and RBAC.
- **Automate Security Testing:**
    - Make SAST, SCA, and DAST fundamental parts of build process.
    - Catch vulnerabilities early.
- **Keep Dependencies Updated:**
    - Maintain current inventory of third-party components.
    - Use tools like Dependabot and Snyk for automated management.
- **Secure Secrets Management:**
    - Never hardcode sensitive information.
    - Use dedicated tools like HashiCorp Vault or AWS Secrets Manager.

#### Conclusion
- Proactively addressing vulnerabilities and implementing security best practices.
- Secure CI/CD foundation crucial for minimizing security risks.
- Essential for building resilient security strategy for applications and infrastructure.

### Defense in Depth Strategy

#### What is Defense in Depth?
- **Defense in depth:** Security model using layered approach to vulnerability management.
- When one barrier fails, another takes its place to stop an attack.
- Reduces risk through multiple layers of protection.
- Commonly referred to as the "castle approach."

#### The Castle Analogy
- Medieval castles were difficult to penetrate due to layered defenses.
- **Multiple defense layers:**
    - **Moat:** Water-filled barrier preventing large groups from reaching walls.
    - **Stone walls:** Second layer that could be climbed.
    - **Watch towers:** Third layer with defenders ready to shoot arrows.
- Each level minimized attack risk by identifying vulnerabilities and implementing security controls.
- If one system failed, another took its place.

#### Five-Layer Design
- Defense in depth can protect any asset.
- Mainly used in cybersecurity to protect information.
- Each layer features security controls protecting information as it travels in and out.

#### The Five Layers
- **1. Perimeter Layer:**
    - User authentication layer filtering external access.
    - Technologies: Usernames and passwords.
    - Function: Only allow trusted partners to reach next layer.
- **2. Network Layer:**
    - Closely aligned with authorization.
    - Technologies: Network firewalls and others.
- **3. Endpoint Layer:**
    - Protects devices with network access (laptops, desktops, servers).
    - Technologies: Anti-virus software.
- **4. Application Layer:**
    - Includes interfaces used to interact with technology.
    - Security measures programmed as part of applications.
    - Example: Multi-factor authentication (password + SMS code).
- **5. Data Layer:**
    - Critical data that must be protected (PII, etc.).
    - Important security control: Asset classification.

### Common Vulnerabilities and Exposures

#### Vulnerabilities vs. Exposures
- **Vulnerability:** Weakness of a system.
- **Exposure:** Mistake that can be exploited by a threat.
- **Example:** Document is vulnerable to being misplaced.
- If document is laid near open window, it's exposed to being blown away.
- Online public libraries share and document common vulnerabilities and exposures.

#### The CVE List
- **CVE (Common Vulnerabilities and Exposures):** Openly accessible dictionary of known vulnerabilities and exposures.
- Created by MITRE Corporation in 1999.
- MITRE: Non-profit research and development centers sponsored by US government.
- Focus on improving security technologies worldwide.
- Popular resource used by organizations to improve defenses.

#### CVE Reporting and Review Process
- **Reporters:** Independent researchers, technology vendors, ethical hackers, anyone.
- **CNA (CVE Numbering Authority):** Organization that volunteers to analyze and distribute CVE information.
- Must have established record of researching vulnerabilities and security advisory capabilities.
- **Four criteria for CVE assignment:**
    1. **Independent:** Can be fixed without fixing something else.
    2. **Recognized risk:** Reported as potential security risk.
    3. **Supporting evidence:** Submitted with evidence.
    4. **Single codebase:** Only affects one program's source code.

#### CVSS Scoring System
- **CVSS (Common Vulnerability Scoring System):** Measurement system scoring vulnerability severity.
- Used by NIST National Vulnerabilities Database.
- **Base score scale:** 0-10 (reflects moment of evaluation, doesn't change over time).
- **Risk levels:**
    - **Below 4.0:** Low risk, no immediate attention required.
    - **Above 9.0:** Critical risk, should be addressed immediately.
- Security teams use CVSS to:
    - Calculate potential impact on system.
    - Determine how quickly to patch vulnerability.

#### Practical Applications
- Security teams use CVE list and CVSS scores in vulnerability management strategy.
- Provide recommendations for prioritizing security fixes.
- Help answer key questions:
    - Is vulnerability dangerous to our business?
    - How soon should we address it?
- Examples: Installing software updates before patches.

### What is OWASP?

#### OWASP Foundation
- **OWASP:** Nonprofit foundation working to improve software security.
- Open platform for security professionals worldwide.
- Shares information, tools, and events focused on securing the web.

#### The OWASP Top 10
- **OWASP Top 10:** Most valuable resource, published since 2003.
- Spreads awareness of web's most targeted vulnerabilities.
- Applies mainly to new or custom-made software.
- Used by world's largest organizations during application development.
- **Updated every few years** as technologies evolve.
- Rankings based on discovery frequency and risk level.
- **Note:** Auditors use as reference for regulatory compliance.

#### Common Vulnerabilities

##### 1. Broken Access Control
- Access controls limit what users can do in web applications.
- **Example:** Blog allows comments but restricts article deletion.
- Failures can lead to unauthorized information disclosure, modification, or destruction.
- Can give unauthorized access to other business applications.

##### 2. Cryptographic Failures
- Information is critical asset businesses need to protect.
- Privacy laws (GDPR) require effective encryption for sensitive data.
- Vulnerabilities occur when businesses fail to encrypt PII.
- **Example:** Using weak hashing algorithm like MD5 increases breach risk.

##### 3. Injection
- Malicious code inserted into vulnerable applications.
- App appears normal but does unintended things.
- Can give threat actors backdoor into organization's information system.
- **Common target:** Website login forms.
- Attackers can insert malicious code to modify or steal credentials.

##### 4. Insecure Design
- Applications should be designed to be resilient to attack.
- Refers to missing or poorly implemented security controls.
- Should have been programmed during development.
- Makes applications vulnerable to injection attacks or malware infections.

##### 5. Security Misconfiguration
- Security settings not properly set or maintained.
- Mistakes happen when interconnected systems aren't properly set up or audited.
- **Common example:** Deploying equipment with default settings.
- Can fail to address organization's security objectives.

##### 6. Vulnerable and Outdated Components
- Relates to application development.
- Developers use open-source libraries instead of coding from scratch.
- Publicly available software maintained by volunteer communities.
- Applications using unmaintained vulnerable components at greater risk.

##### 7. Identification and Authentication Failures
- **Keyword:** Identification.
- Applications fail to recognize who should have access and what they're authorized to do.
- **Example:** Home Wi-Fi router login form failure allows network invasion.
- Can lead to serious privacy and security problems.

##### 8. Software and Data Integrity Failures
- Updates or patches inadequately reviewed before implementation.
- Attackers can exploit to deliver malicious software.
- **Supply chain attack:** Third parties infected if single system compromised.
- **Famous example:** SolarWinds cyber attack (2020) - malicious code injected into software updates.

##### 9. Security Logging and Monitoring Failures
- Important to log and trace back events.
- Record of events (like login attempts) critical for finding and fixing problems.
- Sufficient monitoring and incident response equally important.

##### 10. Server-Side Request Forgery
- Companies store public and private information on web servers.
- When using hyperlinks or clicking buttons, requests sent to servers.
- Servers should validate identity, fetch appropriate data, and return it.
- **SSRFs (Server-side request forgeries):** Attackers manipulate normal server operations to read or update other resources.
- Possible when server application is vulnerable.
- Malicious code carried by vulnerable app to host server fetches unauthorized data.

### Open Source Intelligence

#### Information vs Intelligence
- **Information:** Collection of raw data or facts about a specific subject.
- **Intelligence:** Analysis of information to produce knowledge or insights for decision-making.
- **Example:** New OS update information → research linking cyber threats to update → intelligence guides decision about installing updates.
- Intelligence is derived from information through analysis, interpretation, and integration.
- Both gathering information and intelligence are important in cybersecurity.

#### Intelligence Improves Decision-Making
- Businesses use information to gain customer behavior insights.
- Intelligence used to improve decision-making.
- In security, open-source information used similarly to gain insights into threats and vulnerabilities.
- OSINT plays significant role in Information Security (InfoSec).

#### OSINT in Information Security
- **InfoSec:** Practice of keeping data in all states away from unauthorized users.
- **Example:** Company's InfoSec team protects network from potential threats.
- Use OSINT to monitor online forums and hacker communities for emerging vulnerabilities.
- If forum post discusses new weakness in popular software company uses:
    - Quickly assess risk.
    - Prioritize patching efforts.
    - Implement necessary safeguards.

#### Ways OSINT Generates Intelligence
- **Provide insights into cyber attacks.**
- **Detect potential data exposures.**
- **Evaluate existing defenses.**
- **Identify unknown vulnerabilities.**
- Collecting intelligence is part of vulnerability management process.
- Security teams use OSINT to:
    - Develop profiles of potential targets.
    - Make data-driven decisions on improving defenses.

### Vulnerability Assessments

#### What are Vulnerability Assessments?
- **Vulnerability assessment:** Internal review process of organization's security systems.
- Works similar to CVE list process of identifying and categorizing vulnerabilities.
- **Main difference:** Organization's security team performs, evaluates, scores, and fixes them.
- Security analysts play key role throughout the process.
- **Goals:**
    - Identify weak points and prevent attacks.
    - Determine whether security controls meet regulatory standards.
- Organizations perform them frequently due to many assets to protect.
- Security teams select which areas to focus on through assessments.

#### The Four-Step Process

##### 1. Identification
- Scanning tools and manual testing used to find vulnerabilities.
- Goal: Understand current state of security system (like taking a picture).
- Large number of findings usually appear after identification.

##### 2. Vulnerability Analysis
- Each identified vulnerability is tested.
- Goal: Find the source of the problem (being a digital detective).

##### 3. Risk Assessment
- Score assigned to each vulnerability based on two factors:
    - **Severity of impact** if vulnerability were exploited.
    - **Likelihood** of exploitation happening.
- Vulnerabilities often outnumber people available to fix them.
- Risk assessments prioritize resources based on vulnerability scores.

##### 4. Remediation
- Vulnerabilities that can impact organization are addressed.
- Remediation occurs based on severity score from risk assessment step.
- **Joint effort:** Security staff and IT teams collaborate on best approach.
- **Examples of remediation steps:**
    - Enforcing new security procedures.
    - Updating operating systems.
    - Implementing system patches.

### Approaches to Vulnerability Scanning

#### What is a Vulnerability Scanner?
- **Vulnerability scanner:** Software that automatically compares known vulnerabilities against network technologies.
- Scans systems to find misconfigurations or programming flaws.
- Used to analyze the five attack surfaces from defense in depth strategy.
- **Five attack surfaces:**
    - **Perimeter layer:** Authentication systems validating user access.
    - **Network layer:** Technologies like network firewalls.
    - **Endpoint layer:** Devices on network (laptops, desktops, servers).
    - **Application layer:** Software users interact with.
    - **Data layer:** Information stored, in transit, or in use.
- Scanning tool compares findings against security threat databases.
- Flags vulnerabilities and adds them to reference database.
- Each scan adds more information, improving accuracy.
- **Note:** Vulnerability databases updated by scanning software company.

#### Performing Scans
- **Non-intrusive:** Don't break or take advantage of systems like attackers would.
- Simply scan surface and alert to potentially unlocked doors.
- **Note:** Can inadvertently cause issues like system crashes.
- Different approaches correspond to threat actor pathways.

#### Types of Scans

##### External vs. Internal
- **External scans:** Test perimeter layer outside internal network.
    - Analyze outward-facing systems (websites, firewalls).
    - Uncover vulnerable network ports or servers.
- **Internal scans:** Examine organization's internal systems.
    - Analyze application software for weaknesses in user input handling.

##### Authenticated vs. Unauthenticated
- **Authenticated scans:** Test system with real user or admin account.
    - Check for vulnerabilities like broken access controls.
- **Unauthenticated scans:** Simulate external threat actors without access.
    - **Example:** Analyze file shares for internal-only documents.
    - Should receive "access denied" results.
    - Vulnerability identified if unauthorized access possible.

##### Limited vs. Comprehensive
- **Limited scans:** Analyze particular devices on network.
    - **Example:** Search for misconfigurations on firewall.
- **Comprehensive scans:** Analyze all devices connected to network.
    - Includes operating systems, user databases, and more.
- **Pro tip:** Discovery scanning should be done prior to limited or comprehensive scans.
    - Gets idea of computers, devices, and open ports on network.

### The Importance of Updates

#### Patching Gaps in Security
- **Outdated computer:** Like house with unlocked doors.
- Malicious actors use security gaps to gain unauthorized access.
- **Software updates:** Like locking doors to keep them out.
- **Patch update:** Software and OS update addressing security vulnerabilities.
- Patches contain bug fixes for common vulnerabilities and exposures.
- **Note:** Ideally patches address vulnerabilities before hackers find them.
- Sometimes developed as result of zero-day exploits.

#### Common Update Strategies
- Two installation options when updates become available:
    - **Manual updates**
    - **Automatic updates**
- Each strategy has benefits and disadvantages.

#### Manual Updates
- **Manual deployment:** Relies on IT departments or users obtaining updates from developers.
- **Home/small business:** Find, download, and install updates yourself.
- **Enterprise settings:** Handled with configuration management tools.
- Tools offer options to deploy to all clients or select groups.
- **Advantage:** Control useful if updates not thoroughly tested by developers.
- **Disadvantage:** Critical updates can be forgotten or disregarded entirely.

#### Automatic Updates
- **Automatic deployment:** System or application handles finding, downloading, and installing updates.
- **Pro tip:** CISA recommends using automatic options whenever available.
- Certain permissions need to be enabled before updates can be installed.
- Developers responsible for adequately testing patches before release.
- **Advantage:** Deployment process simplified, keeps systems current with latest patches.
- **Disadvantage:** Instability issues if patches not thoroughly tested by vendor.

#### End-of-Life Software
- **EOL software:** Updates not available for certain software types.
- All software has lifecycle from production to newer version release.
- Developers allocate resources to newer versions, leading to EOL software.
- Older software still useful but manufacturer no longer supports it.
- **Note:** Patches/updates different from upgrades (completely new versions).
- **CISA recommendation:** Discontinue use of EOL software due to unfixable risk.
- Replacing EOL technology can be costly for businesses and users.
- **Growing risks:** More connected devices (IoT) entering marketplace.
- **Example:** Billions of IoT devices like smart light bulbs connected to networks.
- Single unpatched device can give attacker network access.

### Penetration Testing

#### What is Penetration Testing?
- **Penetration test (pen test):** Simulated attack identifying vulnerabilities in systems, networks, websites, applications, and processes.
- Uses same tools and techniques as malicious actors to mimic real-life attack.
- **Authorized attack:** Considered form of ethical hacking.
- Unlike vulnerability assessment (finds weaknesses), pen test exploits weaknesses to determine potential consequences.
- **Example:** Financial company simulates attack on banking app to test for weaknesses allowing customer information theft or illegal fund transfers.
- **Note:** Organizations regulated by PCI DSS, HIPAA, or GDPR must routinely perform penetration testing for compliance.

#### Learning from Varied Perspectives
- Performed by pen testers skilled in programming and network architecture.
- **Three approaches:**
    - **Red team tests:** Simulate attacks to identify vulnerabilities in systems, networks, or applications.
    - **Blue team tests:** Focus on defense and incident response to validate existing security systems.
    - **Purple team tests:** Collaborative, combining elements of red and blue team exercises.
- Red team tests commonly performed by independent pen testers hired to evaluate internal systems.
- Cybersecurity teams may also have their own pen testing experts.
- Important decision before simulating attack: How much access and information do I need?

#### Penetration Testing Strategies
- **Three common strategies:**
    - **Open-box testing:** Tester has same privileged access as internal developer.
        - Information: System architecture, data flow, network diagrams.
        - Also called: Internal, full knowledge, white-box, clear-box testing.
    - **Closed-box testing:** Tester has little to no access to internal systems.
        - Similar to malicious hacker.
        - Also called: External, black-box, zero knowledge testing.
    - **Partial knowledge testing:** Tester has limited access and knowledge.
        - **Example:** Customer service representative level access.
        - Also called: Gray-box testing.
- **Closed-box testers:** Produce most accurate simulations of real-world attack.
- Each strategy produces valuable results showing how attacker might infiltrate system and what information they could access.

### Types of Threat Actors

#### Anticipating Attacks
- Important skill for effective security professionals.
- Requires open and flexible mindset about where attacks can come from.
- **Attack surfaces:** All potential vulnerabilities that threat actors could exploit.
- Examples: Networks, servers, devices, staff.
- Security teams defend these surfaces due to expanding digital landscape.
- **Key to defense:** Limit access to attack surfaces.

#### Threat Actors
- **Threat actor:** Any person or group who presents a security risk.
- Broad definition includes people inside and outside organization.
- Includes intentional threats and accidental risk creators.
- **Five categories based on motivations:**
    - **Competitors:** Rival companies benefiting from leaked information.
    - **State actors:** Government intelligence agencies.
    - **Criminal syndicates:** Organized groups making money from criminal activity.
    - **Insider threats:** Individuals with authorized access to organization's resources.
        - Employees accidentally compromising assets or purposefully putting them at risk.
    - **Shadow IT:** Individuals using technologies lacking IT governance.
        - Example: Employee using personal email for work communications.

#### Types of Hackers
- **Hacker:** Person using computers to gain unauthorized access to systems, networks, or data.
- Broad term applied to three types based on intent:
    - **Unauthorized hackers (unethical):** Use programming skills to commit crimes.
        - Also called malicious hackers.
        - Skill levels vary widely.
        - **Script kiddies:** Limited skills, can't write own malicious software.
        - Use pre-written code from more skilled hackers.
    - **Authorized hackers (ethical):** Use programming skills to improve organization's security.
        - Internal security team members testing and evaluating systems.
        - External security vendors and freelance hackers.
        - **Bug bounty programs:** Companies incentivize finding and reporting vulnerabilities.
    - **Semi-authorized hackers:** Violate ethical standards but not considered malicious.
        - **Hacktivists:** Use skills to achieve political goals.
        - Exploit vulnerabilities to spread awareness.
        - Intentions: Expose security risks before malicious hackers find them.

#### Advanced Persistent Threats (APTs)
- **APT:** Threat actor maintaining unauthorized access to system for extended period.
- Mostly associated with nation states and state-sponsored actors.
- **Typical behavior:** Surveil target to gather information.
- Use intelligence to manipulate government, defense, financial, and telecom services.
- **Not limited to state actors:** Private businesses also targeted.
- **Stealthy approach:** Target private organizations first as step toward larger entities.
- Hacking government agencies/utilities is costly and time-consuming.

#### Access Points
- Each threat actor has unique motivation for targeting organization's assets.
- **Attack vector categories:**
    - **Direct access:** Physical access to system.
    - **Removable media:** Portable hardware like USB flash drives.
    - **Social media platforms:** Communication and content sharing.
    - **Email:** Personal and business accounts.
    - **Wireless networks:** On premises.
    - **Cloud services:** Usually provided by third-party organizations.
    - **Supply chains:** Third-party vendors presenting backdoor into systems.
- Any attack vector can provide system access.
- Recognizing threat actor intentions helps determine which access points they might target.
- **Example:** Remote workers more likely to present threat via email than direct access.

### Protect All Entry Points

#### Understanding Attack Surface
- **Attack surface:** All potential vulnerabilities that a threat actor could exploit.
- Analyzing attack surface is usually first thing security teams do.
- Companies start by understanding environment surrounding their operations.
- **Example:** Castle security team allocating resources to defenses.
    - Giant walls, stone towers, wooden gates as security controls.
    - Don't account for all possibilities (e.g., ocean attacks by ship).
    - Proper understanding would equip castle with catapults for long-range threats.

#### Physical Attack Surface
- Made up of people and their devices.
- Can be attacked from both inside and outside organization (unique characteristic).
- **External threats example:** Unattended laptop in coffee shop with sensitive company information visible.
    - Vulnerable to business competitors recording and exploiting information.
- **Internal threats example:** Angry employees sharing organization's private information on purpose.
- Should be filled with obstacles that deter attacks (security hardening).

#### Security Hardening
- **Security hardening:** Process of strengthening system to reduce vulnerabilities and attack surface.
- Minimizing attack surface by limiting points of entry.
- Smaller attack surface = easier to protect.
- **Common hardening methods:**
    - Organization policies.
    - Access controls.
- These are common ways organizations harden their physical attack surface.

#### Digital Attack Surface
- **Digital attack surface:** Everything beyond organization's firewall.
- Includes anything that connects to organization online.
- **Past approach:** Data stored in single location (on-site servers).
    - Access required connecting to workplace network.
- **Current approach:** Information stored in cloud, accessed from anywhere.
    - Person can work from different locations worldwide.
    - All while outside organization's network.
- **Cloud computing impact:** Expanded digital attack surface.
- **Trade-off:** Quicker access benefits everyone but comes with cost.
- Organizations under more pressure to defend against threats from different entry points.

### Approach Cybersecurity with an Attacker Mindset

#### Being Prepared for Anything
- Having a plan for when things go wrong is important.
- Teams conduct simulations as part of vulnerability management strategy.
- **Attacker mindset:** Like conducting an experiment.
- About causing problems in controlled environment and evaluating outcomes.
- Offers different perspective about challenges you're trying to solve.
- Insights valuable when establishing or modifying security plans.

#### Simulating Threats
- **Attack simulations:** Method of applying attacker mindset.
- Performed in two ways: proactively and reactively.
- **Common goal:** Make systems safer.
- **Proactive simulations:** Assume role of attacker exploiting vulnerabilities.
    - Sometimes called red team exercise.
- **Reactive simulations:** Assume role of defender responding to attack.
    - Sometimes called blue team exercise.
- Each simulation is team effort involving analysts.

#### Proactive vs. Reactive Teams
- **Proactive teams:**
    - Spend more time planning attacks than performing them.
    - Deploy range of tactics.
    - **Example:** Persuade staff to disclose login credentials using fictitious emails.
    - Evaluate security awareness at company.
- **Reactive teams:**
    - Dedicate efforts to gathering information about assets they're protecting.
    - Commonly done with vulnerability scanning tools assistance.

#### Scanning for Trouble
- **Vulnerability scanners:** Software comparing existing vulnerabilities against network technologies.
- Frequently used in field by security teams.
- Employ variety of scanning techniques to uncover weaknesses.
- Reactive simulations rely on scan results to weigh risks and determine remediation.

#### Example: Reactive Simulation Process
- **External vulnerability scan** of network following vulnerability assessment steps:
    1. **Identification:** Vulnerable server flagged for outdated OS.
    2. **Vulnerability analysis:** Research on outdated OS and its vulnerabilities.
    3. **Risk assessment:** Score severity of each vulnerability, evaluate impact of not fixing.
    4. **Remediation:** Use gathered information to address issue.
- **Important:** Produce report of findings for service providers or supervisors.
- Clearly communicating results to others is important skill for security professionals.

### Pathways through Defenses

#### Understanding Attack Vectors
- Organizations need more than understanding of growing digital landscape.
- Must understand types of attacks that can be used against them.
- **Cloud computing impact:** Expanded digital attack surface, increased number of attack vectors.
- **Attack vectors:** Pathways attackers use to penetrate security defenses.
- Like doors and windows of a home - exploitable features of attack surface.
- **Examples:** Social media, removable media (USB drive).
- Most people assume only cyber criminals exploit attack vectors.
- **Reality:** Other groups use them too, including employees.

#### Who Uses Attack Vectors?
- **Malicious hackers:** Steal information.
- **Employees:** Occasionally exploit attack vectors unintentionally.
    - **Example:** Posting sensitive company news on social media that shouldn't be shared.
    - Sometimes happens on purpose.
- **Disgruntled employees:** Intentionally share confidential information to harm company.
- All attack vectors treated as critical risks to asset security.

#### Attacker Mindset Process
- Attackers put forth effort planning attacks before carrying them out.
- Security professionals must put even greater effort into stopping them.
- **Process starts with question:** "How would we exploit this vector?"
- **Four-step process:**
    1. **Identify a target:** Specific information, system, person, group, or organization.
    2. **Determine access:** What information available for attacker to reach target?
    3. **Evaluate attack vectors:** Which can be exploited to gain entry?
    4. **Find tools and methods:** What will attackers use to carry this out?
- Provides valuable insight into best security controls and vulnerabilities to monitor.

#### Defending Attack Vectors
- Every organization has long list of attack vectors to defend.
- **Common rules for protection:**
    - **Educate users about security vulnerabilities:**
        - Usually tied to specific events.
        - **Example:** Advising about new phishing exploit targeting organization users.
    - **Apply principle of least privilege:**
        - Access rights limited to what's required to perform task.
        - Closes multiple security holes in attack surface.
    - **Use right security controls and tools:**
        - Even knowledgeable employees make security mistakes.
        - **Example:** Accidentally clicking malicious link in email.
        - Right tools (like antivirus software) help defend vectors efficiently.
        - Reduces risk of human error.
    - **Build diverse security team:**
        - One of best ways to reduce attack vector risk.
        - Prevents future attacks.

### Fortify against Brute Force Cyber Attacks

#### The Problem with Login Credentials
- Usernames and passwords are most common and important security controls.
- Like door locks restricting access to networks, services, and data.
- **Major issue:** Vulnerable to being stolen and guessed by attackers.
- Brute force attacks are trial-and-error process of discovering private information.

#### A Matter of Trial and Error
- **Simple brute force attacks:** Attackers guess user's login credentials.
    - Enter any combination of username and password until one works.
- **Dictionary attacks:** Use list of commonly used credentials.
    - Similar to matching definition to word in dictionary.
- **Reverse brute force attacks:** Start with single credential, try in various systems.
- **Credential stuffing:** Use stolen login credentials from previous data breaches.
    - **Pass the hash:** Reuse stolen, unsalted hashed credentials to trick authentication system.
- **Note:** Encrypted information can sometimes be brute forced using exhaustive key search.
- Methods involve lot of guesswork - tedious and time-consuming when done manually.
- Threat actors often use tools to conduct attacks.

#### Tools of the Trade
- Manual brute forcing could take years to try every possible combination.
- Attackers use software to do guesswork for them.
- **Common brute forcing tools:**
    - Aircrack-ng
    - Hashcat
    - John the Ripper
    - Ophcrack
    - THC Hydra
- Security professionals sometimes use these tools to test their own systems.
- **Example:** Use Aircrack-ng to test Wi-Fi network for vulnerabilities.

#### Prevention Measures
- Organizations defend with combination of technical and managerial controls.
- **Four main prevention methods:**
    - Hashing and salting
    - Multi-factor authentication (MFA)
    - CAPTCHA
    - Password policies

##### Hashing and Salting
- **Hashing:** Converts information into unique value to determine integrity.
- **Salting:** Additional safeguard strengthening hash functions.
- Adds random characters to data (like passwords).
- Increases length and complexity of hash values.
- Makes them harder to brute force and less susceptible to dictionary attacks.

##### Multi-Factor Authentication (MFA)
- **MFA:** Security measure requiring user to verify identity in two or more ways.
- Layered approach to protecting information.
- Limits chances of brute force attacks.
- Unauthorized users unlikely to meet each authentication requirement.

##### CAPTCHA
- **CAPTCHA:** Completely Automated Public Turing test to tell Computers and Humans Apart.
- Challenge-response authentication system.
- Asks users to complete simple test proving they are human.
- **Two types:**
    - Scrambled/distorted letters/numbers to enter in text box.
    - Match images to randomly generated word.
- Common when accessing sensitive information (online bank accounts).

##### Password Policy
- **Managerial controls** to standardize good password practices.
- **Examples:**
    - Passwords at least 8 characters with letter, number, and symbol.
    - Password lockout policies limiting login attempts.
    - Require new, unique passwords after certain time.
- **Purpose:** Create more possible password combinations.
- Lengthens time for attacker to find working password.
- **NIST Special Publication 800-63B:** Provides detailed guidance for password policies.

## Module 4

### The Criminal Art of Persuasion

#### Beyond Programming Skills
- Malicious hackers rely on sophisticated computer programming skills.
- Other criminals use more traditional approach: **manipulation**.
- **Social engineering:** Manipulation technique that exploits human error.
- Gains private information, access, or valuables.
- Tricks people into breaking normal security procedures on attacker's behalf.
- Can lead to data exposures, malware infections, or unauthorized access.

#### Where Social Engineering Happens
- **Can happen anywhere:** Online, in-person, through other interactions.
- **Timeframes vary:**
    - **Seconds:** Impersonating tech support asking for password.
    - **Months or longer:** Monitoring employee social media for opportunities.
- **Example:** Employee posts about temporary position → attacker targets less knowledgeable worker.
- Knowing what to look for helps quickly identify and stop attacks.

#### Stages of Social Engineering Attacks

##### 1. Prepare
- Attackers gather information about their target.
- Using intel, determine best way to exploit them.

##### 2. Establish Trust (Pretexting)
- Use gathered information to open line of communication.
- Disguise themselves to trick target into false sense of trust.

##### 3. Persuasion Tactics
- Manipulate target into volunteering information.
- Use specific vocabulary to sound like organization member.
- Earlier preparation really matters at this stage.

##### 4. Disconnect
- After collecting desired information, break communication.
- Disappear to cover tracks.

#### Prevention Strategies

##### Managerial Controls
- **First line of defense:** Policies, standards, and procedures.
- **Example:** Businesses follow patch management standard in NIST Special Publication 800-40.
- Standards used to create procedures for updating operating systems, applications, and firmware.

##### Staying Informed
- **Major priority:** Stay informed of trends for security professionals.
- Keep up with latest social engineering tactics.

##### Education and Sharing
- **Best defense:** Share knowledge with others.
- Attackers play on natural curiosity and desire to help.
- Hope targets won't think too hard about what's going on.
- Teaching attack signs to others goes long way toward preventing threats.

### An Introduction to Malware

#### Virus
- **Definition:** Malicious code written to interfere with computer operations and cause damage.
- Must be installed by target user before it can spread and cause damage.
- **Spread method:** Phishing campaigns with malicious links hidden in attachments.
- Requires user interaction to activate.

#### Worm
- **Definition:** Malware that can duplicate and spread itself across systems independently.
- Must be installed by target user initially.
- **Spread method:** Malicious email, targeting devices with shared network access.
- **Famous example:** Blaster worm (Lovesan, Lovsan, MSBlast).
    - Spread on Windows XP and Windows 2000 systems.
    - Forced devices into continuous shutdown/restart loop.
    - Infected hundreds of thousands of users worldwide.
    - Many variants still exist for modern computers.
- **Note:** Popular in mid-2000s, less frequent in recent years.

#### Trojan
- **Definition:** Malware disguised as legitimate file or program (Trojan horse).
- **Spread method:** Hidden in file and application downloads.
- Attackers trick users into believing they're downloading harmless files.
- **Capabilities:** Spy on users, grant access to other devices, and more.

#### Adware
- **Legitimate adware:** Advertising-supported software displaying digital advertisements.
- Developers use to lower production costs or make products free (freeware/shareware).
- Monetize through ad revenue rather than user expense.
- **Malicious adware:** Falls into category of potentially unwanted application (PUA).
- **PUA:** Unwanted software bundled with legitimate programs.
    - May display ads, cause device slowdown, or install other software.
- Attackers hide in freeware with insecure design to monetize ads for themselves.
- Works even when user declines to receive ads.

#### Spyware
- **Definition:** Malware used to gather and sell information without consent.
- Considered a PUA.
- **Spread method:** Hidden in bundleware (additional software packaged with applications).
- **Challenge:** Serious problem in open-source software development ecosystem.
- Developers overlook how software could be misused or abused.

#### Scareware
- **Definition:** PUA that employs tactics to frighten users into infecting their own device.
- **Method:** Displays fake warnings appearing to come from legitimate companies.
- **Spread methods:** Email and pop-ups with phony warnings.
- Claims user's files or data are at risk.

#### Fileless Malware
- **Definition:** Malware that doesn't need user installation.
- Uses legitimate programs already installed to infect computer.
- **Residence:** Lives in memory, never touches hard drive.
- Unlike other malware stored in files on disk.
- **Method:** Gets into operating system or hides within trusted applications.
- **Detection:** Requires memory analysis and operating system experience.

#### Rootkits
- **Definition:** Malware providing remote, administrative access to computer.
- **Purpose:** Open backdoor to systems for installing other malware or conducting attacks.
- **Spread method:** Combination of dropper and loader components.
- **Dropper:** Malware packed with malicious code delivered to target system.
    - Disguised as legitimate file (document, image, executable).
    - Executes malicious code when opened.
- **Loader:** Malware that downloads malicious code from external source.
    - Used in multi-staged malware attacks.
    - Can set up other malware like botnets.

#### Botnet
- **Definition:** "Robot network" - collection of computers infected by malware under single threat actor control.
- **Bot-herder:** Single threat actor controlling the botnet.
- **Initial infection:** Viruses, worms, and trojans used to turn devices into bots.
- **Growth method:** File sharing, email, or social media application protocols.
- **Operation:** Infected computer reports back to bot-herder who can execute commands.

#### Ransomware
- **Definition:** Malicious attack where threat actors encrypt organization's data and demand payment for restoration.
- **Trend:** According to CISA, ransomware crimes are rising and becoming more sophisticated.
- **Impact:** Can cause significant damage to organization and customers.
- **Famous example:** WannaCry attack.
    - Encrypts victim's computer until cryptocurrency ransom is paid.

### The Rise of Cryptojacking

#### What is Cryptojacking?
- **Definition:** Form of malware that installs software to illegally mine cryptocurrencies.
- **Cryptocurrency:** Digital money with real-world value.
- Referred to as coins or tokens.
- **Crypto mining:** Process used to obtain new coins.

#### How Crypto Mining Works
- **Analogy:** Similar to mining for gold.
    - Gold mining: Uses machinery (trucks, bulldozers) to dig through Earth.
    - Crypto mining: Uses computers to dig through billions of lines of encrypted code.
- When enough code is processed, a crypto coin can be found.
- More computers mining = more cryptocurrency discovered.

#### The Rise of Cryptojacking
- **Started in 2017:** Criminals began using malware to gain unauthorized control of personal computers.
- **Evolution:** Techniques have become more sophisticated over time.
- **Current method:** Criminals target vulnerable servers to spread mining software.
- **Infection spread:** Devices communicating with infected server become infected themselves.
- **Operation:** Malicious code runs in background, mining coins unknown to anyone.

#### Detection Challenges
- **Cryptojacking software is hard to detect.**
- **Intrusion Detection System (IDS):** Application that monitors system activity and alerts to possible intrusions.
    - Detects abnormal activity like malware mining for coins.
    - Alerts security personnel.
- **Major drawback:** New forms of malware can remain undetected.

#### Signs of Cryptojacking Infection
- **Most telling sign:** Device slowdown.
- **Other indicators:**
    - Increased CPU usage
    - Sudden system crashes
    - Fast draining batteries
    - Unusually high electricity costs (due to resource-intensive mining process)

#### Prevention Measures
- **Browser extensions** designed to block malware
- **Ad blockers**
- **Disabling JavaScript**
- **Staying alert** on latest trends
- **Education:** Security analysts can educate others in organizations on malware attacks

### Cross-Site Scripting (XSS)

#### Web-Based Exploits
- **Definition:** Malicious code or behavior used to take advantage of coding flaws in web applications.
- **Target:** Cybercriminals target to obtain sensitive personal information.
- **Occurrence:** Attacks happen because web applications interact with multiple users across multiple networks.
- **Common method:** Malicious hackers exploit high level of interaction using injection attacks.

#### Injection Attacks
- **Definition:** Malicious code inserted into a vulnerable application.
- **Appearance:** Infected application often appears to work normally.
- **Operation:** Injected code runs in background, unknown to user.
- **Vulnerability reason:** Applications programmed to receive data inputs.
    - User typing, clicking, or program sharing data.
- **Proper coding:** Applications should interpret and handle user inputs correctly.
- **Example:** Phone number input should validate for numbers only and maximum 10 digits.
- **Challenge:** Web apps have many interactive objects (images, buttons) making input sanitization difficult.

#### Cross-Site Scripting (XSS)
- **Definition:** Injection attack that inserts code into vulnerable website or web application.
- **Delivery method:** Exploiting languages used by most websites (HTML and JavaScript).
- **Access gained:** Everything that loads on infected web page.
    - Session cookies, geolocation, webcams, microphones.
- **Three main types:** Reflected, stored, and DOM-based.

#### Types of XSS Attacks

##### Reflected XSS
- **Definition:** Malicious script sent to server and activated during server's response.
- **Common example:** Search bar of a website.
- **Process:**
    1. Criminals send target web link appearing to go to trusted site.
    2. Click sends HTTP request to vulnerable site server.
    3. Attacker script returned/reflected back to user's browser.
    4. Browser loads malicious script (trusts server's response).
    5. Information like session cookies sent back to attacker.

##### Stored XSS
- **Definition:** Malicious script injected directly on server (not hidden in link).
- **Target:** Elements of site served to user (images, buttons).
- **Activation:** Infected elements activate malicious code when user visits site.
- **Risk:** User has no way of knowing site is infected beforehand.
- **Damage potential:** Can be very damaging due to lack of warning.

##### DOM-Based XSS
- **DOM:** Document Object Model (source code of website).
- **Definition:** Malicious script exists in web page browser loads.
- **Difference:** Don't need to be sent to server to activate (unlike reflected XSS).
- **Visibility:** Malicious script can be seen in URL.
- **Example:** Website with color theme selection.
    - User selection appears as part of URL.
    - Criminals change parameter expecting input.
    - Hide malicious JavaScript in HTML tags.
    - Browser processes HTML and executes JavaScript.

### Exploitable Gaps in Databases

#### SQL in Web Applications
- **Usage:** SQL used by most web applications (e.g., shopping websites).
- **Example:** Online clothing store database contains full inventory of items.
- **User interface:** Websites don't make users enter SQL queries manually.
- **Frontend:** Use menus, images, and buttons to show information meaningfully.
- **Backend process:** When user clicks "add to cart," it triggers SQL query in background.
- **Vulnerability:** Sometimes backend queries are vulnerable to injection attacks.

#### SQL Injection Attacks
- **Definition:** Attack that executes unexpected queries on a database.
- **Cause:** Lack of sanitized input (similar to cross-site scripting).
- **Location:** Takes place in website areas designed to accept user input.
- **Common target:** Login forms to access a site.
- **Process:** Web forms copy user input into SQL statement exactly as written.
- **Problem:** Vulnerable websites insert user input exactly as entered before running code.

#### The Design Flaw
- **Issue:** Serious design flaw in vulnerable websites.
- **Reason:** Web developers expect people to use inputs correctly.
- **Expectation gap:** Don't anticipate attackers exploiting them.
- **Attack method:** Attacker inserts additional SQL code.
- **Result:** Server runs harmful query it wasn't expecting.
- **Capabilities gained:**
    - Obtain sensitive information
    - Modify tables
    - Gain administrative rights to database

#### Prevention: Input Sanitization
- **Best defense:** Code that sanitizes input.
- **Method:** Write code to search for specific SQL characters.
- **Benefit:** Gives server clearer idea of what inputs to expect.

#### Prepared Statements
- **Definition:** Coding technique that executes SQL statements before passing to database.
- **Best practice:** Use when user input is unknown.
- **Process:** Execute code before passing to server.
- **Validation:** Code can be validated before performing query.
- **Implementation:** Requires just few extra lines of code.
- **Key:** Well-written code is essential for preventing SQL injection.

### Prevent Injection Attacks

#### SQL Injection Categories
- **Three main categories:**
    - In-band
    - Out-of-band
    - Inferential
- Each type describes how SQL injection is initiated and how results are returned.

#### In-Band SQL Injection
- **Definition:** Most common type (also called classic SQL injection).
- **Method:** Uses same communication channel to launch attack and gather results.
- **Example:** Search box on retailer's website.
    - If vulnerable, attacker enters malicious query executed in database.
    - Returns sensitive information like user passwords.
    - Data displayed back in search box where attack was initiated.

#### Out-of-Band SQL Injection
- **Definition:** Uses different communication channel to launch attack and gather results.
- **Example:** Attacker uses malicious query to create connection between vulnerable website and database they control.
- **Benefit:** Separate channel bypasses security controls on website's server.
- **Result:** Allows stealing sensitive data.
- **Note:** Very uncommon - only works when certain features enabled on target server.

#### Inferential SQL Injection
- **Definition:** Attacker unable to directly see results of their attack.
- **Method:** Interpret results by analyzing system behavior.
- **Example:** SQL injection on login form causes system to respond with error message.
- **Process:**
    - Sensitive data not returned directly.
    - Attacker figures out database structure based on error.
    - Uses information to craft attacks for accessing sensitive data or taking control.

#### Injection Prevention
- **Problem:** SQL queries assume users will only input relevant information.
- **Example:** Login form expects email format like jdoe@domain.com.
- **Key prevention:** Escape user inputs - prevent inserting unexpected code.

#### Prevention Techniques

##### Prepared Statements
- **Definition:** Coding technique that executes SQL statements before passing to database.

##### Input Sanitization
- **Definition:** Programming that removes user input which could be interpreted as code.

##### Input Validation
- **Definition:** Programming that ensures user input meets system's expectations.

#### Best Practices
- **Combination approach:** Using combination of techniques helps prevent SQL injection attacks.
- **Collaboration:** Work closely with application developers to address vulnerabilities.
- **Resource:** OWASP's SQL injection detection techniques useful for investigating vulnerabilities.

### A Proactive Approach to Security

#### Threat Modeling Overview
- **Definition:** Process of identifying assets, their vulnerabilities, and how each is exposed to threats.
- **Application:** Applied to everything we protect.
    - Entire systems, applications, or business processes.
- **Nature:** Lengthy and detailed activity.
- **Performers:** Collection of individuals with years of experience in field.
- **Skill level:** Considered advanced skill in security.
- **Frameworks:** Several used in field.
    - Some better suited for network security.
    - Others better for information security or application development.

#### Six Steps of Threat Modeling

##### Step 1: Define Scope
- **Objective:** Determine what team is building.
- **Process:** Create inventory of assets and classify them.

##### Step 2: Identify Threats
- **Objective:** Define all potential threat actors.
- **Threat actor:** Any person or group who presents security risk.
- **Categories:**
    - **Internal:** Employee who intentionally exposes asset to harm.
    - **External:** Malicious hacker or competing business.
- **Output:** Attack tree diagram mapping threats to assets.
- **Detail:** Team tries to be as detailed as possible before moving on.

##### Step 3: Characterize Environment
- **Objective:** Apply attacker mindset to business.
- **Considerations:**
    - How customers and employees interact with environment.
    - External partners and third-party vendors.

##### Step 4: Analyze Threats
- **Objective:** Examine existing protections and identify gaps.
- **Process:** Team works together to rank threats according to assigned risk score.

##### Step 5: Mitigate Risk
- **Objective:** Create plan for defending against threats.
- **Choices:**
    - Avoid risk
    - Transfer it
    - Reduce it
    - Accept it

##### Step 6: Evaluate Findings
- **Objective:** Document everything done during exercise.
- **Actions:**
    - Apply fixes
    - Note successes
    - Record lessons learned for future threat models.

### PASTA: The Process for Attack Simulation and Threat Analysis

#### PASTA Framework Overview
- **Definition:** Popular threat modeling framework used across many industries.
- **PASTA:** Process for Attack Simulation and Threat Analysis.
- **Structure:** Seven stages to help organizations prepare their applications.

#### Seven Stages of PASTA

##### Stage 1: Define Business and Security Objectives
- **Objective:** Decide what goals are before starting threat model.
- **Example:** Fitness company app - protecting customer data.
- **Process:** Team asks many questions to understand:
    - How personally identifiable information is handled.
- **Purpose:** Key to evaluating impact of threats found along the way.

##### Stage 2: Define Technical Scope
- **Focus:** Identify application components that must be evaluated.
- **Concept:** What we discussed earlier as the attack surface.
- **For mobile app:** Includes technology involved while data is at rest and in use.
- **Components:** Network protocols, security controls, and other data interactions.

##### Stage 3: Decompose Application
- **Objective:** Identify existing controls that protect user data from threats.
- **Process:** Work with application developers to produce data flow diagram.
- **Diagram shows:**
    - How data gets from user's device to company's database.
    - Controls in place to protect data along the way.

##### Stage 4: Perform Threat Analysis
- **Focus:** Team gets into attacker mindset.
- **Process:** Research to collect most up-to-date information on attack types.
- **Consideration:** Mobile apps have many attack vectors that change regularly.
- **Action:** Reference resources to stay up-to-date.

##### Stage 5: Perform Vulnerability Analysis
- **Objective:** More deeply investigate potential vulnerabilities.
- **Focus:** Consider root of the problem.

##### Stage 6: Conduct Attack Modeling
- **Objective:** Test vulnerabilities analyzed in stage five by simulating attacks.
- **Method:** Create attack tree (looks like flow chart).
- **Example for mobile app:**
    - Customer information (usernames, passwords) is target.
    - Data stored in database vulnerable to SQL injection.
    - Add SQL injection as attack vector to attack tree.
    - Threat actor exploits vulnerabilities from unsanitized inputs.
- **Purpose:** Security team uses attack trees to identify attack vectors needing testing.
- **Note:** Applications typically have many branches with numerous attack vectors.

##### Stage 7: Analyze Risk and Impact
- **Objective:** Assemble all information collected in stages one through six.
- **Outcome:** Team in position to make informed risk management recommendations.
- **Alignment:** Recommendations align with business stakeholder goals.

### Threat Modeling Frameworks

#### Why Application Security Matters
- **Applications:** Essential part of many organizations' success.
- **Web-based applications:** Allow customers worldwide to connect with businesses, partners, and other customers.
- **Mobile applications:** Changed how people access digital world.
- **Smartphones:** Often main way data is exchanged between users and business.
- **Data volume:** Makes securing applications key to reducing risk for everyone connected.
- **Example:** Java-based logging libraries with Log4Shell vulnerability (CVE-2021-44228).
    - If not patched, allows remote code execution.
    - Attacker can gain full access to system from anywhere in world.
    - Can impact millions of devices if exploited.

#### Defending the Application Layer
- **Requirement:** Proper testing to uncover weaknesses that can lead to risk.
- **Primary method:** Threat modeling ensures application meets security requirements.
- **Team:** DevSecOps (development, security, and operations) usually performs analyses.
- **Process:** Performed in cycle with six steps:
    1. Define scope
    2. Identify threats
    3. Characterize environment
    4. Analyze threats
    5. Mitigate risks
    6. Evaluate findings
- **Timing:** Should be performed before, during, and after application development.
- **Challenge:** Thorough software analysis takes time and resources.
- **Evaluation scope:** Everything from architecture to business purposes.
- **Note:** Should be incorporated at every stage of software development lifecycle (SDLC).

#### Common Frameworks
- **Multiple methods available:**
    - STRIDE
    - PASTA
    - Trike
    - VAST
- **Selection:** "Right" model depends on situation and types of risks application might face.

##### STRIDE
- **Developer:** Microsoft.
- **Purpose:** Identify vulnerabilities in six specific attack vectors.
- **Acronym represents:**
    - Spoofing
    - Tampering
    - Repudiation
    - Information disclosure
    - Denial of service
    - Elevation of privilege

##### PASTA
- **Full name:** Process of Attack Simulation and Threat Analysis.
- **Developer:** Two OWASP leaders, supported by VerSprite cybersecurity firm.
- **Focus:** Discover evidence of viable threats and represent as model.
- **Design:** Evidence-based, applicable to application or supporting environment.
- **Process:** Seven-stage process incorporating relevant security artifacts.

##### Trike
- **Type:** Open source methodology and tool.
- **Approach:** Security-centric approach to threat modeling.
- **Focus:** Security permissions, application use cases, privilege models, and other secure environment elements.

##### VAST
- **Full name:** Visual, Agile, and Simple Threat Modeling framework.
- **Platform:** Part of automated threat-modeling platform called ThreatModeler®.
- **Benefit:** Many security teams use to automate and streamline threat modeling assessments.

#### Participating in Threat Modeling
- **Performers:** Often experienced security professionals, but rarely done alone.
- **Complexity:** Programs are complex systems handling lots of data and processing various commands.
- **Key:** Asking the right questions:
    - What are we working on?
    - What kinds of things can go wrong?
    - What are we doing about it?
    - Have we addressed everything?
    - Did we do a good job?
- **Learning:** Takes time and practice to work with data flow diagrams and attack trees.
- **Accessibility:** Anyone can learn to be effective threat modeler.
- **Starting point:** Regardless of experience level, always starts with asking right questions.

# Certificate Completed

![Certificate proof in case I have to pay for it](Screenshot%202025-07-26%20at%209.15.04 PM.png)
