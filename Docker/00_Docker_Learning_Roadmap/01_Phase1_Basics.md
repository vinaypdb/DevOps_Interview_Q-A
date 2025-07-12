# 📘 Docker Phase 1: Fundamentals (Beginner Level)

---

## 🐳 What is Docker?

**Docker** is a **containerization platform** that allows developers to package applications and all their dependencies into a **single unit called a container**. This makes applications portable and ensures they work the same regardless of where they run — on a developer’s laptop, on a test server, or in production.

---

## 💡 Why Docker?

| Traditional Deployment                                 | Docker-based Deployment            |
| ------------------------------------------------------ | ---------------------------------- |
| App + OS-level dependencies need to be set up manually | Everything is inside the container |
| Works on one machine but not another                   | Consistent behavior everywhere     |
| High resource usage due to VMs                         | Lightweight and fast containers    |
| Difficult to scale                                     | Easy to scale and replicate        |

---

## 🧱 Core Docker Concepts

| Concept           | Description                                                                              |
| ----------------- | ---------------------------------------------------------------------------------------- |
| **Image**         | A read-only template with instructions to create a container (like a snapshot of an app) |
| **Container**     | A runnable instance of an image; isolated, lightweight, and portable                     |
| **Dockerfile**    | A script with commands to build an image                                                 |
| **Docker Engine** | The runtime that builds and runs containers                                              |
| **Docker Hub**    | A public registry for sharing container images                                           |

---

## ⚙️ Docker Architecture

```
+-------------------+         docker build/run
|   Docker CLI      |  <------------------------ You
+-------------------+
           |
           v
+-------------------+
| Docker Daemon     | ← Does the heavy lifting: builds, runs, manages
+-------------------+
           |
           v
+-------------------+
| Container Runtime | ← Actually runs the containers (runc)
+-------------------+
```

---

## 📥 Installing Docker

### 🔹 Ubuntu/Linux

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
```

### 🔹 Check Docker Version

```bash
docker --version
```

---

## 💻 Basic Docker Commands

| Command               | Description                       |
| --------------------- | --------------------------------- |
| `docker pull <image>` | Download an image from Docker Hub |
| `docker images`       | List downloaded images            |
| `docker run <image>`  | Run a container from the image    |
| `docker ps`           | Show running containers           |
| `docker ps -a`        | Show all containers               |
| `docker stop <id>`    | Stop a running container          |
| `docker rm <id>`      | Delete a stopped container        |
| `docker rmi <image>`  | Remove an image                   |

---

## ✏️ Writing a Dockerfile

A `Dockerfile` defines how an image should be built.

Example: Dockerfile to host static HTML website using Nginx

```Dockerfile
# Use nginx image as base
FROM nginx:alpine

# Copy local files into container
COPY . /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Run nginx (default command already handled by nginx image)
```

---

## 💪 Build and Run Your Own Image

### Step 1: Build the Image

```bash
docker build -t my-static-site .
```

### Step 2: Run the Container

```bash
docker run -d -p 8080:80 my-static-site
```

✅ Now open `http://localhost:8080` in your browser to view the site!

---

## 🗂️ Example Project: Static Website with Docker

### 🔧 Project Structure

```
static-site/
🔹 index.html
🔹 Dockerfile
```

### 📄 index.html

```html
<!DOCTYPE html>
<html>
  <head><title>My Static Site</title></head>
  <body>
    <h1>Hello from Dockerized Nginx!</h1>
  </body>
</html>
```

### 📄 Dockerfile

```Dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

### 🚀 Steps to Build & Run

```bash
cd static-site
docker build -t my-static-site .
docker run -d -p 8080:80 my-static-site
```

📅 Output: Open `http://localhost:8080` to view your site.

---

## 🚿 Cleaning Up

* Stop all containers:

  ```bash
  docker stop $(docker ps -q)
  ```
* Remove all containers:

  ```bash
  docker rm $(docker ps -aq)
  ```
* Remove all images:

  ```bash
  docker rmi $(docker images -q)
  ```
* Or clean everything:

  ```bash
  docker system prune -a
  ```

---

## ❓ Common Interview Questions (Beginner)

1. **What is Docker and how is it different from a virtual machine?**
2. **What is the difference between an image and a container?**
3. **What is the purpose of a Dockerfile?**
4. **How do you expose a port in Docker?**
5. **How can you persist data in Docker containers?**

---

## 📌 Summary

| Skill                                       | Gained |
| ------------------------------------------- | ------ |
| ✅ Installed Docker                          | ✔️     |
| ✅ Understood Containers vs Images           | ✔️     |
| ✅ Wrote your first Dockerfile               | ✔️     |
| ✅ Built and ran a Dockerized static website | ✔️     |
