# docker-snippets

My doc about docker with snippets


## Docker Images

#### Docker images have **tags** to version them

Download elixir version "1.16.2" and the image has tag "1.16.2" to highlight that.

> docker pull elixir:1.16.2

#### Docker images 

Docker images are formed by **layers**, when a image is download docker only pulls the layers that are not in local system.

Example: **Create Docker image** - create a **Dockerfile** file with apache web server

Everything inside the script, MUST NOT ask for user input or it will give an error

```docker
FROM centos

RUN yum install httpd -y

CMD apachectl -DFOREGROUND
```

> docker build --tag <image_name>:<tag> .

* List all docker images locally

> docker images

## Docker Containers

* Run in background
> docker run .d --name <container_name> <image_name>

* Mapping ports 
> docker run .d --name <container_name> -p <local_port>:<container_port> <image_name>

* Run elixir

> docker run -it --rm elixir:1.16.2
> docker run -it --rm elixir:1.16.2 bash

* Check for Containers running

> docker ps -a

* Remove Containers

> docker rm -fv <container_name>