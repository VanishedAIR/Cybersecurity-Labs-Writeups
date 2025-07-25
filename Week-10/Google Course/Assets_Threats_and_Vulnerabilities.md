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

