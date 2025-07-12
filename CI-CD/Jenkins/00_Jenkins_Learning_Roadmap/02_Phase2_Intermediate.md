

## 📘 Phase 2: Intermediate Jenkins

### 🎯 Objective

Learn how to write Jenkins Pipelines, manage credentials, integrate Git, and build production-level automation.

### 📚 Topics Covered

* Freestyle vs Pipeline Jobs
* Declarative vs Scripted Pipelines
* Writing Jenkinsfiles (Pipeline as Code)
* Environment Variables & Parameters
* Credentials Management
* GitHub/GitLab Integration
* Build Triggers: Webhooks, Poll SCM, Cron
* Jenkins Agent Setup
* Email Notifications
* Securing Jenkins

---

### 🔁 Freestyle vs Pipeline Jobs

* **Freestyle Job**: UI-based, simple configuration
* **Pipeline Job**: Code-based using `Jenkinsfile`, better for complex CI/CD

---

### 📝 Jenkinsfile

#### 🔹 Declarative Example

```groovy
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
```

#### 🔹 Scripted Example

```groovy
node {
  stage('Build') {
    echo 'Building...'
  }
  stage('Test') {
    echo 'Testing...'
  }
  stage('Deploy') {
    echo 'Deploying...'
  }
}
```

---

### 🌐 Git Integration

* Add Git plugin
* Create GitHub PAT (Personal Access Token)
* Use credentials ID inside pipeline:

```groovy
environment {
  GIT_TOKEN = credentials('github_token')
}
```

---

### 🔐 Credentials Management

* Navigate: **Manage Jenkins → Credentials**
* Add credentials (secret text, SSH, username/password)
* Access using `credentials()` in Jenkinsfile

---

### 🔄 Build Triggers

* **Poll SCM**: `H/5 * * * *` → every 5 min
* **Webhooks** from GitHub/GitLab
* **Cron Jobs**: Scheduled builds

---

### 🤖 Jenkins Agents (Nodes)

* Add node in: **Manage Jenkins → Manage Nodes**
* Configure SSH or JNLP connection
* Use `agent { label 'my-node' }` in Jenkinsfile

---

### ✉️ Email Notifications

Install plugin:

* **Email Extension Plugin**

Basic config in Jenkinsfile:

```groovy
post {
  failure {
    mail to: 'admin@example.com', subject: 'Build Failed', body: 'Check Jenkins'
  }
}
```

---

### 🔒 Securing Jenkins

* Enable **Matrix-based security**
* Add users and roles
* Install **Role Strategy Plugin**
* Enable HTTPS using reverse proxy or native setup

---

### ✅ Summary

By end of Phase 2, you’ll be able to:

* Write complex Jenkins pipelines
* Secure credentials and Jenkins UI
* Automate Git-integrated CI/CD
* Run builds on multiple agents
* Configure notifications and triggers

---
