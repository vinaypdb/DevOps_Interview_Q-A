✅ **Docker Interview Questions and Answers (Comprehensive & Simple)**

---

### 1. **What is Docker?**

Docker is a platform that allows you to build, ship, and run applications in containers. Containers package code and dependencies together to ensure consistency across environments.

---

### 2. **What is a container?**

A container is a lightweight, standalone, executable package that includes everything needed to run an application — code, runtime, libraries, and settings.

---

### 3. **What is the difference between a container and a virtual machine (VM)?**

* VMs include a full OS and are heavier.
* Containers share the host OS kernel and are lightweight and faster to start.

---

### 4. **What is Dockerfile?**

A Dockerfile is a script with instructions to build a Docker image. It includes commands like FROM, RUN, COPY, etc.

---

### 5. **What is a Docker image?**

A Docker image is a read-only template used to create containers. It contains the app and its dependencies.

---

### 6. **What is the difference between Docker image and container?**

* Image: Blueprint of the application.
* Container: Running instance of an image.

---

### 7. **What is Docker Hub?**

Docker Hub is a cloud-based registry where you can find, share, and store Docker images.

---

### 8. **How do you create a Docker image?**

1. Write a Dockerfile
2. Run: `docker build -t my-image .`

---

### 9. **How do you run a Docker container?**

```bash
docker run -d -p 8080:80 my-image
```

* `-d` runs in detached mode
* `-p` maps host port to container port

---

### 10. **How do you list running containers?**

```bash
docker ps
```

---

### 11. **How do you stop and remove a container?**

```bash
docker stop <container-id>
docker rm <container-id>
```

---

### 12. **What is the purpose of EXPOSE in Dockerfile?**

It tells Docker which port the container listens on.

---

### 13. **What is ENTRYPOINT and CMD in Dockerfile?**

* `ENTRYPOINT`: Main command to run
* `CMD`: Default arguments passed to ENTRYPOINT

---

### 14. **What is the difference between ADD and COPY in Dockerfile?**

* `COPY`: Copies files/directories
* `ADD`: Same as COPY + supports URLs and unpacking archives

---

### 15. **What is a volume in Docker?**

A volume is a way to persist data outside containers. It allows data sharing between host and container.

---

### 16. **How to create and use a Docker volume?**

```bash
docker volume create myvol
docker run -v myvol:/app/data my-image
```

---

### 17. **What is bind mount?**

Mounts a host directory into the container:

```bash
docker run -v /host/path:/container/path my-image
```

---

### 18. **What is the difference between volume and bind mount?**

* **Volume**: Managed by Docker
* **Bind mount**: Managed by user and points to a specific host path

---

### 19. **What is a Docker network?**

A Docker network allows containers to communicate. Types: bridge, host, overlay.

---

### 20. **How to create a user-defined bridge network?**

```bash
docker network create my-bridge
```

---

### 21. **How do containers communicate in the same network?**

They can refer to each other by container name when on the same user-defined bridge network.

---

### 22. **What is the purpose of Docker Compose?**

Docker Compose allows you to define and run multi-container apps using a YAML file.

---

### 23. **How do you run a Docker Compose file?**

```bash
docker-compose up -d
```

---

### 24. **What is the default Docker Compose file name?**

`docker-compose.yml`

---

### 25. **How do you scale services using Docker Compose?**

```bash
docker-compose up --scale web=3
```

---

### 26. **What is the difference between COPY and VOLUME?**

* `COPY`: Copies files during image build
* `VOLUME`: Defines storage to persist or share data

---

### 27. **How to see container logs?**

```bash
docker logs <container-id>
```

---

### 28. **What is an ephemeral container?**

A temporary container created to debug a running pod in Kubernetes. In Docker, it’s similar to running an interactive shell:

```bash
docker exec -it <container> sh
```

---

### 29. **How to connect to a running container’s shell?**

```bash
docker exec -it <container-id> /bin/bash
```

---

### 30. **What is an image layer?**

Each instruction in Dockerfile creates a layer. Layers make images efficient and reusable.

---

### 31. **What is the .dockerignore file?**

It tells Docker which files to exclude from the build context.

---

### 32. **How do you clean up unused Docker resources?**

```bash
docker system prune
```

---

### 33. **How to view Docker image history?**

```bash
docker history <image-id>
```

---

### 34. **What is the use of `--rm` in Docker run?**

Automatically removes the container when it exits:

```bash
docker run --rm my-image
```

---

### 35. **How do you tag and push an image to Docker Hub?**

```bash
docker tag my-image vinaypdb/my-image:v1
docker push vinaypdb/my-image:v1
```

---

### 36. **How to inspect a Docker image or container?**

```bash
docker inspect <container-or-image>
```

---

### 37. **What is Docker Swarm?**

Docker’s native clustering tool that turns a pool of Docker hosts into a single virtual host.

---

### 38. **How is Docker different from Kubernetes?**

* **Docker**: Container runtime and packaging
* **Kubernetes**: Container orchestration platform

---

### 39. **How to export and import a Docker image?**

```bash
docker save -o my-image.tar my-image
docker load -i my-image.tar
```

---

### 40. **What is multi-stage build in Dockerfile?**

Used to reduce final image size by compiling in one stage and copying only required artifacts to the final image.

---

### 41. **What is Alpine Linux and why use it in Docker?**

A minimal Linux distro (\~5MB) that reduces Docker image size.

---

### 42. **What are best practices for Dockerfile?**

* Use minimal base images (like Alpine)
* Minimize layers
* Use `.dockerignore`
* Pin dependency versions

---

### 43. **Can multiple containers share a volume?**

Yes. Attach the same volume to multiple containers.

---

### 44. **How do you troubleshoot a failed Docker build?**

* Read output logs
* Add `RUN echo` for debugging
* Use `docker build --progress=plain`

---

### 45. **What is the default network for Docker containers?**

The default `bridge` network.

---

### 46. **How to find the IP of a container?**

```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container>
```

---

### 47. **How do you limit CPU and memory usage of containers?**

```bash
docker run --memory=512m --cpus=1 my-image
```

---

### 48. **Can a Docker container run multiple processes?**

Technically yes, but not recommended. Best practice is one process per container.

---

### 49. **How do you update a running container?**

* You can't update directly.
* Rebuild image and restart a new container.

---

### 50. **How do you monitor Docker containers?**

* `docker stats`
* Use tools like cAdvisor, Prometheus, Grafana

---
