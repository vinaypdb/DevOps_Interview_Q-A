
## 📗 Phase 1: Jenkins Basics

### 🎯 Objective

Understand what Jenkins is, how it works, and how to get started with your first jobs and configurations.

### 📚 Topics Covered

* What is Jenkins?
* Why Jenkins is used in CI/CD?
* Jenkins architecture overview
* Installing Jenkins (Ubuntu & Docker)
* Navigating Jenkins Web UI
* Setting up your first Freestyle project
* Installing and configuring plugins
* System and Global Tool Configuration
* Jenkins workspace and job folders

---

### 📌 What is Jenkins?

Jenkins is an open-source automation server used to automate parts of the software development process like:

* Building code
* Running tests
* Deploying applications

---

### 🚀 Why Jenkins in CI/CD?

* Automates the software delivery lifecycle (SDLC)
* Integrates with most DevOps tools
* Flexible (supports plugins, scripting, etc.)
* Open-source and widely adopted

---

### 🧱 Jenkins Architecture

* **Master (Controller)**: Orchestrates builds, schedules jobs
* **Agents (Slaves)**: Execute tasks/jobs as assigned by master
* Communication happens over SSH or other protocols

---

### 🛠️ Installing Jenkins

#### 🔹 Ubuntu (Deb Package)

```bash
sudo apt update
sudo apt install openjdk-11-jdk -y
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

Access Jenkins at `http://<your_ip>:8080`

#### 🔹 Docker

```bash
docker run -d \
  -p 8080:8080 -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  --name jenkins jenkins/jenkins:lts
```

---

### 🌐 Jenkins Web UI Tour

* **Dashboard**: List of jobs
* **New Item**: Create new jobs
* **Manage Jenkins**: System configuration
* **Build History**: Past builds
* **Credentials**: Store secrets
* **Plugins**: Extend Jenkins features

---

### 🛠️ Your First Freestyle Project

1. Click “New Item”
2. Name your job
3. Select “Freestyle project”
4. Configure build steps (e.g., Shell script)
5. Save and build manually

---

### 🔌 Installing & Managing Plugins

* Navigate to `Manage Jenkins → Plugins`
* Use Available tab to install common plugins:

  * Git plugin
  * Pipeline
  * Docker
  * Ansible

---

### ⚙️ System Configuration

* Global Tools Configuration:

  * Git path
  * JDK path
  * Maven/Gradle if needed

* System Settings:

  * Jenkins URL
  * Email notifications

---

### 📁 Jenkins Workspace & Jobs

* **Workspace**: `/var/lib/jenkins/workspace/<job_name>`
* **Job Configuration**: Stored in `/var/lib/jenkins/jobs/<job_name>`

---

### ✅ Summary

By the end of Phase 1, you should be able to:

* Understand Jenkins and its architecture
* Install Jenkins via APT or Docker
* Access and configure the Web UI
* Create and run basic freestyle jobs
* Install essential plugins

---
