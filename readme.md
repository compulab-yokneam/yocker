# Using Docker Containers for Yocto Builds

This is a short man page that shows how to create a Docker container for running the Yocto build environment inside.

# Compatibility Matrix

|mach\distro|hardknott|gatesgarth|honister|kirkstone|mikledore|
|---|---|---|---|---|---|
|ucm-imx93l|||||**22.04<br>(```release```)<br>**|
|ucm-imx93||||**20.04<br>(```release```)<br>**||
|ucm-imx8m-plus|18.04|18.04|20.04|20.04|**22.04<br>(```release```)<br>**|
|mcm-imx8m-plus|||||**22.04<br>(```rc0```)<br>**|
|cl-som-imx8plus|18.04|18.04|20.04|**20.04<br>(```release```)<br>**||
|iot-gate-imx8plus|18.04|18.04|20.04|**20.04<br>(```release```)<br>**||
|mcm-imx8m-mini|18.04|18.04|20.04|**20.04<br>(```release```)<br>**||
|ucm-imx8m-mini|18.04|18.04|20.04|**20.04<br>(```release```)<br>**||
|iot-gate-imx8|18.04|18.04|20.04|**20.04<br>(```release```)<br>**||


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

## Ubuntu 22.04 (Preferred for Mickledore)
```
sudo docker build -t yocto-build:v1 - < $(pwd)/docker/Dockerfile-22.04
```

## Ubuntu 20.04 (Preferred for Kirkstone)
```
sudo docker build -t yocto-build:v1 - < $(pwd)/docker/Dockerfile-20.04
```

## Ubuntu 18.04 (Optional)
```
sudo docker build -t yocto-build:v1 - < $(pwd)/docker/Dockerfile-18.04
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
