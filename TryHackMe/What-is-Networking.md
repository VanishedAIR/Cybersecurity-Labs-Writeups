## What-is-Networking (TryHackMe)

### Task Summary:

- In the first interactive activity I was shown an example of a user named Alice who paid for the Wi-Fi and her packets were allowed to pass and reach TryHackMe website however a user named Bob's MAC address did not indicate he had paid thus his packets were redirected to the trash. To access the TryHackMe website for free, I was told to copy Alice's MAC address, which allowed me to access TryHackMe website, essentially learning about spoofing.

- The second interaction was simply checking the ping of the address 8.8.8.8 and the syntax for checking the ping on the address 10.10.10.10

### Summary:

- Networks are simply things that are connected

- In computing, a network can be formed by anywhere from 2 devices to billions

- The internet is one giant network made up of many small networks

- Tim Berners-Lee created the World Wide Web (WWW) which allowed the Internet to be used as a storing and sharing information platform

- As mentioned earlier, internet is made up of small networks, these small networks are called private networks. The places where the networks connect are called public networks

- Just like how we are identifiable by our name and more permanently by our fingerprint, devices have an IP address and a Media Access Control (MAC) address. An IP address is seen as temporary while MAC is more permanent similar to a serial number

- IP address (or Internet Protocol) address can be used to identify a host on a network for a period of time where that IP can be associated with another device without the IP changing

  - Example IP address: 192.168.1.1

    - An IP address is a set of numbers that are divided into 4 octets
    - This number is calculated through a technique called IP addressing and subnetting
    - IP addresses can change from device to device but cannot be active simultaneously more than once within the same network
    - IP addresses follow a set of standard known protocols which forces devices to communicate in the same language
    - A public address is used to identify the device on the Internet, whereas a private address is used to identify a device amongst other devices

  - Example device: DESKTOP-KJE57FD and CMNatic-PC

    - DESKTOP-KJE57FD has a public IP address of 192.168.1.77 and a private IP address of 86.157.52.21
    - CMNatic-PC has a public IP address of 192.168.1.74 and a private IP address of 86.157.52.21

- These two devices will be able to use their private IP addresses to communicate with each other. However, any data sent to the Internet from either of these devices will be identified by the same public IP address. Public IP addresses are given by your Internet Service Provider (or ISP) at a monthly fee

- One version of the Internet Protocol addressing scheme known as IPv4, which uses a numbering system of 2^32 IP addresses (4.29 billion) which isn't enough for all the devices in the world

- IPv6 is a new iteration of the Internet Protocol addressing scheme to help tackle this issue

  - Supports 2^128 of IP addresses (340 trillion-plus) and more efficient due to new methodologies

- Devices on a network will have physical network interface, a microchip board found on the device's motherboard.

- This is assigned a unique address at the factory it was built at, called a MAC (Media Access Control) address. MAC address is 12-character hexadecimal number. split into two's and separated by a colon

- Example: a4:c3:f0:85:ac:2d

  - The first six character represent the company that made the network interface, and the last six is a unique number
  - In the example, a4:c3:f0 corresponds to Intel and 85:ac:2d is unique address

- An interesting thing about MAC addresses is that they can be faked or "spoofed" in a process known as spoofing. 

- Spoofing occurs when a networked device pretends to identify as another using its MAC address. When this occurs, it can often break poorly implemented security designs that assumes that devices talking on a network are trustworthy.

- Ping is one of the most fundamental network tools available to us. 

- Ping uses ICMP (Internet Control Message Protocol) packets to determine the performance of a connection between devices, for example, if the connection exists or is reliable.  

- The time taken for ICMP packets traveling between devices is measured by ping. 

- This measuring is done using ICMP's echo packet and then ICMP's echo reply from the target device.

- The syntax to do a simple ping is `ping IP address or website URL`