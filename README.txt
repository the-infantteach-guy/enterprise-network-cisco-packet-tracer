# Advanced Enterprise Network — Cisco Packet Tracer

![Cisco](https://img.shields.io/badge/Cisco-Networking-blue)
![Packet Tracer](https://img.shields.io/badge/Cisco%20Packet%20Tracer-Lab-red)
![Networking](https://img.shields.io/badge/Focus-Enterprise%20Networking-green)

## Overview

This project is an advanced enterprise network designed and implemented in **Cisco Packet Tracer**.

The lab was built to simulate a small-to-medium enterprise network environment with multiple network segments, redundant infrastructure, dynamic routing, DHCP services, security controls, and connectivity between departments.

The project focuses on applying practical Cisco networking concepts through configuration, verification, and troubleshooting.

---

## Network Topology

The network includes multiple layers of infrastructure, including:

* Core/distribution switches
* Access switches
* Edge router
* ISP router
* Management switch
* End-user devices
* Multiple VLANs and network segments

![Network Topology](Screenshots/Lab.png)

---

## Technologies & Networking Concepts

The project demonstrates the following:

* Cisco IOS
* Cisco Packet Tracer
* VLAN segmentation
* Inter-VLAN routing
* 802.1Q trunking
* HSRP gateway redundancy
* LACP EtherChannel
* OSPF dynamic routing
* DHCP
* DHCP relay
* Access Control Lists (ACLs)
* Port Security
* Network segmentation
* Connectivity testing
* Network troubleshooting

---

## VLAN Architecture

The network uses separate VLANs to isolate different departments and services.

| VLAN | Purpose         |
| ---: | --------------- |
|   10 | Management      |
|   30 | Sales           |
|   40 | Engineering     |
|   50 | Voice           |
|   60 | Corporate Wi-Fi |
|   70 | Guest Wi-Fi     |
|   99 | Native VLAN     |

VLAN segmentation helps separate traffic between departments and provides a foundation for applying security policies and access controls.

---

## High Availability — HSRP

**Hot Standby Router Protocol (HSRP)** was configured to provide gateway redundancy between the distribution switches.

The two distribution switches were configured with different HSRP priorities so that one device operates as the active gateway while the other remains available as the standby device.

The configuration was verified using:

```text
show standby
```

![HSRP Status](Screenshots/HSRP%20Status.png)

---

## EtherChannel — LACP

**LACP EtherChannel** was configured to bundle multiple physical links into logical port channels.

This provides:

* Link redundancy
* Increased available bandwidth
* Improved resilience
* Simplified logical management

Verification was performed using:

```text
show etherchannel summary
```

![EtherChannel](Screenshots/EtherChannel.png)

---

## OSPF Dynamic Routing

**OSPF** was implemented for dynamic routing within the enterprise network.

The OSPF configuration allows routers and multilayer switches to dynamically exchange routing information instead of relying entirely on static routes.

OSPF neighbor relationships were verified using:

```text
show ip ospf neighbor
```

![OSPF Neighbors](Screenshots/OSPF%20Neighbors.png)

---

## VLAN & Trunk Configuration

VLANs were created and assigned to appropriate switch ports.

Trunk links were configured between network devices to carry traffic from multiple VLANs.

Verification commands included:

```text
show vlan brief
show interfaces trunk
```

![VLAN Configuration](Screenshots/Vlan%20.png)

![Trunk Configuration](Screenshots/Trunk.png)

---

## DHCP

DHCP was configured to provide dynamic IP addressing to network clients.

The project also demonstrates DHCP configuration and relay functionality across the network.

DHCP operation was verified during connectivity testing.

![DHCP Configuration](Screenshots/DHCP%20Configuration.png)

---

## Network Security

Several basic enterprise security controls were implemented.

### Access Control Lists

ACLs were used to control traffic between network segments and restrict unauthorized communication.

![ACL Configuration](Screenshots/ACL%20Configuration.png)

### Port Security

Port Security was configured on access ports to help restrict which devices can connect to specific switch interfaces.

![Port Security](Screenshots/Port%20Security.png)

---

## Guest and Corporate Network Testing

Separate testing was performed for corporate and guest network segments.

The testing helped verify:

* IP addressing
* VLAN assignment
* Routing
* DHCP
* Connectivity
* Network segmentation

![Corporate Network Test](Screenshots/corp%20Tes.png)

![Guest Network Test](Screenshots/Guest%20Test%20.png)

---

## Connectivity Verification

Connectivity tests were performed between different network segments and devices.

Examples included:

```text
ping <destination-ip>
```

and Cisco IOS verification commands such as:

```text
show ip interface brief
show ip route
show vlan brief
show interfaces trunk
show standby
show etherchannel summary
show ip ospf neighbor
```

![Connectivity Test](Screenshots/Connectivity%20Test.png)

---

## Configuration Files

The `/Configs` directory contains the running configurations collected from the network devices.

Examples include:

* Access switches
* Distribution switches
* Core switches
* Edge router
* ISP router
* Management switch

These files allow the configuration of the lab to be reviewed without opening Packet Tracer.

---

## Project Files

```text
enterprise-network-cisco-packet-tracer/
│
├── Advanced Enterprise Lab .pkt
│
├── Configs/
│   ├── Access 1_running-config.txt
│   ├── Access 2_running-config.txt
│   ├── Access_running-config.txt
│   ├── CORE-A_running-config.txt
│   ├── CORE-B_running-config.txt
│   ├── DIST-A_running-config.txt
│   ├── DIST-B_running-config.txt
│   ├── EDGE-RTR_running-config.txt
│   ├── ISP_running-config.txt
│   └── MGMT-SW_running-config.txt
│
└── Screenshots/
    ├── ACL Configuration.png
    ├── Connectivity Test.png
    ├── DHCP Configuration.png
    ├── EtherChannel.png
    ├── HSRP Status.png
    ├── Lab.png
    ├── OSPF Neighbors.png
    ├── Port Security.png
    ├── Trunk.png
    ├── VLAN.png
    └── ...
```

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Enterprise network design
* Cisco IOS configuration
* VLAN implementation
* Network segmentation
* Inter-VLAN routing
* Redundant network gateways
* Dynamic routing with OSPF
* Link aggregation with LACP
* DHCP configuration
* 802.1Q trunking
* ACL configuration
* Switch port security
* Network troubleshooting
* Connectivity verification
* Reading and analyzing Cisco running configurations

---

## Project Outcome

The completed lab demonstrates how multiple enterprise networking technologies can be combined into a single network architecture.

Rather than configuring each technology in isolation, the project required integrating routing, switching, redundancy, addressing, security, and connectivity into one working environment.

---

## Tools

**Platform:** Cisco Packet Tracer
**Networking:** Cisco IOS
**Routing:** OSPF
**Redundancy:** HSRP
**Link Aggregation:** LACP EtherChannel
**Security:** ACLs, Port Security
**Addressing:** DHCP, IPv4
**Switching:** VLANs, 802.1Q Trunking

---

## Status

**Completed**

This project is part of my practical networking and cybersecurity portfolio and demonstrates hands-on experience designing, configuring, verifying, and troubleshooting an enterprise-style Cisco network.
