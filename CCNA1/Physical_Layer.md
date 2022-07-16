# Physical Layer - OSI Layer 1

## Functional Areas handled by the Physical Layer

1. Physical Components

- electronic components such as NICs
- cables
- ports and interfaces of routers

1. Encoding

- translating digital information into bits(0 and 1) for the machine to understand

1. Signaling

- the way bits are represented as electrical or optical pulses

### Manchester Encoding

This is an example of encoding used for 10 Mbps Ethernet.

**NB**: A 0 is represented as a _low to high voltage transition_.
**NB**: A 1 is represented as a _high to low voltage transition_.

The transition occurs at the middle of each bit period.

## Organizations that govern the Standards of the hardware for the Physical Layer

- International Organization for Standardization **(ISO)**
- Telecommunications Industry Association/Electronic Industries Association **(TIA/EIA)**
- International Telecommunication Union **(ITU)**
- American National Standards Institute **(ANSI)**
- Institute of Electrical and Electronics Engineers **(IEEE)**
- National telecommunications regulatory authorities including the Federal Communication Commission **(FCC)** in the USA and the European Telecommunications Standards Institute **(ETSI)**

## Bandwidth

- **Def**: This represents the amount of information that can be transmitted over a medium in a fixed amount of time.
- It's usually measured in _kilobits per second **(kbps)**_, _megabits per second**(Mbps)**_ or _gigabits per second**(Gbps)**_
- Properties that determine the amount of information that can be transmitted over a medium(bandwidth):

1. the properties of the physical media(material)
1. the technology chosen for signaling and detecting network signals

| Unit of Bandwidth   | Abbreviation | Equivalence |
| ------------------- | ------------ | ----------- |
| Bits per second     | bps          | 1 bps       |
| Kilobits per second | Kbps         | 10^3 bps    |
| megabits per second | Mbps         | 10^6 bps    |
| gigabits per second | Gbps         | 10^9 bps    |
| terabits per second | Tbps         | 10^12 bps   |

### Terms used to measure bandwidth quality

1. Latency

- the amount of time, including delays, necessary for data to travel from one given point to another

1. Throughput

- measure of the transfer of bits across the media over a given period of time
- factors that influence throughput
  - the amount of trafic
  - the type of trafic
  - the latency created by the number of devices between source and destination

1. Goodput

- the measure of usable data transfered in a specified amount of time
- it is throughput minus traffic overhead for establishing sessions
- goodput is always lower than throughput, which is generally lower than the bandwidth

## Copper Cabling

- the most common transfer medium for electrical signals used in networks today

### Types of copper cabling

1. Unshielded Twisted-Pair Cable **(UTP)**

- the most common networking media
- terminated with RJ-45 connectors
- used for connecting network devices with hosts
- in LANs, UTP cable consists of four pairs of color-coded wires that have been twisted together and then encased in a flexible plastic sheath that protects from minor physical damage
- twisting prevents interference from other cables
- the outer jacket protects from physical damage
- color-coded plastic insulation helps wth identification and electrical insulation

1. Shielded Twisted-Pair Cable **(STP)**

- better noise protection than UTP
- more expensive and hard to install than UTP
- shielding prevents **EFI and RFI**
- twisting prevents **crosstalk**

1. Coaxial Cable

- consists of:
  - a copper conductor for transmitting data
  - a layer of flexible plastic insulation
  - woven copper braid or metalic foil
  - cable jacket to prevent physical damage
- has been mostly replaced by UTP, but is used in:
  - **wireless installations** - attach antennas to wireless devices
  - **cable internet installations** - the wiring inside ISP customers is still coaxial cables

### Pros

- cheap
- easy to install
- low resistance to electrical current

### Cons

- limited by distance
- signal interference

The signal detereorating due to distance is called **signal attenuation**.

### Interference for copper cabling can come from two sources

1. Electromagnetic interference(EMI) or radio frequency interference(RFI)

- potential sources include radio waves and electromagnetic devices, such as fluorescent lights or electric motors
- to counter the negative effects of EMI and RFI, some types of copper cables are wrapped in metallic shielding and require proper grounding connections.

1. Crosstalk

- a disturbance caused by the electric or magnetic fields of a signal on one wire to the signal in an adjacent wire
- to counter the negative effects of crosstalk, some types of copper cables have opposing circuit wire pairs twisted together, which effectively cancels the crosstalk.

### Ways to limit interference

1. selecting the right kind of wire for the given network environment
1. designing the network to avoid known sources of interference
1. using cabling techniques that include proper handling and termination of the cables

## Fiber-optic cables

- more expensive
- faster than copper cabling

### Types of fiber-optics

1. single-mode fiber

- longer distance (100 km)

1. multimode fiber

- shorter distance (550 m)
- uses LEDs

### Usage

1. Enterprise Networks
1. Fiber-to-the-Home(FTTH)
1. Long Haul Networks
1. Submarine cable networks

### Connectors

1. Straight-Tip**(ST)** Connector
1. Subscriber-Connector**(SC)** Connector
1. Lucent-Connector**(LC)** Simplex Connector
1. Duplex Multimode LC Connectors

### Fiber Patch Cords

1. SC-SC Multimode Patch Cord(Orange)
1. LC-LC Single-mode Patch Cord(Yellow)
1. ST-LC Multimode Patch Cord(Orange)
1. SC-ST Single-Mode Patch Cord(Yellow)

## Wireless Media

### Limitations

- coverage area
- interference
- security
- shared medium - many users accesing the network results in reduced bandwidth for all users

### Types of wireless media

1. Wi-Fi (IEEE 802.11)
1. Bluetooth (IEEE 802.15)
1. WiMAX (IEEE 802:16) - point to multipoint
1. Zigbee (IEEE 802.15.4) - low-power communications; mostly IoT(Internet of Things)
