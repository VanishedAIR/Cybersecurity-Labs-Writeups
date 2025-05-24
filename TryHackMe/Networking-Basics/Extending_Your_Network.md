## Extending your network ([TryHackMe - YouTube](https://www.youtube.com/watch?v=uMkjvpux70I&list=PL0iJrrpaWpyWTmLQxeRy64LKGzLbRLDfD&index=5))

### Task Summary:

-   Adding rules to firewall to stop the server from crashing due to an attack. 198.51.100.34 is the Source IP, or where the attacker is sending the packets from trying to overwhelm the server, and 203.0.110.1 is the Destination IP, or where the system is, and what port its going to, in this case 80, and what action we want to take, which is to drop before it crashes our server.
-   The simulator will break down every step a packet needs to take to get from point a to b. In which the network log looks like the following:
`Network Log`

`HANDSHAKE: Starting TCP/IP Handshake between computer1 and computer3`

`HANDSHAKE: Sending SYN Packet from computer1 to computer3`

`ROUTING: computer1 says computer3 is not on my local network sending to gateway: router`

`ARP REQUEST: Who has router tell computer1`

`ARP RESPONSE: Hey computer1, I am router`

`ARP REQUEST: Who has computer3 tell router`

`ARP RESPONSE: Hey router, I am computer3`

`HANDSHAKE: computer3 received SYN Packet from computer1, sending SYN/ACK Packet to computer1`

`HANDSHAKE: computer1 received SYN/ACK Packet from computer3, sending ACK packet to computer3`

`HANDSHAKE: computer3 received ACK packet from computer1, Handshake Complete`

`TCP: Sending TCP packet from computer1 to computer3`

`TCP: computer3 received TCP Packet from computer1, sending ACK Packet to computer1`

### Summary:

#### Introduction to Port Forwarding

