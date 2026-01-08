Spring Boot DevOps CI/CD Pipeline
Project Overview

This project demonstrates an end-to-end DevOps pipeline for a Spring Boot application, covering build, containerization, CI/CD automation, and deployment.

Tech Stack

Spring Boot

Maven

Docker

GitHub Actions

Docker Hub

Docker Compose

Workflow
Code Commit → GitHub Actions → Docker Image Build → Docker Hub → Docker Compose → Browser

Project Structure
demo/
├── src/
├── target/
│   └── demo-0.0.1-SNAPSHOT.jar
├── Dockerfile
├── docker-compose.yml
├── pom.xml
└── .github/workflows/cicd.yml

Key Commands
# Build application
mvn clean package

# Build Docker image
docker build -t springboot-app .

# Run container
docker run -p 8080:8080 springboot-app

# Push image to Docker Hub
docker tag springboot-app <dockerhub-username>/springboot-app:latest
docker push <dockerhub-username>/springboot-app:latest

# Deploy using Docker Compose
docker compose up -d

CI/CD

Implemented using GitHub Actions

Automatically builds and pushes Docker image on every commit

Docker Hub credentials stored using GitHub Secrets

Access Application
http://localhost:8080

Status

Project completed successfully with a working CI/CD pipeline and deployment.
