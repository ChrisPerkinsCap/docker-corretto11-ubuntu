# docker-corrett11-base-image

This image is to be used as a base image to build from. As it is it has the Amazon Corretto JDK.

### Resources
https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/what-is-corretto-11.html

## HOW TO USE THIS IMAGE

### Image Attributes

> NAME: chrisperkins/corretto-11-ubuntu \
TAG: 18-04-19 \
JAVA: 11.0.3

### Container Attributes
> HOSTNAME: CONTAINER_HOSTNAME

### Structure of the docker-openssh-server build context

```
docker-corretto11-ubuntu
        ├── build-corretto11-ubuntu
        │   ├── Dockerfile
        │   └── amazon-corretto11.0.3.7.1-linux-x64.tar.gz
        ├── README.md
        └── docker-compose.yml

```

## BUILD WITH THE DOCKER CLI

```bash
docker build -t chrisperkins/corretto11-ubuntu:v1 .
```

## BUILD WITH DOCKER COMPOSE / QUICK BUILD

From the docker-corretto11-ubuntu directory run the command

>docker-compose up

or

>docker-compose up --build

This will build the image and run a container and output the following:

```
java_1  | openjdk version "11.0.3" 2019-04-16 LTS
java_1  | OpenJDK Runtime Environment Corretto-11.0.3.7.1 (build 11.0.3+7-LTS)
java_1  | OpenJDK 64-Bit Server VM Corretto-11.0.3.7.1 (build 11.0.3+7-LTS, mixed mode)
docker-corretto11-ubuntu_java_1 exited with code 0
```

To stop and remove the container use

> docker-compose down

## WHEN RUNNING

The following command should return the version of Java if this image builds correctly.

```
docker exec -it docker-corretto11-ubuntu_java_1 java -version

openjdk version "11.0.3" 2019-04-16 LTS
OpenJDK Runtime Environment Corretto-11.0.3.7.1 (build 11.0.3+7-LTS)
OpenJDK 64-Bit Server VM Corretto-11.0.3.7.1 (build 11.0.3+7-LTS, mixed mode)
```
