---
sidebar_position: 22
---

# Docker commands

```bash
docker stop <container-name>

docker exec -it <container-name> /bin/sh

docker images

docker ps
```

```bash
# Remove all containers
docker rm -f $(docker ps -a -q)

# Remove all images
docker rmi --force $(docker images -a -q)

# Remove all volumes
docker volume rm $(docker volume ls -q)
```