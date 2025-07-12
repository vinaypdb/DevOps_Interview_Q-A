

### 📁 Project 4: Jenkins + Ansible for Infra Automation

**🎯 Goal:** Use Jenkins to automate infrastructure provisioning and application deployment with Ansible.

### 📦 Components

* **Jenkins**: Automation server
* **Ansible**: Infrastructure provisioning and app setup
* **SSH Credentials**: For remote connection
* **Sample Ansible Playbook**: Hosted in Git repository

---

### 📂 Directory Structure

```
jenkins-ansible-infra/
├── Jenkinsfile
├── playbooks/
│   └── site.yml
├── inventory/
│   └── hosts.ini
```

---

### 📄 Jenkinsfile

```groovy
pipeline {
  agent any

  environment {
    ANSIBLE_HOME = '/usr/bin/ansible-playbook'
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/youruser/ansible-infra-deploy.git'
      }
    }

    stage('Run Ansible Playbook') {
      steps {
        sshagent(['remote-ssh-key']) {
          sh 'ansible-playbook -i inventory/hosts.ini playbooks/site.yml'
        }
      }
    }
  }
}
```

---

### 📄 site.yml (Sample)

```yaml
- name: Setup Apache Web Server
  hosts: web
  become: true
  tasks:
    - name: Install Apache
      apt:
        name: apache2
        state: present
        update_cache: yes

    - name: Start Apache
      service:
        name: apache2
        state: started
        enabled: yes
```

---

### 🛠️ Setup Steps

1. Install Ansible on Jenkins agent:

```bash
sudo apt install ansible -y
```

2. Add remote SSH key in Jenkins credentials
3. Clone repo with playbook in Jenkins job
4. Configure Jenkins pipeline to execute Ansible

---

### ✅ Expected Output

* Jenkins checks out Ansible repo
* Runs playbook to install and start Apache on target node
* Logs show success/failure of each task

---
