 **Full-stack Deployment Pipeline** | Spring Boot | Docker | AWS EC2 | GitHub Actions | Amazon ECR

---

## Project Overview

This project demonstrates a **complete CI/CD pipeline** for a Spring Boot application deployed on an AWS EC2 instance using Docker and automated GitHub Actions. Pushes to the `main` branch automatically:

1. Build the Docker image locally on GitHub Actions.
2. Push the image to **Amazon ECR**.
3. SSH into an **EC2 instance** to pull the latest image.
4. Recreate and start the container using `docker-compose`.

The application itself is a simple REST service with a `/greeting` endpoint returning `"Hello World"`.

---

## Tech Stack

- **Backend:** Spring Boot (Java)
- **Containerization:** Docker, Docker Compose
- **Cloud:** AWS EC2, Amazon ECR
- **CI/CD:** GitHub Actions
- **Version Control:** GitHub

---

## Features

- Automated **Docker image build** and push on every push to `main`.
- **SSH deployment** to EC2, automatically recreating containers.
- REST API endpoint: `GET /greeting` returns `"Hello World"`.
- Self-contained **Dockerfile** with Maven build stage and runtime stage.
- **Clean, reproducible deployments** with Docker Compose.

---

## Getting Started

### Clone the repository

```bash
git clone https://github.com/AlexKrechmer/AWS_Docker.git
cd AWS_Docker
Build and run locally with Docker
bash
Copy code
docker compose build
docker compose up -d
curl http://localhost:80/greeting
Deploy via GitHub Actions
Push to main → workflow triggers:

Build image

Push to ECR

Deploy to EC2

Your app will be live at your EC2 public IP, e.g., http://<EC2_PUBLIC_IP>/greeting

Repository Structure
arduino
Copy code
AWS_Docker/
├─ Dockerfile
├─ docker-compose.yml
├─ setup.sh
├─ spring-boot-app/
│  ├─ pom.xml
│  ├─ src/
│  └─ target/
└─ .github/workflows/deploy.yml
Live Demo
EC2 Public IP: http://3.134.91.37/greeting

Response: "Hello World"

Learnings / Key Takeaways
How to automate end-to-end CI/CD for Java apps on AWS.

Managing SSH keys and secure deployment.

Multi-stage Docker builds for clean, lightweight images.

Integration of GitHub Actions with AWS services.
