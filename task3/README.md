## Objective
Provision a local Docker container running Nginx using Terraform.

## Tools Used
- Terraform
- Docker Desktop

## Deliverables
- main.tf (Terraform configuration)
- Execution logs
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
