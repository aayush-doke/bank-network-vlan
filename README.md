# bank-network-vlan
Enterprise network using VLANs, EtherChannel &amp; inter-VLAN routing

# Secure Bank Network using VLANs, EtherChannel & Router-on-a-Stick

## 📌 Project Overview
This project simulates a secure enterprise bank network using Cisco Packet Tracer.
The network is logically segmented using VLANs and supports inter-VLAN routing,
redundancy, and basic security mechanisms.

## 🧠 Key Concepts Used
- VLANs (Admin, HR, Tech)
- Access and Trunk ports
- EtherChannel (Link Aggregation)
- Spanning Tree Protocol (STP)
- Router-on-a-Stick Inter-VLAN Routing
- DHCP per VLAN
- Port Security (MAC-based)

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
- Successful inter-VLAN communication

## 🧪 Verification
- `show vlan brief`
- `show etherchannel summary`
- `show ip dhcp binding`
- Ping tests between VLANs

## 📂 Project Files
- Packet Tracer file: `Packet Tracer/Bank Network.pkt`
- Device configs: `Configs/`
- Screenshots: `Screenshots/`

## 🏁 Conclusion
This project demonstrates practical knowledge of enterprise networking concepts
and secure network design principles.
