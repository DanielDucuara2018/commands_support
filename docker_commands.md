# Docker Overview

## General Commands

```sh
sudo snap install docker
sudo apt install docker.io

sudo docker --help
sudo docker search <APP_NAME>
sudo docker ps
sudo docker ps -a
sudo docker images
sudo docker pull <IMAGE>
sudo docker run -d  <IMAGE>:<TAG> # (TAG optional) -d is detach
sudo docker run -d  --name <NAME> <IMAGE>:<TAG> # (TAG optional) --name is for assigning a name to the container 
sudo docker run -d -p <HOSt_PORT>:<CONTAINER_PORT> <IMAGE>:<TAG> # (TAG optional) -p is for assigning a port
sudo docker stop  <CONTAINER ID>
sudo docker start <CONTAINER ID>
sudo docker logs <CONTAINER ID> | tail
sudo docker logs <NAME> | head
sudo docker exec -it <CONTAINER ID> /bin/bash # (bash or sh) and -it is interactive mode
sudo docker exec -it <NAME> /bin/bash # (bash or sh)

sudo docker network ls
sudo docker network create <NETWORK_NAME>
sudo docker run -d -p <HOSt_PORT>:<CONTAINER_PORT> -e <ENV_VARIABLE> = <VALUE> --name <NAME> --net <NETWORK_NAME> <IMAGE>:<TAG> # (TAG optional) -e is for - environment variables and --net assings a network name or attachs the container to a network group

sudo docker rm <CONTAINER_ID> # (get CONTAINER_ID from sudo docker ps -a)
sudo docker rmi <IMAGE ID>  # (get IMAGE ID from sudo docker images)

sudo docker login
sudo docker tag <IMAGE>:<TAG> <DOMAIN_REPOSITORY>/<IMAGE>:<TAG>
sudo docker push <DOMAIN_REPOSITORY>/<IMAGE>:<TAG>

sudo docker inspect <IMAGE_ID>

# In order to supervise docker processes and installations 
sudo watch docker ps # watch command allows to supervise a process in real time
sudo docker logs -f --tail=<NUMBER_LINES> <CONTAINER ID> # -f is for following the logs in real time
```
## Docker Compose file

Configuration YAML file for docker composee -> for deployment

```yml
version:'3'
services:	
	<NAME1>:
		image:<IMAGE>
		ports: 
		- <HOSt_PORT>:<CONTAINER_PORT>
		environment: 
		- <ENV_VARIABLE> = <VALUE>
		.
		.
		.
	<NAME2>:
		image:<IMAGE>
		ports: 
		- <HOSt_PORT>:<CONTAINER_PORT>
		environment: 
		- <ENV_VARIABLE> = <VALUE>
		.
		.
		.
```

Both services will be over the same network (same file same network)

```sh
sudo docker-compose -f <NAME_FILE>.yaml up -d # -f is to define the docker compose file location and -d detach
sudo docker-compose -f <NAME_FILE>.yaml down
```

if we are deploying our own project it's neccessary to add :

```yml
<NAME3>:
	image:<DOMAIN_REPOSITORY>/<IMAGE>:<TAG>
	ports: 
	- <HOSt_PORT>:<CONTAINER_PORT>
```

or data persistance, we need to use "Volume" option -> documentation

## Finding the container Data on the Docker Host

```sh
sudo docker volume inspect <FOLDER_NAME> # ex. jenkins_home
sudo  ls -l <MOUNTPOINT>
```
# DockerFile

Dockerfile to build my own project -> to create a new docker container for my project

```yml
FROM <IMAGE_BASE>:<TAG>

ENV <ENV_VARIABLE> = <VALUE>
	.
	.
	.

RUN mkdir -p /home/app

COPY . /home/app

CMD ["<IMAGE_BASE>","<SERVER_FILE_LOCATION>"]
```

```sh
sudo docker build -t <IMAGE_MY_PROJECT>:<TAG>	<PROJECT_LOCATION> # (TAG optional) and -t means tag
sudo docker run -d  <IMAGE_MY_PROJECT>:<TAG> # (TAG optional)
```
# manage remote docker repositories

AWS -> ECR -> Elastic Container Registry
Create a remote repository using <IMAGE>

```sh
sudo docker login -u <USERNAME> -p <PASSWORD> <URL_DOCKER_REPOSITORY> #-u and -p parameters are optional (log in ECR repository. see documentation)
sudo docker tag <IMAGE>:<TAG> <DOMAIN_REPOSITORY>/<IMAGE>:<TAG>
sudo docker push <DOMAIN_REPOSITORY>/<IMAGE>:<TAG>
```

# References 

 - [Docker Tutorial](https://www.youtube.com/watch?v=3c-iBn73dDE&list=PLJ6z0UeFeiCfFIj0-gaIpVyju190fbp-E&index=24&t=5728s)





