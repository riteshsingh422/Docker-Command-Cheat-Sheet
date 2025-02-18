<img align="right" width="400" alt="raja mondal coding" src="https://media1.tenor.com/m/z3Vqx6hmE5QAAAAd/whale-docker.gif">

# Docker Commands Cheat Sheet

## Images

### List all local images

```sh
docker images
```

### Delete an image

```sh
docker rmi <image_name>
```

### Remove unused images

```sh
docker image prune
```

### Build an image from a Dockerfile

```sh
docker build -t <image_name>:<version> .  # version is optional
```

### Build an image without cache

```sh
docker build -t <image_name>:<version> . --no-cache
```

## Containers

### List all local containers (running & stopped)

```sh
docker ps -a
```

### List all running containers

```sh
docker ps
```

### Create & run a new container

```sh
docker run <image_name>
# If the image is not available locally, it will be downloaded from DockerHub
```

### Run a container in the background

```sh
docker run -d <image_name>
```

### Run a container with a custom name

```sh
docker run --name <container_name> <image_name>
```

### Port Binding in a container

```sh
docker run -p <host_port>:<container_port> <image_name>
```

### Set environment variables in a container

```sh
docker run -e <var_name>=<var_value> <container_name> (or <container_id>)
```

### Start or Stop an existing container

```sh
docker start|stop <container_name> (or <container_id>)
```

### Inspect a running container

```sh
docker inspect <container_name> (or <container_id>)
```

### Delete a container

```sh
docker rm <container_name> (or <container_id>)
```

## TROUBLESHOOT

### Fetch logs of a container

```sh
docker logs <container_name> (or <container_id>)
```

### Open shell inside a running container

```sh
docker exec -it <container_name> /bin/bash
```
```sh
docker exec -it <container_name> sh
```

## DOCKER HUB

### Login into DockerHub

```sh
docker login -u <image_name>
```
Or
```sh
docker login
```

### Logout from DockerHub

```sh
docker logout
```

### Search for an image on DockerHub

```sh
docker search <image_name>
```

### Pull an image from DockerHub

```sh
docker pull <image_name>
```

### Publish an image to DockerHub

```sh
docker push <username>/<image_name>
```

## VOLUMES

### List all Volumes

```sh
docker volume ls
```

### Create new Named volume

```sh
docker volume create <volume_name>
```

### Delete a Named volume

```sh
docker volume rm <volume_name>
```

### Mount Named volume with running container

```sh
docker run --volume <volume_name>:<mount_path>
```
Or using `--mount`
```sh
docker run --mount type=volume,src=<volume_name>,dest=<mount_path>
```

### Mount Anonymous volume with running container

```sh
docker run --volume <mount_path>
```

### To create a Bind Mount

```sh
docker run --volume <host_path>:<container_path>
```
Or using `--mount`
```sh
docker run --mount type=bind,src=<host_path>,dest=<container_path>
```

### Remove unused local volumes

```sh
docker volume prune  # for anonymous volumes
```

## NETWORK

### List all networks

```sh
docker network ls
```

### Create a network

```sh
docker network create <network_name>
```

### Remove a network

```sh
docker network rm <network_name>
```

### Remove all unused networks

```sh
docker network prune
```
