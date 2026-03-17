# CI-CD-GitOps-3-Tier-Microservices-Platform
CI/CD GitOps 3-Tier Microservices Platform
![Architecture](images/cicd.png)

# __Project Overview__

## 2. **Run Trivy file system scan**

A Trivy file system scan is performed on the source code to identify potential vulnerabilities and security issues before the image build process begins.

## 3. **Perform SonarQube analysis**

SonarQube is used to analyze the codebase for code quality, bugs, code smells, and maintainability issues.

## 4. **Build and tag Docker images**

Docker images are built for the frontend and backend services and tagged appropriately for versioning and deployment.

## 5. **Run Trivy image scan**

After the images are built, Trivy is used again to scan the Docker images for known vulnerabilities at the container image level.

## 6. **Push images to Docker Hub**

The validated images are pushed to their respective frontend and backend Docker Hub repositories.

## 7. **Update image reference in Kubernetes deployment manifests**

The pipeline updates the deployment.yaml file with the newly built image tag so that the latest version can be deployed through the CD workflow.

# **CD with Argo CD**

For Continuous Deployment, I used Argo CD, following the GitOps approach.

Argo CD continuously monitored the Kubernetes manifests stored in Git and synchronized the changes to the EKS cluster.

This helped me understand declarative deployments and how Git can act as the source of truth for Kubernetes applications.

# **Project Scope**

The primary focus of this project was to containerize a 3-tier MERN application and implement a CI/CD workflow for deployment on an Amazon EKS cluster. The goal was to gain hands-on experience with core DevOps concepts such as Docker, Docker Compose, Jenkins, Argo CD, Kubernetes manifests, and EKS cluster deployment using eksctl.

This project was built as a learning-focused implementation to understand the end-to-end workflow of packaging, deploying, and managing a containerized application in Kubernetes.

# **Current Project Focus**

This project mainly covers:

1. **Containerization of frontend and backend using multi-stage Dockerfiles**
2. **Local application execution using Docker Compose**
3. **Kubernetes-based deployment of the 3-tier application**
4. **EKS cluster provisioning using eksctl**
5. **CI implementation using Jenkins**
6. **CD implementation using Argo CD**
7. **Traffic routing using Gateway API / Envoy configuration**

# **Future Enhancements**

While this project successfully demonstrates the core deployment workflow, several production-oriented enhancements were intentionally kept out of scope so the main focus could remain on containerization and CI/CD implementation.

Possible improvements for this project include:

1. **Infrastructure as Code using Terraform instead of manual or eksctl-based cluster provisioning**
2. **More secure infrastructure design based on the Principle of Least Privilege**
3. **Persistent storage using AWS EBS volumes for stateful workloads such as MongoDB**
4. **StatefulSet-based database deployment for better storage stability and workload management**
5. **Horizontal Pod Autoscaler (HPA) for scaling application pods based on resource usage**
6. **Cluster Node Autoscaler for automatically adjusting worker nodes based on workload demand**
7. **Canary deployment strategy for safer and gradual application releases**

These enhancements are implemented more deeply in my advanced project: Enterprise GitOps Platform: Automated EKS Infrastructure and 3-Tier Microservices, where the focus shifts from basic deployment to more production-oriented infrastructure automation, security, scalability, and release management.
