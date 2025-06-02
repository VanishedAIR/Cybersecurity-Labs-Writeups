## NMAP - ([Youtube](https://www.youtube.com/watch?v=4t4kBkMsDbQ))

- I wanted to get some practical examples of using nmap, and learn it more concretely through usage so I went to youtube and found [this](https://www.youtube.com/watch?v=4t4kBkMsDbQ) video to practice some basic switches.

- I could search individual host through `ping [ip-address]` and it would tell me if its up and running

- If I wanted to ping an entire network, where there could be as many as 200+ hosts and pinging them individually would be time consuming. This is where we use `nmap -sP [ip-address]` where the -sP switch is used to do a ping sweep

- If I wanted to check the open ports on a server running a website, and recalling that port 80 and 443 are http and https ports, I could use the `-sT` switch which is a tcp connect scan, or full open scan, where it uses the 3 way handshake to confirm whether a port is open. The 3 way handshake consists of the User sending a SYN packet to a port 80 and 443 in this case, and the server responds with SYN/ACK if its open, and the User responds with a ACK confirming that the 3 way handshake is complete. `sudo nmap -sT -p 80,443 [ip-address]`

- Firewalls or Intrusion Detection Systems (IDS) could recognize this 3 way handshake and cause a problem with our scan, so we can use a stealth scan using the `-sS` switch where instead of the full 3 way handshake, it goes something like, User-> SYN, Server-> SYN/ACK, User->RST where the user just doesn't respond essentially not completing the 3 way handshake. `sudo nmap -sS -p 80,443 [ip-address]`

- I could use the `-O` switch to see which OS the target is using. `sudo nmap -o [host]`

- Also could use `-A` which is a combination of stuff including things like os detection, version detection, script scanning, traceroute. `sudo nmap -A [host]`

- We can also use a decoy ip address which will send duplicate packets making it harder to trace who sent the packets through the use of `-D` switch. `sudo nmap -D [decoy-ip-address] [target-ip-address]