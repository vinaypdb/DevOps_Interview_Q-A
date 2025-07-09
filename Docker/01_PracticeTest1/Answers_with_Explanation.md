### Docker MCQ Answer Key with Explanations

**1. c) Containerization**
Docker is primarily a containerization platform used to package applications and their dependencies.

**2. a) Docker Engine**
Docker Engine is the core component that runs and manages containers.

**3. c) LXC**
Docker initially used LXC (Linux Containers) technology.

**4. b) Dockerfile**
Dockerfile is used to create a Docker image with specific instructions.

**5. d) bridge**
The default Docker network driver is `bridge`.

**6. a) docker ps**
`docker ps` shows running containers.

**7. b) docker build**
`docker build` is used to build Docker images.

**8. c) Read-only**
Docker images are immutable and read-only by design.

**9. b) Docker Hub**
Docker Hub is the default public registry for Docker images.

**10. c) docker rm**
`docker rm` removes a stopped container.

**11. b) Removes an image**
`docker rmi` removes a Docker image.

**12. c) docker run -it**
This starts a container in interactive mode with a terminal.

**13. c) Persist data**
Volumes store persistent data outside the container.

**14. b) docker volume create**
This command is used to create volumes.

**15. c) docker-compose.yml**
Used by Docker Compose to define multi-container applications.

**16. d) docker stop**
Gracefully stops a running container.

**17. c) public**
There is no `public` network driver in Docker.

**18. b) docker logs**
Shows logs from a container.

**19. c) Application sandboxes**
Containers isolate applications and their dependencies.

**20. c) Run a command inside a running container**
`docker exec` is used for that purpose.

**21. c) Background process that manages containers**
Docker Daemon (`dockerd`) is the background service.

**22. a) docker ps -a**
Lists all containers, including stopped ones.

**23. c) Managing multi-container applications**
Docker Compose helps define and run multiple containers.

**24. b) 2375**
Docker daemon REST API listens on TCP port 2375 (unencrypted).

**25. b) Displays metadata about objects**
`docker inspect` provides detailed info about containers, images, etc.

**26. b) Run at container start**
`CMD` defines the default command to run.

**27. c) EXPOSE**
Used in Dockerfile to inform Docker about the ports the container listens on.

**28. c) Lists available networks**
`docker network ls` shows all Docker networks.

**29. d) both a and c**
Both `docker tag <image> <tag>` and `docker image tag` are valid.

**30. b) Specify default executable**
`ENTRYPOINT` sets the main command for the container.

**31. a) Removes unused data**
`docker system prune` cleans up unused containers, images, networks, etc.

**32. a) -d**
`-d` runs the container in detached (background) mode.

**33. b) docker run**
`docker run` creates and starts a new container from an image.

**34. b) overlay2**
`overlay2` is the default storage driver on most modern systems.

**35. c) Container orchestration**
Docker Swarm helps in managing a cluster of Docker nodes.

**36. a) docker push**
`docker push` uploads a local image to a registry.

**37. b) Detailed system-wide information**
`docker info` shows info like containers, images, storage drivers, etc.

**38. c) Unlimited (based on system resources)**
There is no hard limit; it depends on CPU, memory, and disk.

**39. b) Trivy**
Trivy is a popular tool to scan Docker images for vulnerabilities.

**40. c) Lightweight and secure**
Alpine Linux is known for being minimal and secure.

**41. c) Firewall**
Containers are isolated using namespaces and cgroups, not firewalls.

**42. c) Building container images**
Dockerfiles are used to define how to build an image.

**43. c) Each Dockerfile instruction is executed**
Each line in Dockerfile creates a new image layer.

**44. b) In /var/lib/docker**
By default, Docker stores data in `/var/lib/docker`.

**45. c) docker container prune**
Removes all stopped containers.

**46. a) Faster rebuilds and caching**
Layered images allow Docker to reuse unchanged layers.

**47. a) Environmental configuration for CLI**
Docker contexts allow switching between environments (local, remote).

**48. b) ADD can also extract tar files**
`ADD` has extra functionality like extracting archives.

**49. a) docker login**
Used to authenticate with Docker registries.

**50. b) Go**
Docker was developed using the Go programming language.
