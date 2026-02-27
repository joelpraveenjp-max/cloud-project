Prometheus & Grafana Monitoring System on AWS EC2

Project Overview

This project demonstrates the implementation of a centralized monitoring and observability system using Prometheus and Grafana deployed on AWS EC2 Ubuntu instances. The architecture consists of one master monitoring server and two worker nodes, enabling real-time system metrics collection, performance monitoring, and visualization through interactive dashboards.

The setup simulates a production-style infrastructure monitoring environment used in modern cloud and DevOps workflows.

---

Objectives

* Implement centralized monitoring for distributed cloud instances
* Collect system and performance metrics using Prometheus
* Visualize infrastructure health using Grafana dashboards
* Monitor multiple nodes from a single monitoring server
* Understand real-time observability practices

---

Technologies & Tools

### Monitoring Stack

* **Prometheus** – Metrics collection and monitoring system
* **Grafana** – Visualization and dashboard platform
* **Node Exporter** – System metrics exporter for Linux servers

### Cloud Infrastructure

* **AWS EC2 (Ubuntu)** – Virtual machine instances

  * 1 Master Monitoring Server
  * 2 Worker Nodes

---

Architecture Overview

The monitoring architecture consists of a master EC2 instance running Prometheus and Grafana. Prometheus periodically scrapes metrics from Node Exporters installed on the two worker EC2 Ubuntu instances.

Collected metrics such as CPU usage, memory consumption, disk I/O, and network activity are stored in Prometheus and visualized using Grafana dashboards, providing real-time infrastructure insights.

---

System Architecture

* **Master Node**

  * Prometheus Server
  * Grafana Dashboard
  * Metrics storage and visualization

* **Worker Nodes**

  * Node Exporter installed
  * System performance metrics exposed to Prometheus

---

Key Features

✅ Centralized monitoring system
✅ Real-time metrics collection
✅ Multi-node infrastructure monitoring
✅ Interactive Grafana dashboards
✅ Scalable monitoring architecture
✅ Cloud-based deployment on AWS

---

Skills Demonstrated

* DevOps Monitoring & Observability
* Prometheus Configuration
* Grafana Dashboard Creation
* Linux Server Management (Ubuntu)
* AWS EC2 Deployment
* Distributed System Monitoring
* Infrastructure Performance Analysis

---

Future Improvements

* Alerting using Prometheus Alertmanager
* Auto-scaling node monitoring
* Kubernetes cluster monitoring
* Log monitoring integration (ELK Stack)

---
Author

Joel Praveen

