Two-Tier Flask Application with MySQL (CI/CD using Jenkins & Docker)

Project Overview

This project demonstrates a **Two-Tier Web Application Architecture** using:

* Flask (Python)** → Web Application
* MySQL** → Database
* Docker** → Containerization
* Docker Compose** → Multi-container management
* Jenkins** → CI/CD automation
* GitHub** → Source code management

The application is automatically built and deployed using a **Jenkins pipeline whenever code changes are pushed to GitHub**.

---

# Architecture

User → Flask Web App → MySQL Database

The application runs using two containers:

1. **Flask Container** – runs the Python web application
2. **MySQL Container** – stores application data

Both containers communicate using **Docker networking**.

---

# Technologies Used

| Technology     | Purpose                       |
| -------------- | ----------------------------- |
| Python Flask   | Web framework                 |
| MySQL          | Database                      |
| Docker         | Containerization              |
| Docker Compose | Multi-container orchestration |
| Jenkins        | CI/CD automation              |
| GitHub         | Source code repository        |

---

# Project Structure

Repository-name-two-tier-flask-app/

├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
└── README.md

---

# How the CI/CD Pipeline Works

The Jenkins pipeline automates the entire deployment process.

### Pipeline Stages

1. **Clone Code**

   * Jenkins pulls the latest code from GitHub.

2. **Build Docker Image**

   * Docker builds the Flask application image using the Dockerfile.

3. **Deploy Application**

   * Docker Compose starts the Flask and MySQL containers.

---

# Jenkins Pipeline

The Jenkinsfile contains the following stages:

* Checkout source code
* Build Docker image
* Deploy application using Docker Compose

Example pipeline steps:

```
Stage 1: Clone Repository
Stage 2: Build Docker Image
Stage 3: Deploy using Docker Compose
```

---

# Docker Setup

### Dockerfile

Used to create the Flask application container.

Steps performed:

* Pull Python base image
* Install dependencies
* Copy application code
* Run Flask server

---

### Docker Compose

Docker Compose starts both services:

* Flask application
* MySQL database

Example:

```
services:
  flask:
    build: .
    ports:
      - "5000:5000"

  mysql:
    image: mysql
    ports:
      - "3306:3306"
```

---

# Application Endpoints

| Endpoint  | Description                    |
| --------- | ------------------------------ |
| `/`       | Displays Flask running message |
| `/health` | Health check endpoint          |

Example response:

```
Flask App Running with MySQL
```

---

# How to Run the Project Locally

### Clone repository

```
git clone https://github.com/your-username/Repository-name-two-tier-flask-app.git
```

### Run using Docker Compose

```
docker-compose up -d --build
```

### Access application

```
http://localhost:5000
```

---

# CI/CD Flow

Developer → GitHub → Jenkins → Docker Build → Docker Compose Deployment → Application Running

Whenever new code is pushed to GitHub, Jenkins automatically:

1. Pulls latest code
2. Builds Docker image
3. Deploys updated containers

---

# Features

* Automated CI/CD pipeline
* Dockerized application
* Two-tier architecture
* Jenkins pipeline automation
* Health check endpoint

---

# Future Improvements

* Add Nginx reverse proxy
* Add Kubernetes deployment
* Add monitoring with Prometheus & Grafana
* Add automated testing in Jenkins pipeline

---

# Author

**Joel Praveen**

DevOps Project – Two Tier Flask Application Deployment using Jenkins and Docker
