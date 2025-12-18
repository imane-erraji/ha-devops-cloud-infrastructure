# Network & Security – HA Firewall & VLANs

## Overview
This network layer ensures segmentation, security, and high availability
for all workloads. pfSense is used as the firewall and router solution.

---

## Why pfSense?

pfSense was chosen due to its open-source nature, enterprise-grade features,
and support for HA, VPN, and advanced firewall policies. This aligns with
solutions like Fortinet, Cisco ASA, or Sophos in production environments.

---

## Network Architecture

Components:
- HA Firewalls using CARP
- Managed switch supporting VLANs
- Segmented network per VLAN

VLANs example:

| VLAN | Usage          | Subnet           |
| ---- | -------------- | ---------------- |
| 10   | Admin          | 192.168.10.0/24 |
| 20   | Users          | 192.168.20.0/24 |
| 30   | IoT / Guest    | 192.168.30.0/24 |
| 40   | DMZ / Servers  | 192.168.40.0/24 |

---

## Firewall HA & CARP

- Redundant firewalls with automatic failover
- Continuous network availability
- Shared virtual IP addresses for services

---

## Firewall Rules

- Deny all by default
- Allow traffic only as necessary per VLAN
- NAT for Internet access
- Logging and monitoring enabled

---

## VPN / Remote Access

- OpenVPN or WireGuard
- Secure remote access for admins and users
- Encrypted communication
- VLAN-based access control

---

## QoS / Traffic Shaping

- Prioritize critical traffic
- Limit non-essential traffic
- Avoid network congestion

---

## Business Value

- Network segmentation & security
- High availability of firewall services
- Controlled access & monitoring
- Enterprise-grade best practices

