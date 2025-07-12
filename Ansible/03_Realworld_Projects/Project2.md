

### 📁 Project 2: Docker + Nginx Setup

**🎯 Goal:** Use Ansible to install Docker and deploy a static website using an Nginx container.

### 📦 Components

* **Docker Engine**: Container runtime
* **Nginx**: Web server running inside Docker container
* **Static Content**: Custom index.html

---

### 📂 Directory Structure

```
docker_nginx/
├── roles/
│   ├── docker/
│   │   └── tasks/main.yml
│   ├── nginx/
│   │   ├── tasks/main.yml
│   │   └── files/index.html
└── site.yml
```

---

### 📄 site.yml

```yaml
- name: Docker + Nginx Web Setup
  hosts: web
  become: yes
  roles:
    - docker
    - nginx
```

---

### 📄 docker/tasks/main.yml

```yaml
- name: Install prerequisite packages
  apt:
    name:
      - apt-transport-https
      - ca-certificates
      - curl
      - gnupg
      - lsb-release
    state: present

- name: Add Docker’s GPG key
  shell: curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

- name: Add Docker repository
  apt_repository:
    repo: "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    state: present

- name: Install Docker Engine
  apt:
    name: docker-ce
    state: present
    update_cache: true

- name: Enable and start Docker
  service:
    name: docker
    state: started
    enabled: true
```

---

### 📄 nginx/tasks/main.yml

```yaml
- name: Copy custom index.html
  copy:
    src: index.html
    dest: /tmp/index.html

- name: Run nginx container
  docker_container:
    name: nginx_web
    image: nginx:latest
    state: started
    ports:
      - "80:80"
    volumes:
      - /tmp/index.html:/usr/share/nginx/html/index.html
```

---

### ▶️ Run the Playbook

```bash
ansible-playbook -i inventory.ini site.yml
```

### ✅ Expected Output

* Docker is installed and running
* Nginx container serves the static index.html

---

