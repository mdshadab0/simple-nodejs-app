
# Simple Node.js App CI/CD with Jenkins and Docker

This project sets up a complete CI/CD pipeline using Jenkins to automate the build, test, and deployment of a simple Node.js application. The pipeline is defined using a `Jenkinsfile` and is triggered automatically on each code commit to the GitHub repository.

---

## 📦 Project Overview

- **App Type:** Simple Node.js application
- **CI/CD Tool:** Jenkins
- **Containerization:** Docker
- **Source Code:** GitHub
- **Build Trigger:** Webhook from GitHub to Jenkins

---

## 🔧 Project Setup Steps

### 1. Install & Setup Jenkins

- Installed Jenkins (locally or in Docker)
- Installed required plugins:
  - Git Plugin
  - GitHub Integration
  - Docker Pipeline

### 2. Clone This Repo

```bash
git clone https://github.com/your-username/simple-node-app.git
cd simple-node-app
```

---

## 🔐 GitHub Credentials in Jenkins

> ⚠️ **Important:** Do not rely on only the GitHub repo URL in Jenkins. You must configure proper credentials.

### Steps:

1. Go to **Jenkins → Manage Jenkins → Credentials**
2. Add your **GitHub Username and Personal Access Token** as credentials
3. In your Jenkins job:
   - Choose **Git** as the SCM
   - Set the repo URL (HTTPS)
   - Select the credential you created.

---

## 🐳 Docker Configuration

- Make sure Docker is installed and the Jenkins user has access to Docker.
- If Jenkins is running inside a container, Docker must also be available **inside** the container (Docker-in-Docker or mounting Docker socket).

---

## 📝 Jenkinsfile

The `Jenkinsfile` in the repo defines the following stages:
- **Build** – builds Docker image
- **Test** – (can be customized)
- **Deploy** – runs the container

---

## 🔁 GitHub Webhook

To trigger Jenkins on every commit:
1. Go to your GitHub repo → Settings → Webhooks
2. Add this URL:

```
http://<your-ngrok-or-public-IP>/github-webhook/
```

3. Set content type to `application/json`
4. Leave **secret field blank** or set if using with Jenkins credentials plugin
5. Make sure your Jenkins job has the trigger:
   - ☑️ GitHub hook trigger for GITScm polling

---

## ✅ Testing the Pipeline

- Commit and push a change to GitHub
- Confirm webhook is delivered successfully
- Jenkins pipeline should start automatically

---

## 📌 Note on GitHub Actions

> If GitHub Actions are running instead of Jenkins:
- Ensure that Jenkins webhook is hitting `/github-webhook/`
- Ensure `Jenkinsfile` is not confused with `.github/workflows/*`
- Disable GitHub Actions if not needed to avoid confusion

---

## 📸 Screenshots

Include images of:
- Jenkins dashboard
- Build stages
- Docker image created
- GitHub webhook delivery success

---

## 📁 Repository

Source code and `Jenkinsfile` are available here:  
👉 [GitHub Repository](https://github.com/your-username/simple-node-app)

---

## 🙌 Credits


![Screenshot 2025-04-08 153149](https://github.com/user-attachments/assets/651c255a-3509-4b24-a9f4-58465ef34e70)
![Screenshot 2025-04-08 153136](https://github.com/user-attachments/assets/19c32c6e-8cbd-4bf7-8fac-26d278c57dd0)
![Screenshot 2025-04-08 152847](https://github.com/user-attachments/assets/09d055bb-ec50-461b-a9d0-2f5526edae08)
![Uploading Screenshot 2025-04-08 151841.png…]()
