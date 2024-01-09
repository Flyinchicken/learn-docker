# Getting started

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started

# learn-docker

1. Dockerfile in the project folder
2. docker build [-t tag_name] <path_of_Dockerfile>      (to build an image of the app)
3. docker run -dp HOST_PORT:PORT <image_name>           (run a container of the image, detached, publish to create a port mapping)
4. docker ps                                            (to check container id and other info about all running containers)
5. docker stop <container_id>
