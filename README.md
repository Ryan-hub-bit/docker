# docker

## the advantage of docker compared to traditional VM
Each individual machine or VM need to install OS, Upgrade and patch(补丁) it. Install dependencies for the application that will run on this instance.

On the other hand, Containerization is increasingly popular because containers are:
* Flexible: even the most complex applications can be containerized.
* LightWeight: Containers leverage and share the host kernel, making them much more efficient in terms of system resources than virtual machines.
* Portable: You can  build locally, deploy to the cloud, and run anywhere.
* Loose coupled: Containers are highly self sufficient and encapsulated, allowing you to replace or upgrade one without disrupting others.
* scalabel: You can increase and automatically distribute container replicas accoss a datacenter.
* Secure: Containers apply aggressive constraints and isolations to processes without any configuration required on the part of the user.

## Solution - Docker to the rescue
* build image:consistently package everything your application needs to run
* ship image:ship these images to runtimes in the cloud or on your local developer machine.
* run image: execute your applications 

## docker command
* From + basic image: what image would you like to be based on.
* WORKDIR + directory: switch  to the current working directory, because the command will execute line by line, so we can't use cd, we use WORKDIR instead.
* ENV PORT 80: environment parameter
* COPY file path :  COPY command, which will COPY file to to the path in server, so the path should be server path
* RUN npm install : RUN command  RUN container,download npm then put them into images
* Copy . /code : copy current file to /code directory
* CMD ["node", "src/server.js"]: CMD command which means how to run our container, for this command docker will run node, then pass the node to src/server.js 

## docker build usage
Usage:docker build [OPTIONS] **PATH** | URL | -

Build an image from a Dockerfile

## docker run command
 * docker run + [-p 8080:80] [--name hello] [-d] name of  image : -p hostport map to docker port, --name rename the container, -d run background
 * docker ps  -a : list the container
 * docker start/stop + names of container : stop or start a container
 * docker rm + container
 * docker logs + containerName
 * docker tag tagName image: tag a image
 * docker push repository/name: tagName: push to dockerhub
 * docker rm --force bb  : -- fore stop a running container.

* docker pull  repository/name : docker pull

## docker-Compose
[docker-compose-getStart](https://docs.docker.com/compose/gettingstarted/)

eg:<br>
![docker compose example](https://github.com/Ryan-hub-bit/docker/blob/master/dockerExample.png)

docker-compose up -d :&nbsp;run script docker-compose.yml 
    


