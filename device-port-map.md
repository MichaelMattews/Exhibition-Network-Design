# Device Port Map

## Project Name

NMAC & Auralabs Exhibition Network Design

## Core Switch Port Assignment

| Switch Port | Connected Device          |  VLAN | Port Mode |
| ----------- | ------------------------- | ----: | --------- |
| Gig0/1      | Router / Firewall         | Trunk | Trunk     |
| Fa0/1       | NMAC Ticketing PC 1       |    10 | Access    |
| Fa0/2       | NMAC Ticketing PC 2       |    10 | Access    |
| Fa0/3       | Auralabs Ticketing Laptop |    10 | Access    |
| Fa0/4       | Media Staff Laptop 1      |    20 | Access    |
| Fa0/5       | Media Staff Laptop 2      |    20 | Access    |
| Fa0/6       | Standard Staff Laptop 1   |    20 | Access    |
| Fa0/7       | Standard Staff Laptop 2   |    20 | Access    |
| Fa0/8       | Standard Staff Laptop 3   |    20 | Access    |
| Fa0/9       | Admin Laptop              |    70 | Access    |
| Fa0/10      | CCTV Camera 1             |    30 | Access    |
| Fa0/11      | CCTV Camera 2             |    30 | Access    |
| Fa0/12      | CCTV Camera 3             |    30 | Access    |
| Fa0/13      | CCTV Camera 4             |    30 | Access    |
| Fa0/14      | Media Device 1            |    40 | Access    |
| Fa0/15      | Media Device 2            |    40 | Access    |
| Fa0/16      | Media Device 3            |    40 | Access    |
| Fa0/17      | Media Device 4            |    40 | Access    |
| Fa0/18      | Media Device 5            |    40 | Access    |
| Fa0/19      | Media Device 6            |    40 | Access    |
| Fa0/20      | NMAC Merch/POS PC         |    50 | Access    |
| Fa0/21      | Guest Wi-Fi Access Point  |    60 | Access    |
| Fa0/22      | Reserved                  |   N/A | Unused    |
| Fa0/23      | Reserved                  |   N/A | Unused    |
| Fa0/24      | Reserved                  |   N/A | Unused    |

## Notes

* Gig0/1 is configured as a trunk link between the router and the switch.
* VLAN 40 represents Auralabs screens, Auralabs projectors, and NMAC projectors.
* Only the admin laptop and two media-authorized staff laptops should access VLAN 40.
* Standard staff laptops should not access media devices.
* Guest Wi-Fi should only have internet access and should be blocked from all internal VLANs.
* Unused switch ports should be shut down for security.
