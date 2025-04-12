
## Jenkins CI/CD Pipeline for Python Docker App

This repository demonstrates a Jenkins pipeline that automates the process of building and running a Python application inside a Docker container. The pipeline is configured using a `Jenkinsfile` stored inside the `task2` directory.



### Folder Structure

```
Devops-tasks/
├── task2/
│   ├── Dockerfile
│   ├── Jenkinsfile
│   └── app.py
```

---

## Prerequisites

- Jenkins installed on an EC2 instance or local machine
- Docker installed and running
- Git installed
- A GitHub repository containing the Jenkinsfile and application code
- Proper Jenkins plugin installed: Pipeline, Git, Docker Pipeline
- Port 5000 open on your firewall or security group (for accessing the containerized app)

---

## Pipeline Flow

1. **Checkout**  
   Jenkins pulls the code from the specified GitHub repository and branch (`main` in this case).

2. **Build Docker Image**  
   Jenkins builds the Docker image from the Dockerfile located in the `task2` directory.

3. **Run Container**  
   The built image is used to create and run a Docker container exposing port 5000.

4. **Post Actions (Cleanup)**  
   Regardless of build success or failure, Jenkins attempts to remove the container named `python-app`.

---

## How to Set Up in Jenkins

1. Open Jenkins and create a new **Pipeline** project.

2. In the pipeline configuration:
   - Choose **Pipeline script from SCM**
   - SCM: Git
   - Repository URL:  
     `https://github.com/guptha-maddula/Devops-tasks.git`
   - Branch Specifier:  
     `*/main`
   - Script Path:  
     `task2/Jenkinsfile`

3. Save the pipeline and click **Build Now** to trigger the process.

---

## Useful Jenkins Pipeline Commands

Below are some key shell commands used during pipeline execution:

- `docker build -t <image_name> .`  
  Builds the Docker image

- `docker run -d -p 5000:5000 --name <container_name> <image_name>`  
  Runs the container in detached mode

- `docker rm -f <container_name>`  
  Removes the container if it already exists

---

## Learnings

- Ensure the EC2 instance has permission to access the GitHub repository (public or configured with credentials).
- You can update the image name or container port as required in the environment section of the `Jenkinsfile`.
- If using a private repository or Docker Hub, configure Jenkins credentials accordingly.

---
