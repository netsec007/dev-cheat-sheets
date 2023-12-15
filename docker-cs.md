# Docker Cheat Sheet

### General
Start Docker Daemon
```
docker -d
```
Docker Help
```
docker --help
```
### Images
Build Image From Dockerfile
```
docker build -t <image_name>
```
Build Image From Dockerfile Without Cache
```
docker build -t <image_name> . -no-cache
```
List Local Images
```
docker images
```
Delete Image
```
docker rmi <image_name>
```
Remove all unused images
```
docker image prune
```
### Container Registry
Login To Docker
```
docker login -u <username>
```
Publish Image To Docker Registry
```
docker push <username>/<image_name>:
```
Search Hub For Image
```
docker Search <image_name>
```
Pull Image From Docker Registry
```
docker pull <image_name:<tag>
```
Rename Existing Docker Image
```
docker tag <image_name> <newname>:<version>
```
### Docker Status
Stats Of All Containers
```
docker stats --all
```
Display Running Processes Of A Container
```
docker top <container_name or container_id>
```
Show Image History
```
docker history <image_name orimage_id>
```
### Containers
Create and run container from an image, with a custom name
```
docker run --name <container_name> <image_name>
```
Run container in background (detacthed mode)
```
docker run -d <image_name>
```
Run container and publish ports to the host
```
docker run -p <host_port>:<container_port> <image_name>
```
Start or stop existing container
```
docker start|stop <container_name or container_id>
```
Remove a stopped container
```
docker rm <container_name>
```
Open/Atach shell inside a running container
```
docker exec -it <container_name> sh
```
Kill/Stop running container
```
docker kill <container_name or container_id>
```
Container Logs
```
docker logs -f <container_name>
```
Inspect running container
```
docker inspect <container_name or container_id>
```
List running containers
```
docker ps
```
View resource usage stats
```
docker container stats
```
### Networking
List docker networks
```
docker network ls
```
Create new network
```
docker network create --driver <driver_name> <bridge_name>
```
Connect running container to network
```
docker network connect <network_name> <container_name>
```
Disconnect container from network
```
docker network disconnect <network_name> <container_name>
```
Remove network
```
docker network rm <network_name>
```
### Docker Compose
Create and start container
```
docker compose up or docker-compose up
```
Stop and remove containers, network
```
docker compose down
```
View output from containers
```
docker compose logs
```
View events from containers
```
docker compose events
```
List containers in compose/stack
```
docker compose ps
```
