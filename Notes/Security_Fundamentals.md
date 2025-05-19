# Summary of all Security Fundamentals
## CIA Triad Summary

### C - Confidentiality

- Only the authenticated user should be allowed to access the service, any malicious user should be blocked

### I - Integrity

- Information should remain unchanged. An example being a bank transfer of 1,000 dollars should not be changed to 10,000 dollars by a malicious user

### A - Availability

- Service should be available at all times, in an event of an attack, you need to make sure your service is secure to where you can still provide services even when under attack


## Least-Privilege-Principle Summary

- Limiting the access rights of the users to the bare minimum to get the job done is highly effective in enhancing security
- Harder to compromise what the user doesn't have access to
- Chances of accidents, errors and unauthorized activities are greatly reduced in this approach
- In an case of a compromised account then the damage is limited to the minimum permissions assigned to that account preventing widespread access
- Easier to track and audit user actions

## Defense in Depth

- No one thing can completely secure a system
- Idea being that if one part fails, then another part should be able to resist the attack by implementing security in layers
- Consider technical, physical, and administrative controls

## AAA

-  Authentication: 
    - Prove you are who you say you are 
    - Passwords and other authentication factors
- Authorization: 
    - Based on your identification and authentication, what access do you have?
- Accounting:
    - Resources used: Login time, data send and received, logout time