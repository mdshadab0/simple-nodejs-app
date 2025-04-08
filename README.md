# 🚀 Simple Node.js App CI/CD Pipeline with Jenkins & Docker

This project demonstrates a complete CI/CD pipeline using **Jenkins (running in Docker)** to build and manage a **Node.js** app with Docker.

---

## ✅ Project Overview

The project includes:
- Node.js application source code.
- A `Dockerfile` to containerize the app.
- A `Jenkinsfile` defining the CI/CD pipeline.

All code files are available in this GitHub repository.

---

## 🔧 Setup Instructions

### 1. Run Jenkins in Docker

Make sure to run Jenkins with Docker socket mounting to allow Docker commands inside Jenkins.

### 2. Install Jenkins Plugins
- Docker Pipeline
- Git Plugin
- Pipeline

### 3. Configure GitHub Credentials in Jenkins

> 🔐 **Important Note: Do NOT directly use just the GitHub repository URL without credentials.**

Instead:

1. Go to **Jenkins → Manage Jenkins → Credentials → System → Global Credentials (unrestricted)**.
2. Click on **"Add Credentials"**.
   - **Kind**: `Username with password`
   - **Username**: Your GitHub username
   - **Password**: Your GitHub personal access token (not your password)
   - **ID**: (e.g., `github-creds`) — remember this ID
3. In your pipeline setup, **use this credentials ID** to access the repository securely.

### 4. Create a Jenkins Pipeline Job

- Go to Jenkins dashboard
- Click **"New Item" → Pipeline**
- Under **Pipeline script from SCM**:
  - SCM: `Git`
  - URL: `https://github.com/your-username/simple-app.git`
  - Credentials: Select the ID you created (e.g., `github-creds`)

---

## 📌 Notes

- This setup assumes Docker is installed and properly configured on the host machine.
- Jenkins should have access to Docker via volume mount: `/var/run/docker.sock:/var/run/docker.sock`
- If you get `docker: not found` errors inside Jenkins, it's likely due to:
  - Missing Docker socket mount
  - Permissions issue
  - Jenkins running in a container without Docker access

---

## 🙌 Acknowledgement

This is a learning project to practice DevOps tools like **Jenkins**, **Docker**, and **CI/CD** pipelines.

---
![Screenshot 2025-04-08 153705](https://github.com/user-attachments/assets/8cf361e0-7487-4416-a8ac-f6b6de873b56)

![Screenshot 2025-04-08 153149](https://github.com/user-attachments/assets/651c255a-3509-4b24-a9f4-58465ef34e70)
![Screenshot 2025-04-08 153136](https://github.com/user-attachments/assets/19c32c6e-8cbd-4bf7-8fac-26d278c57dd0)
![Screenshot 2025-04-08 152847](https://github.com/user-attachments/assets/09d055bb-ec50-461b-a9d0-2f5526edae08)
![Uploading Screenshot 2025-04-08 151841.png…]()
