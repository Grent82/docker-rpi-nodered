# docker-rpi-nodered
Node-RED docker image for Raspberry Pi https://cloud.docker.com/u/texnoid/repository/docker/texnoid/rpi-nodered

# Node-RED for Raspberry Pi

Based on the [balenalib/raspberrypi3-node](https://hub.docker.com/r/balenalib/raspberrypi3-node) image this Docker image provides a Node-RED installation on a Raspberry Pi.

## Running the image
Use [Hypriot OS](https://blog.hypriot.com/downloads/) to run this image on Raspberry Pi.

The image itself can be run with Docker compose: `docker-compose up -d`, Node-RED will then be available on port 1880.

## Building the image
The most recent version of the image is available on [Docker Hub](https://cloud.docker.com/u/texnoid/repository/docker/texnoid/rpi-nodered).
Building is not needed. 
If you still want to build the image you can do that with `docker-compose build`.