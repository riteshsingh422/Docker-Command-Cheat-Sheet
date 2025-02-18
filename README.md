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
