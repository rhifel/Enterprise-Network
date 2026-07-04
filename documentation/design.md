# Network Design

## Project Goal

The objective of this project was to design and implement a small enterprise network that demonstrates fundamental enterprise networking concepts including VLAN segmentation, IEEE 802.1Q trunking, and Router-on-a-Stick (ROAS) inter-VLAN routing.

Rather than focusing solely on device configuration, the project emphasizes understanding packet flow, network segmentation, and Layer 2 and Layer 3 interactions commonly found in production environments.

---

# Design Requirements

The network was designed to meet the following requirements:

- Separate departments into isolated broadcast domains.
- Allow controlled communication between departments.
- Provide a scalable addressing scheme.
- Minimize hardware requirements by using Router-on-a-Stick.
- Follow common Cisco enterprise design practices.

---

# Department Segmentation

The company consists of five logical departments:

- IT
- Finance
- Customer Support
- Management
- Printers

Each department was assigned its own VLAN to isolate broadcast traffic and prepare the network for future security policies such as Access Control Lists (ACLs).

---

# VLAN Design

Each department was mapped to its own VLAN.

| VLAN |   Department   |
|------|----------------|
|  10  |       IT       |
|  20  |    Finance     |
|  30  |Customer Support|
|  40  |   Management   |
|  50  |    Printers    |

Using separate VLANs improves:

- Security
- Broadcast containment
- Network organization
- Future scalability

---

# IP Addressing Plan

Each VLAN was assigned its own /24 subnet.

This provides a clear one-to-one relationship between VLANs and IP networks, simplifying routing and troubleshooting.

Example:

- VLAN 10 → 192.168.10.0/24
- VLAN 20 → 192.168.20.0/24

---

# Router Selection

Router-on-a-Stick (ROAS) was selected because the simulated company is relatively small and only requires a single Layer 2 switch.

Using router subinterfaces allows multiple VLANs to share one physical connection while maintaining logical separation.

Although Layer 3 switches provide higher performance, Router-on-a-Stick offers a cost-effective solution suitable for small business environments.

---

# Security Considerations

Basic switch hardening practices were incorporated into the design.

The native VLAN was changed from VLAN 1 to VLAN 999 to avoid using the default VLAN on trunk links.

This follows common enterprise recommendations and prepares the network for additional security features in future iterations.