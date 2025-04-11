# Task 3: Infrastructure as Code (IaC) with Terraform

## Objective
Provision a local Docker container running Nginx using Terraform.

## Tools Used
- Terraform
- Docker Desktop

## Deliverables
- main.tf (Terraform configuration)
- Execution logs
- Screenshot of the running container

---

## Steps to Execute

- Navigate to the working directory:
 `cd task3/`

- Initialize Terraform:
 `terraform init`

- Apply the Terraform configuration:
`terraform apply -auto-approve`


- Verify the container:
- Run `docker ps` to check the container status
- Open `http://localhost:8080` in a browser to confirm Nginx is running


- Check Terraform-managed resources:
`terraform destroy -auto-approve`

---

---

## Learnings

- Learned to provision Docker containers using Terraform with the Docker provider.  
- Understood key Terraform commands like `init`, `plan`, `apply`, and `destroy`.  
- Gained hands-on experience writing and executing Terraform configurations.  
- Verified Nginx deployment by accessing it through `http://localhost:8080`.  

---