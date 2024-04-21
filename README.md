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

> docker build --tag apache-centos .

* List all docker images locally

> docker images

## Docker Containers

* Run in background
> docker run .d --name container-name image-name

* Mapping ports local-port:container-port
> docker run .d --name container-name -p 80:80 image-name

* Run elixir

> docker run -it --rm elixir:1.16.2

* Check for Containers running

> docker ps -a

* Remove Containers

> docker rm -fv <name>