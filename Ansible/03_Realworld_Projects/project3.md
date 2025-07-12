
### 📁 Project 3: Bootstrap Kubernetes Nodes

**🎯 Goal:** Prepare Ubuntu servers to be used as Kubernetes master and worker nodes using kubeadm.

### 📦 Components

* **containerd**: Container runtime
* **kubelet**, **kubeadm**, **kubectl**: Kubernetes tools
* Disable swap, setup networking and modules

---

### 📂 Directory Structure

```
k8s_bootstrap/
├── roles/
│   ├── prereqs/
│   │   └── tasks/main.yml
│   └── kube-tools/
│       └── tasks/main.yml
└── site.yml
```

---

### 📄 site.yml

```yaml
- name: Kubernetes Bootstrap
  hosts: k8s
  become: yes
  roles:
    - prereqs
    - kube-tools
```

---

### 📄 prereqs/tasks/main.yml

```yaml
- name: Disable swap
  command: swapoff -a

- name: Remove swap entry from fstab
  replace:
    path: /etc/fstab
    regexp: '^.*swap.*$'
    replace: ''

- name: Load kernel modules
  copy:
    dest: /etc/modules-load.d/k8s.conf
    content: |
      overlay
      br_netfilter

- name: Enable kernel params
  copy:
    dest: /etc/sysctl.d/k8s.conf
    content: |
      net.bridge.bridge-nf-call-ip6tables = 1
      net.bridge.bridge-nf-call-iptables = 1
  notify: apply sysctl

handlers:
  - name: apply sysctl
    command: sysctl --system
```

---

### 📄 kube-tools/tasks/main.yml

```yaml
- name: Add Kubernetes APT key
  apt_key:
    url: https://packages.cloud.google.com/apt/doc/apt-key.gpg
    state: present

- name: Add Kubernetes repo
  apt_repository:
    repo: deb http://apt.kubernetes.io/ kubernetes-xenial main
    state: present

- name: Install kubeadm, kubelet, kubectl
  apt:
    name:
      - kubelet
      - kubeadm
      - kubectl
    state: present
    update_cache: yes

- name: Hold Kubernetes packages
  apt:
    name:
      - kubelet
      - kubeadm
      - kubectl
    state: hold
```

---

### ▶️ Run the Playbook

```bash
ansible-playbook -i inventory.ini site.yml
```

### ✅ Expected Output

* Swap disabled
* Kernel modules and sysctl configured
* Kubernetes binaries installed and held

---

