

### 📁 Project 4: Prometheus + Grafana Monitoring

**🎯 Goal:** Use Ansible to deploy Prometheus and Grafana for monitoring infrastructure.

### 📦 Components

* **Prometheus**: Time-series database and monitoring system
* **Grafana**: Visualization and dashboard tool
* **Systemd Services**: For Prometheus and Grafana

---

### 📂 Directory Structure

```
prometheus_grafana/
├── roles/
│   ├── prometheus/
│   │   ├── tasks/main.yml
│   │   └── templates/prometheus.yml.j2
│   └── grafana/
│       └── tasks/main.yml
└── site.yml
```

---

### 📄 site.yml

```yaml
- name: Setup Prometheus and Grafana
  hosts: monitor
  become: yes
  roles:
    - prometheus
    - grafana
```

---

### 📄 prometheus/tasks/main.yml

```yaml
- name: Create prometheus user
  user:
    name: prometheus
    shell: /sbin/nologin

- name: Download Prometheus
  get_url:
    url: https://github.com/prometheus/prometheus/releases/download/v2.46.0/prometheus-2.46.0.linux-amd64.tar.gz
    dest: /tmp/prometheus.tar.gz

- name: Extract Prometheus
  unarchive:
    src: /tmp/prometheus.tar.gz
    dest: /opt/
    remote_src: yes

- name: Copy config
  template:
    src: prometheus.yml.j2
    dest: /opt/prometheus-2.46.0.linux-amd64/prometheus.yml

- name: Setup systemd service
  copy:
    dest: /etc/systemd/system/prometheus.service
    content: |
      [Unit]
      Description=Prometheus

      [Service]
      ExecStart=/opt/prometheus-2.46.0.linux-amd64/prometheus \
        --config.file=/opt/prometheus-2.46.0.linux-amd64/prometheus.yml

      [Install]
      WantedBy=multi-user.target

- name: Start Prometheus
  systemd:
    name: prometheus
    enabled: yes
    state: started
```

---

### 📄 grafana/tasks/main.yml

```yaml
- name: Install Grafana
  apt:
    name: grafana
    update_cache: yes
    state: present

- name: Enable and start Grafana
  service:
    name: grafana-server
    enabled: yes
    state: started
```

---

### 📄 prometheus/templates/prometheus.yml.j2

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'node'
    static_configs:
      - targets: ['localhost:9100']
```

---

### ▶️ Run the Playbook

```bash
ansible-playbook -i inventory.ini site.yml
```

### ✅ Expected Output

* Prometheus and Grafana installed
* Monitoring accessible at `http://<host>:3000`
* Prometheus running as a systemd service

---

