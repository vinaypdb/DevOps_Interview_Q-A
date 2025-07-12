

## 📘 Phase 2: Intermediate Ansible

### 🎯 Objective

Deepen your Ansible skills by learning dynamic automation, secure secrets management, reusable roles, and improved error handling.

### 📚 Topics Covered

* Jinja2 Templating
* Loops and Conditionals
* Tags and Selective Task Execution
* Ansible Vault (Secrets Management)
* Error Handling and Debugging
* Advanced Role Structuring
* Dynamic Inventory (e.g., AWS EC2)
* Ansible Pull (Pull Mode)
* Ansible Galaxy (Using Community Roles)

---

### 🧩 Jinja2 Templating

Use templating in configuration files:

```jinja
server_name {{ inventory_hostname }};
listen {{ http_port }};
```

**Module:** `template`

```yaml
- name: Deploy Nginx config
  template:
    src: nginx.conf.j2
    dest: /etc/nginx/nginx.conf
```

---

### 🔁 Loops and Conditionals

**Loops:**

```yaml
- name: Install packages
  apt:
    name: "{{ item }}"
    state: present
  loop:
    - nginx
    - curl
```

**Conditionals:**

```yaml
- name: Restart nginx only on Ubuntu
  service:
    name: nginx
    state: restarted
  when: ansible_distribution == 'Ubuntu'
```

---

### 🏷️ Tags

Run only specific tasks in a playbook:

```yaml
- name: Update cache
  apt:
    update_cache: yes
  tags: update
```

Run with:

```bash
ansible-playbook site.yml --tags "update"
```

---

### 🔐 Ansible Vault

Encrypt sensitive data like passwords:

```bash
ansible-vault encrypt secrets.yml
```

Use in playbook:

```yaml
vars_files:
  - secrets.yml
```

Decrypt:

```bash
ansible-vault decrypt secrets.yml
```

---

### 🧪 Error Handling

Use `ignore_errors`, `failed_when`, and `rescue` blocks:

```yaml
- name: Attempt command
  command: /bin/false
  register: result
  ignore_errors: true

- name: Fail manually
  fail:
    msg: "Something failed"
  when: result.rc != 0
```

---

### 📦 Advanced Role Structure

Roles can be reused and shared.
Additional folders:

* `tests/`: Test playbook
* `library/`: Custom modules
* `tasks/*.yml`: Split tasks by function

Use with:

```yaml
roles:
  - { role: nginx, tags: ["web"] }
```

---

### 🛰️ Dynamic Inventory

Example with AWS EC2 plugin:

```ini
plugin: aws_ec2
regions:
  - us-east-1
filters:
  tag:Environment: dev
```

Command:

```bash
ansible-inventory -i aws_ec2.yml --list
```

---

### 🔁 Ansible Pull

Run from managed nodes (pull mode):

```bash
ansible-pull -U https://github.com/user/repo.git playbook.yml
```

Useful for cron jobs or immutable infrastructure.

---

### 🌐 Ansible Galaxy

Use roles from the community:

```bash
ansible-galaxy install geerlingguy.nginx
```

Use in playbook:

```yaml
roles:
  - geerlingguy.nginx
```

---

### ✅ Summary

By end of Phase 2, you'll:

* Write dynamic and reusable playbooks
* Handle errors gracefully
* Encrypt sensitive data
* Use advanced roles and inventory
* Integrate with AWS/GCP via dynamic inventory

---