# Requirememts
```
sudo apt install docker.io
```

# Docker
* Create
```
docker build --no-cache -t yocto-build:v1 docker
```

* Execute docker
```
docker run --interactive --tty  --privileged --volume $(pwd)/work:/work yocto-build:v1
```
