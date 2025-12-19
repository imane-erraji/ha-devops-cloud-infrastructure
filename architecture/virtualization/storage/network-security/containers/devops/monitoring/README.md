# Monitoring & Observability

## 1. Overview

This directory describes the monitoring and observability strategy implemented in the **High Availability & DevOps Infrastructure** project.

Monitoring is a critical component of any production-grade infrastructure.  
It ensures service availability, performance visibility, proactive incident detection, and SLA compliance.

The monitoring stack in this project is designed to simulate a **real enterprise environment**, using widely adopted open-source tools.

---

## 2. Objectives

The main objectives of the monitoring system are:

- Ensure high availability of infrastructure and services
- Detect failures and performance degradation early
- Provide real-time visibility into system health
- Generate alerts for critical incidents
- Support troubleshooting and root cause analysis
- Simulate SLA and availability monitoring

---

## 3. Monitoring Stack

| Component     | Tool           | Role |
|---------------|---------------|------|
| Infrastructure Monitoring | Zabbix | Monitor servers, VMs, network devices, and services |
| Metrics Collection | Prometheus | Collect system and application metrics |
| Visualization | Grafana | Dashboards and visual analytics |
| Log Management | ELK Stack (Elasticsearch, Logstash, Kibana) | Centralized logging and analysis |
| Alerting | Alertmanager / Zabbix Alerts | Notifications and incident detection |

---

## 4. Scope of Monitoring

### 4.1 Infrastructure Monitoring

- Proxmox cluster nodes
- Virtual machines (CPU, RAM, Disk, Load)
- Network interfaces and traffic
- Storage usage and availability
- High Availability status

### 4.2 Network Monitoring

- pfSense firewall status
- Interface throughput
- Packet loss and latency
- VPN connectivity (WireGuard)
- VLAN segmentation health

### 4.3 Application & Container Monitoring

- Docker containers
- Kubernetes nodes and pods
- Application availability
- Resource consumption per service
- Health checks and readiness probes

### 4.4 Log Monitoring

- System logs (Linux)
- Application logs
- Security-related events
- Container and Kubernetes logs

---

## 5. Dashboards & Visualization

Grafana dashboards provide a centralized view of the infrastructure:

- CPU, Memory, Disk utilization
- Network traffic and latency
- Kubernetes cluster health
- Application performance metrics
- Availability and uptime indicators

Dashboards are designed to be **clear, actionable, and production-oriented**.

---

## 6. Alerting Strategy

Alerts are configured to notify administrators when predefined thresholds are exceeded.

### Example Alerts:

- Server unreachable
- High CPU or memory usage
- Disk space below critical threshold
- Service downtime
- Kubernetes pod failures

Alerts are categorized by severity:
- **Critical**
- **Warning**
- **Informational**

---

## 7. SLA & Availability Monitoring

The monitoring system supports simulated SLA tracking, including:

- Service uptime percentage
- Mean Time to Detect (MTTD)
- Mean Time to Resolve (MTTR)
- Availability of critical services

This approach reflects **enterprise-grade operational monitoring practices**.

---

## 8. Security & Best Practices

- Least privilege access to monitoring tools
- Secure communication between agents and servers
- Role-based dashboards (Admin / Viewer)
- Audit and logging of monitoring activities

---

## 9. Future Improvements

Planned enhancements include:

- Advanced alert correlation
- Automated remediation (self-healing)
- Integration with CI/CD pipelines
- Long-term metrics retention
- Advanced security monitoring rules

---

## 10. Evidence & Screenshots

Screenshots and monitoring evidence will be added in the `screenshots/` directory, including:

- Grafana dashboards
- Zabbix host status
- Prometheus targets
- Alert notifications

These elements will demonstrate the **real implementation** of the monitoring strategy.

