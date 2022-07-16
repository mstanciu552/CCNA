# IPv4 Addresses

## Types of addresses

### Unicast

- sends a packet to only **one** receiver
- source address can only be **unicast**

### Broadcast

- all **ones (1)** in the host part or all 32 bits are **1**
- IPv4 uses broadcast addresses, while IPv6 doesn't uses broadcast
- by default routeres do not forward broadcast packets
- directed broadcast is the IPv4 address on the network where the host bits are all 1

### Multicast

- multicast range => **224.0.0.0 - 239.255.255.255**

## Public and Private addresses

### Private address block range

| Network and Prefix | Range                         |
| ------------------ | ----------------------------- |
| 10.0.0.0/8         | 10.0.0.0 - 10.255.255.255     |
| 172.16.0.0/12      | 172.16.0.0 - 172.31.255.255   |
| 192.168.0.0/16     | 192.168.0.0 - 192.168.255.255 |

Within a network, there are different types of devices that require addresses:

- End user clients
  - Most networks allocate IPv4 addresses to client devices dynamically, using Dynamic Host Configuration Protocol (DHCP). This reduces the burden on network support staff and virtually eliminates entry errors.
  - With DHCP, addresses are only leased for a period of time, and can be reused when the lease expires. This is an important feature for networks that support transient users and wireless devices. Changing the subnetting scheme means that the DHCP server needs to be reconfigured, and the clients must renew their IPv4 addresses.
  - IPv6 clients can obtain address information using DHCPv6 or SLAAC.
- Servers and peripherals
  - These should have a predictable static IP address. Use a consistent numbering system for these devices.
- Servers that are accessible from the internet
  - Servers that need to be publicly available on the internet must have a public IPv4 address, most often accessed using NAT. In some organizations, internal servers (not publicly available) must be made available to the remote users.
  - In most cases, these servers are assigned private addresses internally, and the user is required to create a virtual private network (VPN) connection to access the server.
  - This has the same effect as if the user is accessing the server from a host within the intranet.
- Intermediary devices
  - These devices are assigned addresses for network management, monitoring, and security.
  - Because we must know how to communicate with intermediary devices, they should have predictable, statically assigned addresses.
- Gateway
  - Routers and firewall devices have an IP address assigned to each interface which serves as the gateway for the hosts in that network.
  - Typically, the router interface uses either the lowest or highest address in the network.
