# Kubernetes Multi-Tier Web Application Deployment

This project demonstrates a multi-tier web application deployed on a local Kubernetes cluster using MicroK8s. It includes:

- **Frontend:** NGINX serving static files
- **Backend:** Flask app connecting to MongoDB
- **Database:** MongoDB instance
- **Additional:** CronJob to clean logs periodically

  
## Project Architecture
Frontend: Built using NGINX to serve a static UI.

Backend: A Flask application that handles business logic and communicates with MongoDB.

Database: MongoDB is used to persist and manage application data.

All components are containerized and run in separate pods managed by Kubernetes. The application uses:

ClusterIP services for internal communication between backend and database.

NodePort service to expose the frontend to external users.

## What’s Been Done
### Containerization:

Created Docker images for each tier (frontend, backend, MongoDB).

Saved and loaded these images into MicroK8s to avoid external pulls.

### Kubernetes Setup:

Defined deployments for each component using YAML files.

Configured services for internal and external communication.

Used imagePullPolicy: Never to use locally available images.

### Connectivity:

MongoDB was exposed via a ClusterIP to backend only (secured).

Frontend exposed via NodePort allowing access in a browser.

### Log Cleanup:

Implemented a CronJob that runs at regular intervals to clean up log files in pods.

## How to Access the App
Visit the frontend using your browser:

php-template
Copy
Edit
http://<your-node-ip>:<node-port>
Example: http://localhost:30007

The backend interacts with MongoDB internally via a ClusterIP service.

## Files in the Repo
frontend.yaml, backend.yaml, mongodb.yaml: Define deployments.

*.service.yaml: Define services to expose deployments.

README.md: You’re reading it.









