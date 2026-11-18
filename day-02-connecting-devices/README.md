# Lab: Day 02 - Connecting Devices

## Problem
Understand how a switch learns where a device lives, using Jeremy's IT Lab Day 02 topology (R1-R4, SW1-SW8, PC1-PC3, SRV1) in Cisco Packet Tracer.

## Steps Taken
1. Opened Day 02 Lab - Connecting Devices.pkt from Downloads on the HP ProBook in Packet Tracer (Logical view).
2. Clicked a switch connected to PC1, opened the CLI tab.
3. Ran show mac address-table at the Switch> prompt.
4. Read the table: VLAN 1, two entries, Type = DYNAMIC.
   - 0001.9635.8d0e - Fa0/1
   - 000c.cf0c.ec83 - Fa1/1
5. Matched the table to the topology: the cable from PC1 lands on that switch, and the switch learned PC1's MAC on the port that cable plugs into.

## Resolution
The switch works. It learned both MAC addresses by itself (DYNAMIC) and will now send traffic for each MAC out only its learned port, instead of flooding it everywhere. If the destination MAC is not in the table yet, the switch floods it - then learns from the reply.

- Switch = learns a device's MAC address on the exact physical port the cable plugs into
- MAC address table = the switch's memory of MAC -> port
- DYNAMIC = learned automatically, not typed in by an admin
- Fa0/1 = FastEthernet 0/1, a physical port / interface on the switch
- Trunk port = one physical port/cable that carries multiple VLANs at the same time
- Port (engineer view) = physical jack + logical place the switch tracks, learns, and can configure

## Files
- Day 02 Lab - Connecting Devices.pkt - Packet Tracer file for this lab

## Sanitized
Generic lab topology and lab MACs from Packet Tracer only. No real employer/City configs, IPs, hostnames, usernames, passwords, or keys.
