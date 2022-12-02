# CCNA

## VPN Lab

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
