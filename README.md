# Docker

## Docker Commands

### Images

| Command                                                                                        |               Action                                          |
|------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
|`docker build -t <image name>:<tag> .`                                                          | build docker container from Dockerfile                        |
|`docker images`                                                                                 | shows the list of container images on a machine               |
|`docker rmi <image id>`                                                                         | remove image                                                  |
|`docker image prune`                                                                            | remove images                                                 |
|`docker rmi $(docker images -q)`                                                                | delete all images                                             |

### Containers

| Command                                                                                        |               Action                                          |
|------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
|`docker run <image name>:<tag>` -p [external port]:[internal port]                              | create and start docker container from image                  |
|`docker run -p [external port]:[internal port] --name my-cotainer <image name>:<tag>`           | create and start docker container from image                  |
|`docker run <image id>` -p [external port]:[internal port]                                      | create and start docker container from image (first 3 chars)  |
|`docker start <docker id>`                                                                      | start docker container                                        |
|`docker ps`                                                                                     | docker running containers                                     |
|`docker ps -a`                                                                                  | docker exited containers                                      |
|`docker build -t <image name>:<tag> .`                                                          | build docker container from Dockerfile                        |
|`docker run -t imagename:latest -f .\CreateTestDb.Dockerfile .`                                 | build docker container from specified Dockerfile              |
|`docker inspect <docker name>`                                                                  | show details docker container                                 |

If you get error message `image operating system "windows" cannot be used on this platform` you need to switch to
Windows Containers on Docker -> Right Click on Docker Icon in Notification Area and choose `Switch to Windows Containers...`

| Command                                                                                        |               Action                                          |
|------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
|`docker exec <container name> ipconfig`                                                         | get the IP address of a running container                     |
|`docker ps -a`                                                                                  | list of running containers (-a slso show exited containers)   |
|`docker network`                                                                                | manage networking with Docker                                 |
|`docker pull microsoft/windowsservercore`                                                       | pull latest windowsservercore image from Docker Hub           |
|`docker rm <container id>`                                                                      | remove a specific container                                   |
|`docker rm -f <container id>`                                                                   | remove a specific running container                           |
|`docker rm $(docker ps -a -q)`                                                                  | delete all containers                                         |
|`docker system prune`                                                                           | clean up any resources — images, containers, volumes and      |
|                                                                                                | network sthat are dangling (not associated with a container)  |
|`docker system prune -a`                                                                        | to additionally remove any stopped containers and all unused  |
|                                                                                                | images (not just dangling images)                             |

ATTENTION: You may get error like: Error response from daemon: conflict: unable to remove repository reference IMAGE NAME  (must force) - container 302e8bd is using its referenced image 3334b287844 -> a stopped container isn't actually removed.

### Docker Parameters

| Parameter                                                                                      |               Description                                     |
|------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
|`-d`                                                                                            | detached, when you need to run a background service.          |
|`-p` 8080:80                                                                                    | expose inside container port 80 to port 8080 on your machine  |
|`--rm`                                                                                          | removes the container from list after container has stopped   |
|`-t`                                                                                            | tag                                                           |
|`-v`                                                                                            | volume                                                        |

### Volumes

| Command                                                                                        |               Action                                          |
|------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
|`docker volume create <volume name>`                                                            | create volume                                                 |
|`docker volume ls`                                                                              | overview volumes                                              |
|`docker volume prune`                                                                           | delete all volumes that are not in use                        |
|`docker volume rm <volume name>`                                                                | delete a volume by name                                       |
|`docker inspect <volume name>`                                                                  | inspect a volume                                              |
|`docker run -d -p 8083:3000 --name <container name> -v /d:/app:/<volume name> <image name>`     | Create and run container with volume path d:/app              |
