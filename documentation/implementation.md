# Implementation

## Overview

The enterprise network was implemented using Cisco Packet Tracer.

Configuration was completed using the Cisco IOS Command Line Interface (CLI) following a phased implementation process.

---

# Phase 1 - VLAN Creation

Departmental VLANs were created on the Layer 2 switch.

Each VLAN represents a separate Layer 2 broadcast domain.

Access ports were assigned according to department membership.

---

# Phase 2 - Access Port Assignment

Switch interfaces connected to end devices were configured as access ports.

Each access port belongs to a single VLAN.

This allows end devices to communicate without requiring VLAN awareness.

---

# Phase 3 - Trunk Configuration

The uplink between the switch and router was configured as an IEEE 802.1Q trunk.

The trunk carries traffic for multiple VLANs simultaneously over a single physical cable.

Allowed VLANs were explicitly defined, and the native VLAN was changed to VLAN 999.

---

# Phase 4 - Router-on-a-Stick Configuration

The router was configured using one logical subinterface per VLAN.

Each subinterface was assigned:

- IEEE 802.1Q encapsulation
- Gateway IP address

These subinterfaces provide Layer 3 routing between VLANs.

---

# Phase 5 - Host Configuration

End devices were assigned static IPv4 addresses.

Each device received:

- IP Address
- Subnet Mask
- Default Gateway

DNS configuration was omitted because Internet connectivity was outside the scope of this project.

---

# Phase 6 - Verification

Network functionality was verified using Cisco IOS commands including:

- show vlan brief
- show interfaces trunk
- show ip interface brief
- show ip route

Inter-VLAN communication was confirmed through successful ICMP testing between hosts located in different VLANs.