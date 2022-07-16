# Ethernet Switching

Ethernet operates in the data link layer and the physical layer. Defined by IEEE 802.2 and 802.3.

Ethernet supports bandwidths of the folowing:

- 10 Mbps
- 100 Mbps
- 1000 Mbps (1 Gbps)
- 10.000 Mbps (10 Gbps)
- 40.000 Mbps (40 Gbps)
- 100.000 Mbps (100 Gbps)

## Ethernet Frame

**Reminder**

- Data Link sub-layers
  - LLC Sublayer
    - IEEE 802.2 communicates between network software and the physical layer
  - MAC Sublayer
    - responsible for data encapsulation and media access control
    - integrated with various physical layer technologies
    - provides data link addressing

### Ethernet Encapsulation

The MAC sublayer is responsible for data encapsulation

IEEE 802.3 data encapsulation includes the following:

- Ethernet frame
  - internal structure of the **ethernet frame**
- Ethernet addressing
  - destination and source NICs
- Ethernet Error detection
  - frame check sequence **(FCS)** trailer

Ethernet over a half-duplex medium uses a **contention-based access method** => **Carrier sense multiple access/collision detection _(CSMA/CD)_**

This _CSMA/CD_ allows more than one device to share the same half-duplex medium. It detects a collision when more than one device attempts to transmit simultaneously.

**NB**: It also provides a back-off algorithm for retransmission.

**NB**: Ethernet LANs today use _full-duplex mediums_, so _CSMA/CD_ is not needed.

### Ethernet Frame Fields

- Minimum Ethernet frame size => 64 bytes
- Maximum Ethernet frame size => 1518 bytes

**NB**: The preamble field is not included when describing frame size.

Limits exceding frame size:

- less than 64 bytes (minimum)
  - considered a _collision fragment_ or _runt frame_
  - automatically discarded
- more than 1500 bytes (maximum)
  - considered _jumbo_ or _baby giant frames_
  - supported by most **Fast Ethernet** and **Gigabit Ethernet** switches and NICs

**NB**: If the size exceeds the limit, the frame is discarded. Dropped frames are, likely, the result of collision or unwanted signals.

#### Frame Fields

| Field            | Size          |
| ---------------- | ------------- |
| Preamble and SFD | 8 bytes       |
| Destination MAC  | 6 bytes       |
| Source MAC       | 6 bytes       |
| Type/Length      | 2 bytes       |
| Data             | 46-1500 bytes |
| FCS              | 4 bytes       |

1. Preamble and Start Frame Delimiter

- preamble (7 bytes)
- start of frame (1 bytes)
- used for syncronization between sending and receiving devices
- tells a device to get ready to receive

2. Destination MAC

- the address in the frame si compared to the MAC address in the device
- if matching MAC the frame is accepted

3. Source MAC

- tells where the frame is heading

4. Type/Length

- identifies the upper layer protocol
- 0x800 for IPv4
- 0x86DD for IPv6

5. Data

- contains encapsulated data from a higher layer
- usually a Layer 3 PDU (a.k.a. _IPv4 Packet_)
- if the packet is too small and the frame does not exceed 64 bytes because of it additional padding is added

6. Frame Check Sequence

- uses _cyclic redundancy check (CRC)_
- both sender and receiver calculate a circuit
  - if they match no error occured
  - if they do not match the data has changed and the frame is dropped

## Ethernet MAC Address

MAC Address consists of **12 hex values**.

All MAC Addresses must be unique for every Ethernet Device or Interface. To ensure this all vendors must register with the IEEE to obtain a unique 6 hexadecimal value(OUI - Organizationally Unique Identifier) and then add 6 unique hexadecimal values themselves.

### Frame processing

**NB**: It is possible, with modern PC operating systems and NICs to change the MAC address in software. As such filtering based on MAC is less secure.

### Broadcast MAC Address

- it has a destination MAC of FF-FF-FF-FF-FF-FF
- it is flooded out all Ethernet switch ports except incoming port
- it is **NOT** forwarded by a router
- an example is **ARP** (Address Resolution Protocol)

### Multicast MAC Address

- there is a destination MAC of **01-00-5E** when the encapsulated data is **IPv4** protocol and **33-33** when the data is **IPv6** protocol
- there are other reserved multicast MAC addresses for when encapsulated data is not IP, such as **Spanning Tree Protocol(STP)** and **Link Layer Discovery Protocol(LLDP)**
- flooded out all switch ports except incoming, unless it is configured for multicast snooping
- not forwarded by router, unless configured for route multicast packets
- source will always be **unicast**

## The MAC Address Table

### Switch Fundamentals

- only aware of Layer 2 MAC Addresses, not of the data encapsulated in the frame
- MAC address table is also known as **CAM** (content adressable memory) table
- dynamically builds the CAM by examining source MAC of frames received on ports
- forwards by looking for a match between the destination MAC and an entry in the CAM

### Learning and Forwarding for Switches

1. Learning

- examine source MAC and port where frame came from; if it does not exist it is added to the CAM
- if it exists the refresh timer is updated for that entry

**NB**: most switches keep an entry in the CAM for 5 minutes

2. Forwarding

- switch checks for entry with that destination MAC in CAM table
  - if match found then forward unicast to specified port
  - if match not found then forward on all ports **(unknown unicast)**

## Switch Speeds and Forwarding Methods

### Forwarding Methods

1. Store-and-forward switching

- waits for frame and checks CRC
- required for quality of service (QoS)

2. Cut-through switching

- sends it out before receiving it fully
- must wait for at least destination MAC
- variants of this method
  - fast-forward switching
    - lowest level of latency
    - typical variant
    - measure of latency is from first bit received to first bit transmitted
  - fragment-free switching
    - stores first 64 bytes
    - compromise between store-and-forward and cut-through
- some switches are configured to perform cut-through until a user-defined error threshold is reached and then switch to store-and-forward

### Memory buffering

- switch stores frame until it can be transmitted if congestion occurs
- methods
  - port-based memory
    - stored in queues linked to specific outgoing ports
    - it is possible for a single frame to block trafic due to busy destination port
    - delay occurs even if other frames could be transmitted
  - shared memory
    - amount of memory required by port is dynamically allocated
    - frames in buffer are dynamically linked to destination port, allowing for a packet to be received on one port and transmitted on another port, without moving it to a different queue
    - store larger frames with fewer dropped frames

### Duplex and Speed settings

**Reminder**

1. full-duplex

- simultaneously send and receive

2. half-duplex

- only one end of the connection can send at a time

Autonegotiation is an optional function found on most Ethernet switches and NICs. It enables two devices to automatically negotiate the best speed and duplex capabilities. Full-duplex is chosen if both devices have the capability along with their highest common bandwidth.

**NB**: Most Cisco switches and Ethernet NICs default to autonegotiation for speed and duplex. Gigabit Ethernet ports only operate in full-duplex.

Duplex mismatch occurs when one or both ports on a link are reset, and the autonegotiation process does not result in both link partners having the same configuration. It also can occur when users reconfigure one side of a link and forget to reconfigure the other. Both sides of a link should have autonegotiation on, or both sides should have it off. Best practice is to configure both Ethernet switch ports as full-duplex.

### Auto-MDIX

- When enabled, the switch automatically detects the type of cable attached to the port and configures the interfaces accordingly.
- you can use either a crossover or a straight-through cable for connections to a copper 10/100/1000 port on the switch, regardless of the type of device on the other end of the connection.
