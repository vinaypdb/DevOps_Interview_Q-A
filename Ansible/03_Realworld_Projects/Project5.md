
### 📁 Project 5: CI/CD Pipeline with Jenkins + Ansible

**🎯 Goal:** Build a CI/CD pipeline to deploy a sample application using Jenkins and Ansible.

### 📦 Components

* **Jenkins**: CI/CD server
* **Git**: Source control system
* **Ansible**: Used by Jenkins to deploy app
* **Sample App**: Simple web app in a Git repo

---

### 📂 Directory Structure

```
jenkins_ansible_ci_cd/
├── roles/
│   ├── jenkins/
│   │   └── tasks/main.yml
│   └── deploy_app/
│       └── tasks/main.yml
└── site.yml
```

---

### 📄 site.yml

```yaml
- name: Setup Jenkins CI/CD with Ansible
  hosts: jenkins
  become: yes
  roles:
    - jenkins
    - deploy_app
```

---

### 📄 jenkins/tasks/main.yml

```yaml
- name: Install Java
  apt:
    name: openjdk-11-jdk
    state: present

- name: Add Jenkins repo key
  apt_key:
    url: https://pkg.jenkins.io/debian-stable/jenkins.io.key
    state: present

- name: Add Jenkins repo
  apt_repository:
    repo: deb https://pkg.jenkins.io/debian-stable binary/
    state: present

- name: Install Jenkins
  apt:
    name: jenkins
    update_cache: yes
    state: present

- name: Enable and start Jenkins
  service:
    name: jenkins
    state: started
    enabled: yes
```

---

### 📄 deploy\_app/tasks/main.yml

```yaml
- name: Install Git
  apt:
    name: git
    state: present

- name: Clone sample app repo
  git:
    repo: 'https://github.com/example/sample-webapp.git'
    dest: /opt/sample-webapp

- name: Deploy app (copy index.html)
  copy:
    src: /opt/sample-webapp/index.html
    dest: /var/www/html/index.html
```

---

### ▶️ Jenkins Job Setup

1. Create a freestyle job
2. Configure Git repository URL
3. Add a post-build step to run:

```bash
ansible-playbook -i inventory.ini site.yml
```

---

### ✅ Expected Output

* Jenkins server up and running on port 8080
* Jenkins pulls code from Git
* Ansible deploys app to web server automatically

---
