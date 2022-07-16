# CURS 3 - OSI & TCP/IP

## Teorie

**Protocol** = set de reguli ce definesc tranmiterea informatiilor = cum e transmis un mesaj pe o retea

- sunt grupate pe **layers**

**Pachet** = mesaj transmis printr-o retea

- destinatie
- sursa
- encoding

### Metode de comunicare pe o retea

1. unicast = one-to-one
1. multicast = one-to-many (nu toti)
1. broadcast = one-to-all

## TCP/IP Model exemple protocoale - 4 Layers

1. 7 - Application Layer - interfata cu utilizatorul, codeaza informatia, asigura schimbul de date

- POP(PostOffice Protocol) - descarca mail-uri si le sterge de pe server
- IMAP(Instant Message Access Protocol) - accesibile de peste tot; trebuie sterse manual
- SMTP(Simple Message Transfer Protocol)
- TFTP(Trivial File Transfer Protocol)

2. 4 - Transport Layer - transfer de date, reasamblarea lor

- UDP - informatie inexacta, dar mai rapida
- TCP - informatie precisa, dar mai inceata

3. 3 - Internet Layer - determina caile de transfer a informatiei in retea

- IP (v4 - 32 bit)
- NAT - Network Address Translation
- ICMP - ping
- OSPF
- EIGRP

4. 2 - Network Access Layer - translatarea datelor intre software si hardware

- ARP
- PPP
- Ethernet
- Interface Driver

## OSI Model - 7 Layers

1. Application Layer - interfata cu user - **data**
1. Presentation Layer - codeaza + compreseaza informatia - **data**
1. Session Layer - manageriaza schimbul de date si asigura conexiunea - **data**
1. Transport Layer - transportarea efectiva pe retea - **segment**
1. Network Layer - ofera servicii de transmitere a datelor prin retea (adrese IP) - **pachet**
1. Data Link Layer - transfer de date din binar la nivelul fizic (fibra optica) - **frame**
1. Physical Layer - mediu de transfer (cablu retea, wireless, fibra optica) - **bit**
