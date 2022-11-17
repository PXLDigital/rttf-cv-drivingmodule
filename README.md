# RTTF CV driving module

Simple Computer Vision solution to let the RTTF car complete the track (2020 version)

Can be plugged into the `aidrivingmodule` and replaces neural network usage with some easy OpenCV magic to drive the car.

## Installation

1. Clone this repo in a folder (e.g. `~/projects/drivingmodule`) on the Raspberry Pi of the car
2. Open up the docker compose file in to `~/projects/rttf-edgecar/docker-compose.yml`
3. Add the cloned directory as a mounted volume. In `aidrivingmodule` under `volumes` add:

  `- "../drivingmodule:/home/aidrivingmodule/catkin_ws/src/driving_module/src"`
  
4. If needed, stop, remove and rebuild the `aidrivingmodule` docker container with docker-compose

The code in this repo should then be executed when AI driving is enabled on the car.

## config.py

Contains some default values for throttle, angle, location, ... These values can be overwritten with a simple shell command. View [PiComm](https://github.com/PXLDigital/rttf-pi-comm) project to do this remotely from webpage or Android app.

## masks.py

Contains some default masks to recognize red track tubes on different locations. (see `config.py`).
Can be adjusted when needed. (different colors, lighting, range, ...)
