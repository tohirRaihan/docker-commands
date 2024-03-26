# Docker Commands
_A list of most important and commonly used Docker Commands for easy reference_:sparkles::sparkles:
___

### Docker General Commands for Installation and Config Information:
| Command | Description |
| ------- | ----------- |
| `docker version` | Provides full description of docker version |
| `docker -v` | Provides short description of docker version |
| `docker info` | Display system wide information |
| `docker info --format '{{.DriverStatus}}'` | display 'DriverStatus' fragment from docker information |
| `docker <command> (options)` | Docker command line structure (OLD but still works) |
| `docker <command> <sub-command> (options)` | Docker command line structure (NEW) |
---

### Docker Commands for Managing Containers:
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