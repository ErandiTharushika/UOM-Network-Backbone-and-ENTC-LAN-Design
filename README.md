# University of Moratuwa - Network Design Project

**EN2150 - Communication Network Engineering**
Department of Electronic and Telecommunication Engineering, University of Moratuwa

## Group Members

| Name | Index No. |
|---|---|
| Eranga O.A. | 230175U |
| Garusinghe S.B. | 230197M |
| Gamage S.K. | 230195F |
| Tharushika G.K.E. | 230636K |

## Overview

This project presents a two-level network design for the University of Moratuwa:

1. **Campus Backbone Network** – connects all major buildings (Library, ENTC, L Block, Sumanadasa, CITeS, Mechanical, CSE, Electrical, etc.) using a hierarchical, dual-core topology for reliability and scalability.
2. **ENTC Building Internal LAN** – a multi-floor building network connecting labs, staff areas, and wireless users, built around a central multilayer switch.

Both designs were simulated in **Cisco Packet Tracer**, with full IPv4/IPv6 addressing plans and a Bill of Quantities (BOQ) for active and passive components.

## Repository Structure

```
├── README.md
├── docs/
│   └── Network_Project.pdf          # Full project report
└── packet-tracer/
    ├── Backbone_of_university.pkt   # Campus backbone simulation
    └── ENTC_internal_network.pkt    # ENTC building LAN simulation
```

## Design Highlights

### Campus Backbone
- **Topology:** Extended star / hierarchical, with two core switches (Cisco 3650-24PS) for redundancy.
- **Building switches** connect Library, ENTC, L Block, and Sumanadasa to the core.
- **Passive media:**
  - Single-mode fibre - core-to-core and core-to-main-node links (high bandwidth, low attenuation, long distance).
  - Multimode fibre - shorter local distribution links (e.g., Sumanadasa to Mechanical/CSE/Electrical).
  - Copper crossover cable - inter-building links where fibre wasn't required.

### ENTC Internal LAN
- Central multilayer switch on the ground floor acts as the building core.
- Access-layer switches (Cisco Catalyst 2960-24TT) per floor connect PCs, laptops, and access points.
- Wired connections for labs/fixed devices; wireless APs for mobility.
- Copper straight-through cabling used throughout.

### Active Components
- **Cisco Catalyst 3650-24PS** - Layer 2/3 multilayer switch, used at the core and department level.
- **Cisco Catalyst 2960-24TT** - Layer 2 access switch, used for end-device connectivity.
- Cisco 2911 Routers, Cisco ASA 5506-X Firewalls, and a Cloud-PT WAN emulator complete the backbone.

### IP Addressing
- **IPv4:** VLAN-based subnetting (10.0.0.0/20 down to /25) sized by user count per VLAN.
- **IPv6:** `2001:db8:0:x::/64` per VLAN, using a mix of SLAAC and DHCPv6.

### Bill of Quantities (Backbone)
| Item | Quantity |
|---|---|
| Cisco 3650-24PS switches | 17 |
| Cisco 2911 Routers | 4 |
| Cisco ASA 5506-X Firewalls | 2 |
| Cloud-PT (WAN Emulator) | 1 |
| Single-mode fibre | 1065 m |
| Multimode fibre | 345 m |
| Copper crossover cable | 2725 m |

Full details, diagrams, and device specifications are in [`docs/Network_Project.pdf`](docs/Network_Project.pdf).

## How to View the Simulations

1. Download [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free with a Cisco Networking Academy account).
2. Open the `.pkt` files in the `packet-tracer/` folder:
   - `Backbone_of_university.pkt` - campus-wide backbone
   - `ENTC_internal_network.pkt` - ENTC building LAN

## Tools Used

- Cisco Packet Tracer
- LaTeX (project report)

## Course

EN2150 – Communication Network Engineering, Semester 2, 2026
