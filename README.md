# Secure Bank Network using VLANs, EtherChannel & Router-on-a-Stick

Enterprise bank network designed in Cisco Packet Tracer with VLAN segmentation,
controlled inter-VLAN routing, redundancy, and basic security mechanisms.

## 📌 Project Overview
This project simulates a secure enterprise bank network using Cisco Packet Tracer.
The network is logically segmented using VLANs and supports controlled inter-VLAN routing,
redundancy, and basic security mechanisms.

## 🧠 Key Concepts Used
- VLANs (Admin, HR, Tech)
- Access and Trunk ports
- EtherChannel (Link Aggregation)
- Spanning Tree Protocol (STP)
- Router-on-a-Stick Inter-VLAN Routing
- DHCP per VLAN
- Port Security (MAC-based)
- Extended Access Control Lists (ACLs) for inter-VLAN traffic restriction

## 🧩 Network Design
- 2 Layer-2 Switches
- 1 Router
- Multiple PCs across different VLANs
- Trunk links with EtherChannel between switches
- Router subinterfaces for inter-VLAN routing

## 🔐 VLAN Structure
| VLAN | Name  | Subnet |
|-----|------|--------|
| 10  | Admin | 192.168.10.0/24 |
| 20  | HR    | 192.168.20.0/24 |
| 30  | Tech  | 192.168.30.0/24 |

## ⚙️ Features Implemented
- Redundant switch links using EtherChannel
- Loop prevention using STP
- Dynamic IP assignment using DHCP
- Secure access ports using Port Security
- Controlled inter-VLAN communication using ACLs

## 🔐 Security Architecture

This network implements multiple Layer-2 and Layer-3 security mechanisms to protect against common enterprise network attacks:

### Layer-2 Security
- **Port Security** limits the number of MAC addresses per access port to prevent unauthorized devices.
- **DHCP Snooping** prevents rogue DHCP servers by allowing DHCP responses only from trusted ports.
- **Dynamic ARP Inspection (DAI)** validates ARP packets using the DHCP snooping binding table to prevent ARP spoofing attacks.

### Layer-3 Security
- **Access Control Lists (ACLs)** are applied on router subinterfaces to restrict inter-VLAN communication.
  - HR and Tech VLANs are blocked from communicating with each other.
  - Admin VLAN is treated as trusted and can access all departments.

## 🚦 Inter-VLAN Access Policy

| Source VLAN | Destination VLAN | Access |
|------------|------------------|--------|
| Admin (10) | HR (20) | Allowed |
| Admin (10) | Tech (30) | Allowed |
| HR (20) | Tech (30) | Denied |
| Tech (30) | HR (20) | Denied |

ACLs are applied inbound on HR and Tech router subinterfaces to prevent lateral movement between departments while allowing administrative access.

## 🧪 Verification

The network configuration and security policies were verified using the following commands and tests:

- `show vlan brief`
- `show etherchannel summary`
- `show interfaces trunk`
- `show ip route`
- `show ip dhcp binding`
- `show port-security interface`
- `show ip dhcp snooping`
- `show ip arp inspection`
- `show access-lists`
- Ping tests validating ACL behavior

Connectivity was validated using ping tests to confirm allowed and denied inter-VLAN traffic.

## 📂 Project Files
- Packet Tracer file: `Packet Tracer/Bank Network.pkt`
- Device configs: `Configurations/`
- Screenshots: `Screenshots/`

## 🧠 Why This Project Matters

This project reflects real-world enterprise network design by combining redundancy, segmentation, and layered security.  
It demonstrates how VLANs, routing, and security mechanisms work together to reduce attack surfaces and enforce access control policies in a corporate environment.


## 🏁 Conclusion
This project demonstrates practical knowledge of enterprise networking concepts
and secure network design principles.
