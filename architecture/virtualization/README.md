# Virtualization & High Availability – Proxmox VE

## Why Proxmox VE?

Proxmox VE was selected as the virtualization platform for this project as a
pragmatic and enterprise-aligned alternative to proprietary solutions such as
VMware ESXi and IBM PowerVM.

The objective is to demonstrate a strong understanding of **enterprise
virtualization concepts** while using an **open-source and accessible platform**
suitable for a laboratory environment.

---

## Comparison with Enterprise Solutions

| Criteria | Proxmox VE | VMware ESXi | IBM PowerVM |
|--------|-----------|-------------|-------------|
| Licensing | Open Source | Proprietary | Proprietary |
| High Availability | Yes | Yes | Yes |
| Live Migration | Yes | Yes | Yes |
| Cluster Support | Yes | Yes | Yes |
| Distributed Storage | Ceph | vSAN | SAN (IBM) |
| Lab Accessibility | High | Medium | Low |

---

## Key Advantages of Proxmox VE

- Enterprise-grade virtualization features
- Built-in High Availability (HA)
- Native cluster management
- Integrated Ceph storage
- Open-source ecosystem
- Strong adoption in modern infrastructures

---

## High Availability Design

The Proxmox cluster is designed with multiple nodes to ensure service continuity
in case of node failure.

High Availability features include:
- VM and container failover
- Live migration
- Cluster quorum management
- Shared storage integration

---

## Use Case in This Project

Proxmox VE is used to host:
- Infrastructure services (firewall, monitoring, CI/CD)
- Kubernetes worker and control nodes
- Databases and application services

This approach closely simulates real-world production environments.

---

## Conclusion

The use of Proxmox VE enables the implementation of a robust, scalable, and
highly available virtualization layer while remaining aligned with current
market trends and enterprise requirements.

