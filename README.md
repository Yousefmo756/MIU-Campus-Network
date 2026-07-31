
# Enterprise Campus Network Infrastructure

## Overview

This project demonstrates the design and implementation of a secure
enterprise network topology connecting a university headquarters, a
remote branch, and a home network through the Internet using a
**Site-to-Site VPN**. The network is segmented into multiple VLANs,
utilizes dynamic routing protocols (OSPF and EIGRP), and provides
centralized network services.

## Network Architecture

### Headquarters

-   Private network: `172.20.5.0/18`
-   Server Room
-   Main Building (OSPF)
-   South Building (OSPF)
-   North Building (EIGRP)
-   Research Building (EIGRP)

### Server Room

Services: - DHCP - DNS - Web - Email - NTP - Syslog

### Buildings

  Building   Routing   VLANs
  ---------- --------- --------------------------------
  Main       OSPF      110 (61 hosts), 120 (30 hosts)
  South      OSPF      30 (12 hosts), 140 (20 hosts)
  North      EIGRP     150 (15 hosts), 160 (29 hosts)
  Research   EIGRP     170 (31 hosts), 180 (25 hosts)

All buildings use Layer-3 switching with LACP EtherChannels.

## Internet Connectivity

Headquarters connects to the ISP using **209.165.200.224/28**.

The ISP provides connectivity to: - Headquarters - Branch Office - Home
Network

## Branch Office

Connected through a **Site-to-Site IPsec VPN**.

Public Network: `64.100.1.0/27`

Internal VLANs: - VLAN 2 → `192.168.2.0/24` - VLAN 3 → `192.168.3.0/24`

Gateway: - G0/0.2 → 192.168.2.1/24 - G0/0.3 → 192.168.3.1/24

## Home Network

Public: `64.100.2.0/27`

LAN: `192.168.10.0/25`

Devices: - Laptop - Smartphone - Tablet

## Features

-   VLAN segmentation
-   Inter-VLAN routing
-   OSPF
-   EIGRP
-   DHCP
-   DNS
-   Web Server
-   Email Server
-   NTP
-   Syslog
-   EtherChannel (LACP)
-   Site-to-Site VPN
-   Internet connectivity

## Technologies

-   Cisco Packet Tracer
-   VLANs
-   OSPF
-   EIGRP
-   DHCP
-   DNS
-   SMTP/POP3
-   HTTP
-   NTP
-   Syslog
-   LACP
-   IPsec VPN

## Objectives

-   Design a scalable enterprise network.
-   Implement VLAN segmentation.
-   Provide centralized services.
-   Configure dynamic routing.
-   Secure branch connectivity using Site-to-Site VPN.
-   Demonstrate redundancy with EtherChannel.
