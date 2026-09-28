# Enterprise Cisco Network Infrastructure

A complete enterprise network built in Cisco Packet Tracer demonstrating VLAN segmentation, inter-VLAN routing, HSRP gateway redundancy, OSPF dynamic routing, LACP EtherChannel, DHCP, ACLs, and switch port security.

**Author:** Amoah Ebenezer

---

## Project Overview

This project simulates a small enterprise network using Cisco Packet Tracer. The objective was to design a secure, scalable, and fault-tolerant network that separates departments into VLANs while providing high availability and controlled communication between network segments.

The lab includes redundant distribution switches, dynamic routing, DHCP services, guest network isolation, and Layer 2 security features commonly found in enterprise environments.

---

## Network Topology

![Enterprise Topology](screenshots/01-topology.png)

The topology includes:

- Cisco 2911 Router
- Core and Distribution multilayer switches
- Access switches
- Windows clients
- Server
- Wireless LAN Controller
- Corporate and Guest network segmentation

---

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- VLANs
- Inter-VLAN Routing
- HSRP
- OSPF
- LACP EtherChannel
- DHCP
- ACLs
- Port Security
- Spanning Tree PortFast
- BPDU Guard

---

## VLAN Design

| VLAN | Name | Purpose |
|------|------|---------|
| 10 | MANAGEMENT | IT & Management |
| 30 | SALES | Sales Department |
| 40 | ENGINEERING | Engineering Department |
| 50 | SERVERS | Server Network |
| 60 | CORPORATE_WIFI | Corporate Wireless |
| 70 | GUEST_WIFI | Guest Wireless |
| 99 | MANAGEMENT_NATIVE | Native/Management VLAN |

### VLAN Verification

![VLAN Configuration](screenshots/02-vlan-configuration.png)

---

## High Availability with HSRP

Gateway redundancy was implemented between the distribution switches using Hot Standby Router Protocol (HSRP). DIST-A operates as the primary active gateway while DIST-B remains on standby for failover.

**Features implemented:**

- Virtual default gateways
- Priority-based active router election
- Preemption enabled
- Redundant gateway for multiple VLANs

![HSRP Status](screenshots/03-hsrp-status.png)

---

## Dynamic Routing (OSPF)

Open Shortest Path First (OSPF) provides dynamic Layer 3 routing across the enterprise infrastructure.

**Verification**

![OSPF Neighbors](screenshots/04-ospf-neighbors.png)

---

## EtherChannel (LACP)

Multiple physical links were bundled into a single logical Port-Channel using LACP to increase bandwidth and provide redundancy.

**Benefits**

- Link redundancy
- Higher throughput
- Simplified trunk management

![EtherChannel](screenshots/05-etherchannel.png)

---

## Trunk Configuration

802.1Q trunking carries multiple VLANs between switches while VLAN 99 is configured as the native management VLAN.

![Trunk Configuration](screenshots/06-trunk-configuration.png)

---

## DHCP Services

Centralized DHCP dynamically assigns IP addresses to clients in each VLAN.

**Configuration includes:**

- DHCP pools
- Excluded addresses
- Default gateway
- DNS server
- DHCP relay using IP Helper Address

![DHCP Configuration](screenshots/07-dhcp-configuration.png)

### Client Lease Verification

The workstation successfully receives its IP configuration automatically.

![DHCP Client](screenshots/08-dhcp-client.png)

---

## Access Control Lists (ACLs)

ACLs were implemented to control communication between network segments and isolate guest wireless users from internal enterprise resources.

![ACL Configuration](screenshots/09-acl-configuration.png)

---

## Port Security

Access ports were hardened using Cisco Port Security.

**Security features**

- Sticky MAC addresses
- Maximum MAC limit
- Restrict violation mode
- PortFast
- BPDU Guard

![Port Security](screenshots/10-port-security.png)

---

## Connectivity Testing

End-to-end connectivity was verified using successful ping tests between clients and their default gateways.

![Connectivity Tests](screenshots/11-connectivity-tests.png)

---

## Skills Demonstrated

- Enterprise Network Design
- VLAN Segmentation
- Inter-VLAN Routing
- HSRP High Availability
- OSPF Configuration
- LACP EtherChannel
- DHCP Deployment
- ACL Implementation
- Switch Hardening
- Cisco IOS Troubleshooting

---

## What I Learned

This project strengthened my understanding of how enterprise networks are designed for scalability, redundancy, and security. Rather than configuring devices independently, I learned how VLANs, routing, gateway redundancy, DHCP, ACLs, and Layer 2 security work together to create a resilient network infrastructure.

---

## Disclaimer

This project was built in a controlled Cisco Packet Tracer lab for educational and defensive networking purposes.