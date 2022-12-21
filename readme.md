# Using Docker Containers for Yocto Builds

This is a short man page that shows how to create a Docker container for running the Yocto build environment inside.

# Requirements
* Install the Docker package:
```
sudo apt install docker.io
```
* Clone this repostory:
```
git clone https://github.com/compulab-yokneam/yocker.git
```

# Create a container
It is up to developers to decide what container to create.

## Ubuntu 18.04
```
docker build --config=$(pwd)/docker/Dockerfile-18.04 --no-cache -t yocto-build:v1 docker
```

## Ubuntu 20.04
```
docker build --config=$(pwd)/docker/Dockerfile-20.04 --no-cache -t yocto-build:v1 docker
```

## Execute docker
```
docker run --interactive --tty  --privileged --volume $(pwd)/work:/work yocto-build:v1
```
