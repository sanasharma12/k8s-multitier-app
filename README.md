Multi-Tier Web Application on Kubernetes 🚀
This project showcases a full-stack web application deployed on Kubernetes using MicroK8s. It includes a frontend (NGINX), a backend (Flask), and a MongoDB database, all containerized and orchestrated using Kubernetes deployments and services.

🧱 Project Architecture
Frontend: Built using NGINX to serve a static UI.

Backend: A Flask application that handles business logic and communicates with MongoDB.

Database: MongoDB is used to persist and manage application data.

All components are containerized and run in separate pods managed by Kubernetes. The application uses:

ClusterIP services for internal communication between backend and database.

NodePort service to expose the frontend to external users.

⚙️ What’s Been Done
Containerization:

Created Docker images for each tier (frontend, backend, MongoDB).

Saved and loaded these images into MicroK8s to avoid external pulls.

Kubernetes Setup:

Defined deployments for each component using YAML files.

Configured services for internal and external communication.

Used imagePullPolicy: Never to use locally available images.

Connectivity:

MongoDB was exposed via a ClusterIP to backend only (secured).

Frontend exposed via NodePort allowing access in a browser.

Log Cleanup:

Implemented a CronJob that runs at regular intervals to clean up log files in pods.

🧪 How to Access the App
Visit the frontend using your browser:

php-template
Copy
Edit
http://<your-node-ip>:<node-port>
Example: http://localhost:30007

The backend interacts with MongoDB internally via a ClusterIP service.

🧠 What I Learned
Hands-on with Kubernetes concepts: Pods, Services, Deployments, CronJobs.

Image management within a closed MicroK8s environment.

Managing inter-container communication.

Debugging issues like ImagePullBackOff, ErrImageNeverPull, and service misconfigurations.

📁 Files in the Repo
frontend.yaml, backend.yaml, mongodb.yaml: Define deployments.

*.service.yaml: Define services to expose deployments.

log-cleaner-cron.yaml: Sets up the log cleaner CronJob.

README.md: You’re reading it.

🧼 Cleanup Commands (If Needed)
Just in case you want to tear everything down:

bash
Copy
Edit
microk8s kubectl delete -f .








