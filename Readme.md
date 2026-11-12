
# Docker Commands Cheat Sheet

## 1. Docker Image Commands

| Command | Description |
| --- | --- |
| `docker images` | List all Docker images |
| `docker build -t hello-docker .` | Build an image |
| `docker build -t name:tag .` | Build image with a tag |
| `docker rmi image_name` | Remove an image |
| `docker pull node:20-alpine` | Download an image |
| `docker image inspect hello-docker` | Inspect image details |
| `docker image prune` | Remove unused images |

## 2. Docker Container Commands

| Command | Description |
| --- | --- |
| `docker run hello-docker` | Create and run a container |
| `docker run -it ubuntu` | Run container interactively |
| `docker run -d nginx` | Run container in background |
| `docker ps` | Show running containers |
| `docker ps -a` | Show all containers |
| `docker stop container_id` | Stop a container |
| `docker start container_id` | Start a stopped container |
| `docker restart container_id` | Restart a container |
| `docker rm container_id` | Remove a container |
| `docker logs container_id` | View container logs |
| `docker exec -it container_id sh` | Enter a running container |
| `docker inspect container_id` | Inspect container details |

## 3. Docker Build & Run Commands

powershell

```powershell
# Build Docker image
docker build -t hello-docker .

# List images
docker images

# Run container
docker run hello-docker

# Run with a custom container name
docker run --name my-container hello-docker

# Run in detached mode
docker run -d --name my-container hello-docker

# Run and automatically remove container after exit
docker run --rm hello-docker

# Run interactively
docker run -it ubuntu bash
```

## 4. Docker Port Mapping

powershell

```powershell
# Map host port 8080 to container port 80
docker run -d -p 8080:80 nginx

# Map multiple ports
docker run -d -p 8080:80 -p 3000:3000 my-image
```

Syntax:

text

```text
-p HOST_PORT:CONTAINER_PORT
```

## 5. Docker Volume Commands

powershell

```powershell
# List volumes
docker volume ls

# Create volume
docker volume create my-volume

# Inspect volume
docker volume inspect my-volume

# Run container with volume
docker run -v my-volume:/app hello-docker

# Remove volume
docker volume rm my-volume
```

## 6. Docker Network Commands

powershell

```powershell
# List networks
docker network ls

# Create network
docker network create my-network

# Run container inside network
docker run -d --network my-network nginx

# Inspect network
docker network inspect my-network

# Remove network
docker network rm my-network
```

## 7. Docker System Commands

powershell

```powershell
# Check Docker version
docker --version

# Docker system information
docker info

# Check running containers
docker stats

# View Docker disk usage
docker system df

# Remove unused resources
docker system prune

# Remove unused images, containers and volumes
docker system prune -a --volumes
```

Warning `docker system prune -a --volumes` can delete unused resources and data. Use it carefully.

## 8. Docker Compose Commands

powershell

```powershell
# Start services
docker compose up

# Start in background
docker compose up -d

# Stop services
docker compose stop

# Stop and remove containers
docker compose down

# Build and start services
docker compose up --build

# List services
docker compose ps

# View logs
docker compose logs

# Follow logs
docker compose logs -f
```

## 9. Most Important Commands to Memorize

These are especially useful for beginners:

| Command | Remember |
| --- | --- |
| `docker build` | Build image |
| `docker images` | List images |
| `docker run` | Run container |
| `docker ps` | Running containers |
| `docker ps -a` | All containers |
| `docker stop` | Stop container |
| `docker start` | Start container |
| `docker rm` | Delete container |
| `docker rmi` | Delete image |
| `docker logs` | View logs |
| `docker exec` | Execute inside container |

## 10. Your First Docker Workflow

bash

```bash

# 1. Create Docker image
docker build -t hello-docker .

# 2. Check images
docker images

# 3. Run container
docker run --name hello-container hello-docker

# 4. Check all containers
docker ps -a

# 5. View logs
docker logs hello-container

# 6. Remove container
docker rm hello-container

# 7. Remove image
docker rmi hello-docker
```

My recommendation: Learn these topics in order:

1. Dockerfile
2. Docker Images
3. Docker Containers
4. Port Mapping
5. Docker Volumes
6. Docker Networks
7. Docker Compose
8. Docker Hub
9. Dockerizing Node.js applications
10. Docker in CI/CD pipelines

These fundamentals will give you a strong foundation for Docker and DevOps.




### Docker Commands – My Practice

bash

```bash

1. Build Docker Image
powershell
docker build -t hello-docker .

2. List Docker Images
powershell
docker images

3. Run Docker Container
powershell
docker run hello-docker

4. Run Container with Custom Name
powershell
docker run --name my-container hello-docker

5. List Running Containers
powershell
docker ps

6. List All Containers
powershell
docker ps -a

7. Stop a Container
powershell
docker stop container_name
```




docker build -t FILENAME .
docker run FILENAME

docker run -p 5173:5173 FILENAME

docker run -p 5173:5173 -v "$(pwd):/app" react-docker
docker run --rm -it -p 5173:5173 -v "${PWD}:/app" -v /app/node_modules react-docker
docker run --rm -it -p 5173:5173 `
  -v "${PWD}:/app" `
  -v react_node_modules:/app/node_modules `
  react-docker

  docker run --rm -it -p 5173:5173 `
  -v "${PWD}:/app" `
  -v react_node_modules:/app/node_modules `
  react-docker



```console
npm create vite@latest my-vite-app
docker init 
{ANSER question} last two NO NO[npm run dev]  poer : 5173

sudo docker compose up 


```
