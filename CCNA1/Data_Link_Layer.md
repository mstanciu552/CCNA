# Data Link Layer

## Protocols

- Ethernet
- 802.11 Wireless
- Point-to-Point Protocol (PPP)
- High-Level Data Link Control (HDLC)
- Frame Relay

## What it does

1. Enables upper layers to access data. They are not aware of the transfer media(cables, wireless, fibre optic, etc.)
1. Encapsulates the packets (IPv4 and IPv6) into frames
1. Controls how data is placed and received on the media.
1. Exchanges frames between endpoints on the network
1. Performs error detection and rejects corrupted frames
1. Receives encapsulated frames and sends them to the appropriate upper layers

## Header to add to Layer 3 Packets

- Destination NICs
- Source NICs

## IEEE 802 LAN/MAN

This standard is specific to LANs, WLANs and WPANs.

### Consists of the following 2 sub-layers:

1. Logical Link Control(LLC)
   This **IEEE 802.2 sublayer** provides communication between the higher levels of software and the lower levels of hardware.
   It places information in the frame that identifies which network layer protocol is used for the frame.
   It also allows for integration with both IPv4 and IPv6 protocols on the same interfaces.
   Adds Layer 2 Control Information.
1. Media Access Control(MAC)
   IEEE 802.3, 802.11, 802.15
   It is used for data encapsulation

- Data encapsulation of the Data Link Layer:
  - Frame delimiting - provides important delimiters to identify fields within a frame; they provide syncronization between the transmitting and receiving node
  - Addressing - provides source and destination addressing
  - Error detection - includes a trailer used to detect transmission errors

## Encapsulation process

At each hop along the path of a network, a router performs the following functions:

- accepts the frame from a medium
- de-encapsulates the frame
- re-encapsulates the packet into a new frame
- sends the frame along the network

## Organizations that define standards for this layer

- Institute of Electrical and Electronics Engineers **(IEEE)**
- International Telecommunication Union **(ITU)**
- International Organization for Standardization **(ISO)**
- American National Standards Institute **(ANSI)**

## Network Topologies

It is the arrangement of the network devices and the interconnections between them.

There are 2 types of topologies when describing LAN and WAN:

1. Physical topology - identifies the physical connections between devices; can contain room number, building, location on rack, etc.
1. Logical topology - identifies virtual connections using device interfaces and Layer 3 IPs.

### WAN topologies

1. Point-to-Point
1. Hub and Spoke
1. Mesh

### WAN protocols

- Point-to-Point Protocol (PPP)
- High-Level Data Link Control (HDLC)
- Frame Relay
- Asynchronous Transfer Mode (ATM)
- X.25

### LAN topologies

1. Star Topology
1. Extended Star Topology - 2 star topologies connected
1. Bus Topology
1. Ring Topology

### Duplex communication

1. Half-duplex Communication

- can send and receive but not simultaneously

1. Full-duplex Communication

- can send and receive simultaneously

## The Frame

It contains 3 basic parts:

- header
- data
- trailer

The structure of the frame and the fields contained in the header and trailer vary according to the protocol.

### Frame Fields

Frame fields include the following:

1. **Frame start and stop indicator flags** - used to identify the beginning and ending of the frame
1. **Addressing** - source and destination NICs
1. **Type** - identifies the layer 3 protocol in the data field
1. **Control** - special flow control services such as quality of service (QoS) which gives priority to certain messages(e.g. VoIP)
1. **Data** - frame payload; usually a packet
1. **Error Detection** - included after data to form the trailer