-   Port forwarding is an essential component in connecting applications and services to the Internet.
-   Without port forwarding, applications and services such as web servers are only available to devices within the same direct network.
-   Take the network below as an example. Within this network, the server with an IP address of "192.168.1.10" runs a webserver on port 80. Only the two other computers on this network will be able to access it (this is known as an intranet).
    ![intranet](https://camo.githubusercontent.com/e0df7dbbae8a6cb55ba84d1cc2e20a94a8f8e0cb4af0e88cf5d8a95fc7ad7b99/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f657874656e64696e672d796f75722d6e6574776f726b2f706f7274666f7277617264696e672d696e742e706e67)
-   If the administrator wanted the website to be accessible to the public (using the Internet), they would have to implement port forwarding, like in the diagram below:
    ![forwarding](https://camo.githubusercontent.com/4fa07b718c8272eee84f8c28a8aba041a2bbaf3b962d8205ee9b4b263aabaa5b/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f657874656e64696e672d796f75722d6e6574776f726b2f706f7274666f7277617264696e672e706e67)
-   With this design, Network #2 will now be able to access the webserver running on Network #1 using the public IP address of Network #1 (82.62.51.70).
-   It is easy to confuse port forwarding with the behaviors of a firewall
-   Port forwarding opens specific ports
-   In comparison, firewalls determine if traffic can travel across these ports (even if these ports are open by port forwarding)
-   Port forwarding is configured at the router of a network

#### Firewalls 101

-   A firewall is a device within a network responsible for determining what traffic is allowed to enter and exit.
-   An administrator can configure a firewall to permit or deny traffic from entering or exiting a network based on numerous factors such as:
    -   Where the traffic is coming from? (has the firewall been told to accept/deny traffic from a specific network?)
    -   Where is the traffic going to? (has the firewall been told to accept/deny traffic destined for a specific network?)
    -   What port is the traffic for? (has the firewall been told to accept/deny traffic destined for port 80 only?)
    -   What protocol is the traffic using? (has the firewall been told to accept/deny traffic that is UDP, TCP or both?)
-   Firewalls perform packet inspection to determine the answers to these questions.
-   Firewalls come in all shapes and sizes. From dedicated pieces of hardware (often found in large networks like businesses) that can handle a magnitude of data to residential routers or software, firewalls can be categorized into 2 to 5 categories
-   2 primary categories of firewalls:
    -   ![firewalls](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Extending%20your%20network/Pastedimage20210703115709.png)

#### VPN Basics

-   A Virtual Private Network (or VPN for short) is a technology that allows devices on separate networks to communicate securely by creating a dedicated path between each other over the Internet (known as a tunnel). Devices connected within this tunnel form their own private network.
-   Only devices within the same network (such as within a business) can directly communicate. However, a VPN allows two offices to be connected. The diagram below, shows where there are three networks:
    ![vpn](https://camo.githubusercontent.com/770fa802afe191b9b0d1db854ad0e85cc7b500d7e41776d0e7e560ff5d3e1d64/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f657874656e64696e672d796f75722d6e6574776f726b2f76706e312e706e67)

        - Network #1 (Office #1)
        - Network #2 (Office #2)
        - Network #3 (Two devices connected via a VPN)

-   The devices connected on Network #3 are still a part of Network #1 and Network #2 but also form together to create a private network (Network #3) that only devices that are connected via this VPN can communicate over.

-   Some of the other benefits offered by a VPN in the table below:
    ![vpn benefits](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Extending%20your%20network/Pastedimage20210703115931.png)

-   Some existing VPN technologies below
    ![vpn tech](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Extending%20your%20network/Pastedimage20210703120002.png)

#### LAN Networking Devices

-   It's a router's job to connect networks and pass data between them.
-   It does this by using routing.

-   Routing is the label given to the process of data traveling across networks.
-   Routing involves creating a path between networks so that this data can be successfully delivered.
-   Routers operate at Layer 3 of the OSI model.
-   They often feature an interactive interface (such as a website or a console) that allows an administrator to configure various rules such as port forwarding or firewall-ing.
-   Routing is useful when devices are connected by many paths, such as in the example diagram below, where the most optimal path is taken:

![routing](https://camo.githubusercontent.com/17576d8a0006c3e35562b69ed0ab47b073e2e7a15662381a152b077bf5b0e0af/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f696e74726f2d746f2d6e6574776f726b696e672f776861742d69732d7468652d696e7465726e65742f726f7574696e67322e706e67)

-   Routers are dedicated devices and do not perform the same functions as switches.

-   A switch is a dedicated networking device responsible for providing a means of connecting to multiple devices.
-   Switches can facilitate many devices (from 3 to 63) using Ethernet cables.

-   Switches can operate at both layer 2 and layer 3 of the OSI model.
-   However, these are exclusive in the sense that Layer 2 switches cannot operate at layer 3.

-   Take, for example, a layer 2 switch in the diagram below. These switches will forward frames (remember these are no longer packets as the IP protocol has been stripped) onto the connected devices using their MAC address.

![switch](https://camo.githubusercontent.com/2257180423a1c7731097a67d3a2c6e14d5e5c09e1cea54052bc5517d7e558dc9/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f657874656e64696e672d796f75722d6e6574776f726b2f6c61796572327377697463682e706e67)

-   These switches are solely responsible for sending frames to the correct device.

-   Layer 3 switches are more sophisticated than layer 2, as they can perform some of the responsibilities of a router.
-   Namely, these switches will send frames to devices (as layer 2 does) and route packets to other devices using the IP protocol.

-   Let's take a look at the diagram below of a layer 3 switch in action. We can see that there are two IP addresses:

    -   192.168.1.1
    -   192.168.2.1

-   A technology called VLAN (Virtual Local Area Network) allows specific devices within a network to be virtually split up.
-   This split means they can all benefit from things such as an Internet connection but are treated separately.
-   This network separation provides security because it means that rules in place determine how specific devices communicate with each other.
-   This segregation is illustrated in the diagram below:
    ![layer 3 switches](https://camo.githubusercontent.com/99e6df6a03f8731720c8c27f0eca79a14c77898c8b179a5cee4b6a73ac0a6c2c/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f657874656e64696e672d796f75722d6e6574776f726b2f766c616e732e706e67)
-   In the context of the diagram above, the "Sales Department" and "Accounting Department" will be able to access the Internet, but not able to communicate with each other (although they are connected to the same switch).
