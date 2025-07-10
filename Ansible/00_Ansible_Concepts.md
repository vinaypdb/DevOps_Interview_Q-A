# Ansible: Simple to Advanced Guide

## 🧰 What is Ansible?

**Ansible** is an open-source **automation tool** used for **configuration management**, **application deployment**, **task automation**, and **orchestration**. It uses simple YAML syntax in **playbooks** and operates agentlessly over SSH.

---

## 🧠 Why Use Ansible?

* ✅ Agentless: Uses SSH, no software needs to be installed on target systems
* ✅ Simple YAML syntax: Human-readable playbooks
* ✅ Scalable: Manage thousands of servers with one playbook
* ✅ Idempotent: Safe to run repeatedly without unintended effects
* ✅ Extensible: Supports plugins, roles, modules

---

## ⚙️ Core Concepts of Ansible

### 1. **Inventory**

* Defines the list of hosts or groups of hosts to manage
* Example:

  ```ini
  [webservers]
  server1.example.com
  server2.example.com
  ```

### 2. **Modules**

* Perform tasks like installing packages, managing files, etc.
* Run via `ansible` or in playbooks
* Example:

  ```yaml
  - name: Install nginx
    ansible.builtin.yum:
      name: nginx
      state: present
  ```

### 3. **Playbooks**

* YAML files defining tasks and configurations
* Declarative, repeatable, human-readable
* Example:

  ```yaml
  - hosts: webservers
    tasks:
      - name: Ensure Nginx is installed
        ansible.builtin.yum:
          name: nginx
          state: present
  ```

### 4. **Tasks and Handlers**

* **Tasks** are executed in order
* **Handlers** run when notified (e.g., restart service)
* Example:

  ```yaml
  handlers:
    - name: restart nginx
      ansible.builtin.service:
        name: nginx
        state: restarted
  ```

### 5. **Variables**

* Define values dynamically based on host/group/environment
* Sources: Inventory, command line, playbooks, external files

### 6. **Facts**

* Automatically gathered system information (e.g., OS, IP, memory)
* Accessible via `ansible_facts` variable

### 7. **Roles**

* Pre-structured reusable units with tasks, handlers, templates, files
* Directory structure simplifies code reuse and organization

### 8. **Templates**

* Use **Jinja2** to dynamically generate config files
* Example:

  ```yaml
  - name: Generate config
    ansible.builtin.template:
      src: nginx.conf.j2
      dest: /etc/nginx/nginx.conf
  ```

### 9. **Conditionals & Loops**

* Add logic using `when`, `with_items`, `loop`
* Example:

  ```yaml
  - name: Install multiple packages
    ansible.builtin.yum:
      name: "{{ item }}"
      state: present
    loop:
      - nginx
      - git
  ```

### 10. **Ansible Galaxy**

* Public hub of Ansible roles and collections
* Use roles shared by community and organizations
* Install with:

  ```sh
  ansible-galaxy install <role_name>
  ```

### 11. **Ansible Vault**

* Encrypt secrets like passwords, keys
* Commands:

  ```sh
  ansible-vault encrypt secret.yml
  ansible-vault decrypt secret.yml
  ansible-vault edit secret.yml
  ```

### 12. **Command Summary**

| Command             | Purpose                       |
| ------------------- | ----------------------------- |
| `ansible`           | Run ad-hoc commands           |
| `ansible-playbook`  | Execute playbooks             |
| `ansible-galaxy`    | Install/download roles        |
| `ansible-vault`     | Encrypt/decrypt/edit secrets  |
| `ansible-doc`       | Show module documentation     |
| `ansible-inventory` | View/manage inventory details |

---

## 🚀 Advanced Ansible Concepts

### 🔀 Dynamic Inventory

* Pulls inventory from external sources (e.g., AWS, GCP)
* Supports JSON format or scripts
* Example: `inventory/aws_ec2.yaml` using `boto`

### 🔧 Custom Modules & Plugins

* Extend Ansible with custom Python modules or plugins
* Types: action, connection, callback, lookup, inventory

### 🧪 Testing with Molecule

* Molecule + Testinfra used for role and playbook testing
* Local Docker-based or remote system testing

### 🔐 Ansible in DevSecOps

* Combine Vault with roles for secure secrets
* Integrate security tools like Trivy or OpenSCAP
* Automate compliance with Ansible + OPA

### 📦 Collections

* Distribute roles, plugins, modules together
* Installed with `ansible-galaxy collection install`

### 📈 Performance Tuning

* Use `forks` in `ansible.cfg` to parallelize execution
* Disable fact gathering for speedup

---

## ☁️ Ansible + Cloud & CI/CD

* Use Ansible in Jenkins, GitHub Actions, GitLab pipelines
* Provision cloud infra (AWS EC2, Azure VMs, GCP) using dynamic inventory
* Integrate with Terraform or Packer in automation workflows

---

## ✅ Summary

Ansible is a powerful, agentless automation tool that simplifies configuration management and deployment across systems. Its flexibility and support for DevOps pipelines and cloud platforms make it ideal for both small scripts and large-scale enterprise workflows.

