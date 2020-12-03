---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

(about_py)=

# Docker

## What\'s Docker?

Is a system of running processes on the hosting machine in an isolated way, using several Linux kernel features.

Disadvantages vs Virtual Machine:
1. Multiple containers share the same underlying OS kernel

## Docker Components

1. Docker Daemon that runs on host machine
2. Docker client that communicates with Docker daemon to execute commands
3. REST API for interact with Docker daemon remotely

## Images, containers and volumes

### Docker Image
A Docker image can be though of as recipe for setting up a machine with **all required software and dependencies installed**. Also it is defined what **processes to run** when launched. Docker images are created via instructions written in a Dockerfile. There is always a base layer, potentially followed by additional layers that represent file changes (Union file system).

#### Custom Docker images
Docker images are specified via Dockerfile. Basic example with ubuntu base and copies sysinfo fon current directory into container:

FROM ubuntu:18.04
COPY sysinfo /
CMD ["/sysinfo"]



### Docker container
Is the running instance of an image. Include operating system, application code, runtime, system tools, system libraries, etc. 

### Docker volume
Is the data part of a container, initialized when a container is created. Volumes allow you to persist and share a container's data. Docker Volumes are separate from the default Union File System and exist as normal directories and files on the host filesystem.

## Common commands

1. List all images: **docker images**
2. Run interactively from an image in a new container: **docker run -it ubuntu bash**
3. List all running containers: **docker ps**
4. List all previously run containers: **docker ps -a**
5. Jump into it **docker attach ubuntu bash**
6. 

