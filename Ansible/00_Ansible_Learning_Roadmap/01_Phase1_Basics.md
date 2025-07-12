# 📘 Ansible Learning Phases

## ✅ Overview

This document outlines the 3 structured phases to learn and master Ansible, from beginner to advanced level with real-world project implementations.

---

## 📗 Phase 1: Ansible Basics

### 🎯 Objective

Gain a solid foundation in Ansible — understand how it works and start writing basic playbooks to automate infrastructure.

### 📚 Topics Covered

* ✅ What is Ansible?
* ✅ How Ansible Works (Architecture)
* ✅ Inventory Files (Static & Dynamic)
* ✅ Ad-Hoc Commands
* ✅ YAML Basics & Playbook Structure
* ✅ Common Ansible Modules
* ✅ Variables and Facts
* ✅ Handlers
* ✅ Basic Role Structure

---

### 🔍 What is Ansible?

Ansible is an open-source automation tool used for:

* Configuration management
* Application deployment
* Task automation
* Infrastructure as Code (IaC)

**Key features:**

* Agentless (works over SSH)
* Idempotent (safe to run multiple times)
* Declarative YAML-based syntax

---

### ⚙️ How Ansible Works

* **Control Node:** The system from which you run Ansible
* **Managed Nodes:** Target systems (e.g., servers, VMs)
* Communicates via **SSH** or **WinRM**
* Uses **Inventory** to define target systems

---

### 🗂️ Inventory Files

Inventory lists target machines:

**Static Example:**

```ini
[web]
192.168.1.10
192.168.1.11

group1 ansible_host=10.0.0.1 ansible_user=ubuntu
```

**Dynamic Example:**
Use scripts or plugins (e.g., AWS EC2 plugin) to generate inventory on the fly.

---

### ⚡ Ad-Hoc Commands

Quick tasks without writing playbooks:

```bash
ansible all -i hosts -m ping
ansible web -m shell -a 'uptime'
ansible web -m yum -a 'name=nginx state=latest'
```

---

### 🧾 YAML & Playbooks

Ansible Playbooks are YAML files used to define desired configurations:

```yaml
- name: Install nginx
  hosts: web
  become: yes
  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present
```

---

### 🧰 Modules

Modules are units of work Ansible executes:

* **Package Management:** `apt`, `yum`, `dnf`
* **File Ops:** `copy`, `template`, `file`
* **Service Management:** `service`, `systemd`
* **Command Execution:** `command`, `shell`, `raw`

Example:

```yaml
- name: Start nginx
  service:
    name: nginx
    state: started
```

---

### 🔧 Variables and Facts

* Variables: User-defined or group/host level
* Facts: System info gathered automatically (`ansible_facts`)

Example:

```yaml
vars:
  http_port: 80
```

Use in playbook:

```yaml
port: "{{ http_port }}"
```

---

### 🔁 Handlers

Triggered when a task changes:

```yaml
- name: Restart nginx
  service:
    name: nginx
    state: restarted
  when: nginx_status.changed
```

Or:

```yaml
handlers:
  - name: restart nginx
    service:
      name: nginx
      state: restarted

tasks:
  - name: Update config
    template:
      src: nginx.conf.j2
      dest: /etc/nginx/nginx.conf
    notify: restart nginx
```

---

### 📦 Basic Role Structure

```
my-role/
├── defaults/main.yml
├── files/
├── handlers/main.yml
├── meta/main.yml
├── tasks/main.yml
├── templates/
└── vars/main.yml
```

Use roles for reusable playbooks.

Run with:

```yaml
- hosts: web
  roles:
    - my-role
```

---

### ✅ Summary

By the end of Phase 1, you should be able to:

* Run ad-hoc tasks
* Write playbooks to automate installations
* Use variables, handlers, and modules
* Understand inventory files
* Organize tasks into basic roles

---

