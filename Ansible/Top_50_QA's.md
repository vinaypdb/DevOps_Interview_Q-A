✅ **Top 50 Ansible Interview Questions & Answers (Simple & Comprehensive)**

---

### 1. **What is Ansible?**

Ansible is an open-source automation tool used for configuration management, application deployment, and task automation.

---

### 2. **Is Ansible agentless?**

Yes, Ansible is agentless. It uses SSH (or WinRM for Windows) to connect to nodes.

---

### 3. **What language is Ansible written in?**

Ansible is written in Python.

---

### 4. **What is an Inventory in Ansible?**

Inventory is a file that lists target servers (hosts or groups) Ansible will manage.

---

### 5. **What is a Playbook in Ansible?**

A Playbook is a YAML file that defines automation tasks in a structured format.

---

### 6. **What is a Task in Ansible?**

A task is a single unit of work in a playbook, such as installing a package or copying a file.

---

### 7. **What is a Role in Ansible?**

A Role is a reusable, structured way to organize playbooks, variables, tasks, handlers, and templates.

---

### 8. **What is a Module in Ansible?**

A Module is a unit of code that performs a specific task. Examples: `yum`, `copy`, `service`, `command`.

---

### 9. **What is the difference between a Play and a Task?**

* **Play**: Maps hosts to tasks.
* **Task**: Executes an action on the host.

---

### 10. **How do you run an Ansible playbook?**

```bash
ansible-playbook playbook.yml
```

---

### 11. **What is ad-hoc command in Ansible?**

A one-liner command to perform quick tasks without a playbook:

```bash
ansible all -m ping
```

---

### 12. **What is the default Ansible inventory file?**

`/etc/ansible/hosts`

---

### 13. **How do you install Ansible?**

```bash
sudo apt install ansible  # Debian/Ubuntu
sudo yum install ansible  # RHEL/CentOS
```

---

### 14. **How do you define variables in Ansible?**

* Inline in playbook
* In `vars` section
* In group/host vars
* In `vars_files`

---

### 15. **What is the use of `gather_facts` in Ansible?**

Collects system information (e.g., OS, IP, RAM) before running tasks.

---

### 16. **How do you create a new role?**

```bash
ansible-galaxy init myrole
```

---

### 17. **What are Handlers in Ansible?**

Handlers are tasks that run only when notified, e.g., restarting a service.

---

### 18. **What is Ansible Galaxy?**

A public repository of pre-built roles and collections that you can reuse.

---

### 19. **How do you pass extra variables to a playbook?**

```bash
ansible-playbook playbook.yml -e "var1=value1"
```

---

### 20. **What is `when` in Ansible?**

A conditional statement to run tasks only when conditions are met.

---

### 21. **What is the difference between `command` and `shell` modules?**

* `command`: Doesn't process shell features.
* `shell`: Allows shell operations like piping, redirection.

---

### 22. **How to debug in Ansible?**

Use the `debug` module to print variables or messages.

---

### 23. **What is Ansible Vault?**

Tool to encrypt sensitive data like passwords or keys.

```bash
ansible-vault encrypt secrets.yml
```

---

### 24. **How do you use a template in Ansible?**

Templates are Jinja2 files that can be rendered using variables:

```yaml
- name: Deploy config
  template:
    src: nginx.conf.j2
    dest: /etc/nginx/nginx.conf
```

---

### 25. **What are facts in Ansible?**

Facts are system details collected by Ansible (OS, CPU, IP, etc.).

---

### 26. **How do you disable fact gathering?**

```yaml
gather_facts: false
```

---

### 27. **What is idempotency in Ansible?**

Running a playbook multiple times doesn't change the result if nothing has changed.

---

### 28. **What is the default location for custom roles?**

`/etc/ansible/roles` or defined in `ansible.cfg`

---

### 29. **How to include one playbook in another?**

```yaml
- import_playbook: other_playbook.yml
```

---

### 30. **Difference between `include` and `import`?**

* `import`: Static, resolved at parse time.
* `include`: Dynamic, resolved at runtime.

---

### 31. **What is `register` in Ansible?**

Used to capture output of a task:

```yaml
- command: uname -r
  register: kernel_version
```

---

### 32. **How do you check if a file exists on remote host?**

```yaml
- stat:
    path: /etc/file
  register: file_stat
- debug:
    msg: "File exists"
  when: file_stat.stat.exists
```

---

### 33. **Can Ansible be used with Windows?**

Yes, using WinRM instead of SSH.

---

### 34. **How to loop in Ansible?**

```yaml
- name: Install packages
  yum:
    name: "{{ item }}"
    state: present
  loop:
    - nginx
    - git
    - curl
```

---

### 35. **What is `block` in Ansible?**

Group multiple tasks with error handling or shared conditions.

---

### 36. **How do you tag tasks in Ansible?**

```yaml
- name: Install nginx
  yum:
    name: nginx
    state: present
  tags: web
```

Run with:

```bash
ansible-playbook site.yml --tags web
```

---

### 37. **What are collections in Ansible?**

Collections are namespaces for modules, plugins, and roles shared via Ansible Galaxy.

---

### 38. **What is `local_action`?**

Runs a task on the control node:

```yaml
- local_action: command date
```

---

### 39. **How do you copy files in Ansible?**

Using the `copy` module:

```yaml
- copy:
    src: /src/file
    dest: /dest/file
```

---

### 40. **What is the `become` keyword in Ansible?**

Used for privilege escalation (e.g., sudo):

```yaml
- name: Install nginx
  become: true
```

---

### 41. **Can you write multiple plays in one playbook?**

Yes, just separate them with `---`.

---

### 42. **How do you test Ansible roles locally?**

Use tools like Molecule or `ansible-playbook --check` for dry run.

---

### 43. **What is `ansible-pull`?**

Pulls playbooks from a git repo and applies them—used for pull-based automation.

---

### 44. **How do you retry failed hosts in Ansible?**

Ansible generates a `.retry` file:

```bash
ansible-playbook site.yml --limit @site.retry
```

---

### 45. **How do you stop a playbook on failure?**

Use `fail` module or `any_errors_fatal: true`.

---

### 46. **How do you skip certain tasks?**

Use `when` conditions or `--skip-tags` option.

---

### 47. **What is the use of `ansible-config`?**

View and manage Ansible configuration:

```bash
ansible-config dump
```

---

### 48. **What is dynamic inventory?**

An inventory generated from external sources (AWS, Azure, etc.) using scripts or plugins.

---

### 49. **How do you install roles from Galaxy?**

```bash
ansible-galaxy install geerlingguy.nginx
```

---

### 50. **What are best practices for writing Ansible playbooks?**

* Use roles and collections for modularity
* Encrypt secrets
* Use tags, handlers, variables
* Follow idempotency
* Use linting and Molecule for testing

---
