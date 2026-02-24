# DevOps Zero to Operator

## Project Overview

This project demonstrates a production-style DevOps deployment built from scratch using:

- AWS EC2
- Docker containerization
- Nginx reverse proxy
- GitHub Actions CI/CD
- Automated deployment via SSH

The goal was to build and understand a complete runtime + deployment pipeline instead of just writing code.

---

## Architecture

Runtime Flow:

Browser  
→ Public IP  
→ Port 80  
→ Nginx  
→ Port 5000  
→ Docker Container  
→ Flask Application  

Deployment Flow:

git push  
→ GitHub Actions (CI)  
→ Docker image build  
→ Push to Docker Hub  
→ SSH to EC2 (CD)  
→ Pull new image  
→ Replace container  

---

## What This Project Demonstrates

- Containerizing a Flask application using Docker
- Mapping host ports to container ports (`-p 5000:5000`)
- Configuring Nginx as a reverse proxy (80 → 5000)
- Implementing CI pipeline (build + push)
- Implementing CD pipeline (auto-deploy via SSH)
- Debugging runtime errors (502, connection refused, port conflicts)
- Understanding system layers (EC2, Nginx, Container, Application)

---

## Key Commands Used

Build Docker image:
docker build -t <image-name> .

Run container:
docker run -d -p 5000:5000 --restart unless-stopped <image-name>

---

## Learning Focus

This project focuses on:
- System-level understanding
- Failure simulation
- Layer-based debugging
- Real-world deployment thinking

---

## Status

Project successfully deployed with automated CI/CD pipeline.



