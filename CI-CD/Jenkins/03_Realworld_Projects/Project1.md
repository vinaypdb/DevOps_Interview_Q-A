

### 📁 Project 1: CI/CD Pipeline for a Node.js App

**🎯 Goal:** Automate the build, test, and deployment process of a Node.js application hosted on GitHub using Jenkins.

### 📦 Components

* **Node.js App**: Sample Express-based web app
* **GitHub**: Source code repository
* **Jenkins**: Pipeline orchestration
* **Target Host**: A remote Ubuntu server (for deployment)

---

### 📂 Directory Structure

```
nodejs-ci-cd/
├── Jenkinsfile
├── app/
│   ├── index.js
│   ├── package.json
│   └── test/
│       └── test.js
```

---

### 📄 Jenkinsfile

```groovy
pipeline {
  agent any

  environment {
    NODE_ENV = 'production'
    DEPLOY_USER = 'ubuntu'
    DEPLOY_HOST = 'your.remote.host'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/youruser/sample-nodejs-app.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }

    stage('Build') {
      steps {
        echo 'Node.js does not need build step, skipping...'
      }
    }

    stage('Deploy') {
      steps {
        sshagent(['my-ssh-key']) {
          sh 'scp -r * $DEPLOY_USER@$DEPLOY_HOST:/var/www/nodeapp'
        }
      }
    }
  }
}
```

---

### 🛠️ Setup Steps

1. Install Node.js on Jenkins agent:

```bash
sudo apt install nodejs npm -y
```

2. Add GitHub project webhook to trigger job
3. Configure SSH credentials in Jenkins (for deployment)
4. Create a freestyle or pipeline job
5. Use Jenkinsfile from source repo

---

### ✅ Expected Output

* Jenkins fetches latest code from GitHub
* Runs `npm install` and `npm test`
* Deploys to remote server on success

---
