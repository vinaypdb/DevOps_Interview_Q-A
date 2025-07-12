
### 📁 Project 3: Jenkins + SonarQube for Code Quality

**🎯 Goal:** Analyze source code using SonarQube during Jenkins builds for quality assurance.

### 📦 Components

* **SonarQube Server**: Local or remote code analysis server
* **SonarQube Plugin**: Installed in Jenkins
* **Sonar Scanner**: CLI tool for analyzing code
* **Jenkins Pipeline**: Integrates analysis with CI/CD

---

### 📂 Directory Structure

```
sonarqube-ci/
├── Jenkinsfile
├── sonar-project.properties
├── app/
│   └── main.js
```

---

### 📄 sonar-project.properties

```properties
sonar.projectKey=my-node-app
sonar.projectName=My Node.js App
sonar.projectVersion=1.0
sonar.sources=.
sonar.language=js
sonar.sourceEncoding=UTF-8
```

---

### 📄 Jenkinsfile

```groovy
pipeline {
  agent any

  environment {
    SONAR_SCANNER_HOME = tool 'SonarScanner'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/youruser/my-nodejs-app.git'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv('MySonarQube') {
          sh "${SONAR_SCANNER_HOME}/bin/sonar-scanner"
        }
      }
    }
  }
}
```

---

### 🛠️ Setup Steps

1. Run SonarQube (local or Docker):

```bash
docker run -d --name sonarqube -p 9000:9000 sonarqube:lts
```

2. Install **SonarQube Scanner Plugin** in Jenkins
3. Configure SonarQube server in Jenkins:

   * Manage Jenkins → Configure System → SonarQube Servers
4. Add SonarScanner to Jenkins Tools
5. Create token from SonarQube UI and use as Jenkins credentials if needed

---

### ✅ Expected Output

* Jenkins scans code via SonarQube
* Results visible in SonarQube UI ([http://localhost:9000](http://localhost:9000))
* Code smells, bugs, duplications highlighted

---

