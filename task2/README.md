# Python App CI/CD with Jenkins and Docker

This project demonstrates how to set up a CI/CD pipeline for a Python application using Jenkins and Docker. The Jenkins pipeline is configured to build, test, and run the app inside a Docker container.

## 📁 Project Layout

All project files are placed inside the `task/` directory:
- `task/` contains the source code, `Dockerfile`, `Jenkinsfile`, and other dependencies.

## 🚀 What It Does

- Pulls the code from GitHub
- Installs Python dependencies
- Builds a Docker image for the Python app
- Runs the app in a Docker container
- Uses Jenkins Pipeline on an AWS EC2 instance

## ✅ Requirements

- AWS EC2 instance (Ubuntu recommended)
- Docker installed and running
- Jenkins installed and configured
- GitHub repository with your project

