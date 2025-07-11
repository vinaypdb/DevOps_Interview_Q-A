**Docker Multiple Choice Questions (MCQs)**

1. What is Docker primarily used for?

* A. Virtualization
* B. Containerization
* C. Orchestration
* D. Monitoring

2. What does a Docker container contain?

* A. A virtual machine
* B. Application and its dependencies
* C. Only source code
* D. Just the OS

3. Which of the following best defines Docker?

* A. Package manager
* B. Cloud provider
* C. Container platform
* D. Virtual machine monitor

4. What command is used to build a Docker image?

* A. docker run
* B. docker image
* C. docker build
* D. docker create

5. What file is used to define instructions to build a Docker image?

* A. Dockerfile
* B. docker-compose.yml
* C. imagefile
* D. containerfile

6. Which command lists all running containers?

* A. docker ps
* B. docker images
* C. docker containers
* D. docker list

7. What does the `docker run` command do?

* A. Builds a container
* B. Runs a new container
* C. Deletes a container
* D. Lists containers

8. How do you stop a running Docker container?

* A. docker end \<container\_id>
* B. docker halt \<container\_id>
* C. docker stop \<container\_id>
* D. docker killall

9. What command removes a Docker image?

* A. docker image rm <image>
* B. docker delete image <image>
* C. docker rmi <image>
* D. Both A and C

10. What is Docker Hub?

* A. Local registry
* B. CI/CD tool
* C. Public image registry
* D. Monitoring dashboard

11. Which file is used with Docker Compose?

* A. Dockerfile
* B. app.yaml
* C. docker-compose.yml
* D. composefile.txt

12. What is a Docker Volume used for?

* A. Storing container logs
* B. Persistent storage
* C. Sharing images
* D. Networking

13. Which of these starts a container in detached mode?

* A. docker run --bg
* B. docker start -d
* C. docker run -d
* D. docker up -d

14. What command removes all stopped containers?

* A. docker prune
* B. docker container prune
* C. docker clean
* D. docker flush

15. Which port does Docker daemon listen on by default?

* A. 2375
* B. 2376
* C. 8080
* D. 80

16. What does ENTRYPOINT in Dockerfile do?

* A. Defines base image
* B. Sets default executable
* C. Copies file to image
* D. Exposes port

17. What is the default network driver in Docker?

* A. host
* B. bridge
* C. overlay
* D. none

18. How to see logs of a Docker container?

* A. docker log <id>
* B. docker showlog <id>
* C. docker logs <id>
* D. docker tail <id>

19. What command is used to tag a Docker image?

* A. docker mark
* B. docker tag
* C. docker label
* D. docker labelimage

20. How can you connect a container to a specific network?

* A. docker connect
* B. docker network attach
* C. docker run --network
* D. docker join net

21. What is a multi-stage build?

* A. Multiple containers in one image
* B. Using multiple Dockerfiles
* C. Building images in stages to reduce size
* D. Rebuilding the image repeatedly

22. Which Docker component runs the containers?

* A. Docker Client
* B. Docker Daemon
* C. Docker Engine
* D. Dockerfile

23. Which flag is used to name a container?

* A. --n
* B. --container-name
* C. --name
* D. --id

24. How do you copy files from container to host?

* A. docker copy out
* B. docker export
* C. docker cp
* D. docker fetch

25. Which layer is shared between images?

* A. Container Layer
* B. Top Layer
* C. Base Layers
* D. All layers are unique

26. What does `EXPOSE 80` in Dockerfile mean?

* A. Opens port 80 to the internet
* B. Makes port 80 available to linked containers
* C. Makes port 80 default port
* D. None of the above

27. How do you restart a stopped container?

* A. docker up <id>
* B. docker restart <id>
* C. docker rerun <id>
* D. docker play <id>

28. Which command shows image history?

* A. docker history <image>
* B. docker log <image>
* C. docker describe <image>
* D. docker inspect history

29. What is the purpose of .dockerignore file?

* A. List files to exclude during image build
* B. Ignore volumes
* C. Prevent container execution
* D. List untracked containers

30. How do you run an interactive shell inside a container?

* A. docker connect
* B. docker run -shell
* C. docker exec -it <id> /bin/sh
* D. docker run --cmd bash

31. Which Docker object represents a blueprint for containers?

* A. Container
* B. Dockerfile
* C. Image
* D. Registry

32. What does CMD do in Dockerfile?

* A. Copies files
* B. Sets environment variables
* C. Specifies default command to run
* D. Exposes ports

33. How to inspect detailed info about a container?

* A. docker info <id>
* B. docker logs <id>
* C. docker inspect <id>
* D. docker detail <id>

34. How to remove unused volumes?

* A. docker volume clean
* B. docker volume rm
* C. docker volume prune
* D. docker remove volume

35. What is a Docker Registry?

* A. Service to manage networks
* B. Centralized logging
* C. Storage for Docker images
* D. Image scanner

36. What is the default base directory of Docker images?

* A. /opt/docker
* B. /var/lib/docker
* C. /docker/base
* D. /srv/docker

37. What command shows container stats?

* A. docker top
* B. docker logs
* C. docker stats
* D. docker performance

38. How to rename a running container?

* A. docker rename
* B. docker mv
* C. docker change-name
* D. Cannot rename running container

39. What’s the command to create a custom Docker network?

* A. docker net add
* B. docker create network
* C. docker network create
* D. docker network up

40. What does the -v option do?

* A. View verbose logs
* B. Version info
* C. Mount volume
* D. Validate config

41. Which is a valid base image?

* A. mainos
* B. linuxcore
* C. alpine
* D. containerroot

42. Docker Swarm is used for?

* A. Monitoring
* B. Log aggregation
* C. Container orchestration
* D. Networking only

43. What’s the default bridge network subnet?

* A. 192.168.0.0/16
* B. 172.17.0.0/16
* C. 10.0.0.0/16
* D. 127.0.0.1/8

44. Which tool is used to scan Docker images for vulnerabilities?

* A. Jenkins
* B. Trivy
* C. Harbor
* D. Traefik

45. What’s the difference between ADD and COPY in Dockerfile?

* A. ADD supports remote URLs and unpacking
* B. COPY is used for volumes only
* C. ADD adds environment variables
* D. No difference

46. How to login to Docker Hub?

* A. docker loginhub
* B. docker login
* C. docker auth
* D. docker connect

47. Docker Desktop includes:

* A. Docker Engine
* B. Docker CLI
* C. Kubernetes
* D. All of the above

48. Which flag runs container with auto-remove?

* A. --rm
* B. --cleanup
* C. --auto-del
* D. --erase

49. What command runs a container from an image?

* A. docker make
* B. docker image run
* C. docker run
* D. docker exec

50. Docker images are made up of:

* A. Scripts only
* B. Layers
* C. Containers
* D. Packages
