# Project: TrendStore
## Overview
This project demonstrates a complete CI/CD pipeline for containerized application deployment using Docker, Terraform, AWS EKS (Kubernetes), DockerHub, GitHub, Jenkins, and monitoring with Prometheus and Grafana.

The workflow includes:

- Dockerizing the application  
- Automating infrastructure provisioning with Terraform  
- Using GitHub for version control  
- Publishing images to DockerHub  
- Automating pipelines in Jenkins with GitHub webhooks  
- Deploying on AWS EKS with Kubernetes manifests  
- Monitoring cluster and application health using Prometheus and Grafana  

---

## 1. Docker
- Created a Dockerfile to containerize the application  
- Built and verified the Docker image locally  
- Pushed images to DockerHub for centralized storage  
- Tested the containerized application locally  

---

## 2. Terraform (Infrastructure as Code)
- Defined infrastructure in `main.tf` including:  
  - VPC, subnets, and security groups  
  - IAM roles for Jenkins and EKS  
  - EC2 instance for Jenkins  
- Used Terraform CLI to provision AWS infrastructure consistently  

---

## 3. Version Control (GitHub)
- Used GitHub for source code management  
- Performed all Git operations via CLI in VS Code terminal  
- Added `.gitignore` and `.dockerignore` to exclude unnecessary files  

---

## 4. DockerHub
- Created a DockerHub repository to store images  
- Configured Jenkins to push built Docker images to DockerHub  
- Ensures consistent image versioning for development and production  

---

## 5. Jenkins (CI/CD Pipeline)
- Installed Jenkins on an EC2 instance and configured required plugins (Git, Docker, Kubernetes, Pipeline)  
- Added DockerHub credentials securely in Jenkins  
- Created a Declarative Pipeline to:  
  1. Build the Docker image  
  2. Push the image to DockerHub  
  3. Deploy the application on AWS EKS using Kubernetes manifests  
- Connected GitHub repo to Jenkins using webhooks for automated builds on every commit  

---

## 6. AWS EKS Deployment
- Provisioned a Kubernetes cluster using AWS EKS  
- Wrote **Deployment** and **Service** YAML manifests for the application  
- Deployed the application via Jenkins using `kubectl apply`  
- Verified the application is running successfully in the cluster  

---

## 7. Monitoring (Prometheus & Grafana)
- Deployed **Prometheus** to collect metrics from the cluster and application  
- Deployed **Grafana** for visualization and dashboards  
- Monitored:  
  - Cluster health  
  - Pod and application status  
  - Resource utilization (CPU, memory)  
- Set up Grafana dashboards to easily track performance and uptime  

---

## Conclusion
This project demonstrates:  

- End-to-end CI/CD with Docker, Jenkins, GitHub, and AWS EKS  
- Infrastructure provisioning using Terraform for consistent environments  
- Automated builds, image pushes, and deployments via Jenkins pipeline  
- Real-time monitoring and visualization using Prometheus and Grafana  

This ensures the application is always available, reliably deployed, and automatically updated whenever code changes are pushed.
