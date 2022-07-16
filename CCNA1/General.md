# General Information about Networking

**Clients** and **servers** usually run on separate hosts. When a single hosts acts as **both** it's called a **Peer-to-peer** network.

## End devices

The network devices that people are most familiar with are end devices. To distinguish one **end device** from another, each end device on a network has an **address**. When an end device initiates communication, it uses the **address of the destination** end device to specify where to deliver the message.

### Examples

- computers
- laptops
- phones
- servers

## Intermediary devices

Intermediary devices connect the individual end devices to the network. They can connect multiple individual networks to form an internetwork. These intermediary devices provide connectivity and ensure that data flows across the network.

### Examples

- routers
- switches

### Functions

- regenerate and retransmit communication signals
- maintain information about the pathways in the network
- notify other devices of errors and communication failures
- direct data along alternate pathways when there are errors
- classify and direct messages according to priority
- permit or deny data flow based on security settings

## Network media

Modern networks primarily use three types of media to interconnect devices, as shown in the figure:

- Metal wires within cables
  - Data is encoded into electrical impulses.
- Glass or plastic fibers within cables (fiber-optic cable)
  - Data is encoded into pulses of light.
- Wireless transmission
  - Data is encoded via modulation of specific frequencies of electromagnetic waves.

## Specialized terminology

- Network Interface Card (NIC)
  - A NIC physically connects the end device to the network.
- Physical Port
  - A connector or outlet on a networking device where the media connects to an end device or another networking device.
- Interface
  - Specialized ports on a networking device that connect to individual networks. Because routers connect networks, the ports on a router are referred to as network interfaces.

## Topologies

### Physical Topologies

Physical topology diagrams illustrate the physical location of intermediary devices and cable installation. You can see that the rooms in which these devices are located are labeled in this physical topology.

### Logical Topologies

Physical topology diagrams illustrate the physical location of intermediary devices and cable installation. You can see that the rooms in which these devices are located are labeled in this physical topology.

## Network Sizes

1. Small Home Network
1. Small Office and Home Network
1. Medim to Large Network
1. World Wide Network

## LAN

A LAN is a network infrastructure that spans a small geographical area. LANs have specific characteristics:

- LANs interconnect end devices in a limited area such as a home, school, office building, or campus.
- A LAN is usually administered by a single organization or individual. Administrative control is enforced at the network level and governs the security and access control policies.
- LANs provide high-speed bandwidth to internal end devices and intermediary devices, as shown in the figure.

## WAN

The figure shows a WAN which interconnects two LANs. A WAN is a network infrastructure that spans a wide geographical area. WANs are typically managed by service providers (SPs) or Internet Service Providers (ISPs).

WANs have specific characteristics:

- WANs interconnect LANs over wide geographical areas such as between cities, states, provinces, countries, or continents.
- WANs are usually administered by multiple service providers.
- WANs typically provide slower speed links between LANs.

## Extranet

- only accessible to suppliers, customers and collaborators

## Intranet

- only accessible to the company

## Common types of connections for SOHO users

- Cable
  - Typically offered by cable television service providers, the internet data signal transmits on the same cable that delivers cable television. It provides a high bandwidth, high availability, and an always-on connection to the internet.
- DSL
  - Digital Subscriber Lines also provide high bandwidth, high availability, and an always-on connection to the internet. DSL runs over a telephone line. In general, small office and home office users connect using Asymmetrical DSL (ADSL), which means that the download speed is faster than the upload speed.
- Cellular
  - Cellular internet access uses a cell phone network to connect. Wherever you can get a cellular signal, you can get cellular internet access. Performance is limited by the capabilities of the phone and the cell tower to which it is connected.
- Satellite
  - The availability of satellite internet access is a benefit in those areas that would otherwise have no internet connectivity at all. Satellite dishes require a clear line of sight to the satellite.
- Dial-up Telephone
  - An inexpensive option that uses any phone line and a modem. The low bandwidth provided by a dial-up modem connection is not sufficient for large data transfer, although it is useful for mobile access while traveling.

## Common types of connections for business users

- Dedicated Leased Line
  - Leased lines are reserved circuits within the service provider’s network that connect geographically separated offices for private voice and/or data networking. The circuits are rented at a monthly or yearly rate.
- Metro Ethernet
  - This is sometimes known as Ethernet WAN. In this module, we will refer to it as Metro Ethernet. Metro ethernets extend LAN access technology into the WAN. Ethernet is a LAN technology you will learn about in a later module.
- Business DSL
  - Business DSL is available in various formats. A popular choice is Symmetric Digital Subscriber Line (SDSL) which is similar to the consumer version of DSL but provides uploads and downloads at the same high speeds.
- Satellite
  - Satellite service can provide a connection when a wired solution is not available.

As networks evolve, we have learned that there are four basic characteristics that network architects must address to meet user expectations:

- Fault Tolerance
- Scalability
- Quality of Service (QoS)
- Security

## Fault Tolerance

- A fault tolerant network is one that limits the number of affected devices during a failure.
- It is built to allow quick recovery when such a failure occurs.
- These networks depend on multiple paths between the source and destination of a message.
- If one path fails, the messages are instantly sent over a different link. Having multiple paths to a destination is known as redundancy.

