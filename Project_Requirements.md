# Project Overview
## Project Title

## NMAC & Auralabs Exhibition Network Design

### Objective

Design and implement a secure, scalable, and segmented network infrastructure for the NMAC and Auralabs exhibition venues. The network will support ticketing operations, merchandise sales, staff devices, CCTV systems, digital media displays, projectors, and guest wireless access while enforcing role-based access control.

### Business Requirements
### NMAC
2 Ticketing PCs
1 Merchandise/POS PC
CCTV Cameras
Multiple projectors

### Auralabs
1 Ticketing Laptop
14 Digital Screens
8 Projectors
CCTV Cameras


### Staff and Administration
5 Staff Laptops
  2 Media-authorized staff laptops
  3 Standard staff laptops
1 Admin Laptop

### Network Services
Internet Connectivity
Guest Wi-Fi
DHCP
Inter-VLAN Routing
Access Control Lists (ACLs)


### Security Requirements
Only the Admin laptop has full network access.
Only two authorized staff laptops may access media devices.
Standard staff laptops cannot access media devices.
Guest Wi-Fi users may access the Internet only.
CCTV devices must be isolated from guest traffic.
Ticketing and merchandise systems must be protected from unauthorized access.
Success Criteria

The network must:

Provide connectivity to all authorized devices.
Isolate departments using VLANs.
Restrict access using ACLs.
Allow secure communication between required systems.
Prevent unauthorized access to media and administrative resources.
