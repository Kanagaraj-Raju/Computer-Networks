# 1.Introduction to Computer Networks

## Types of Networks
Computer networks can be classified based on their geographical span:

### Local Area Network (LAN):
Covers a small geographical area like a single building or campus.

**Example**: Your university computer lab network connecting all computers within that building

### Metropolitan Area Network (MAN):
Spans a city or large campus.  
**Example**: A network connecting multiple university buildings across a city

### Wide Area Network (WAN):
Spans large geographical distances, potentially worldwide.  
**Example**: The internet itself is the largest WAN

### Personal Area Network (PAN):
Very small network for personal use.  
**Example**: Your smartphone connecting to your wireless earbuds and smartwatch via Bluetooth

## Types of Network Architecture

### Client-Server Architecture:
Dedicated servers provide resources and services to client computers.  
**Example**: When you access your university's online portal, your laptop (client) requests information from the university's server

### Peer-to-Peer Architecture:
All computers have equal status and can be both clients and servers.  
**Example**: BitTorrent file sharing where each participant both uploads and downloads file fragments

### Hybrid Architecture:
Combines both client-server and peer-to-peer elements.  
**Example**: Modern online gaming platforms where game state is managed by central servers but direct peer connections may be established for low-latency gameplay

## How Networks Work
Networks function by breaking data into packets that are transmitted across physical or wireless media using standardized protocols.
Imagine sending a letter through the postal system. You write a letter (data), put it in an envelope with a destination address (packet), and the postal service uses its infrastructure (network) to deliver it to the recipient. In computer networks, this process happens billions of times per second across the world.

## Protocols
Protocols are standardized rules that govern how data is formatted, transmitted, received, and processed on a network.

### Composition of Protocols:
- **Header**: Contains control information like source and destination addresses
- **Payload**: The actual data being transmitted
- **Trailer/Footer**: Sometimes used for error detection

### Physical Protocols:
- Define the electrical, optical, or radio wave specifications
- **Example**: Ethernet (IEEE 802.3) defines voltage levels, timing, and physical connectors

### Logical Protocols:
- Define how data is formatted, addressed, transmitted, and received
- **Example**: TCP defines how to establish connections, sequence packets, and handle errors

## How Addressing is Done

### Temporary Address:
Assigned dynamically and may change  
**Example**: IP addresses assigned by DHCP when devices connect to a network

### Permanent Address:
Hardware-embedded and doesn't change  
**Example**: MAC addresses burned into network interface cards

### MAC Address (Media Access Control):
48-bit physical address (6 bytes) expressed as 12 hexadecimal digits  
**Example**: `00:1A:2B:3C:4D:5E`  
First 6 digits identify the manufacturer (OUI), last 6 are unique to the device  
Like a device's "serial number" for networking

### IP Address (Internet Protocol Address):
Logical address that identifies a device on a network  
Can change as a device moves between networks  
Like a "postal address" that can change when you move

### IP Address Types:
- **IPv4**: 32-bit address (e.g., `192.168.1.1`)
- **IPv6**: 128-bit address (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)
- **Unicast**: Sends to one specific destination
- **Multicast**: Sends to multiple specific destinations
- **Broadcast**: Sends to all devices on a network segment

## Network Topology
Network topology describes the arrangement of nodes and connections in a network:

### Bus Topology:
All devices connect to a single cable (the bus).  
**Example**: Early Ethernet networks using coaxial cable

### Star Topology:
All devices connect to a central hub or switch.  
**Example**: Most modern LANs using Ethernet switches

### Ring Topology:
Devices form a closed loop.  
**Example**: Token Ring networks (mostly historical now)

### Mesh Topology:
Every device connects directly to every other device.  
**Example**: Internet backbone routers often use partial mesh for redundancy

### Tree/Hierarchical Topology:
Hybrid of star and bus topologies arranged in a hierarchy.  
**Example**: Campus networks with building switches connecting to core switches

### Hybrid Topology:
Combination of two or more topologies.  
**Example**: Most enterprise networks use a hybrid approach

## OSI Layer Model
The Open Systems Interconnection (OSI) model divides network communication into seven conceptual layers. Each layer serves the layer above it and is served by the layer below.

### Layer 7: Application Layer
**Function**: Provides network services directly to end-users  
**Protocols**: HTTP, SMTP, FTP, DNS  
**Data unit**: Data  
**Real-world example**: When you open your browser and type "www.mit.edu," you're interacting with the application layer. The browser (application) communicates using HTTP protocol.

### Layer 6: Presentation Layer
**Function**: Translates, encrypts, and compresses data  
**Protocols**: SSL/TLS, JPEG, MPEG  
**Data unit**: Data  
**Real-world example**: When you access your bank's website, SSL/TLS encrypts your data. It's like translating English to a secret code that only your bank can understand.

### Layer 5: Session Layer
**Function**: Establishes, manages, and terminates connections  
**Protocols**: NetBIOS, RPC  
**Data unit**: Data  
**Real-world example**: Video conferencing software manages the ongoing session between participants. If you temporarily lose connection, the session layer helps reestablish it without starting over.