## Scalability

- A scalable network expands quickly to support new users and applications.
- It does this without degrading the performance of services that are being accessed by existing users.
- These networks are scalable because the designers follow accepted standards and protocols.
- This lets software and hardware vendors focus on improving products and services without having to design a new set of rules for operating within the network.

## Quality of Service (QoS)

- Quality of Service (QoS) is an increasing requirement of networks today.
- New applications available to users over networks, such as voice and live video transmissions, create higher expectations for the quality of the delivered services.
- Have you ever tried to watch a video with constant breaks and pauses? As data, voice, and video content continue to converge onto the same network, QoS becomes a primary mechanism for managing congestion and ensuring reliable delivery of content to all users.

## Security

- The network infrastructure, services, and the data contained on network-attached devices are crucial personal and business assets.
- Network administrators must address two types of network security concerns: network infrastructure security and information security.
- Securing the network infrastructure includes physically securing devices that provide network connectivity and preventing unauthorized access to the management software that resides on them, as shown in the figure.

Network administrators must also protect the information contained within the packets being transmitted over the network, and the information stored on network attached devices. In order to achieve the goals of network security, there are three primary requirements.

- Confidentiality
  - Data confidentiality means that only the intended and authorized recipients can access and read data.
- Integrity
  - Data integrity assures users that the information has not been altered in transmission, from origin to destination.
- Availability
  - Data availability assures users of timely and reliable access to data services for authorized users.

## Network trends

As new technologies and end-user devices come to market, businesses and consumers must continue to adjust to this ever-changing environment. There are several networking trends that affect organizations and consumers:

- Bring Your Own Device (BYOD)
- Online collaboration
- Video communications
- Cloud Computing

### Bring Your Own Device (BYOD)

- The concept of any device, for any content, in any manner, is a major global trend that requires significant changes to the way we use devices and safely connect them to networks. This is called Bring Your Own Device (BYOD).

- BYOD enables end users the freedom to use personal tools to access information and communicate across a business or campus network. With the growth of consumer devices, and the related drop in cost, employees and students may have advanced computing and networking devices for personal use. These include laptops, notebooks, tablets, smart phones, and e-readers. These may be purchased by the company or school, purchased by the individual, or both.

- BYOD means any device, with any ownership, used anywhere.

### Online collaboration

- Individuals want to connect to the network, not only for access to data applications, but also to collaborate with one another.
- Collaboration is defined as “the act of working with another or others on a joint project.”
- Collaboration tools, like **Cisco WebEx**, shown in the figure, give employees, students, teachers, customers, and partners a way to instantly connect, interact, and achieve their objectives.

### Video communications

- Another facet of networking that is critical to the communication and collaboration effort is video.
- Video is used for communications, collaboration, and entertainment.
- Video calls are made to and from anyone with an internet connection, regardless of where they are located.
- Video conferencing is a powerful tool for communicating with others, both locally and globally.
- Video is becoming a critical requirement for effective collaboration as organizations extend across geographic and cultural boundaries.

### Cloud Computing

- Cloud computing is one of the ways that we access and store data.
- Cloud computing allows us to store personal files, even backup an entire drive on servers over the internet. Applications such as word processing and photo editing can be accessed using the cloud.
- For businesses, Cloud computing extends the capabilities of IT without requiring investment in new infrastructure, training new personnel, or licensing new software.
- These services are available on-demand and delivered economically to any device that is anywhere in the world without compromising security or function.

There are four primary types of clouds:

- Public clouds
- Private clouds
- Hybrid clouds
- Community clouds

### Powerline Networking

Using a standard powerline adapter, devices can connect to the LAN wherever there is an electrical outlet. No data cables need to be installed, and there is little to no additional electricity used. Using the same wiring that delivers electricity, powerline networking sends information by sending data on certain frequencies.

## Messaging Time

- Flow Control
  - This is the process of managing the rate of data transmission. Flow control defines how much information can be sent and the speed at which it can be delivered. For example, if one person speaks too quickly, it may be difficult for the receiver to hear and understand the message. In network communication, there are network protocols used by the source and destination devices to negotiate and manage the flow of information.
- Response Timeout
  - If a person asks a question and does not hear a response within an acceptable amount of time, the person assumes that no answer is coming and reacts accordingly. The person may repeat the question or instead, may go on with the conversation. Hosts on the network use network protocols that specify how long to wait for responses and what action to take if a response timeout occurs.
- Access method
  - This determines when someone can send a message. Click Play in the figure to see an animation of two people talking at the same time, then a "collision of information" occurs, and it is necessary for the two to back off and start again. Likewise, when a device wants to transmit on a wireless LAN, it is necessary for the WLAN network interface card (NIC) to determine whether the wireless medium is available.

## Encoding

One of the first steps to sending a message is encoding. Encoding is the process of converting information into another acceptable form, for transmission. Decoding reverses this process to interpret the information.

## Formatting and Encapsulation

When a message is sent from source to destination, it must use a specific format or structure. Message formats depend on the type of message and the channel that is used to deliver the message.
