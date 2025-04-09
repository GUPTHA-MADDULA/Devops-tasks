# Python App CI/CD with Jenkins and Docker

This project demonstrates how to set up a CI/CD pipeline using Jenkins and Docker to build and run a simple Python application.

## Project Structure

All the project files are inside the `task/` folder:
- `simple-app.py`: Python app entry point
- `Dockerfile`: Used to build the Docker image
- `requirements.txt`: Python dependencies
- `Jenkinsfile`: Jenkins pipeline script

## How It Works

- Jenkins pulls code from GitHub
- Installs Python dependencies
- Builds a Docker image
- Runs the application inside a Docker container

## Requirements

- AWS EC2 instance (Ubuntu)
- Jenkins installed and running
- Docker installed and configured
- Jenkins user added to Docker group
- Port 8080 open in EC2 security group

## Access Jenkins

1. Open `http://<EC2_PUBLIC_IP>:8080` in your browser
2. Get the initial password:
   ```bash
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword

## Jenkins Setup
--Create a new Pipeline job
--Choose "Pipeline script from SCM"
--Use your GitHub repo URL
--Set the script path to (task/Jenkinsfile)

