# Inter-VLAN Routing Configuration

## Overview
This project demonstrates VLAN segmentation with inter-VLAN communication using router-on-a-stick (encapsulation).

## Topology
![Topology](screenshots/topology.png)

## Network Design
- VLAN 90 → 192.168.20.0/27
- VLAN 80 → 192.168.20.32/27
- VLAN 70 → 192.168.20.64/27

A single switch connects all devices, and a router is used to enable communication between VLANs.

## What I Did
- Created VLAN 70, 80, and 90 on the switch
- Assigned devices to their respective VLANs
- Configured trunk link between switch and router
- Used subinterfaces with encapsulation on the router
- Enabled communication between different VLANs

## Configuration
Key commands used:

Switch:
- vlan 70
- vlan 80
- vlan 90
- switchport mode access
- switchport access vlan X
- switchport mode trunk

Router:
- interface g0/0/0.3
- encapsulation dot1Q 70
- ip address 192.168.20.65 255.255.255.224

## Testing
![Ping Test](screenshots/ping-test.png)

- Devices across different VLANs communicated successfully
- Inter-VLAN routing verified using ping

## Tools Used
- Cisco Packet Tracer

## Result
Successfully configured inter-VLAN routing using encapsulation, allowing communication between multiple VLANs on a single network.