## Packets and Frames ([TryHackMe - YouTube](https://www.youtube.com/watch?v=vzcLrE0SfiQ&list=PL0iJrrpaWpyWTmLQxeRy64LKGzLbRLDfD&index=4))

### Task Summary:

- Checking if we understand the flow from connection to closing, SYN (User 1) -> SYN/ACK (User 2) -> ACK (User 1) -> DATA (User 1) -> ACK (User 2) -> FIN/ACK (User 1) -> FIN/ACK (User 2) -> ACK (User 1)
- Connect to the IP address "8.8.8.8" on port "1234" done by using netcat (nc) reading and writing to network connections using TCP/UDP. `nc 8.8.8.8 1234`

### Summary:

#### What are Packets and Frames

-   Packets and frames are small pieces of data that, when forming together, make a larger piece of information or message.
-   However, they are two different things in the OSI model. A frame is at layer 2 - the data link layer, meaning there is no such information as IP addresses.
-   Think of this as putting an envelope within an envelope and sending it away. The first envelope will be the packet that you mail, but once it is opened, the envelope within still exists and contains data (this is a frame).
-   This process is called encapsulation
-   At this stage, it's safe to assume that when we are talking about anything IP addresses, we are talking about packets.
-   When the encapsulating information is stripped away, we're talking about the frame itself.
    -Packets have different structures that are dependant upon the type of packet that is being sent
-   Networking is full of standards and protocols that act as a set of rules for how the packet is handled on a device
-   A packet using this protocol will have a set of headers that contain additional pieces of information to the data that is being sent across a network.
-   Some notable headers include:
    -   ![headers](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Packets%20%26%20Frames/Pastedimage20210703002118.png)

#### TCP/IP(The Three-Way Handshake)

- TCP (or Transmission Control Protocol for short) is another one of these rules used in networking
- The TCP/IP protocol consists of four layers and is arguably just a summarized version of the OSI model. These layers are:
    - Application
    - Transport
    - Internet
    - Network Interface
- Very similar to how the OSI model works, information is added to each layer of the TCP model as the piece of data (or packet) traverses it. As you may recall, this process is known as encapsulation - where the reverse of this process is decapsulation.
- One defining feature of TCP is that it is connection-based, which means that TCP must establish a connection between both a client and a device acting as a server before data is sent.
- TCP guarantees that any data sent will be received on the other end. This process is named the Three-way handshake
- TCP packets contain various sections of information known as headers that are added from encapsulation
- Important headers:
    - ![header](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Packets%20%26%20Frames/Pastedimage20210703002503.png)
- Next, we'll come on to discuss the Three-way handshake - the term given for the process used to establish a connection between two devices. The Three-way handshake communicates using a few special messages - the table below highlights the main ones:
    - ![handshake](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Packets%20%26%20Frames/Pastedimage20210703002531.png)
- Connection:
    - ![connection](https://camo.githubusercontent.com/98a920b488dbd6434cd5804b52a53bfb91e71611877445935b62d98661b76bfc/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f7061636b6574732d6672616d65732f74637068616e647368616b652e706e67)
    - Any sent data is given a random number sequence and is reconstructed using this number sequence and incrementing by 1. Both computers must agree on the same number sequence for data to be sent in the correct order. This order is agreed upon during three steps:

        - SYN - Client: Here's my Initial Number Sequence (ISN) to SYNchronize with (0)
        - SYN/ACK - Server: Here's my Initial Number Sequence (ISN) to SYNchronize with (5,000), and I ACKnowledge your initial number sequence (0)
        - ACK - Client: I ACKnowledge your Initial Number Sequence (ISN) of (5,000), here is some data that is my ISN+1 (5,000 + 1)
        - ![sequence](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Packets%20%26%20Frames/Pastedimage20210703002605.png)
- Closing a connection:
    - First, TCP will close a connection once a device has determined that the other device has successfully received all of the data
    - Because TCP reserves system resources on a device, it is best practice to close TCP connections as soon as possible
    - To initiate the closure of a TCP connection, the device will send a "FIN" packet to the other device. Of course, with TCP, the other device will also have to acknowledge this packet.
    - ![closing](https://camo.githubusercontent.com/b47c7d50521b63ca0a3bd51290c265aaeeeb3776de5813a2d795d9aa3fc15262/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f7061636b6574732d6672616d65732f74637068616e647368616b652d322e706e67)
    -  Alice has sent Bob a "FIN" packet. Because Bob received this, he will let Alice know that he received it and that he also wants to close the connection (using FIN). Alice has heard Bob loud and clear and will let Bob know that she acknowledges this

#### UDP/IP

- The User Datagram Protocol (UDP) is another protocol that is used to communicate data between devices
- UDP is a stateless protocol that doesn't require a constant connection between the two devices for data to be sent. For example, the Three-way handshake does not occur, nor is there any synchronization between the two devices.
- As mentioned, no process takes place in setting up a connection between two devices. Meaning that there is no regard for whether or not data is received, and there are no safeguards such as those offered by TCP, such as data integrity
- UDP packets are much simpler than TCP packets and have fewer headers. However, both protocols share some standard headers, which are what is annotated in the table below:
- ![udp/ip](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Packets%20%26%20Frames/Pastedimage20210703003100.png)
- How connection in UDP looks like:
    - ![UDP connection](https://camo.githubusercontent.com/588baaee0809059849491e18a108bc57f7aa8498cf88d8d325e0ae1e8050e4ed/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f7061636b6574732d6672616d65732f7564707368616b652d312e706e67)
    - There is no sync, and just sends data constantly without confirmation it was received
443
666 - doom

#### Ports 101

- Ports are an essential point in which data can be exchanged
- Networking devices also use ports to enforce strict rules when communicating with one another
- When a connection has been established, any data sent or received by a device will be sent through these ports
- In computing, ports are a numerical value between 0 and 65535 (65,535)
- We associate applications, software and behaviors with a standard set of rules
- For example, by enforcing that any web browser data is sent over port 80 or 443, software developers can design a web browser such as Google Chrome or Firefox to interpret the data the same way as one another.
- While the standard rule for web data is port 80 or 443, a few other protocols have been allocated a standard rule. Any port that is within 0 and 1024 (1,024) is known as a common port. Let's explore some of these other protocols below:
- ![ports](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Packets%20%26%20Frames/Pastedimage20210703003433.png)
- Port 666 is reserved to Doom
- [More ports](http://www.vmaxx.net/techinfo/ports.htm)
- These protocols only follow the standards. I.e. you can administer applications that interact with these protocols on a different port other than what is the standard (running a web server on 8080 instead of the 80 standard port). Note, however, applications will presume that the standard is being followed, so you will have to provide a colon ( : ) along with the port number