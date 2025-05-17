## Offensive Security Intro (TryHackMe)

### Task Summary:

Brute forcing through directories to check for public admin pages that should have been made private.

### Commands Used:

- `gobuster -u http://fakebank.thm -w wordlist.txt dir`

### Key Learnings:

- Importance of properly securing admin pages from public enumeration.
- How attackers utilize basic enumeration to discover exposed web resources.

### CIA Triad Connection:

- Confidentiality compromised (admin page exposed).
- Integrity compromised (fake transaction completed without proper checks).

### Reflection:

Practiced using gobuster; learned the real-world risks of unprotected pages.
