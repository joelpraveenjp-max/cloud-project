📦 AWS DevOps Automation Project
🚀 Terraform + Ansible + Jenkins + Docker + Prometheus + Grafana
📌 Overview

End-to-end DevOps pipeline on AWS:

👉 Terraform → Ansible → Jenkins → Docker → Flask App → Prometheus → Grafana

⚙️ Step 1: Terraform (Infrastructure Setup)

Provision VPC, subnet, gateway, and 3 EC2 instances.

# Install Terraform
sudo apt update
sudo apt install terraform -y

# Initialize & apply
terraform init
terraform plan
terraform apply -auto-approve
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/34ae3cf5-bf0f-48bf-9b56-6cad83856aa5" />




⚙️ Step 2: Ansible (Configuration Management)

Setup Ansible control node and install services.

# Install Ansible
sudo apt update
sudo apt install ansible -y

# Inventory file
vi hosts.ini

# Run playbooks
ansible-playbook -i hosts.ini install_jenkins.yml --private-key=connect.pem
ansible-playbook -i hosts.ini install_monitoring.yml --private-key=connect.pem

![b4361a41-0869-4e82-acc3-235892dcae6d](https://github.com/user-attachments/assets/6022378d-854b-4721-ad09-d5f816a44d11)

⚙️ Step 3: Jenkins + Docker (CI/CD Pipeline)

Connect Jenkins with GitHub repo and deploy app.

👉 Repo:
https://github.com/joelpraveenjp-max/Repository-name-two-tier-flask-app.git

Jenkins Pipeline Steps:
Pull code from GitHub
Build Docker image
Run container
# Install Docker
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo usermod -aG docker ubuntu

# Verify containers
docker ps
docker images

App runs on:

http://<EC2-PUBLIC-IP>:5000

![1c9507f2-b930-4976-9903-ada58bb2364e](https://github.com/user-attachments/assets/e5f20364-6156-4660-b911-3d1aea5af6d3)
![8bb1c686-360d-4448-8cf2-3af1e03564b6](https://github.com/user-attachments/assets/8ec45f5f-7479-4e9b-99d5-951e3bf39a0d)
![b39797af-319f-404e-941e-2809408bba5d](https://github.com/user-attachments/assets/302b8636-bd48-4441-8857-eedbc8f92dce)

⚙️ Step 4: Prometheus (Monitoring Setup)
# Run Prometheus
./prometheus --config.file=prometheus.yml

# Check targets
http://<PROMETHEUS-IP>:9090/targets

Add Jenkins target in prometheus.yml:

- job_name: "jenkins"
  static_configs:
    - targets: ["<JENKINS-IP>:8080"]


 ![05db4bad-2727-46ca-aded-c41d724f0f88](https://github.com/user-attachments/assets/93913936-4b87-477b-88a8-b9ddaf2125eb)

⚙️ Step 5: Grafana (Visualization)
# Install Grafana
sudo apt install -y grafana
sudo systemctl start grafana-server
sudo systemctl enable grafana-server

![193ca13f-b5c5-4951-84ec-546b1c2df81f](https://github.com/user-attachments/assets/b0126e28-6e90-42e8-a4d2-f577787d94e7)


Access:

http://<GRAFANA-IP>:3000
Add Prometheus as Data Source
Create dashboards
📁 Project Structure
cloud-devops-project/
├── terraform/
├── ansible/
├── jenkins/
├── README.md
🔁 Workflow
GitHub → Jenkins → Docker → Deploy → Monitor
🛠️ Tools
AWS EC2
Terraform
Ansible
Jenkins
Docker
Prometheus
Grafana
🎯 Result

✔ Infrastructure automated
✔ CI/CD pipeline working
✔ Docker deployment successful
✔ Monitoring enabled
