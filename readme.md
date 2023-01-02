# Using Docker Containers for Yocto Builds

This is a short man page that shows how to create a Docker container for running the Yocto build environment inside.

# Requirements
* Install the Docker package:
```
sudo apt install docker.io
```
* WorkDir
```
mkdir compulab-yocker && cd compulab-yocker
```
* Clone this repostory:
```
git clone https://github.com/compulab-yokneam/yocker.git .
```

# Create a container
It is up to developers to decide what container to create.

## Ubuntu 18.04
```
sudo docker build -t yocto-build:v1 - < $(pwd)/docker/Dockerfile-18.04
```

## Ubuntu 20.04
```
sudo docker build -t yocto-build:v1 - < $(pwd)/docker/Dockerfile-20.04
```

## Execute docker
```
sudo docker run --interactive --tty  --privileged --volume $(pwd)/work:/work yocto-build:v1
```

## Create internal work folder:
```
sudo mkdir in-work
sudo chown $USER:$USER in-work
cd in-work
```
