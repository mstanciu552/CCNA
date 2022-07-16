# Address Resolution

## Destination on same network

There are 2 primary addresses assigned to a device on an Ethernet LAN:

- Physical Address (the **MAC** address)
  - used for NIC to NIC communications on the same network
- Logical Address (the **IP** address)
  - used to send the packet from source to destination
  - could be on local or remote network

When the destination IP is on a different network, the MAC address will be that of the router

## ARP - Address Resolution Protocol

An ARP request is sent when a device needs to determine the MAC address of a device associated with an IPv4 address and it does not have an entry in the **ARP cache**.

- ARP messages are encapsulated directly within an Ethernet frame.
- there is no IPv4 header.

Provides 2 basic functions:

- resolving IPv4 addresses to MAC addresses
- maintaining a table of IPv4 to MAC address mappings

The sending device will search its ARP table for a destination IPv4 address and a corresponding MAC address.

- if the packet’s destination IPv4 address is on the same network as the source IPv4 address, the device will search the _ARP table_ for the destination IPv4 address.
- if the destination IPv4 address is on a different network than the source IPv4 address, the device will search the _ARP table_ for the IPv4 address of the **default gateway**.

The ARP request is encapsulated in a Layer 2 Ethernet Frame containing the following header information:

- destination MAC address
  - FF-FF-FF-FF-FF-FF
  - requires devices to process it as an ARP request
- source MAC address
  - MAC of the sender
- type
  - **0x806** - indicates this is an ARP request

**NB**: A router will not forward broadcasts out other interfaces.

### ARP Reply

Only the device with the target IPv4 address associated with the ARP request will respond with an ARP reply.
The ARP reply is encapsulated in an Ethernet frame using the following header information:

- Destination MAC address
  – This is the MAC address of the sender of the ARP request.
- Source MAC address
  – This is the MAC address of the sender of the ARP reply.
- Type
  - ARP messages have a type field of 0x806. This informs the receiving NIC that the data portion of the frame needs to be passed to the ARP process.

**NB**: IPv6 uses a similar process to ARP for IPv4, known as ICMPv6 Neighbor Discovery (ND). IPv6 uses neighbor solicitation and neighbor advertisement messages, similar to IPv4 ARP requests and ARP replies.

#### IMPORTANT

On a CISCO router the command to see the ARP table is **show ip arp**
On a Windows PC the command is **arp -a**

## IPv6 Neighboard Discovery - ND

IPv6 Neighbor Discovery protocol is sometimes referred to as ND or NDP. In this course, we will refer to it as ND.
ND provides address resolution, router discovery, and redirection services for IPv6 using ICMPv6. ICMPv6 ND uses five ICMPv6 messages to perform these services:

- Neighbor Solicitation messages
- Neighbor Advertisement messages
- Router Solicitation messages
- Router Advertisement messages
- Redirect Message
