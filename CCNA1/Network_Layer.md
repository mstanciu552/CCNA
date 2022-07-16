# Network Layer

There are 2 major protocols in this Layer:

1. Internet Protocol version 4 => IPv4
1. Internet Protocol version 6 => IPv6

## Network Layer Characteristics

### Characteristics of IP

- conectionless
  - no connection with the destination before sending data packets
  - conceptually similar to sending a letter without notifing the receiver
- best effort
  - packet delivery is not guaranteed, which makes it unreliable
  - reduces overhead
  - the source doesn't know if the packet was received
- media independent
  - operation is independent of the medium (copper, wireless, etc.)
  - the maximum size of the PDU that the medium can handle - maximum transmission unit (MTU) is decided by the _data link layer_ (2) and the _network layer_ (4)
  - in some cases a router must split the PDU so that it matches the required MTU - this action is called **fragmenting**
  - IPv6 packets cannot be _fragmented_ by a router

### Basic Operations of Network Layer

1. Addressing end devices

- end devices must be configured with a unique IP address for identification on the network

2. Encapsulation

- encapsulates the **protocol data unit** (PDU) from the transport layer into a **packet**
- adds IP header information
  - source IP
  - destination IP

3. Routing

- a packet needs to reach a _router_ in order for it to exit the network
- a router selects the best path and directs the packets towards the destination host
- each router a packet croses to reach its destination is called a hop

4. De-encapsulation

- a host checks the IP header and looks for matching destination IP address with its own IP address
- if the destination matches the IP address, then the packet is passed on as a Layer 4 PDU, having its IP header removed

### IP Encapsulation

An IP Header is added onto the encapsulated data from the Transport Layer(4) (a.k.a. **segment**).

## IPv4 Packet

### Major issues of IPv4

- IPv4 address depletion
  - only 4 billion IPv4 addresses are available in 32 bits
- lack of end-to-end connectivity
  - Network Address Translation **(NAT)** shares a single _public IP address_ for multiple devices
  - can be problematic for technologies that require end-to-end connectivity
- increased network complexity
  - because of the use of NAT adds complexity in networks, creating latency and making troubleshooting more difficult
  - NAT was only meant as a transitional tool for IPv6

### IPv4 Packet Header Fields

#### Version

- 4-bit binary value set to **0100** that identifies this as an IPv4 packet

#### Differentiated Services or DiffServ(DS)

- formerly the _type of service_ (ToS)
- 8-bit field used to determine the priority of each packet
- the 6 most significant bits of the DiffServ are the _differentiated services code point_ (DSCP) bits
- the last 2 bits are the _explicit congestion notification_ (ECN)

#### Header Checksum

- used to detect corruption in the IPv4

#### Time to Live (TTL)

- 8-bit binary used to limit the lifetime of a packet
- the source sets the TTL and for each hop through a router it decrements by 1
- if the TTL is zero the device sends an **ICMP Time Exceeded** message to the source IP address
- because a router decrements the TTL, it must also recalculate the Header Checksum

#### Protocol

- 8-bit binary value that identifies the upper-layer protocol
- common values
  - ICMP - 1
  - TCP - 6
  - UDP - 17

#### Source IPv4 Address

- 32-bit value that represents the source IP of the packet
- **always** unicast

#### Destination IPv4 Address

- 32-bit value that represents the destination IP of the packet
- unicast, multicast or broadcast address

**NB**:

- the Internet Header Length (IHL), Total Length, and Header Checksum fields are used to identify and validate the packet.
- other fields are used to reorder a fragmented packet. Specifically, the IPv4 packet uses Identification, Flags, and Fragment Offset fields to keep track of the fragments.
- a router may have to fragment an IPv4 packet when forwarding it from one medium to another with a smaller MTU.

## IPv6 Packet

### Improvements from IPv4

1. Increased address space

- 128-bit hierarchical addresses

2. Improved packet handling

- fewer header fields

3. Eliminates the need for NAT

- NAT not needed as there are enough addresses

### IPv6 Header Fields

#### Version

- 4-bit value set to **0110** that identifies the packet as IPv6

#### Trafic Class

- 8-bit field
- equivalent to DiffServ

#### Flow Label

- 20-bit field
- packets with same _flow label_ receive the same type of handling from routers

#### Payload Length

- 16-bit field
- length of data portion or **payload** of the IPv6 packet
- does not include the length of the IPv6 header

#### Next Header

- 8-bit field
- equivalent to **Protocol** field in IPv4

#### Hop Limit

- 8-bit field that replaces the TTL field

#### Source IPv6 Address

- 128-bit field identifing the source host

#### Destination IPv6 Address

- 128-bit field identifing the destination host

## IP Router Routing Table

#### Stores 3 types of route entries

- directly-connected networks
  - these routes entries are active router interfaces
  - routers add this when an interface is configured with an IP address and is activated
- remote networks
  - routers learn about remote networks either by being explicitly configured by an administrator or by exchanging route information using a dynamic routing protocol.
- default route
  - gateway of last resort
  - used when there is no better match

#### A router can learn about remote networks in one of two ways

- Manually
  - usually entered using static routes
- Dynamically
  - automatically learned using a dynamic routing protocol

### Static Routing

- the static route includes the remote network address and the IP address of the next hop router.

- if there is a change in the network topology, the static route is not automatically updated and must be manually reconfigured

#### Characteristics

- must be configured manually
- needs reconfiguring if the topology changes
- appropriate for small networks with no redundant links
- commonly used with a dynamic routing protocol for configuring a default route

### Dynamic Routing

- a dynamic routing protocol allows the routers to automatically learn about remote networks, including a default route, from other routers
- routers that use dynamic routing protocols automatically share routing information with other routers and compensate for any topology changes without involving the network administrator.
- if there is a change in the network topology, routers share this information using the dynamic routing protocol and automatically update their routing tables.

#### Protocols

- Open Shortest Path First => **OSPF**
- Enhanced Interior Gateway Routing Protocol => **EIGRP**

#### Will automatically do as follows

- Discover remote networks
- Maintain up-to-date routing information
- Choose the best path to destination networks
- Attempt to find a new best path if the current path is no longer available

**NB**: It is common for some routers to use a combination of both static routes and a dynamic routing protocol.
