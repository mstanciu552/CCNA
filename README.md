# CCNA

## Notes from question on simulation 1

Advantages of IPsec:
- Authentication
- Antireplay
- Privacy

Viruses are self-injected into other software.

Solicited-node multicast address: FF02::1:FF71:{end of ipv6 - 4 hex digits}.

Standard ACLs should be configured closest to destination, while extended ACLs should be configured closest to source.
Standard ACLs filter only on source IP which makes it drop packets on simple source IP match.
Extended ACLs filter using multiple parameters, making it more flexible, thus being able to filter only specific traffic while allowing other traffic from the same source IP.

When sending a relayed DHCP message, a router will use the source IP address of the interface on the side with the network of the device that sent the message.

By default, on Cisco IOS, MD5 is used for hashing.

SNMPv3 NMS uses username and password over groups(v1 and v2).

In split-MAC architectures, 

## VPN Lab

Lab commands:

```
crypto isakmp policy 1
  encryption aes
  hash sha
  authentication pre-share
  group 5
  lifetime 3600

crypto isakmp key <WORD1> address <other_IP>

ip access-list extended <WORD2>
permit ip <SOURCE> <WILDCARD> <DESTINATION> <WILDCARD>

crypto ipsec transform-set <WORD3> esp-aes esp-sha

crypto map <WORD4> 10 ipsec-isakmp
  set peer <other_IP>
    set transform-set <WORD3>
    match address <WORD2>

interface <NR>
  crypto map <WORD4>
```
Show commands
```
show crypto isakmp sa
show crypto ipsec sa
```

## QoS Lab

```
class-map <WORD-CM>
  match <argument>
  description <OPTIONAL>

policy-map <WORD-P>
  class <WORD-CM>
    set <argument>
    bandwidth <VAL>
    
interface <NR>
  service-policy {input|output} <WORD-P>
```
