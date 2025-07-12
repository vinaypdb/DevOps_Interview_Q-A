# 🚀 Docker Phase 2: Intermediate Concepts

---

## 🔄 Dockerfile Deep Dive

A Dockerfile is a script used to build a Docker image. Understanding each instruction helps build optimized images.

### 🛠️ Common Instructions

| Instruction  | Description                                              |
| ------------ | -------------------------------------------------------- |
| `FROM`       | Base image to start from (e.g., `ubuntu`, `nginx`, etc.) |
| `RUN`        | Executes a command inside the image while building       |
| `CMD`        | Default command to run in container                      |
| `ENTRYPOINT` | Similar to CMD but preferred for executables             |
| `COPY`       | Copies files from local machine into image               |
| `ADD`        | Like COPY but can handle remote URLs and archives        |
| `ENV`        | Sets environment variables                               |
| `EXPOSE`     | Documents the port container listens on                  |
| `WORKDIR`    | Sets working directory for RUN, CMD, ENTRYPOINT          |

### 🔁 CMD vs ENTRYPOINT

| CMD                                                   | ENTRYPOINT                                 |
| ----------------------------------------------------- | ------------------------------------------ |
| Used for default commands                             | Used to define a container’s main behavior |
| Can be overridden by arguments passed at `docker run` | More strict, less flexible                 |

---

## 🧱 Docker Volumes

Volumes are used to persist data created and used by Docker containers.

### 🎯 Why Volumes?

* Data won't be lost when a container is removed.
* Useful for sharing data between host and container.

### 🔧 Volume Types

| Type      | Description                        |
| --------- | ---------------------------------- |
| Named     | Created and managed by Docker      |
| Anonymous | Not given a name, harder to manage |
| Host      | Maps a specific host directory     |

### 🧪 Example

```bash
docker volume create mydata
docker run -v mydata:/app/data busybox
```

To mount a host directory:

```bash
docker run -v $(pwd)/logs:/app/logs myapp
```

---

## 🌐 Docker Networking

Docker provides several networking options to allow containers to communicate.

### 🔌 Network Types

| Network | Description                                   |
| ------- | --------------------------------------------- |
| Bridge  | Default for containers on the same host       |
| Host    | Shares host network (no isolation)            |
| None    | No networking                                 |
| Overlay | For multi-host networking (used in Swarm/K8s) |

### 🧪 Creating Custom Network

```bash
docker network create mynet
docker run -d --name redis --network mynet redis
docker run -it --network mynet busybox
# ping redis
```

---

## 🧩 Docker Compose

Docker Compose allows you to define and run multi-container Docker applications using a YAML file.

### 📁 docker-compose.yml Example

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  redis:
    image: redis
```

### 🛠️ Common Commands

```bash
docker-compose up
docker-compose up -d
docker-compose down
```

---

## 🧰 .dockerignore

Like `.gitignore`, this file prevents unnecessary files from being added to the image during build.

### ✍️ Sample .dockerignore

```
.git
*.log
docker-compose.yml
node_modules
```

This reduces image size and build time.

---

## 📦 Intermediate Project: Fullstack App with Docker Compose

### 🗂️ Structure

```
fullstack-app/
├── backend/
│   ├── server.js
│   └── Dockerfile
├── frontend/
│   ├── index.html
│   └── Dockerfile
└── docker-compose.yml
```

### 🔧 backend/Dockerfile

```Dockerfile
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["node", "server.js"]
```

### 🔧 frontend/Dockerfile

```Dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

### 🔧 docker-compose.yml

```yaml
version: '3'
services:
  backend:
    build: ./backend
    ports:
      - "5000:5000"
  frontend:
    build: ./frontend
    ports:
      - "3000:80"
    depends_on:
      - backend
```

### ▶️ Run the Project

```bash
docker-compose up --build
```

✅ Access the frontend at [http://localhost:3000](http://localhost:3000) and backend at [http://localhost:5000](http://localhost:5000)

---

## 🧹 Cleaning Up Resources

```bash
docker-compose down
```

---

## ❓ Interview Questions (Intermediate)

1. What are volumes in Docker and how do they differ from bind mounts?
2. How do containers communicate with each other?
3. What is the difference between CMD and ENTRYPOINT?
4. How do you manage multi-container applications?
5. What does the `.dockerignore` file do?

---

## 📌 Summary

| Skill                                      | Gained |
| ------------------------------------------ | ------ |
| ✅ Dockerfile advanced usage                | ✔️     |
| ✅ Volumes and data persistence             | ✔️     |
| ✅ Docker networks and container linking    | ✔️     |
| ✅ Docker Compose for multi-container setup | ✔️     |
| ✅ Built fullstack app with Compose         | ✔️     |