### Layer 4: Transport Layer
**Function**: End-to-end communication, reliability, flow control  
**Protocols**: TCP, UDP  
**Data unit**: Segments (TCP) or Datagrams (UDP)  
**Real-world example**: When downloading a large file, TCP ensures all parts arrive correctly and in order. It's like tracking a package with delivery confirmation.

### Layer 3: Network Layer
**Function**: Routing and logical addressing  
**Protocols**: IP, ICMP, OSPF  
**Data unit**: Packets  
**Real-world example**: When you send an email across the country, routers at the network layer determine the best path for your data packets, similar to how postal services route packages.

### Layer 2: Data Link Layer
**Function**: Physical addressing, access to media, error detection  
**Protocols**: Ethernet, PPP, Frame Relay  
**Data unit**: Frames  
**Real-world example**: When your laptop communicates with your wireless router, the data link layer adds the MAC addresses to identify the specific devices. It's like addressing an envelope with specific names rather than just street addresses.

### Layer 1: Physical Layer
**Function**: Transmission and reception of raw bit streams  
**Standards**: RS-232, Ethernet physical layer  
**Data unit**: Bits  
**Real-world example**: The Ethernet cable connecting your computer to a router transmits electrical signals representing 1s and 0s across copper wires, or light pulses in fiber optic cables.

# 2.Network Protocols and Communication

## Internet
The Internet is a global system of interconnected computer networks using the TCP/IP protocol suite to communicate. It's not a single network but a "network of networks" that links billions of devices worldwide.

## TCP/IP Model with Real-World Example
The TCP/IP model is a simplified version of the OSI model with four layers:

### Application Layer (Combines OSI layers 5-7)
**Protocols**: HTTP, SMTP, FTP, DNS  
**Real-world example**: When you check email, your email client (like Outlook) uses SMTP/POP3/IMAP protocols to communicate with mail servers  

### Transport Layer (OSI Layer 4)
**Protocols**: TCP, UDP  
**Real-world example**: When streaming a video, your device might use UDP for real-time delivery where occasional dropped frames are acceptable

### Internet Layer (OSI Layer 3)
**Protocols**: IP, ICMP  
**Real-world example**: Traceroute command uses ICMP to track the path of packets across networks

### Network Interface Layer (OSI Layers 1-2)
**Protocols**: Ethernet, Wi-Fi, PPP  
**Real-world example**: Your laptop's Wi-Fi card implementing 802.11ac to connect to your home router

## TCP (Transmission Control Protocol)
TCP is a connection-oriented protocol that ensures reliable, ordered delivery of data.

**Key features:**
1. [x] Connection establishment via three-way handshake (SYN, SYN-ACK, ACK)
2. [x] Flow control to prevent overwhelming receivers
3. [x] Error detection and correction
4. [x] Acknowledgments and retransmission of lost packets
5. [x] Ordered delivery  

**Real-world analogy**: TCP is like a phone call where both parties establish a connection, confirm they hear each other, and can ask for clarification if something is misheard.  

## UDP (User Datagram Protocol)

UDP is a connectionless protocol with minimal overhead, prioritizing speed over reliability.

**Key features:**

1. [x] No connection establishment
2. [x] No acknowledgment of received packets
3. [x] No retransmission of lost packets
4. [x] Lower latency than TCP
5. [x] Suitable for real-time applications

**Real-world analogy**: UDP is like sending a postcard—you send it out and hope it arrives, but don't get confirmation of delivery. This is fine for applications where speed matters more than perfect delivery.

## IP Address

An IP address is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication.  
IPv4, IPv6, Finite IPs

### IPv4:
32-bit addresses (4 bytes)  
**Format**: Four decimal numbers (0-255) separated by dots
**Example**: `192.168.1.1`  
Limited to approximately 4.3 billion unique addresses  

### IPv6:
128-bit addresses (16 bytes)  
**Format**: Eight groups of four hexadecimal digits separated by colons
**Example**: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
Can be shortened by removing leading zeros and replacing consecutive all-zero groups with ::  
Provides approximately 340 undecillion addresses (3.4 × 10^38)  

## ISP (Internet Service Provider)
ISPs provide services for accessing, using, and participating in the Internet. They maintain infrastructure and serve as gateways between end-users and the broader Internet.  
**Types of ISPs:**
* Tier 1: Connect directly to the Internet backbone
* Tier 2: Connect to Tier 1 providers and each other
* Tier 3: Provide "last mile" service to end-users

## ICANN (Internet Corporation for Assigned Names and Numbers)
ICANN is a non-profit organization responsible for:
1. [x] Coordinating maintenance of databases for namespaces of the Internet
2. [x] IP address allocation
3. [x] Domain name system management
4. [x] Root server system management

## Network Bits and Host Bits
IP addresses are divided into two portions:
1. Network portion: Identifies the specific network  
2. Host portion: Identifies a specific device on that network  

The subnet mask determines which portion is which.  
**Example**: `192.168.1.100` with subnet mask `255.255.255.0` (or` /24`)  

**Network portion**: `192.168.1`
**Host portion**: `100`

