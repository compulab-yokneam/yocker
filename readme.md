# Using Docker Containers for Yocto Builds

This is a short man page that shows how to create a Docker container for running the Yocto build environment inside.

# Requirements

To ensure optimal Yocto build speed and performance, it is important to note that the computation power of your host system plays a crucial role. It is recommended to use a host system with at least 4 CPUs, 16 GB of RAM, and 500 GB of free disk space to handle the Yocto build process efficiently. Additionally, the system should have an option to open a large number of files simultaneously, preferably up to 4096 or higher, to prevent any performance issues during the build process.

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
git clone https://github.com/compulab-yokneam/yocker.git
```

# Create a container
It is up to developers to decide what container to create.

## Ubuntu 20.04 (Preferred)
```
sudo docker build -t yocto-build:v1 - < $(pwd)/yocker/docker/Dockerfile-20.04
```

## Ubuntu 18.04 (Optional)
```
sudo docker build -t yocto-build:v1 - < $(pwd)/yocker/docker/Dockerfile-18.04
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
