# Computer-Networks
In this repository, I will be adding my notes on computer networks to enhance my understanding of the subject.

# Introduction to Computer Networks

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