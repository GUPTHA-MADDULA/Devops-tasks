# Terraform Docker Nginx Setup

This project uses **Terraform** and the **Docker Desktop** to spin up a simple **Nginx** web server container.

##  Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed and running
- [Terraform](https://developer.hashicorp.com/terraform/downloads) installed

      
##  What It Does

- Pulls the latest `nginx` image from Docker Hub
- Creates a Docker container named `nginx_container`
- Maps **port 8080 on your host** to **port 80 in the container**

##  Terraform Configuration

```hcl
provider "docker" {}

resource "docker_image" "nginx_image" {
  name         = "nginx:latest"
  keep_locally = false
}

resource "docker_container" "nginx_container" {
  name  = "nginx_container"
  image = docker_image.nginx_image.name

  ports {
    internal = 80
    external = 8080
  }
}
```

## Terraform Initialization Setup

- Steps to Run Terrafrom Environment

- Initialize Terraform: `terraform init`

- View the execution plan: `terraform plan`

- Apply the configuration: `terraform apply -auto-approve`


![Terrform creating is completed](./pictures/output%201.png)


## Docker-Desktop Setup

- Ensure keep your Docker-Desktop is running while creating this infrastructure.
- Also pre-login to your Docker registry to run the containers
- When completing the **Terraform configuration** with **Dockerfile** then automatically created the dockerimage and running **docker container**


## Access Nginx

- Once deployed, open your browser and go to:
 http://localhost:8080

- Confirmation of your Server is running of your desired port:

## Nginx server is running
![Server is Running Successfully](./pictures/output%202.png)


## To Destroy Terrafrom infrastructure

- Clean up all Terraform-managed resources:
`terraform destroy -auto-approve`

## Learnings By Implementing this:

---

## Learnings

- Learned to provision Docker containers using Terraform with the Docker provider.  
- Understood key Terraform commands like `init`, `plan`, `apply`, and `destroy`.  
- Gained hands-on experience writing and executing Terraform configurations.  
- Verified Nginx deployment by accessing it through `http://localhost:8080`.  

---


