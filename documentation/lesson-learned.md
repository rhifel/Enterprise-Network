# Lessons Learned

This project significantly improved my understanding of enterprise networking concepts beyond basic Cisco IOS configuration.

## Key Learning Outcomes

- VLANs provide logical network segmentation independent of physical topology.
- Layer 2 switches forward Ethernet frames using MAC addresses and VLAN information.
- Router-on-a-Stick enables multiple VLANs to share a single physical router interface through IEEE 802.1Q encapsulation.
- Access ports carry traffic for one VLAN, while trunk ports transport multiple VLANs simultaneously.
- The router selects the appropriate subinterface based on the VLAN tag before routing packets using the destination IP address.
- Address Resolution Protocol (ARP) explains the initial ICMP timeout commonly observed during first-time communication.
- Verification commands are essential for troubleshooting and confirming network behavior.

## Personal Reflection

One of the most valuable lessons from this project was learning to understand how packets move through the network instead of memorizing Cisco commands.

Following the complete packet journey—from an end device, through a switch, across an IEEE 802.1Q trunk, into a router subinterface, and finally to another VLAN—provided a much deeper understanding of how Layer 2 and Layer 3 technologies work together.

This project also demonstrated the importance of verifying configurations using operational commands rather than assuming the network is functioning correctly.

Future projects will build on this foundation by introducing DHCP, Access Control Lists (ACLs), dynamic routing protocols, and server integration to create more realistic enterprise network environments.