# Requirememts
```
sudo apt install docker.io
```

# Docker
* Create 18.04
```
docker build --config=$(pwd)/docker/Dockerfile-18.04 --no-cache -t yocto-build:v1 docker
```
* Create 20.04
```
docker build --config=$(pwd)/docker/Dockerfile-20.04 --no-cache -t yocto-build:v1 docker
```

* Execute docker
```
docker run --interactive --tty  --privileged --volume $(pwd)/work:/work yocto-build:v1
```
