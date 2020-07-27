# Docker Basics

## What is Docker?

Docker is a set of tools that allow us to easily execute containers and containerised applications.

## Why Docker?

On the course of building large applications, it is obligatory to deploy them in various environments. 
Docker makes this a lot easier. Typically, these containers are light-weight and have minimal overheads.

## Basic Terminologies

 - **Docker Image:** It includes a set of instructions for creating a container that can run on Docker environments. It constitutes everything that is 
	required to run the concerned application as a Docker container. This includes code, libraries, packages and other dependencies required for container
	execution.
	
 - **Containers:** In a very basic sense, a container is a running instance of the Docker Image defined above. 
	Images are the packing part of Docker, and is compared to "source code" or a "program". 
	Containers are the execution part of Docker, and is compared to a "process".
	
 - **Docker Hub:** It is basically GitHub but for Docker Images.
 
 **Installing the Docker Engine:** [Official documentation: Installing Docker Engine](https://docs.docker.com/engine/install/ubuntu/)

## The Docker Workflow: Basics

![Docker Workflow](/Notes/assets/docker-intro.png)

#### View all containers running on Docker's host

`docker ps`

#### Start any stopped containers

`docker start <container-name or container-id>`

#### Stop any running containers

`docker stop <container-name or beginning-of-container-id>` 

#### Create containers from Docker Images

`docker run <container-name>`

#### Delete a container

`docker rm <container-name>`

#### Download/pull Docker Images

`docker pull <image-author>/<image-name>`

#### Run Docker Image as a bash script

`docker run -ti <image-author>/<image-name> /bin/bash`

#### Copy any file inside Docker container with <container-id>

`docker cp <code-filename> <container-id>:/`

Furthermore, write a bash script say `install-dependencies.sh` to install all dependencies for successful execution of <code-filename> 

For instance, say <code-filename> was a basic python `.py` executable

`install-dependencies.sh` will include:

	apt update
	apt install python3

Now, copy the bash script into the same Docker container too

`docker cp install-dependencies.sh <container-id>:/`

#### Installing dependencies

 - Allow running bash script as executable 
 
 `docker exec -it <container-id> chmod +x install-dependencies.sh`
	
 - Install dependencies
 
 `docker exec -it <container-id> /bin/bash ./install-dependencies.sh`
	
#### Run program inside the container

Start the container

`docker start <container-id>`

For the example given above, the following will be the line for execution

`docker exec <container-id> python3 <code-filename>`

#### Save copied program inside Docker Image

`docker commit <container-id> <image-author>/<image-name>`

#### Tag Docker Image with a different name

`docker tag <image-author>/<image-name> <user-name>/<repo-name>`

#### Push Docker Image into DockerHub

`docker push <user-name>/<repo-name>`