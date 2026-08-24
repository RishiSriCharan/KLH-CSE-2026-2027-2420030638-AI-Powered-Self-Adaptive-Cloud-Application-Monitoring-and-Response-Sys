# 📄 README.md

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Course Outcomes (CO) Alignment](#-course-outcomes-co-alignment)
- [Technology Stack](#-technology-stack)
- [Project Directory Structure](#-project-directory-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation & Setup](#installation--setup)
  - [Running the Platform](#running-the-platform)
- [Agile Management (CO1)](#-agile-management-co1)
- [DevOps Pipeline (CO2)](#-devops-pipeline-co2)
- [Security & DevSecOps (CO3)](#-security--devsecops-co3)
- [MLOps & Incident Engine (CO4)](#-mlops--incident-engine-co4)
- [Observability & Dashboards](#-observability--dashboards)
- [Dataset Information](#-dataset-information)
- [Team Members](#-team-members)
- [License](#-license)

---

## 📖 Overview

The **AI-Powered Self-Adaptive Cloud Application Monitoring and Intelligent Incident Response System** is an end-to-end AIOps platform built to continuously observe cloud-native microservices, detect anomalous behavior in real time, and trigger automated remediation workflows.

Traditional monitoring systems rely on static alert thresholds that fail in dynamic cloud environments. This platform leverages machine learning models to dynamically understand operational baselines, adapt to fluctuating traffic loads, predict resource bottlenecks, and automatically execute self-healing actions (e.g., dynamic pod scaling, automated service restarts, and traffic redirection) before system outages occur.

---

## ❗ Problem Statement

Modern enterprise software relies on microservice architectures running on distributed cloud clusters. This introduces several operational hurdles:

- ❌ **Metric & Log Overload**: Thousands of real-time telemetry signals overwhelm human operators.
- ❌ **Static Threshold Inefficiency**: Hardcoded alerts result in high false-positive rates and alert fatigue.
- ❌ **Delayed MTTR (Mean Time to Resolution)**: Manual incident triaging leads to prolonged application downtime.
- ❌ **Cost of Unplanned Outages**: Critical cloud service outages incur heavy operational and financial penalties.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🤖 **Adaptive Anomaly Detection** | Real-time ML-driven detection that adjusts dynamically based on workload patterns. |
| 🛡️ **Automated Incident Remediation** | Self-healing engine capable of auto-scaling, restarting unhealthy pods, and isolating failing microservices. |
| 🔄 **Automated CI/CD & Testing** | Complete deployment lifecycle managed via GitHub Actions and containerization. |
| 🔒 **DevSecOps Integration** | Automated SAST, container vulnerability scanning, DAST, and secrets auditing within pipelines. |
| 📊 **Real-Time Observability** | Centralized metric scraping via Prometheus and dynamic dashboard visualization via Grafana. |
| 📦 **Continuous MLOps Pipeline** | Automated model retraining, data versioning (DVC), and model lifecycle tracking (MLflow). |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         Target Cloud Microservices                           │
│                      (Deployed on Kubernetes Cluster)                        │
└──────────────────────────────────────┬──────────────────────────────────────┘
                                       │ Real-time Telemetry (Metrics & Logs)
                                       ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                          Observability Layer                                │
│                     [ Prometheus + PromQL Exporters ]                       │
└──────────────────────────────────────┬──────────────────────────────────────┘
                                       │ Scraped Metrics Stream
                                       ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                    AI Adaptive Anomaly Detection Engine                     │
│               [ Time-Series Isolation Forest / Autoencoder ]                │
│                                      │
│                  ┌───────────────────┴───────────────────┐                  │
│                  ▼                                       ▼                  │
│     [ Normal Workload Pattern ]               [ Anomaly Detected ]          │
│        (Update Metric Baseline)                          │                  │
└──────────────────────────────────────────────────────────┼──────────────────┘
                                                           │ Trigger Signal
                                                           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                    Intelligent Incident Response Engine                     │
│   ┌──────────────────────────────┬──────────────────────────────┐           │
│   ▼                              ▼                              ▼           │
│ [ Auto-Healing / Scaling ]  [ Alert Notification ]    [ Audit & Log Event ] │
│ (Kubernetes API Execution)   (Slack / PagerDuty API)    (Grafana Incident)  │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 🎯 Course Outcomes (CO) Alignment

| Outcome | Syllabus Area | Implementation in this Project |
|---|---|---|
| **CO1** | Agile & Scrum Fundamentals | 4 Sprints managed via Jira, User Stories with estimation, velocity tracking, and sprint retrospectives. |
| **CO2** | DevOps, Containers & Observability | Docker multi-stage builds, Kubernetes (Minikube) manifests, GitHub Actions CI/CD, Prometheus, and Grafana. |
| **CO3** | DevSecOps & Security Practices | SonarQube SAST, Trivy container scanning, OWASP ZAP DAST, GitHub Secrets, and GDPR-compliant audit logs. |
| **CO4** | Cloud MLOps & Continuous AI Delivery | Data versioning with DVC, experiment tracking and model registration with MLflow, automated retraining on AWS. |

---

## 🛠️ Technology Stack

| Domain | Technology / Tool | Usage in Project |
|---|---|---|
| **AI / ML** | `Python`, `Scikit-learn`, `PyTorch` | Isolation Forest & LSTM/Autoencoder models for anomaly prediction |
| **MLOps** | `MLflow`, `DVC` | Model registry, experiment tracking, and dataset versioning |
| **Monitoring** | `Prometheus`, `Grafana` | Metrics scraping, PromQL queries, and live operational dashboards |
| **Containers** | `Docker`, `Docker Compose` | Multi-container microservice packaging |
| **Orchestration** | `Kubernetes`, `Minikube` | Pod auto-healing, Horizontal Pod Autoscaling (HPA), ClusterIP |
| **CI/CD** | `GitHub Actions` | Automated build, test, scan, and continuous deployment workflows |
| **Security** | `SonarQube`, `Trivy`, `OWASP ZAP` | Static analysis, image vulnerability checks, and dynamic API testing |
| **Cloud** | `AWS (EC2, S3, CloudWatch)` | Cloud hosting, metric storage, and scalable runtime environments |
| **Agile & PM** | `Jira`, `Git / GitHub` | Sprint backlog grooming, burndown tracking, and GitFlow branching |

---

## 📁 Project Directory Structure

```
ai-adaptive-monitoring/
├── .github/
│   └── workflows/
│       ├── ci-cd.yml                 # Core build, test, scan, and deployment pipeline
│       └── mlops-retrain.yml         # Automated retraining and model evaluation pipeline
├── src/
│   ├── anomaly_detector/
│   │   ├── __init__.py
│   │   ├── detector.py               # Inference engine for anomaly scoring
│   │   ├── model.py                  # Model architecture definitions
│   │   └── preprocess.py             # Telemetry time-series normalizer
│   ├── incident_engine/
│   │   ├── __init__.py
│   │   ├── handler.py                # Rules-based & ML remediation router
│   │   ├── k8s_remediator.py         # Kubernetes API calls (restart pod, scale deployment)
│   │   └── notifier.py               # Dispatch alerts to Slack/webhooks
│   ├── collector/
│   │   └── prometheus_exporter.py    # Custom application metrics exporter
│   └── web_dashboard/
│       └── app.py                    # Streamlit interface for administrative control
├── k8s/
│   ├── app-deployment.yaml           # Monitored microservice deployment
│   ├── detector-deployment.yaml      # Anomaly engine pod configuration
│   ├── prometheus-config.yaml        # Scraping targets and recording rules
│   └── hpa.yaml                      # Horizontal Pod Autoscaler manifest
├── security/
│   ├── sonar-project.properties      # SonarQube quality gate thresholds
│   ├── trivy-scan.sh                 # Container image scanner script
│   └── zap-baseline.conf             # DAST baseline scan configuration
├── tests/
│   ├── test_detector.py              # Unit tests for anomaly engine
│   ├── test_incident_engine.py       # Integration tests for remediation triggers
│   └── test_security_rules.py        # Security configuration validations
├── docs/
│   ├── agile/
│   │   ├── product_backlog.md
│   │   ├── sprint_1_plan.md
│   │   ├── sprint_2_plan.md
│   │   └── sprint_retrospectives.md
│   ├── architecture_design.md
│   └── devsecops_report.md
├── docker-compose.yml
├── Dockerfile.detector
├── Dockerfile.dashboard
├── dvc.yaml
├── params.yaml
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

Ensure the following tools are installed in your environment:
- **Python**: Version 3.10 or above
- **Docker Desktop**: Version 20.10+
- **Kubectl & Minikube**: For local cluster orchestration
- **Git**: Configured with standard SSH/HTTPS access

---

### Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/ai-adaptive-monitoring.git
   cd ai-adaptive-monitoring
   ```

2. **Set Up a Python Virtual Environment**
   ```bash
   python -m venv venv
   # On macOS/Linux:
   source venv/bin/activate
   # On Windows:
   venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Initialize DVC for Dataset Tracking**
   ```bash
   dvc pull
   ```

---

### Running the Platform

#### Local Execution via Docker Compose
To run the anomaly detection engine, Prometheus, Grafana, and the sample microservice locally:
```bash
docker-compose up --build -d
```

#### Verification Endpoints
- **Streamlit Web Dashboard**: `http://localhost:8501`
- **Prometheus Metrics Portal**: `http://localhost:9090`
- **Grafana Live Dashboards**: `http://localhost:3000` (Default Credentials: `admin` / `admin`)

---

## 📋 Agile Management (CO1)

The system development cycle is mapped across 4 distinct **Scrum Sprints** managed on **Jira**:

```
Sprint 1 (Weeks 1-2): Problem definition, dataset ingestion, basic anomaly model training.
Sprint 2 (Weeks 3-4): Containerization, Prometheus instrumentation, Minikube deployment.
Sprint 3 (Weeks 5-6): Automated incident response engine, DevSecOps pipeline integration.
Sprint 4 (Weeks 7-8): Cloud MLOps automation, Grafana alerting integration, final verification.
```

- Detailed user stories, acceptance criteria, and burndown reports are maintained under [`docs/agile/`](docs/agile/).

---

## 🔄 DevOps Pipeline (CO2)

Every pull request initiates a zero-touch **GitHub Actions CI/CD** pipeline:

1. **Lint & Test**: Code formatting checks via `flake8` and unit tests via `pytest`.
2. **Container Build**: Multi-stage Docker image builds reducing image footprint.
3. **Cluster Sync**: Automated rollout of updated deployment manifests to the Kubernetes cluster.

---

## 🔒 Security & DevSecOps (CO3)

Security controls are applied at each layer of the software lifecycle:

```
Code Check-in ──▶ [ SonarQube SAST ]  (Scans for logic vulnerabilities and code smells)
Image Build    ──▶ [ Trivy Scanner ]   (Blocks deployment on CRITICAL/HIGH CVEs)
Cluster Deploy ──▶ [ OWASP ZAP DAST ]  (Tests active API endpoints for security flaws)
Runtime        ──▶ [ Least-Privilege ] (Containers executed using non-root system users)
```

---

## 📦 MLOps & Incident Engine (CO4)

### Anomaly Detection & Retraining Workflow
- **Model**: Isolation Forest and Autoencoders trained on multivariate telemetry (CPU, Memory, Disk I/O, Network Throughput).
- **Tracking**: `MLflow` logs hyperparameters, mean squared error (MSE), and F1 anomaly detection scores.
- **Continuous Retraining**: When drift is observed in live system metrics, a GitHub Actions workflow executes `dvc repro` to retrain and update model weights automatically.

---

## 📊 Observability & Dashboards

The platform exposes real-time operational telemetry via Grafana:
- **Application Health**: Latency percentiles ($p_{50}, p_{95}, p_{99}$), error rates ($HTTP\ 5xx$).
- **AI Engine Health**: Anomaly confidence indices, baseline drift scores.
- **Incident Response Tracking**: Count of automated pod restarts, auto-scale events, and alert dispatches.

---

## 📁 Dataset Information

- **Dataset Name**: Server Machine Dataset (SMD)
- **Source**: NetManAIOps Research Group (Tsinghua University)
- **Download Reference**: [GitHub - SMD Repository](https://github.com/NetManAIOps/OmniAnomaly/tree/master/ServerMachineDataset)
- **Content**: 5-week-long time-series data gathered from a large internet enterprise cluster, containing 38 system metrics per record with verified anomaly ground-truth annotations.

---

## ## 👥 Team Members & Project Guidance

| S.No | ID Number | Name | Role |
| --- | --- | --- | --- |
| **1** | 2420030638 | Rayapureddi Rishi SriCharan | Team Member |
| **2** | 2420030161 | Yennam Sesank Reddy | Team Member |
| **3** | 2420090074 | Ramannagari Harshath | Team Member |
| **Guide** | — | Anugu Swapna | Project Guide |


## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for complete details.

---

<p align="center">
  <b>Developed for Adaptive Software Engineering</b> • 2026
</p>
```

---
