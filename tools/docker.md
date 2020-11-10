# Docker commands

## General

### Run doker without SUDO

```txt
sudo groupadd docker
sudo usermod -aG docker $USER
reboot ubuntu
docker run hello-world
```

### Accessing the container shell

```txt
docker exec -it [container_id] bash
```

### Inspect container

```txt
docker container inspect <container_id>
```

### Check container IP

```txt
docker inspect <container_id> | grep IPAddress
```

### Remove all containers and images

```txt
docker stop $(docker ps -a -q)

docker rm $(docker ps -a -q)

docker rmi $(docker images -a -q)
```

### Build from docker compose yaml file

```txt
docker-compose -f custom-docker-compose-mock.yaml up

Default execution:
If not specified -f (file) the yaml file should named docker-compose.yaml
docker-compose up
```
