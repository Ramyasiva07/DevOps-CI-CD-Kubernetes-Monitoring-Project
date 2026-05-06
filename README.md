🚀 DevOps CI/CD Kubernetes Project

📌 Project Overview

This project demonstrates a complete CI/CD pipeline using:

- GitHub (Source Code)
- Jenkins (CI/CD)
- Docker (Containerization)
- Kubernetes (Deployment using Minikube)
- Ngrok (Expose Jenkins to GitHub Webhook)

---

🛠️ Tools & Technologies

- GitHub
- Jenkins
- Docker
- Kubernetes (Minikube)
- Ngrok
- Python (Flask App)

---

🔁 CI/CD Flow

1. Developer pushes code to GitHub
2. GitHub Webhook triggers Jenkins
3. Jenkins pipeline:
   - Builds Docker image
   - Pushes image to Docker Hub
   - Deploys to Kubernetes
4. Kubernetes updates the application
5. Application is accessible via service

---

⚙️ Jenkins Setup

1. Start Jenkins

- Open: http://localhost:8080

2. Expose Jenkins using Ngrok

ngrok http 8080

Copy URL and add to GitHub webhook:

https://<ngrok-url>/github-webhook/

---

🐳 Docker Commands

docker build -t ramyasiva07/portfolio:latest .
docker push ramyasiva07/portfolio:latest

---

☸️ Kubernetes Commands

Start Minikube:

minikube start

Apply manifests:

kubectl apply -f k8s/

Restart deployment:

kubectl rollout restart deployment portfolio

Access service:

minikube service portfolio-service

---

🔄 Restart Workflow

After system restart:

minikube start
kubectl apply -f k8s/
minikube service portfolio-service

Start Jenkins and Ngrok again.

---

🔐 Credentials Used

- Docker Hub credentials stored in Jenkins
- Used for secure login and image push

---

📡 Webhook Trigger

GitHub webhook is used to automatically trigger Jenkins pipeline on every code push.

---

📌 Notes

- Ngrok URL changes every time → update webhook
- Minikube runs locally → needs restart after shutdown
- This setup is for local development/demo

---

🌍 Future Improvements

- Deploy on AWS EKS
- Use LoadBalancer instead of NodePort
- Add monitoring using Prometheus & Grafana

---

🎯 Conclusion

This project demonstrates a real-time DevOps workflow including CI/CD automation, containerization, and Kubernetes deployment.

---
