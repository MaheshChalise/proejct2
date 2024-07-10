

# Toronto Time Web Application

This project deploys a Python web application using Docker and Kubernetes to display the current time in Toronto, Canada.

## Steps to Build and Run the Docker Container

1. **Build the Docker Image:**

   ```sh
   docker build -t toronto-time-app:latest .
Run the Docker Container
```
docker run -p 3030:3030 toronto-time-app:latest
```
Access the application at http://127.0.0.1:62006 in your web browser.

Steps to Deploy and Access the Application on Kubernetes
Deploy Kubernetes Resources:
```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```
Verify Deployment:
```
kubectl get deployments
kubectl get services
```
Ensure the toronto-time-deployment and toronto-time-service are running.
Access the Application:
Use Minikube to access the application via NodePort:
```
minikube service toronto-time-service
```
This will open the application in your default web browser using NodePort 30300, which forwards traffic to port 3030 of your application.


Challenges Faced and Solutions;
Issue with Docker CLI context on Windows:
When using Minikube, encountered an error related to Docker CLI context not found.

Solution: Ensure Docker and Minikube are properly configured and running in the same terminal session.

Deployment YAML issues:
Initially faced errors in the deployment.yaml file related to indentation and syntax.

Solution: Debugged YAML file and corrected indentation errors.
```
This README.md file now correctly specifies port `3030` for the application and port `30300` for NodePort in Kubernetes.
```
