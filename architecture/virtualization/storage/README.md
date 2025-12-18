# Storage & Backup – High Availability Design

## Storage Strategy Overview
The storage layer is designed to ensure data availability, resilience, and
performance for critical workloads.

The project uses **Ceph** as a distributed storage solution, acting as an
enterprise-grade SAN equivalent.

---

## Why Ceph?

Ceph was selected as the shared storage solution due to its ability to provide:
- Distributed storage
- High availability
- Automatic replication
- Self-healing capabilities
- Native integration with Proxmox VE

This approach closely matches enterprise SAN solutions such as Dell EMC storage.

---

## Ceph Architecture

The Ceph cluster consists of the following components:
- MON (Monitor): maintains cluster state and quorum
- OSD (Object Storage Daemon): stores data and handles replication
- MGR (Manager): monitoring and management services

---

## Data Replication & Resilience
- Replication factor: 3 copies
- Automatic rebalancing
- No single point of failure
- Continuous data availability during node failures

---

## Storage Usage
- Ceph RBD for virtual machine disks
- CephFS for shared file storage (optional)

---

## Backup Strategy

To protect data and ensure disaster recovery, a centralized backup strategy is
implemented using **Proxmox Backup Server**.

---

## Backup Features
- Incremental backups
- Scheduled jobs
- Encryption at rest
- Data deduplication
- Retention policies

---

## Backup Policy

| Backup Type | Frequency | Retention |
|------------|-----------|-----------|
| Snapshot | Daily | 7 days |
| Full Backup | Weekly | 4 weeks |
| Monthly Backup | Monthly | 6 months |

---

## Business Value
- Data protection
- Rapid recovery
- Compliance with enterprise best practices
- Reduced risk of data loss

