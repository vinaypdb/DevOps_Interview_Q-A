
### 🔨 Projects

---

### 📁 Project 1: LAMP Stack Setup on Ubuntu Servers

**Goal:** Automate the setup of a Linux + Apache + MySQL + PHP environment

**Tasks:**

* Install Apache, MySQL, PHP
* Configure virtual hosts
* Set firewall rules
* Start and enable services

**Tools:** `apt`, `service`, `template`, `copy`, `ufw`

---

### 📁 Project 2: Docker + Nginx Setup

**Goal:** Install Docker and deploy a static website using Nginx container

**Tasks:**

* Install Docker engine
* Pull Nginx image
* Run Nginx container
* Copy custom index.html

**Tools:** `apt`, `docker_container`, `copy`, `template`

---

### 📁 Project 3: Bootstrap Kubernetes Nodes

**Goal:** Prepare Ubuntu VMs for Kubernetes setup

**Tasks:**

* Disable swap
* Install containerd
* Load required kernel modules
* Setup kubeadm, kubelet, kubectl
* Enable IP forwarding

**Tools:** `shell`, `lineinfile`, `copy`, `apt`, `reboot`

---

### 📁 Project 4: Prometheus + Grafana Monitoring

**Goal:** Deploy Prometheus and Grafana using Ansible

**Tasks:**

* Download & install Prometheus
* Setup systemd service
* Install Grafana from repo
* Configure dashboards and scrape configs

**Tools:** `get_url`, `unarchive`, `template`, `service`, `yum`, `apt`

---

### 📁 Project 5: CI/CD Pipeline with Jenkins + Ansible

**Goal:** Use Jenkins and Ansible to build and deploy a sample app

**Tasks:**

* Setup Jenkins
* Install required plugins
* Configure Jenkins job
* Trigger Ansible playbook from Jenkins
* Deploy app on remote node using playbook

**Tools:** `git`, `jenkins_job`, `shell`, `command`, `service`

---

### ✅ Summary

These real-world projects will help you:

* Apply Ansible to automate real infrastructure
* Get comfortable with reusable playbooks and roles
* Integrate with tools like Docker, Kubernetes, and Jenkins
* Prepare for DevOps job scenarios

---