## Reserved IPs, Host Address, Broadcast Address
In each subnet:  
* **Network address**: All host bits set to 0 (e.g., `192.168.1.0/24`)
* **Broadcast address**: All host bits set to 1 (e.g., `192.168.1.255/24`)
* **Host addresses**: All addresses between network and broadcast

## Significance of Broadcast Address with Real-World Example
The broadcast address allows sending data to all devices on a network segment simultaneously.  
**Real-world example**: When your device first connects to a network and needs an IP address, it sends a DHCP discovery request to the broadcast address (`255.255.255.255`). This is like walking into a crowded room and shouting "Can anyone help me find a seat?" instead of asking each person individually.  

## Number of IPs Available for IP Address Using CIDR Values
CIDR (Classless Inter-Domain Routing) notation specifies the number of bits in the network portion using slash notation.  
**Formula**: Available host addresses = 2^(32-prefix) - 2  
**Examples**:
* /24 network: 2^(32-24) - 2 = 2^8 - 2 = 254 usable addresses
* /16 network: 2^(32-16) - 2 = 2^16 - 2 = 65,534 usable addresses

## Public IP and Private IP
### Public IP:
Globally unique and routable on the internet  
Assigned by ISPs or internet registries  
**Example**: The IP address your ISP assigns to your home router  

### Private IP:
Used within private networks  
Not routable on the internet  
Defined in RFC 1918:  
1. Class A: `10.0.0.0` to `10.255.255.255`
2. Class B: `172.16.0.0` to `172.31.255.255`
3. Class C: `192.168.0.0` to `192.168.255.255`

## How Efficiently Public IP is Managed
Public IP addresses are managed through various techniques:  
1. [x] CIDR: Allows for more efficient allocation than the older classful system
2. [x] Regional Internet Registries (RIRs) allocation policies
3. [x] NAT: Allows multiple private devices to share public IPs
4. [x] IP address recycling
5. [x] Address transfer markets

## NAT (Network Address Translation)
NAT allows multiple devices with private IP addresses to share a single public IP address for internet access.

### Types of NAT:
1. **Static NAT**: One-to-one mapping of private to public IPs
2. **Dynamic NAT**: Maps private IPs to a pool of public IPs
3. **PAT (Port Address Translation)/NAT Overload**: Maps multiple private IPs to a single public IP using different ports  
**Real-world example**: Your home router performs NAT when multiple devices (phones, laptops, smart TVs) all connect to the internet through a single public IP address assigned by your ISP.

## Network Protocols

### DHCP (Dynamic Host Configuration Protocol)
DHCP automatically assigns IP addresses and network configuration to devices.  
**DHCP Discover:**  
Client broadcasts message to discover available DHCP servers  
Message sent to `255.255.255.255` (broadcast) on UDP port 67  
Like shouting "Is there anyone who can give me an address?"  

**DHCP Offer:**  
Server responds with an offer of an IP address  
Includes lease time and other configuration parameters  
Like responding "I can give you address `192.168.1.100`"  

**DHCP Request:**  
Client requests the offered IP address  
Also broadcasts so all DHCP servers know which offer was accepted  
Like saying "I'll take the `192.168.1.100` address that you offered"  

**DHCP ACK (Acknowledgment):**  
Server acknowledges the request and finalizes the lease  
Includes confirmed lease time and configuration  
Like saying "Address `192.168.1.100` is officially yours for the next 24 hours"  

**Lease Renewal:**
Client tries to renew the lease when it reaches 50% of its lifetime  
If renewal fails, client tries again at 87.5% of lease time  
If still unsuccessful, client must restart the DHCP process  
Like renewing your apartment lease before it expires  

## ARP (Address Resolution Protocol)
ARP resolves IP addresses to MAC addresses within a local network.
**ARP Request:**  
Broadcast message asking "Who has IP address `x.x.x.x`?"  
Sent to MAC address `FF:FF:FF:FF:FF:FF` (broadcast)  
Example: "Who has `192.168.1.1`? Tell `00:1A:2B:3C:4D:5E`"  

**ARP Reply:**  
Unicast message with "IP address `x.x.x.x` is at MAC address `yy:yy:yy:yy:yy:yy`"  
Sent directly to the requester  
Example: "`192.168.1.1` is at `00:1A:2B:3C:4D:5E`"

### ARP Important Commands and Debugging Issues:
`arp -a`: Displays the ARP cache  
`arp -d [ip_address]`: Deletes an entry from the ARP cache  
`arp -s [ip_address] [mac_address]`: Adds a static entry to the ARP cache  
**Common issues:** ARP poisoning, stale ARP entries, duplicate IP addresses  

## ICMP (Internet Control Message Protocol)
ICMP provides error reporting and operational information for IP.  

### ICMP Important Commands and Debug Issues:
`ping`: Tests reachability (uses ICMP Echo Request/Reply)  
`traceroute or tracert`: Traces the route to a destination (uses ICMP Time Exceeded)  
`pathping`: Combines ping and traceroute functionality  
**Common issues:** ICMP blocking by firewalls, rate limiting, MTU problems  