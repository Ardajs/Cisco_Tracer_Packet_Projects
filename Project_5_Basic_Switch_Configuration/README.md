#  Project 5 - Basic Switch Configuration and Remote Management

##  Overview

In this project, a Cisco switch was configured with basic management and security settings. Remote management was enabled using Telnet and connectivity was verified through successful login tests.

This project demonstrates initial switch setup and remote administration concepts.

---

##  Objectives

- Configure a switch hostname
- Configure management VLAN
- Assign management IP address
- Configure default gateway
- Enable remote access using Telnet
- Verify connectivity using ping and Telnet

---

##  Network Topology

This project includes:

- 1 Cisco 2960 Switch
- 1 PC



---

##  IP Addressing

| Device | IP Address | Subnet Mask |
|----------|------------|-------------|
| Switch (VLAN99) | 192.168.1.2 | 255.255.255.0 |
| PC0 | 192.168.1.X | 255.255.255.0 |

Default Gateway:

192.168.1.1

---

## ⚙️ Configuration

### Switch Configuration

```bash
enable
conf t

hostname S1

no ip domain-lookup

interface vlan 99
ip address 192.168.1.2 255.255.255.0
no shutdown

ip default-gateway 192.168.1.1

interface fa0/2
switchport access vlan 99
switchport mode access

line console 0
password cisco
login
logging synchronous

line vty 0 4
password cisco
login


## Testing & Verification
Ping Test
PC → Switch successful 
Telnet Test
PC → Switch successful 

Example: telnet 192.168.1.2

Successful remote login verified.


## Key Concepts:

- Switch configuration
- Management VLAN
- Default gateway
- Telnet
- Remote administration
