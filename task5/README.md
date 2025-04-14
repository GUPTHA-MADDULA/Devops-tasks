# Deploying a Dockerized App on Kubernetes with Minikube and Run Nginx 
---

## 1. Introduction  
This project demonstrates how to:  
1.1. Build a Docker image for your application.  
1.2. Use Minikube to set up a local Kubernetes cluster.  
1.3. Deploy the application on Kubernetes using `kubectl`.  
1.4. Expose the app and access it via a local URL.

## 2. Prerequisites  
Make sure the following are installed on your system:  
2.1. Docker – for building the image.  
2.2. Minikube – to run a local Kubernetes cluster.  
2.3. kubectl – the Kubernetes CLI tool.

## 3. Docker Image Setup  
3.1. Navigate to the project directory containing the Dockerfile.  
3.2. Build your image using Docker.  
3.3. Optionally, run the Docker container to test it locally.

## 4. Minikube Setup  
4.1. Start Minikube using the `minikube start` command.  
4.2. If you're building the Docker image inside Minikube, point Docker to Minikube’s environment.  
4.3. Rebuild the Docker image so it's accessible to Minikube.

## 5. Kubernetes Deployment  
5.1. Create a Kubernetes deployment YAML file (e.g., `deployment.yaml`) for your app.  
5.2. Apply the configuration using `kubectl apply -f deployment.yaml`.  
5.3. Verify that the deployment and pods are running using `kubectl get deployments` and `kubectl get pods`.

![Kubernetes Pods Information](./Pictures/Kubernetes%20output.png)

## 6. Exposing the App  
6.1. Create a service to expose your app using NodePort.  
6.2. Use `kubectl expose deployment` to expose the app.  
6.3. Use `minikube service <service-name> --url` to get the access URL.  
6.4. Open the app in your browser using the URL provided.
![Nginx Server Running](./Pictures/Nginx%20server.png)

## 7. Cleanup Process  
7.1. To delete the deployment and service, use `kubectl delete`.  
7.2. Stop the Minikube cluster when finished using `minikube stop`.  
7.3. Optionally, delete the Minikube cluster with `minikube delete`.

## 8. Conclusion  
This guide covers the full lifecycle of containerizing an app and running it on a Kubernetes cluster locally using Minikube. It’s a practical way to understand cloud-native development and DevOps workflows on your local machine.

---
