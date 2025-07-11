**Docker Multiple Choice Questions (MCQs)**

1. **B - Containerization**
   Docker is a platform for developing, shipping, and running containers.

2. **B - Application and its dependencies**
   A Docker container bundles an app with everything it needs to run.

3. **C - Container platform**
   Docker is a container-based technology, not a virtualization tool.

4. **C - docker build**
   Used to build a Docker image from a Dockerfile.

5. **A - Dockerfile**
   Contains instructions to build a Docker image.

6. **A - docker ps**
   Lists all currently running containers.

7. **B - Runs a new container**
   `docker run` creates and starts a container.

8. **C - docker stop \<container\_id>**
   Gracefully stops a running container.

9. **D - Both A and C**
   `docker image rm` and `docker rmi` both remove images.

10. **C - Public image registry**
    Docker Hub is a cloud-based registry for Docker images.

11. **C - docker-compose.yml**
    Used by Docker Compose to define multi-container applications.

12. **B - Persistent storage**
    Docker Volumes store data outside containers.

13. **C - docker run -d**
    `-d` flag runs the container in detached mode.

14. **B - docker container prune**
    Removes all stopped containers.

15. **A - 2375**
    This is the default port for non-TLS Docker daemon.

16. **B - Sets default executable**
    ENTRYPOINT defines the main executable of the container.

17. **B - bridge**
    Default network driver used by Docker.

18. **C - docker logs <id>**
    Shows logs for the specified container.

19. **B - docker tag**
    Used to tag images before pushing to a registry.

20. **C - docker run --network**
    Attaches container to specified network during `run`.

21. **C - Building images in stages to reduce size**
    Multi-stage builds make smaller, cleaner images.

22. **C - Docker Engine**
    Core of Docker responsible for building/running containers.

23. **C - --name**
    `--name` assigns a name to the container.

24. **C - docker cp**
    Copies files between container and host.

25. **C - Base Layers**
    Docker uses shared layers across images to save space.

26. **B - Makes port 80 available to linked containers**
    `EXPOSE` declares the port containers listen on.

27. **B - docker restart <id>**
    Restarts a stopped or running container.

28. **A - docker history <image>**
    Displays layer-by-layer history of image creation.

29. **A - List files to exclude during image build**
    .dockerignore avoids copying unnecessary files.

30. **C - docker exec -it <id> /bin/sh**
    Starts an interactive shell session inside the container.

31. **C - Image**
    An image is a blueprint from which containers are created.

32. **C - Specifies default command to run**
    CMD provides default arguments for ENTRYPOINT or container.

33. **C - docker inspect <id>**
    Gives detailed configuration info about a container.

34. **C - docker volume prune**
    Deletes all unused Docker volumes.

35. **C - Storage for Docker images**
    Registry hosts and serves Docker images.

36. **B - /var/lib/docker**
    Default directory used for Docker storage.

37. **C - docker stats**
    Shows real-time CPU, memory usage of containers.

38. **D - Cannot rename running container**
    Containers must be stopped to be renamed.

39. **C - docker network create**
    Creates a new custom Docker network.

40. **C - Mount volume**
    `-v` option mounts host volume into container.

41. **C - alpine**
    Alpine is a minimal and popular base image.

42. **C - Container orchestration**
    Docker Swarm manages multiple containers across nodes.

43. **B - 172.17.0.0/16**
    Default subnet for Docker’s bridge network.

44. **B - Trivy**
    Trivy is a vulnerability scanner for Docker images.

45. **A - ADD supports remote URLs and unpacking**
    ADD does more than COPY, like fetching URLs or extracting archives.

46. **B - docker login**
    Authenticates to Docker Hub or private registry.

47. **D - All of the above**
    Docker Desktop includes CLI, engine, GUI, and Kubernetes.

48. **A - --rm**
    Removes the container after it exits.

49. **C - docker run**
    Starts a container from a specified image.

50. **B - Layers**
    Docker images consist of read-only layers stacked together.
