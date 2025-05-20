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
