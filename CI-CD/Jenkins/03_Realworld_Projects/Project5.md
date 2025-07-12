
### 📁 Project 5: Jenkins + Kubernetes Deployment (Helm + Argo CD)

**🎯 Goal:** Automate containerized application deployment to a Kubernetes cluster using Jenkins, Helm, and Argo CD.

### 📦 Components

* **Docker**: Build app image
* **Helm**: Manage Kubernetes manifests
* **Argo CD**: GitOps tool to sync Helm charts
* **Kubernetes Cluster**: EKS/Minikube target
* **Jenkins**: Automates build, push, deploy

---

### 📂 Directory Structure

```
k8s-deploy-pipeline/
├── Jenkinsfile
├── Dockerfile
├── app/
│   └── main.go
├── helm-chart/
│   └── birthdaymate/
│       ├── Chart.yaml
│       └── templates/
│           └── deployment.yaml
```

---

### 📄 Jenkinsfile

```groovy
pipeline {
  agent any

  environment {
    IMAGE_NAME = 'yourdockerhubuser/birthdaymate:latest'
    CHART_REPO = 'https://github.com/youruser/birthdaymate-infra.git'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/youruser/birthdaymate-app.git'
      }
    }

    stage('Build Image') {
      steps {
        sh 'docker build -t $IMAGE_NAME .'
      }
    }

    stage('Push Image') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
          sh '''
            echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
            docker push $IMAGE_NAME
          '''
        }
      }
    }

    stage('Update Helm Chart') {
      steps {
        sshagent(['github-ssh']) {
          sh '''
            git clone $CHART_REPO
            cd birthdaymate-infra/helm-chart/birthdaymate/templates
            sed -i 's|image:.*|image: $IMAGE_NAME|' deployment.yaml
            git commit -am "Update image tag"
            git push
          '''
        }
      }
    }
  }
}
```

---

### 🛠️ Setup Steps

1. Configure Docker on Jenkins agent
2. Install `kubectl`, `helm`, and `argo` CLI tools
3. Setup Argo CD to auto-sync the Helm chart repo
4. Create GitHub SSH and Docker Hub credentials in Jenkins

---

### ✅ Expected Output

* Jenkins builds and pushes the app image
* Helm chart is updated and committed to Git repo
* Argo CD syncs new version and deploys to cluster
* App is live on Kubernetes

---

