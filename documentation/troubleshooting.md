# Troubleshooting

## Issue 1 - Initial ICMP Timeout

### Observation

The first ICMP request timed out while subsequent requests completed successfully.

### Cause

The host first performed Address Resolution Protocol (ARP) to discover the MAC address of its default gateway.

Only after ARP completed could the ICMP packet be forwarded.

### Resolution

Repeating the ping after ARP resolution resulted in successful communication.

---

## Issue 2 - Native VLAN Visibility

### Observation

After configuring VLAN 999 as the native VLAN, VLAN 1 still appeared in the output of `show vlan brief`.

### Cause

Changing the native VLAN affects only trunk interfaces.

Unused access ports remained assigned to VLAN 1 because they were not reconfigured.

### Resolution

Understanding the distinction between access VLANs and trunk native VLANs clarified the observed behavior.

---

## Issue 3 - Understanding VLAN Tagging

### Initial Assumption

The router uses destination IP addresses to determine the incoming VLAN.

### Actual Behavior

The switch inserts the IEEE 802.1Q VLAN tag before forwarding traffic over the trunk.

The router first identifies the incoming subinterface based on the VLAN tag before examining the destination IP address for Layer 3 routing.

This clarified the relationship between Layer 2 switching and Layer 3 routing.