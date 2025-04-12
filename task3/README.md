
---

#  Terraform Docker Nginx Setup

This project demonstrates how to use **Terraform**, an Infrastructure as Code (IaC) tool, with **Docker Desktop** to deploy a simple **Nginx** web server container. It helps you understand how to automate container provisioning using Terraform.

---

##  Prerequisites

Before starting, ensure you have the following installed:

- **Docker Desktop**: Needed to run containers locally. Make sure it's up and running.
- **Terraform**: Used to define and manage infrastructure using code.

---

##  What This Project Does

This Terraform configuration:

- **Pulls the latest Nginx image** from Docker Hub, ensuring you always get the most updated version.
- **Creates a Docker container** named `nginx_container`, which runs the Nginx web server.
- **Maps port 8080 on your local machine** to port 80 inside the container so you can access Nginx via your browser at `http://localhost:8080`.

This setup is ideal for local testing and learning Terraform’s Docker provider.

---

##  Steps to Run

Follow these steps to deploy the Nginx server:

1. **Start Docker Desktop**  
   Ensure Docker is running in the background; Terraform needs it to provision the container.

2. **Login to Docker Registry (if required)**  
   If you're pulling private images, make sure you’re logged in. For public images like Nginx, no login is needed.

3. **Initialize Terraform**  
   This sets up the working directory and downloads necessary provider plugins (like the Docker provider).

4. **Review the Execution Plan**  
   Use Terraform's plan command to see what resources will be created before applying.

5. **Apply the Configuration**  
   This will create the Docker image (if not already pulled) and start the Nginx container.

---

##  Access the Web Server

Once the setup is applied successfully:

- Open any web browser.
- Visit: **http://localhost:8080**
- You should see the **Nginx welcome page**, which confirms your container is running and accessible.

This means Terraform successfully deployed the infrastructure using Docker.

---

##  Destroy the Setup

To clean up the environment:

- Run the Terraform destroy command:
  ```
  terraform destroy -auto-approve
  ```
- This will stop and remove the container and associated resources that were created by Terraform.

It’s a good practice to clean up after testing to free up resources.

---

##  Learnings from This Project

By working on this repo, you’ll gain:

- ✅ **Hands-on experience with Terraform** and its Docker provider, learning how IaC works in real-world containerized environments.
- ✅ A strong understanding of **key Terraform commands**:  
  - `init`: for setting up the working directory  
  - `plan`: for previewing changes  
  - `apply`: for creating resources  
  - `destroy`: for cleanup  
- ✅ Insight into **how Docker and Terraform integrate**, making it easier to automate containerized deployments in the future.
- ✅ Confidence in validating deployments by accessing applications via browser — in this case, the default Nginx page.

---
