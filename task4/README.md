# 🚀 Terraform Docker Nginx Setup

This project uses **Terraform** and the **Docker Desktop** to spin up a simple **Nginx** web server container.

##  Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed and running
- [Terraform](https://developer.hashicorp.com/terraform/downloads) installed

##  Project Structure

task3/ 
 ├── main.tf 
 ├── terraform.lock.hcl 
 ├── terraform.tfstate 
      └── terraform.tfstate.backup

      
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


 Commands to Run

Initialize Terraform: `terraform init`

View the execution plan: `terraform plan`
Apply the configuration: `terraform apply -auto-approve`



 Access Nginx

Once deployed, open your browser and go to:
http://localhost:8080
You should see the Nginx welcome page.

 To Destroy
Clean up all Terraform-managed resources:
`terraform destroy -auto-approve`

![Terrform creating is completed](./pictures/output%201.png)

## Nginx server is running
![Terrform creating is completed](./pictures/output%201.png)
