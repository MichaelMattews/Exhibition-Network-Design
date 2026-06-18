# Network Plan

## Project Name

NMAC & Auralabs Exhibition Network Design

## Project Goal

Design a segmented exhibition network for NMAC and Auralabs that separates staff, ticketing, media, CCTV, guest Wi-Fi, merchandise/POS, and admin access using VLANs, DHCP scopes, and access control rules.

## 1. Network Topology Overview

The network is designed to support two exhibition environments: NMAC and Auralabs. It separates ticketing, staff, CCTV, media devices, merchandise/POS, guest Wi-Fi, and admin access using VLANs.

```text
Internet
   |
Router / Firewall
   |
Core Switch
   |
---------------------------------------------------------
| Ticketing | Staff | CCTV | Media | Merch | Guest | Admin |
```

| VLAN ID | VLAN Name | Purpose |
|---|---|---|
| 10 | Ticketing | NMAC ticketing PCs and Auralabs ticketing laptop |
| 20 | Staff | Staff laptops |
| 30 | CCTV | Security cameras |
| 40 | Media | Screens and projectors |
| 50 | Merch_POS | Merchandise/POS PC |
| 60 | Guest_WiFi | Visitor wireless access |
| 70 | Admin | Admin laptop and network management |

## 3. IP Addressing Plan

| VLAN ID | VLAN Name  | Network         | Default Gateway |
| ------- | ---------- | --------------- | --------------- |
| 10      | Ticketing  | 192.168.10.0/24 | 192.168.10.1    |
| 20      | Staff      | 192.168.20.0/24 | 192.168.20.1    |
| 30      | CCTV       | 192.168.30.0/24 | 192.168.30.1    |
| 40      | Media      | 192.168.40.0/24 | 192.168.40.1    |
| 50      | Merch_POS  | 192.168.50.0/24 | 192.168.50.1    |
| 60      | Guest_WiFi | 192.168.60.0/24 | 192.168.60.1    |
| 70      | Admin      | 192.168.70.0/24 | 192.168.70.1    |

## 4. Device Inventory

| Device                    | Quantity | VLAN    | Notes                                           |
| ------------------------- | -------: | ------- | ----------------------------------------------- |
| NMAC Ticketing PCs        |        2 | VLAN 10 | Used for visitor ticketing                      |
| Auralabs Ticketing Laptop |        1 | VLAN 10 | Used for visitor ticketing                      |
| NMAC Merch/POS PC         |        1 | VLAN 50 | Used for merchandise sales                      |
| Staff Laptops             |        5 | VLAN 20 | 2 authorized for media access, 3 standard staff |
| Admin Laptop              |        1 | VLAN 70 | Full network administration access              |
| CCTV Cameras              | Multiple | VLAN 30 | Isolated security camera network                |
| Auralabs Screens          |       14 | VLAN 40 | Media display devices                           |
| Auralabs Projectors       |        8 | VLAN 40 | Media projection devices                        |
| NMAC Projectors           | Multiple | VLAN 40 | Media projection devices                        |
| Guest Wi-Fi Devices       | Variable | VLAN 60 | Internet-only visitor access                    |

## 5. Static IP Assignment

| Device                    | IP Address    | VLAN    |
| ------------------------- | ------------- | ------- |
| Admin Laptop              | 192.168.70.10 | VLAN 70 |
| Media Staff Laptop 1      | 192.168.20.10 | VLAN 20 |
| Media Staff Laptop 2      | 192.168.20.11 | VLAN 20 |
| Standard Staff Laptop 1   | 192.168.20.20 | VLAN 20 |
| Standard Staff Laptop 2   | 192.168.20.21 | VLAN 20 |
| Standard Staff Laptop 3   | 192.168.20.22 | VLAN 20 |
| NMAC Ticketing PC 1       | 192.168.10.10 | VLAN 10 |
| NMAC Ticketing PC 2       | 192.168.10.11 | VLAN 10 |
| Auralabs Ticketing Laptop | 192.168.10.12 | VLAN 10 |
| NMAC Merch/POS PC         | 192.168.50.10 | VLAN 50 |

## 6. DHCP Scope Plan

| VLAN               | DHCP Range                      |
| ------------------ | ------------------------------- |
| VLAN 10 Ticketing  | 192.168.10.100 - 192.168.10.200 |
| VLAN 20 Staff      | 192.168.20.100 - 192.168.20.200 |
| VLAN 30 CCTV       | 192.168.30.100 - 192.168.30.200 |
| VLAN 40 Media      | 192.168.40.100 - 192.168.40.200 |
| VLAN 50 Merch_POS  | 192.168.50.100 - 192.168.50.200 |
| VLAN 60 Guest_WiFi | 192.168.60.100 - 192.168.60.250 |
| VLAN 70 Admin      | 192.168.70.100 - 192.168.70.150 |

## 7. Access Control Requirements

| Source                 | Destination      | Permission |
| ---------------------- | ---------------- | ---------- |
| Admin Laptop           | All VLANs        | Allow      |
| Media Staff Laptop 1   | Media VLAN       | Allow      |
| Media Staff Laptop 2   | Media VLAN       | Allow      |
| Standard Staff Laptops | Media VLAN       | Deny       |
| Staff VLAN             | Internet         | Allow      |
| Ticketing VLAN         | Internet         | Allow      |
| Merch/POS VLAN         | Internet         | Allow      |
| Guest Wi-Fi VLAN       | Internet         | Allow      |
| Guest Wi-Fi VLAN       | Internal VLANs   | Deny       |
| CCTV VLAN              | Guest Wi-Fi VLAN | Deny       |
| Guest Wi-Fi VLAN       | CCTV VLAN        | Deny       |

## 8. Testing Plan

| Test                                     | Expected Result |
| ---------------------------------------- | --------------- |
| Admin laptop pings media device          | Success         |
| Admin laptop pings ticketing device      | Success         |
| Media staff laptop pings media device    | Success         |
| Standard staff laptop pings media device | Fail            |
| Guest device pings internal device       | Fail            |
| Ticketing PC reaches gateway             | Success         |
| Merch/POS PC reaches gateway             | Success         |
| Staff laptop reaches gateway             | Success         |

## 9. Packet Tracer Implementation Notes

The Packet Tracer version will simulate the exhibition network using a reduced number of devices. Media devices will represent screens and projectors, while a smaller number of cameras will represent the CCTV network.

The goal is to demonstrate network segmentation, inter-VLAN routing, DHCP, and ACL-based access control.
