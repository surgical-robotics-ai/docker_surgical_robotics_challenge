# Dockerfiles for the Surgical Robotics Challenge

## Note:
These dockerfiles can be used to create Docker images that contain the correct [ROS](https://hub.docker.com/_/ros) install, the [surgical robotics challenge](https://github.com/collaborative-robotics/surgical_robotics_challenge) and the necessary AMBF ROS msgs, and the [Python Client](https://github.com/adnanmunawar/ambf_python_client).

The Docker containers created from the Docker images can then be used to communicate with the Surgical Scene running in AMBF on the host machine.


## Steps:
Please install Docker based on the official [instructions](https://docs.docker.com/engine/install/):
Afterward, depending upon which Ubuntu / ROS is preferred (`Ubuntu 20.04 with ROS Noetic` OR `Ubuntu 18.04 with ROS melodic`), build the image using the correct Dockerfile.

E.g.
```bash
cd docker_surgical_robotics_challenge/noetic
docker build -t collaborativerobotics/ros-ambf-surg_challenge:noetic .
```
Once built, the Docker container can be created with the `--network host` argument to share the host network for ROS.

```bash
docker run -it --name surg_challenge --network host collaborativerobotics/ros-ambf-surg-challenge:noetic bash
```
To access the running container from a new terminal:

```
docker exec -it surg_challenge bash
```
