## 📂 Repository Contents

This repository demonstrates a basic PostgreSQL deployment on AWS EKS using Infrastructure as Code and GitHub Actions. Here's a breakdown of the key components:


### 🐘 PostgreSQL Helm Chart

- **`postgresql/`**  
  A Helm chart based on the Bitnami template (with minimal adjustments) to deploy PostgreSQL on an AWS EKS cluster.  
  - Designed for testing purposes only  
  - Credentials are hard-coded for simplicity
  - **High Availability Setup**: Deploys one primary PostgreSQL node and two read replicas for redundancy.
   - **Multi-AZ Resilience**: Leveraging AWS EKS, the cluster spans multiple Availability Zones to enhance fault tolerance and uptime 

### ⚙️ GitHub Actions Workflows

- **`.github/workflows/create-cluster.yml`**  
  Manually triggered workflow to create the EKS cluster

- **`.github/workflows/deploy-postgresql.yml`**  
  Manually triggered workflow to deploy the PostgreSQL app (incl. persistent volumes).

- **`.github/workflows/delete-cluster.yml`**  
  Manually triggered workflow to destroy the EKS cluster and clean up resources after testing.

- **`.github/workflows/test-database.yml`**  
  Manually triggered workflow that connects to the pod and perform some basic commands: CREATE DATABASE, INSERT INTO, UPDATE, DELETE      <br><br><br>
---
<br>
As mentioned above, the PostgreSQL Helm chart included here is intentionally minimal and designed for testing purposes only. It does not contain any data, and credentials are hard-coded for simplicity. The goal is not to showcase a production-ready database setup, but rather to illustrate how I approach infrastructure provisioning, container orchestration, and CI/CD automation.


