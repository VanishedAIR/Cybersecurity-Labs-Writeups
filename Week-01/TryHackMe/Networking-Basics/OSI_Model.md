## OSI Model ([TryHackMe - YouTube](https://www.youtube.com/watch?v=hWIktHvNjeM&list=PL0iJrrpaWpyWTmLQxeRy64LKGzLbRLDfD&index=3))

### Task Summary:

-   Our hacker has been locked in the dungeon, and their only chance of freedom is by choosing the correct path based on the OSI model. Physical -> Data Link -> Network -> Transport -> Session -> Presentation -> Application.
-   A mini-game to help remember the OSI layers from bottom up by choosing the right doors.

### Summary:

#### What is the OSI Model?

-   The OSI model (or Open Systems Interconnection Model) is an absolute fundamental model used in networking.
-   This critical model provides a framework dictating how all networked devices will send, receive and interpret data.
-   Main benefits of the OSI model is that devices can have different functions and designs on a network while communicating with other devices.
-   OSI model consists of seven layers, with each layer has a different set of responsibilities and is arranged from Layer 7 to Layer 1.
-   At every individual layer that data travels through, specific processes take place, and pieces of information are added to this data
-   We only need to understand that this process is called encapsulation and what the OSI model looks like in the diagram below:
    -   ![OSI](https://camo.githubusercontent.com/dbb90964bd9f60458fb2e432721e42818a55d1d705ce0a51299e9b51c4b01070/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f6f73692d6d6f64656c2f6f73696d6f64656c2e737667)

#### Layer 7 - Application

-   The application layer of the OSI model is the layer in which protocols and rules are in place to determine how the user should interact with data sent or received.
-   Everyday applications such as email clients, browsers, or file server browsing software such as FileZilla provide a friendly, Graphical User Interface (GUI) for users to interact with data sent or received.
-   Other protocols include DNS (Domain Name System), which is how website addresses are translated into IP addresses.

#### Layer 6 - Presentation

-   Layer 6 of the OSI model is the layer in which standardization starts to take place. Because software developers can develop any software such as an email client differently, the data still needs to be handled in the same way — no matter how the software works.
-   This layer acts as a translator for data to and from the application layer (layer 7).
-   The receiving computer will also understand data sent to a computer in one format destined for in another format.
-   Security features such as data encryption (like HTTPS when visiting a secure site) occur at this layer.

#### Layer 5 - Session

-   Once data has been correctly translated or formatted from the presentation layer (layer 6), the session layer (layer 5) will begin to create a connection to the other computer that the data is destined for. When a connection is established, a session is created. Whilst this connection is active, so is the session.
-   The session layer (layer 5) synchronizes the two computers to ensure that they are on the same page before data is sent and received.
-   Once these checks are in place, the session layer will begin to divide up the data sent into smaller chunks of data and begin to send these chunks (packets) one at a time.
-   This dividing up is beneficial because if the connection is lost, only the chunks that weren't yet sent will have to be sent again — not the entire piece of the data
-   What is worthy of noting is that sessions are unique — meaning that data cannot travel over different sessions, but in fact, only across each session instead.

#### Layer 4 - Transport

-   Layer 4 of the OSI model plays a vital part in transmitting data across a network
-   When data is sent between devices, it follows one of two different protocols that are decided based upon several factors: TCP or UDP
-   TCP:

    -   Transmission Control Protocol
    -   This protocol is designed with reliability and guarantee in mind
    -   This protocol reserves a constant connection between the two devices for the amount of time it takes for the data to be sent and received.
    -   TCP incorporates error checking into its design
    -   Error checking is how TCP can guarantee that data sent from the small chunks in the session layer (layer 5) has then been received and reassembled in the same order
    -   Pros and Cons:
        -   ![TCP](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/OSI%20Model/Pastedimage20210702234847.png)
    -   TCP is used for situations such as file sharing, internet browsing or sending an email. This usage is because these services require the data to be accurate and complete
    -   In the diagram below, we can see how a picture of a dog is broken down into small pieces of data (known as packets) from the "webserver", where the "computer" re-constructs the picture of the dog into the correct order.
        -   ![TCP Dog](https://camo.githubusercontent.com/7998905a08e96b34b320db307220cd018a98ed6364219ba4c600d71d14ebe9fb/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f6f73692d6d6f64656c2f746370646f672e706e67)

-   UDP:

    -   User Datagram Protocol
    -   This protocol is not nearly as advanced as TCP
    -   It doesn't boast the many features offered by TCP, such as error checking and reliability
    -   In fact, any data that gets sent via UDP is sent to the computer whether it gets there or not. There is no synchronization between the two devices or guarantee; just hope for the best, and fingers crossed.
    -   Pros and Cons:
        -   ![UDP](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/OSI%20Model/Pastedimage20210702235017.png)
    -   Using the same example as before, we can now see that only Packets #1 and #3 have been received by the "Computer", meaning that half of the image is missing.
        -   ![UDP Dog](https://camo.githubusercontent.com/5caa1dcb74ebe4f7a3b53445afe055105dd5d24c1e5b823b8e2798238a6877db/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f6f73692d6d6f64656c2f756470646f672e706e67)
    -   UDP is useful in situations where there are small pieces of data being sent. For example, protocols used for discovering devices (ARP and DHCP) or larger files such as video streaming (where it is okay if some part of the video is pixelated. Pixels are just lost pieces of data!)

#### Layer 3 - Network

-   The third layer of the OSI model (network layer) is where the magic of routing & re-assembly of data takes place (from these small chunks to the larger chunk).
-   Firstly, routing simply determines the most optimal path in which these chunks of data should be sent.
-   Some protocols at this layer determine exactly what is the "optimal" path that data should take to reach a device, Briefly, these protocols include OSPF (Open Shortest Path First) and RIP (Routing Information Protocol).
-   The factors that decide what route is taken is decided by the following:
    -   What path is the shortest? I.e. has the least amount of devices that the packet needs to travel across.
    -   What path is the most reliable? I.e. have packets been lost on that path before?
    -   Which path has the faster physical connection? I.e. is one path using a copper connection (slower) or a fibre (considerably faster)?
-   At this layer, everything is dealt with via IP addresses such as 192.168.1.100. Devices such as routers capable of delivering packets using IP addresses are known as Layer 3 devices — because they are capable of working at the third layer of the OSI model.
-   [Network](https://camo.githubusercontent.com/17576d8a0006c3e35562b69ed0ab47b073e2e7a15662381a152b077bf5b0e0af/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f696e74726f2d746f2d6e6574776f726b696e672f776861742d69732d7468652d696e7465726e65742f726f7574696e67322e706e67)

#### Layer 2 - Data Link

-   The data link layer focuses on the physical addressing of the transmission.
-   It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical MAC (Media Access Control) address of the receiving endpoint.
-   Inside every network-enabled computer is a Network Interface Card (NIC) which comes with a unique MAC address to identify it.
-   MAC addresses are set by the manufacturer and literally burnt into the card; they can't be changed -- although they can be spoofed. When information is sent across a network, it's actually the physical address that is used to identify where exactly to send the information.

#### Layer 1 - Physical

-   This layer references the physical components of the hardware used in networking and is the lowest layer that you will find. Devices use electrical signals to transfer data between each other in a binary numbering system (1's and 0's).
-   For example, ethernet cables connecting devices
