# Docker Commands
_A list of most important and commonly used Docker Commands for easy reference_:sparkles::sparkles::sparkles:
___

### 💫Docker General Commands for Installation and Config Information:
| Command | Description |
| ------- | ----------- |
| `docker version` | Provides full description of docker version |
| `docker -v` | Provides short description of docker version |
| `docker info` | Display system wide information |
| `docker info --format '{{.DriverStatus}}'` | display 'DriverStatus' fragment from docker information |
| `docker <command> (options)` | Docker command line structure (OLD but still works) |
| `docker <command> <sub-command> (options)` | Docker command line structure (NEW) |
---

### 💫Docker Commands for Managing Containers:
#### Display Container Information
| Command | Description |
| ------- | ----------- |
| `docker container ls` | Show all running containers |
| `docker container ls -a` | Show all containers regardless of state |
| `docker container ls --filter "status=exited" --filter "ancestor=mysql"` | Show all container instances of the mysql image that have exited |
| `docker container port <container-name>` | Show port mapping for the container |
| `docker container logs <container-name>` | Display all logs in specified container |
| `docker container top <container-name>` | Shows all running processes in an existing container |
| `docker container inspect <container-name>` | Display detailed information about specified container |
| `docker container inspect --format '{{.NetworkSettings.IPAddress}}' <container-name>` | Display detailed information about specified container using specified format |
| `docker container stats'` | Shows container resource usage statistics |

#### Run Container
| Command | Description |
| ------- | ----------- |
| `docker container run <image-name>` | Run container based on specified image |
| `docker container run --rm <image-name>` | Run container based on specified imaged and immediately remove it once it stops |
| `docker container run --name <custom-image-name> <image-name>` | Assign name and run container based on specified image |
| `docker container run -d <image-name>` | Run container in detach mode |
| `docker container run -p <host-port>:<container-port> <image-name>` | Run container with host port |

#### Container Interaction Commands
| Command | Description |
| ------- | ----------- |
| `docker container start <container-name>` | Starts a container |
| `docker container stop <container-name>` | Stop a container |
| `docker container restart <container-name>` | Restarts a container |
| `docker container exec -it <container-name> bash/sh` | Open terminal inside specified container for additional command |
| `docker container rename <container-name> <new-name>` | Rename a container |

#### Remove Container
| Command | Description |
| ------- | ----------- |
| `docker container rm <container-name>` | Remove specified container |
| `docker container rm -f <container-name>` | Force remove specified container even if it is running |
| `docker container rm $(docker container ls --filter "status=exited" --filter "ancestor=mysql" -q)` | remove all containers whose id's are returned from '$(...)' list |
| `docker container prune` | Remove all stopped containers |
---

### 💫Docker Commands for Managing Networks:
| Command | Description |
| ------- | ----------- |
| `docker network create <network-name>` | Creates a new network (default type: bridge) |
| `docker network rm <network-name>` | Remove one or more networks |
| `docker network prune` | Remove all unused networks |
| `docker network ls` | Lists all networks |
| `docker network connect <network-name> <container-name>` | Connects a container to a network |
| `docker network disconnect <network-name> <container-name>` | Disconnects a container from a network |
| `docker network inspect <network-name>` | Displays detailed information about a network |
---

### 💫Docker Commands for Managing Images:
| Command | Description |
| ------- | ----------- |
| `docker image ls` | Shows all local images |
| `docker image ls --filter 'reference=ubuntu:16.04'` | Show images filtered by name and tag |
| `docker image pull <image-name>` | Pull specified image from registry |
| `docker image push <image-name[:TAG]>` | Upload an image to a registry |
| `docker search <image-name> --filter "is-official=true"` | Find only official images having _[image-name]_ |
| `docker image history <image-name>` | Show the history of an image |
| `docker image inspect <image-name>` | Display detailed information on one or more images |
| `docker image tag <source-image[:TAG]> <target-image[:TAG]>` | Create a tag _[target-image]_ that refers to _[source-image]_ |
| `docker image build <PATH \| URL>` | Build an image from a Dockerfile |
| `docker image build -t <new-image-name[:TAG]> <PATH \| URL>` | Builds and tags an image for easier tracking from a Dockerfile |
| `docker image rm <image-name>` | Remove image for specified _image-name_ |
| `docker image rm <image-id>` | Remove image for specified _image-id_ |
| `docker image prune` | Remove unused images |
| `docker image prune -a` | Clears all images that are not being used by containers |
---