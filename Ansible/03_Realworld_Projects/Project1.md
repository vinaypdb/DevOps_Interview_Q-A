
### 📁 Project 1: LAMP Stack Setup on Ubuntu Servers

**🎯 Goal:** Deploy a fully functional LAMP (Linux, Apache, MySQL, PHP) stack on a group of Ubuntu servers.

### 📦 Stack Components

* **Linux**: Ubuntu 20.04
* **Apache**: Web server
* **MySQL**: Database server
* **PHP**: Application layer

---

### 📂 Directory Structure

```
lamp_stack/
├── group_vars/
│   └── all.yml
├── roles/
│   ├── apache/
│   │   ├── tasks/main.yml
│   │   └── templates/vhost.conf.j2
│   ├── mysql/
│   │   ├── tasks/main.yml
│   └── php/
│       └── tasks/main.yml
└── site.yml
```

---

### 📄 site.yml

```yaml
- name: Setup LAMP Stack
  hosts: web
  become: yes
  roles:
    - apache
    - mysql
    - php
```

---

### 📄 group\_vars/all.yml

```yaml
mysql_root_password: strongpassword123
```

---

### 📄 apache/tasks/main.yml

```yaml
- name: Install Apache
  apt:
    name: apache2
    state: present

- name: Enable and start Apache
  service:
    name: apache2
    enabled: true
    state: started

- name: Deploy virtual host file
  template:
    src: vhost.conf.j2
    dest: /etc/apache2/sites-available/000-default.conf
  notify: restart apache

handlers:
  - name: restart apache
    service:
      name: apache2
      state: restarted
```

---

### 📄 mysql/tasks/main.yml

```yaml
- name: Install MySQL
  apt:
    name: mysql-server
    state: present

- name: Set root password
  mysql_user:
    login_user: root
    login_password: ''
    name: root
    password: "{{ mysql_root_password }}"
    host_all: true
```

---

### 📄 php/tasks/main.yml

```yaml
- name: Install PHP and modules
  apt:
    name: [php, libapache2-mod-php, php-mysql]
    state: present
```

---

### ▶️ Run the Playbook

```bash
ansible-playbook -i inventory.ini site.yml
```

### ✅ Expected Output

* Apache is installed and running
* MySQL is installed with root password set
* PHP is installed and configured

---

