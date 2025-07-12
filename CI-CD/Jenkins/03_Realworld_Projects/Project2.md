
### 📁 Project 1: CI/CD Pipeline for a Node.js App

...\[Project 1 Content]...

---

### 📁 Project 2: Docker Image Build and Push using Jenkins

**🎯 Goal:** Use Jenkins to build a Docker image for an application and push it to Docker Hub.

### 📦 Components

* **Dockerfile**: Defines image build instructions
* **Docker Hub**: Container registry for storing images
* **Jenkins**: Executes pipeline to build and push
* **Credentials**: Docker Hub credentials in Jenkins

---

### 📂 Directory Structure

```
docker-ci/
├── Dockerfile
├── app/
│   └── index.html
├── Jenkinsfile
```

---

### 📄 Jenkinsfile

```groovy
pipeline {
  agent any

  environment {
    IMAGE_NAME = 'yourdockerhubuser/myapp:latest'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/youruser/docker-web-app.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          docker.build("$IMAGE_NAME")
        }
      }
    }

    stage('Push to Docker Hub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
          sh '''
            echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
            docker push $IMAGE_NAME
          '''
        }
      }
    }
  }
}
```

---

### 🛠️ Setup Steps

1. Install Docker on Jenkins agent
2. Add Docker Hub credentials in Jenkins → Manage Credentials
3. Configure pipeline project using Jenkinsfile from GitHub repo

---

### ✅ Expected Output

* Jenkins builds a Docker image from Dockerfile
* Logs into Docker Hub
* Pushes image to Docker Hub repo

---
