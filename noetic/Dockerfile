# This is an auto generated Dockerfile for ros:ros-base
# generated from docker_images/create_ros_image.Dockerfile.em
FROM ros:noetic-ros-base

# Source ROS
RUN apt-get update && apt-get install -y ros-noetic-tf
RUN echo 'source /opt/ros/noetic/setup.bash' >> ~/.bashrc

# Install Git, Python pip, tf
RUN apt-get update && apt-get install -y git python3-pykdl pip

# clone AMBF Msgs and Python Client
RUN cd  && git clone https://github.com/adnanmunawar/ambf_python_client.git
RUN . /opt/ros/noetic/setup.sh && cd ~/ambf_python_client && mkdir build && cd build && cmake .. && make
RUN echo 'source ~/ambf_python_client/build/devel/setup.bash' >> ~/.bashrc

# clone surgical_robotics_challenge
RUN cd && git clone https://github.com/surgical-robotics-ai/surgical_robotics_challenge

# Install the scripts
RUN cd && cd surgical_robotics_challenge/scripts/ && pip install -e .
