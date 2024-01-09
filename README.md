# Getting started

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started

# Docker Basics (Dockerfile, build an image, run/stop/remove a container of an image)

1. Dockerfile in the project folder
2. docker build [-t tag_name] <path_of_Dockerfile> (to build an image of the app)
3. docker run -dp HOST_PORT:PORT <image_name> (run a container of the image, detached, publish to create a port mapping)
4. docker ps (to check container id and other info about all running containers)
5. docker stop <container_id>
6. docker rm <container_id>
7. docker rm -f <container_id> (to force stop and remove container)
8. docker image ls

# Persist Data

## volume mount (docker managed filesystem on the host machine to persist data; mount the app to the volume when started)

1. docker volume create <volume_name>
2. docker run -dp HOST_PORT:PORT --mount type=volume,src=<volume_name>,target=/etc/todos <image_name>

## bind mount (share a local directory into the container; development container for example, referring to the source code)

1. docker run -dp HOST_PORT:PORT -w /app `
    > --mount type=bind,src=<local_directory_path>,target=/app <image_name> <commands_to_run_at_start_up>
2. docker logs -f <container_id> (to see logs of the container)

# Multi Container App
## Container networking
1. docker network create <network_name>
2. docker run [optional_flags] --network <network_name> --network-alias <component_name_in_network> [-v volume_name:PATH_to_mount] [-e ENV_VAR=value] <image_name>
