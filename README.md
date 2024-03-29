# Docker Cheat Sheet
`Some necessary docker commands`


### Manage Containers

```bash
$ docker ps
$ docker ps -a
$ docker kill <IMAGE_ID>
```

### Manage `container's` using ps/kill.


## Images && Containers
```bash
$ docker images
$ docker image ls
$ docker images -a   # also show intermediate
$ docker iamge ls -q  # Get only id
$ docker rmi <b750fe78269d> # Delete image with image ID
$ docker image rm $(docker iamge ls -q) # Delete unused images
$ docker image rm $(docker container ls -q) # Delete unused containers
$ docker container rm $(docker container ls -q) # Delete unused containers
$ docker container rm $(docker container ls -a -q) # Delete unused containers
$ docker container rm $(docker container ls -aq) # Delete unused containers
$ docker container rm -f $(docker container ls -aq) # Delete unused containers forcefully
```


## Image Management Commands
```bash
$ docker images # list all local images
$ docker image ls # List of images
$ docker history image # show the image history
$ docker inspect image # Display detailed information on one or more images
$ docker image prune # Remove unused images
$ docker image tag # Create a tag <TARGET_IMAGE> that refers to <SOURCE_IMAGE>
$ docker image build # Build an image from a Dockerfile
$ docker image rm # Remove one or more images
$ docker image rmi # Remove one or more images
$ docker image build # Build an image from a Dockerfile
```


## Container Management CLIs
```bash
$ docker create <IMAGE_NAME>
$ docker run <IMAGE_NAME>
$ docker start <CONTAINER_ID_OR_NAME>
$ docker stop <CONTAINER_ID_OR_NAME>
$ docker kill <CONTAINER_ID_OR_NAME>
$ docker restart <CONTAINER_ID_OR_NAME>
$ docker pause <CONTAINER_ID_OR_NAME>
$ docker unpause <CONTAINER_ID_OR_NAME>
$ docker rm -f <CONTAINER_ID_OR_NAME>
$ docker container ls
$ docker container diff	# Inspect changes to files or directories on a container’s filesystem
$ docker container exec	# Run a command in a running container
$ docker container export	# Export a container’s filesystem as a tar archive
$ docker container inspect	# Display detailed information on one or more containers
$ docker container kill	# Kill one or more running containers
$ docker container logs	# Fetch the logs of a container
$ docker container port	# List port mappings or a specific mapping for the container
$ docker container prune	# Remove all stopped containers
$ docker container rename	# Rename a container
$ docker container stats	# Display a live stream of container(s) resource usage statistics
$ docker container wait	# Block until one or more containers stop, then print their exit codes
$ docker container start	# Start one or more stopped containers
$ docker container stop	# Stop one or more running containers
$ docker rename <YOUR_CONTAINER> <YOUR_NEW_CONTAINER>
$ docker service inspect [OPTIONS] SERVICE [SERVICE...]
$ docker stats awesome_brattain 67b2525d8ad1
```


## Project Build && Run With Docker 
```bash
$ docker build -t <PROJECT_NAME> .
$ docker build . # build current directory project
$ docker run <IMAGE_NAME>
$ docker build -f local.Dockerfile -t <IMAGE_NAME> .  # docker file read from another docker file
$ docker build github.com/creack/docker-firefox  # Build with URL
$ docker build --rm -t <YOUR_PROJECT_NAME> . # delete command with build
$ docker run -p 8081:8081 <YOUR_PROJECT_NAME> # run command
```


## Pull a repository with multiple images
By default, docker pull pulls a single image from the registry. A repository can contain multiple images. To pull all images from a repository, provide the `-a (or --all-tags)` option when using docker pull.

This command pulls all images from the fedora repository:
```bash
$ docker pull --all-tags <IMAGE_NAME>
```


## Cancel a pull
Killing the `docker pull` process, for example by pressing `CTRL-c` while it is running in a terminal, will terminate the pull operation.
```bash
$ docker pull <IMAGE_NAME>
```


## Docker Network
Description
Manage networks. You can use subcommands to create, inspect, list, remove, prune, connect, and disconnect networks.
```bash
$ docker network connect	# Connect a container to a network
$ docker network create	# Create a network
$ docker network disconnect	# Disconnect a container from a network
$ docker network inspect	# Display detailed information on one or more networks
$ docker network ls	# List networks
$ docker network prune	# Remove all unused networks
$ docker network rm	# Remove one or more networks
```


## Docker shell (Get into the docker container)
```bash
$ docker exec -it <CONTAINER_ID_OR_IMAGE_NAME> sh
$ docker exec -it <CONTAINER_ID_OR_IMAGE_NAME> bash
```


## Run docker image with .env file
```bash
$ docker run -p 8080:8083 --env-file ./.env -t -it <PROJECT_NAME>
```

## Run image with port
```bash
$ docker run -d -p 7777:7777 <IMAGE_NAME> --port 7777
$ docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.8-management # Example: rabbitmq image
```


#### DELETE UNUSED CONTAINERS
```bash 
$ docker rm $(docker ps -a -q -f status=exited)
or
$ docker container prune
```

































