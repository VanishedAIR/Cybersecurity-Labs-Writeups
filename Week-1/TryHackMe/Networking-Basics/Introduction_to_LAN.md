## Introduction to LAN ([TryHackMe - YouTube](https://www.youtube.com/watch?v=csYtPidvvFQ&list=PL0iJrrpaWpyWTmLQxeRy64LKGzLbRLDfD&index=2))

### Task Summary:

-   First simulation showed the flaws in each topology:
    -   Ring: if a device goes down or a cable is broken, then data will no longer be passed
    -   Bus: it cannot handle a large amount of data
    -   Star: if the switch goes down the network will no longer work

### Summary:

#### Introducing LAN Topologies

-   When talking about "topology", we are actually referring to the design or look of the network at hand
-   Star Topology:

    -   Devices are individually connected via a central networking device such as a switch or hub. This topology is common today due to its reliability and scalability - despite the cost
    -   Any info sent to a device is sent via the central device
    -   It is more expensive considering more cabling and the purchase of dedicated networking equipment
    -   However, this has its own advantages, such as being more scalable meaning it is very easy to add devices as the demand for the network increases
    -   The more the network scales, the more maintenance is required to keep the network functional
    -   Increased dependence on maintenance can also make troubleshooting faults much harder
    -   Star topology is prone to failure, if the centralized hardware that connects devices fails, the devices will no long be able to send or receive data

-   Bus Topology:

    -   This type of connection relies upon a single connection which is known as a backbone cable
    -   This type of topology is similar to the leaf off of a tree in the sense that devices (leaves) stem from where the branches are on this cable
    -   It is also very quickly prone to becoming slow and bottle-necked since data destined for each device travels along the same cable and can become a problem if devices are simultaneously requesting data
    -   This bottleneck also results in very difficult troubleshooting because it quickly becomes difficult to identify which device is experiencing issues with data all traveling along the same route
    -   However, this topology is easier and more cost-efficient due to the expenses which includes cabling or dedicated networking equipment used to connect these devices
    -   There is a single point of failure along the backbone cable, if it were to break devices can no longer receive or transmit data along the bus

-   Ring Topology

    -   The ring topology (also known as token topology) boasts some similarities
    -   Devices such as computers are connected directly to each other to form a loop, meaning that there is little cabling required and less dependence on dedicated hardware such as within a star topology
    -   A ring topology works by sending data across the loop until it reaches the destined device, using other devices along the loop to forward the data
    -   Interestingly, a device will only send received data from another device in this topology if it does not have any to send itself. If the device happens to have data to send, it will send its own data first before sending data from another device.
    -   It is easy to troubleshoot considering there is only one direction for data to travel across
    -   However it isn't an efficient way of data traveling across a network, as it may have to visit many multiple devices first before reaching the intended device
    -   ring topologies are less prone to bottlenecks, such as within a bus topology, as large amounts of traffic are not traveling across the network at any one time
    -   The design of this topology does, however, mean that a fault such as cut cable, or broken device will result in the entire networking breaking
    -   Not very common

-   Router:

    -   Router's job to connect networks and pass data between them through routing
    -   Routing is the label given to the process of data traveling across networks
    -   Routing involves creating a path between networks so that this data can be successfully delivered

-   Switch:

    -   Switches are dedicated devices within a network that are designed to aggregate multiple other devices such as computers, printers, or any other networking-capable device using ethernet
    -   Switches are usually found in larger networks such as businesses, schools, or similar-sized networks, where there are many devices to connect to the network
    -   Switches can connect a large number of devices by having ports of 4, 8, 16, 24, 32, and 64 for devices to plug into
    -   Switches use a technology called "packet switching" to break down pieces of data into smaller, more manageable chunks of data called packets
    -   This technology allows for the efficiency of a network because large pieces of data take up more resources -- slowing down a busy network
    -   Both Switches and Routers can be connected to one another
    -   The ability to do this increases the redundancy (the reliability) of a network by adding multiple paths for data to take. If one path goes down, another can be used
    -   Whilst this may reduce the overall performance of a network because packets have to take longer to travel, there is no downtime

#### A Primer on Subnetting

-   Subnetting is the term given to splitting up a network into smaller, miniature networks within itself
-   Whilst you know where to send information in real life to the correct department, networks need to know as well
-   Network administrators use subnetting to categorize and assign specific parts of a network to reflect this
-   Subnetting is achieved by splitting up the number of hosts that can fit within the network, represented by a number called a subnet mask
-   Subnets use IP addresses in three different ways:
    -   Identify the network address
    -   Identify the host address
    -   Identify the default gateway
    -   Their purpose:
    -   ![purpose](https://github.com/0xashiii/TryHackMe_Writeups/raw/353ca214d0f7cb7eb587a0f10eb8f78d1694d943/Intro%20to%20LAN/Pastedimage20210702175809.png)
-   Subnetting provides a range of benefits, including efficiency, security, full control
-   Let's take the typical café on the street. This cafe will have two networks:

    -   One for employees, cash registers, and other devices for the facility
    -   One for the general public to use as a hotspot

-   Subnetting allows you to separate these two use cases from each other whilst having the benefits of a connection to larger networks such as the Internet.

#### The ARP Protocol

-   Devices can have two identifiers:
    -   A MAC address and an IP address, the ARP protocol or Address Resolution Protocol for short, is the technology that is responsible for allowing devices to identify themselves on a network
    -   ARP protocol allows a device to associate its MAC address with an IP address on the network
    -   Each device on a network will keep a log of the MAC addresses associated with other devices
    -   When devices wish to communicate with another, they will send a broadcast to the entire network searching for the specific device
    -   Devices can use the ARP protocol to find the MAC address (and therefore the physical identifier) of a device for communication

-   How does ARP Work?
    -   Each device within a network has a ledger to store information on, which is called a cache
    -   In the context of the ARP protocol, this cache stores the identifiers of other devices on the network

-   In order to map these two identifiers together (IP address and MAC address), the ARP protocol sends two types of messages:

    -   ARP Request
    -   ARP Reply

- When an ARP request is sent, a message is broadcasted to every other device found on a network by the device, asking whether or not the device's MAC address matches the requested IP address
- If the device does have the requested IP address, an ARP reply is returned to the initial device to acknowledge this. The initial device will now remember this and store it within its cache (an ARP entry)

- ![ARP](https://camo.githubusercontent.com/2fbb60bf391656f15480714df8c308176344d0f30763910ac499c001da77c23a/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f696e74726f2d746f2d6c616e2f617270342e706e67)

#### The DHCP Protocol

- IP addresses can be assigned either manually, by entering them physically into a device, or automatically and most commonly by using a DHCP (Dynamic Host Configuration Protocol) server
- When a device connects to a network, if it has not already been manually assigned an IP address, it sends out a request (DHCP Discover) to see if any DHCP servers are on the network.
- The DHCP server then replies back with an IP address the device could use (DHCP Offer). 
- The device then sends a reply confirming it wants the offered IP Address (DHCP Request), and then lastly, the DHCP server sends a reply acknowledging this has been completed, and the device can start using the IP Address (DHCP ACK)

![DHCP](https://camo.githubusercontent.com/67009be171456c2dd4baf6d469763f85f097f764c0d119522a0ac51017024f83/68747470733a2f2f6173736574732e7472796861636b6d652e636f6d2f6164646974696f6e616c2f6e6574776f726b696e672d66756e64616d656e74616c732f696e74726f2d746f2d6e6574776f726b696e672f776861742d69732d612d6e6574776f726b2f444843502e706e67)