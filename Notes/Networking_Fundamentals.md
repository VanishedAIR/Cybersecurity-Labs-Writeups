## OSI Model ([Youtube](https://www.youtube.com/watch?v=Ilk7UXzV_Qc))

### Summary:

- OSI = Open Systems Interconnection

  - Conceptual framework for how applications communicate over a network

- There are 7 layers in the model and the layers depiction is used to help users identify what is happening within a networking system

- Typically described from top layer down

  - Application

    - This is the layer that most users interact with and recognize
    - Provides network services to the end user
    - Protocols that work with the data the client is using
    - Example: HTTP used with web browsers, Office, Outlook, and Skype
    - All of them provide set of services that allow the application layer to supply data to and receive data from presentation layer

  - Presentation

    - Performs the uncomplicated task of syntax processing
    - Converting data from one format to another
    - Translating the data from the top layer, presented application format to network format and vice versa

  - Session

    - The construction, direction, and conclusion of connection between devices occur
    - Responsible for authentication, reconnection in case of a network interruption

  - Transport

    - Responsible for transmission of data across network connections
    - How much data to send, how fast, and where it goes
    - These services may be provided by Transmission Control Protocol (TCP) or User Datagram Protocol (UDP)

  - Network

    - Handles routing of the data
    - After the data arrives at this layer, each frame of data is examined to conclude that the data has reached its ultimate target
    - Sends data to correct destination on outgoing/incoming transmission
    - IP portion of TCP/IP is the commonly known network layer for the Internet
    - Mapping between logical address and physical addresses
    - For IP addresses this is accomplished through Address Resolution Protocol (ARP)

  - Data Link

    - Considered the most complex, and often divided into sublayers
      - Media Access Control (MAC) and Logical Link Control (LLC)
      - Layer sets up link across the physical network when it receives data from the physical layer, it checks for transmission errors then packages the bits into data frames

  - Physical
    - The electrical/physical layer of the model
    - Encompasses the network cables, power plugs, cable pinouts, wireless radio frequencies, connectors, transceivers, receivers, repeaters, pulses of light, electric voltages, etc.
    - When troubleshooting, this is where it starts.
    - At this layer the model transmits the digital data bits from the source or sending devices physical layer over network communication media, which can be electrical, mechanical, or radio to the receiving or destination devices of the physical layer.

- Layers are provided by a mixture of network card drivers, OS, applications, networking hardware facilitate the transmission of signals over Ethernet, Fiber Optic, Wi-Fi or other wireless protocols.

- Acronym to remember the layers:
  - Probably (physical)
  - Didn't (data link)
  - Need (network)
  - Those (transport)
  - Stupid (session)
  - Packets (presentation)
  - Anyway (application)

## TCP/IP ([Youtube](https://www.youtube.com/watch?v=PpsEaqJV_A0))

### Summary:

- Internet traffic has to be routed to the correct place directly

- Online data has to know where it has to go

- Transmission Control Protocol (TCP)/Internet Protocol (IP)

- Think of TCP/IP as a cake, since the way it works is conceptualized in layers, except its made up in computer code

- Top most layer is Application layer what the program directly interact with

- The transport, where TCP lives and UDP (faster for low latency application).
  - After the application layer gets the data from whatever program you're using, it talks to the transport layer through something called a port.
  
  - Each port can be assigned to a different protocol in the application layer so TCP knows where data is coming from.
  
  - Once TCP gets the data, it breaks it down into packets so they can take the quickest route over the internet to get to where ever they are going
  
  - TCP attaches a header with instructions on how to assemble the packets as well as error checking info so the receiving computer knows whether the packets data arrived without any mishaps

- Then pushed onto the Internet layer, which uses IP (Internet Protocol) to attach both origin and destination IP addresses so that the packet knows where it came from and where its going

- Then sent though the network layer which handles the mac addressing so it reaches the right physical machine as well as converting the data into electrical impulses that will pass through the verbial series of tubes

## Difference between Segments, Packets and Frames ([GeeksForGeeks](https://www.geeksforgeeks.org/difference-between-segments-packets-and-frames/))

### Summary:

- When data is sent over the internet or any network, it isn't transmitted as one large block, rather divided into smaller units known as segments, packets, and frames

- These units are different layers of packaging that helps the data travel efficiently through the network.

- Segment:
  - Data sent from the application layer is broken down into smaller parts according to the Maximum Segment Size (MSS) defined by the network.
  
  - Each of these smaller data parts is then encapsulated with a TCP header and form a segment
  
  - Key parts of TCP header:
    - Source Port: shows which port data is coming from
    - Destination Port: where the data is going (which app/service on the receiving device)
    - Flag Bits: Special signals helping control how data is sent, whether it can be broken up or more data is coming
    - Sequence Number: Helps make sure pieces are assembled correctly on the receiving end
    - Checksum: Error check making sure data wasn't damaged along the way
    - Options: Extra settings, like how big the data chunks can be or how fast they can be sent

- Packets:
  - Once the Transport Layer generates segments, the Network Layer (usually using the IP) processes these segments further to create packets, crucial for routing data across different networks
  
  - Structure of an IP packet:
    - Header: typically 20 bytes, but can go up to 60 bytes if options are used
    - Body: Contains the segment from the transport layer
  
  - Fields in the IP header
    - Source IP Address: Specifies origin of the packet
    - Destination IP address: Specifies the final destination
    - TTL (Time To Live): Packet's lifespan, and decreases by 1 with each hop (router) and when TTL reaches 0, packet is discarded
    - Identification: Aids in reassembling fragmented packets
    - Protocol Type: Indicates the transport layer protocol being used (TCP, UDP)
    - Version: Specifies the IP protocol version IPv4 or IPv6
  
  - IP headers along with the body (containing the segment from the Transport layer) makes the IP Packet or popularly only Packet. This layer is also responsible for fragmentation if required, when MTU (Maximum Transmission Unit) of the network is less. This fragmentation is done at the Routers.

- Frames:
  - When a packet arrives, it gets wrapped with another header (sometimes a trailer), turning into a frame.
  
  - This wrapping helps the data move from one physical device (like your computer) to another (like a router or switch) on the same local network
  
  - Frame Header Contents:
    - MAC (Media Access Control) Address Source: Identifies the device sending the frame
    - MAC Address - Destination: Identifies the device meant to receive the frame
    - Type/Length Field: Tells what kind of data is being carried (like an IPv4 packet)
    - Error Checking (usually in trailer): Often a CRC (Cyclic Redundancy Check) is added to help detect any errors that happened while the data was moving across the wire. 
