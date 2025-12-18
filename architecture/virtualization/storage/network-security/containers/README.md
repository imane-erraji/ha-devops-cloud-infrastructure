# Containers & Kubernetes – High Availability Infrastructure

## Overview
This layer focuses on containerization and orchestration, enabling deployment
of applications in a scalable, portable, and production-like environment.
Containers run on top of the Proxmox HA cluster and leverage shared Ceph storage
for persistent data.

---

## Why Containers & Kubernetes?

- Containerization ensures **portability** across environments
- Kubernetes provides **orchestration**, high availability, and scaling
- Enables rapid deployment of microservices and databases
- Aligns with industry standards: Docker, Kubernetes (k3s or kubeadm)
- Production-like architecture for GitHub portfolios and freelance projects

---

## Container Technologies

| Technology | Purpose |
|------------|---------|
| Docker | Build, package, and run containerized applications |
| Kubernetes (k3s / kubeadm) | Orchestrate containers, HA, scaling |
| Helm (optional) | Package management for Kubernetes applications |
| PostgreSQL / MySQL containers | Databases running in containers for dev/test |

---

## Kubernetes Architecture (example)

- **Master Node**: control plane, schedules workloads
- **Worker Nodes**: run containers (pods)
- **Ceph RBD**: persistent storage for applications
- **Network Segmentation**: VLANs used for app, management, and storage traffic

Topology example:

[Proxmox HA Cluster]
|
+-- [Kubernetes Master Node]
+-- [Kubernetes Worker Node 1]
+-- [Kubernetes Worker Node 2]
|
+-- [Ceph RBD Storage]



---

## Application Deployment

1. **Build Docker images** locally or in CI/CD pipelines
2. **Push images** to GitHub Container Registry or Nexus
3. **Deploy via Kubernetes manifests** or Helm charts
4. **Mount Ceph RBD volumes** for persistent storage
5. **Monitor pods** and applications using Prometheus / Grafana

---

## Example Kubernetes Deployment (MySQL)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mysql-db
spec:
  replicas: 1
  selector:
    matchLabels:
      app: mysql-db
  template:
    metadata:
      labels:
        app: mysql-db
    spec:
      containers:
      - name: mysql
        image: mysql:8.0
        env:
        - name: MYSQL_ROOT_PASSWORD
          value: "rootpassword"
        volumeMounts:
        - name: mysql-pvc
          mountPath: /var/lib/mysql
      volumes:
      - name: mysql-pvc
        persistentVolumeClaim:
          claimName: mysql-pvc

