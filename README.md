# Cisco Enterprise Networking Lab

## Overview

This project demonstrates the implementation of a small enterprise network using Cisco Packet Tracer. The lab was designed to simulate a real-world business environment by implementing VLAN segmentation, Router-on-a-Stick inter-VLAN routing, DHCP services, Access Control Lists (ACLs), and Switch Port Security.

The objective was to improve network organization, automate IP address assignment, secure switch ports from unauthorized devices, and restrict communication between departments using extended ACLs.

---

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS CLI
- Router-on-a-Stick (802.1Q)
- VLANs
- Inter-VLAN Routing
- DHCP
- Extended ACLs
- Switch Port Security
- Sticky MAC Addresses

---

## Network Design

The network consists of one Cisco router, one Layer 2 switch, three departmental PCs, and one server.

| Department | VLAN | Network |
|------------|------|----------------|
| HR | 10 | 192.168.10.0/24 |
| IT | 20 | 192.168.20.0/24 |
| Sales | 30 | 192.168.30.0/24 |
| Servers | 40 | 192.168.40.0/24 |

---

# Features Implemented

## Router-on-a-Stick

Configured router subinterfaces using IEEE 802.1Q encapsulation to enable communication between multiple VLANs over a single physical interface.

---

## VLAN Configuration

Created separate VLANs for:

- HR
- IT
- Sales
- Servers

Each VLAN was assigned its own subnet and default gateway.

---

## DHCP

Configured DHCP pools for each VLAN to automatically assign:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

---

## Extended Access Control List (ACL)

Configured an extended ACL to prevent Sales devices from communicating with the HR network while allowing all other traffic.

ACL Rule:

```
deny ip 192.168.30.0 0.0.0.255 192.168.10.0 0.0.0.255
permit ip any any
```

---

## Switch Port Security

Configured Port Security on user access ports using:

- Sticky MAC Addresses
- Maximum of 1 MAC Address
- Restrict Violation Mode

This prevents unauthorized devices from accessing the network while keeping the interface online.

---

# Verification

## Network Topology

*(<img width="1920" height="1080" alt="Network Topology" src="https://github.com/user-attachments/assets/5ae0a573-cccd-4ffc-aab7-a7304f73f9f2" />)*


---

## DHCP Verification

DHCP successfully assigned IP addresses to hosts in each VLAN.

<img width="423" height="423" alt="dhcp-working" src="https://github.com/user-attachments/assets/4db3e670-57c3-4bac-9606-fbc77511e2ef" />


---

## ACL Verification

Sales VLAN was unable to communicate with the HR VLAN, confirming that the extended ACL was functioning correctly.

*(<img width="1920" height="1080" alt="port-security-violation" src="https://github.com/user-attachments/assets/8408dce8-c0c3-4d1b-9485-69e2e9ebd6ae" />)*

---

## Port Security Configuration

Port Security was enabled on switch access ports using Sticky MAC learning and Restrict mode.

<img width="1920" height="1080" alt="acl-blocking-sales-to-hr" src="https://github.com/user-attachments/assets/fb8bbafe-85fa-4cdd-9fbd-943566eaec5a" />


---

## Port Security Violation Test

An unauthorized device was connected to the HR switch port.

The switch detected the unknown MAC address and generated Port Security violation messages while blocking traffic from the unauthorized device.

<img width="1920" height="1080" alt="Security-Violation" src="https://github.com/user-attachments/assets/50e5a4ab-bcbb-4f52-9fa2-6fa16ed89b00" />


---

## Router Configuration

The router configuration file included in this repository contains:

- VLAN Subinterfaces
- DHCP Pools
- Extended ACL
- Inter-VLAN Routing Configuration

---

# Skills Demonstrated

- Enterprise Network Design
- VLAN Segmentation
- Router-on-a-Stick Configuration
- DHCP Configuration
- Extended ACL Implementation
- Cisco IOS CLI
- Network Troubleshooting
- Port Security
- Sticky MAC Address Configuration
- Network Verification and Testing

---

# Files Included

```
Cisco-Enterprise-Networking-Lab/

├── README.md
├── Small_Business_Network_Lab1.pkt
├── router-config.txt
└── screenshots/
    ├── topology.png
    ├── dhcp-verification.png
    ├── acl-verification.png
    ├── port-security-config.png
    └── port-security-violation.png
```

---

## Author

**Mateen Mamou**

Cybersecurity & Networking Professional

- CompTIA A+
- CompTIA Network+
- Bachelor of Information Technology Student
