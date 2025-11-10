# 🚀 Flask Application CI/CD Pipeline using Jenkins & Docker on AWS EC2

This project demonstrates a **complete end-to-end CI/CD pipeline** where every code change pushed to **GitHub** automatically triggers a deployment pipeline in **Jenkins**, which then **builds and runs a Docker container** on an **AWS EC2** instance.  
This ensures **zero manual deployment steps**, delivering a production-style automated delivery workflow.

---

## 🏗️ Architecture Overview

Developer → Push Code → GitHub → Webhook Trigger → Jenkins Pipeline → Docker Build & Run → Live App on EC2


| Component | Purpose |
|----------|----------|
| **Python + Flask** | Web application backend |
| **GitHub** | Source code management |
| **Jenkins** | CI/CD automation |
| **Docker** | Containerization |
| **AWS EC2 (Amazon Linux 2)** | Server hosting Jenkins + Application |

---

## 📂 Project Structure

flask-demo/
│
├── app.py # Application source code
├── requirements.txt # Python dependencies
├── Dockerfile # Docker image build instructions
└── README.md # Project documentation


---


## 🔔 GitHub Webhook (Automatic Build Setup)

This allows Jenkins to start the build when you push to GitHub.

### 1) Webhook URL
Copy your Jenkins webhook URL:

http://44.201.180.147:8080/github-webhook/


### 2) Add Webhook in GitHub
Go to:
**GitHub → Repo → Settings → Webhooks → Add Webhook**

Fill:
- **Payload URL:** `http://:8080/github-webhook/`
- **Content type:** `application/json`
- Select: **Just the push event**
- Click **Add Webhook**

### 3) Enable in Jenkins
Go to:
**Jenkins → Job → Configure → Build Triggers**

Check:

Jenkins will **start automatically** ✅
GitHub hook trigger for GITScm polling : Save.

### 4) Test
Make any code change → commit → push:
git add .
git commit -m "test"
git push



Jenkins will **start automatically** ✅


