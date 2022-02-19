# Ros2 Foxy Fitzroy is built for Ubuntu 20.04 
# FROM ubuntu:20.04
FROM ros:foxy-ros-core

# How the language and time/zone formatting works. C = computer, could be en_us.utf-8 as well
ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8

# Update and set sources (currnetly only ROS2 sources set)
RUN apt-get update && apt-get install -y curl gnupg2 lsb-release
RUN curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg

# Add repos to sources lists
# RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/ros2.list > /dev/nul

# Install packages
# In theory debian frontend should allow the selection of defaults for installation of a package
RUN apt-get update && apt-get install -y git
# RUN apt-get install -y ros-foxy-desktop

# Set up a workspace (Currently just a turorial for ros2)
WORKDIR /root/dev_ws/src
RUN git clone https://github.com/ros/ros_tutorials.git -b foxy-devel
WORKDIR /root/dev_ws

# Install dependancies for workspace
RUN apt-get update && apt-get install python3-rosdep -y
RUN rosdep init
RUN rosdep update
RUN rosdep install -i --from-path src --rosdistro foxy -y
RUN apt-get update && apt-get install python3-colcon-common-extensions -y

# Prep ROS2 (source setup.bash) - Creative solution to not needing to add a script to bash.rc
#COPY ros2_entrypoint.sh /root/.
#ENTRYPOINT ["/root/ros2_entrypoint.sh"]
CMD ["bash"]


